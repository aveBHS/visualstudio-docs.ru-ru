---
title: 'CA1804: удалите неиспользуемые локальные переменные'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA1804
- RemoveUnusedLocals
helpviewer_keywords:
- RemoveUnusedLocals
- CA1804
ms.assetid: cc332e67-6543-4813-bd8a-6f6fc75bf22a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4a9212d4fd11a13e9905d0327e3c4c91413e2a8d
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="ca1804-remove-unused-locals"></a>CA1804: удалите неиспользуемые локальные переменные
|||
|-|-|
|TypeName|RemoveUnusedLocals|
|CheckId|CA1804|
|Категория|Microsoft.Performance|
|Критическое изменение|Не критическое|

## <a name="cause"></a>Причина
 Метод объявляет локальную переменную, но не использовать переменную, за исключением возможно как получателя оператора присваивания. Для анализа с помощью этого правила тестируемой сборки должны быть построены с отладочной информацией и связанный PDB-файл должен быть доступен.

## <a name="rule-description"></a>Описание правила
 Неиспользуемые локальные переменные и ненужные присвоения увеличивают размер сборки и снижают производительность.

## <a name="how-to-fix-violations"></a>Устранение нарушений
 Чтобы устранить нарушение данного правила, удалите или использовать локальную переменную. Обратите внимание, что компилятор C#, входят в состав [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)] удаляет неиспользуемые локальные переменные при `optimize` включен параметр.

## <a name="when-to-suppress-warnings"></a>Отключение предупреждений
 Отключайте предупреждение из этого правила, если переменная создана компилятором. Можно также безопасно подавить предупреждение из этого правила, или отключить правило, если производительность и обслуживание кода не критичными моментами.

## <a name="example"></a>Пример
 В следующем примере показано несколько неиспользуемые локальные переменные.

 [!code-vb[FxCop.Performance.UnusedLocals#1](../code-quality/codesnippet/VisualBasic/ca1804-remove-unused-locals_1.vb)]
 [!code-csharp[FxCop.Performance.UnusedLocals#1](../code-quality/codesnippet/CSharp/ca1804-remove-unused-locals_1.cs)]

## <a name="related-rules"></a>Связанные правила
 [CA1809: избегайте чрезмерного использования локальных переменных](../code-quality/ca1809-avoid-excessive-locals.md)

 [CA1811: не используйте невызываемый закрытый код](../code-quality/ca1811-avoid-uncalled-private-code.md)

 [CA1812: не создавайте внутренние классы без экземпляров](../code-quality/ca1812-avoid-uninstantiated-internal-classes.md)

 [CA1801: проверьте неиспользуемые параметры](../code-quality/ca1801-review-unused-parameters.md)
---
title: 'CA2122: не используйте косвенное представление методов с запросами компоновки'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2122
- DoNotIndirectlyExposeMethodsWithLinkDemands
helpviewer_keywords:
- DoNotIndirectlyExposeMethodsWithLinkDemands
- CA2122
ms.assetid: 3eda58e7-c6ec-41c3-8112-ae0841109c6a
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c43cfc1a448d9073a8bbe493d75c7c117f57d737
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="ca2122-do-not-indirectly-expose-methods-with-link-demands"></a>CA2122: не используйте косвенное представление методов с запросами компоновки
|||
|-|-|
|TypeName|DoNotIndirectlyExposeMethodsWithLinkDemands|
|CheckId|CA2122|
|Категория|Microsoft.Security|
|Критическое изменение|Не критическое|

## <a name="cause"></a>Причина
 Открытый или защищенный член имеет [требования связывания](/dotnet/framework/misc/link-demands) и он вызывается членом, который не выполняет каких-либо проверок безопасности.

## <a name="rule-description"></a>Описание правила
 Запрос компоновки проверяет разрешения только непосредственно вызывающего метода. Если элемент `X` делает ее вызывающие и вызывает код защищен требованием связывания, вызывающему объекту без необходимых разрешений можно использовать без требования безопасности `X` для доступа к защищенному члену.

## <a name="how-to-fix-violations"></a>Устранение нарушений
 Добавьте безопасный [данных и моделирование](/dotnet/framework/data/index) или ссылка на элемент запросу, чтобы он больше не содержит небезопасный доступ к члену, защищенному запросом компоновки.

## <a name="when-to-suppress-warnings"></a>Отключение предупреждений
 Чтобы безопасно подавить предупреждение из этого правила, необходимо проверить, что код не предоставлял доступ к операциям или ресурсам, которые могут использоваться в злонамеренных целях.

## <a name="example"></a>Пример
 В следующих примерах библиотеки, который нарушает правила и приложение, демонстрирующее слабость библиотеки. Пример библиотеки содержит два метода, которые вместе нарушают правило. `EnvironmentSetting` Метод защищен требованием связывания для неограниченного доступа к переменным среды. `DomainInformation` Метод производит никаких требований безопасности, вызывающих перед вызовом `EnvironmentSetting`.

 [!code-csharp[FxCop.Security.UnsecuredDoNotCall#1](../code-quality/codesnippet/CSharp/ca2122-do-not-indirectly-expose-methods-with-link-demands_1.cs)]

## <a name="example"></a>Пример
 Следующее приложение вызывает незащищенный член библиотеки.

 [!code-csharp[FxCop.Security.TestUnsecuredDoNot1#1](../code-quality/codesnippet/CSharp/ca2122-do-not-indirectly-expose-methods-with-link-demands_2.cs)]

 В этом примере формируются следующие данные:

 **Значение из незащищенных член: seattle.corp.contoso.com**
## <a name="see-also"></a>См. также
 [Правила написания безопасного кода](/dotnet/standard/security/secure-coding-guidelines) [требования связывания](/dotnet/framework/misc/link-demands) [данных и моделирование](/dotnet/framework/data/index)
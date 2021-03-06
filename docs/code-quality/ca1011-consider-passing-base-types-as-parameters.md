---
title: 'CA1011: попробуйте передать базовые типы в качестве параметров'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- ConsiderPassingBaseTypesAsParameters
- CA1011
helpviewer_keywords:
- CA1011
- ConsiderPassingBaseTypesAsParameters
ms.assetid: ce1e1241-dcf4-419b-9363-1d5bc4989279
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 1eaa68b6046fd2d3cfb6370b18de2b478b16db9d
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="ca1011-consider-passing-base-types-as-parameters"></a>CA1011: попробуйте передать базовые типы в качестве параметров
|||
|-|-|
|TypeName|ConsiderPassingBaseTypesAsParameters|
|CheckId|CA1011|
|Категория|Microsoft.Design|
|Критическое изменение|Критическое|

## <a name="cause"></a>Причина
 Объявление метода содержит формальный параметр, который является производным типом, а метод вызывает только члены базового типа параметра.

## <a name="rule-description"></a>Описание правила
 Если в объявлении метода в качестве параметра указан базовый тип, любой тип, производный от базового, можно передать методу в качестве соответствующего аргумента. При использовании аргумента в теле метода конкретный метод, который выполняется зависит от типа аргумента. Если дополнительные функции, предоставляемые производным типом, не является обязательной, использование базового типа позволит более широко применять метод.

## <a name="how-to-fix-violations"></a>Устранение нарушений
 Чтобы устранить нарушение данного правила, измените тип параметра со своим базовым типом.

## <a name="when-to-suppress-warnings"></a>Отключение предупреждений
 Его можно безопасно подавить предупреждение из этого правила

-   Если методу требуется конкретные функции, предоставляемые производным типом

     \- или -

-   для принудительного применения только производного типа или производного типа, переданный методу.

 В этом случае код будет более надежными из-за строгая проверка типов, предоставленных компилятор и среда выполнения.

## <a name="example"></a>Пример
 В следующем примере показан метод, `ManipulateFileStream`, который может использоваться только с <xref:System.IO.FileStream> объекта, который нарушает это правило. Второй метод, `ManipulateAnyStream`, соответствующий этому правилу, заменив <xref:System.IO.FileStream> параметра с помощью <xref:System.IO.Stream>.

 [!code-csharp[FxCop.Design.ConsiderPassingBaseTypes#1](../code-quality/codesnippet/CSharp/ca1011-consider-passing-base-types-as-parameters_1.cs)]
 [!code-cpp[FxCop.Design.ConsiderPassingBaseTypes#1](../code-quality/codesnippet/CPP/ca1011-consider-passing-base-types-as-parameters_1.cpp)]
 [!code-vb[FxCop.Design.ConsiderPassingBaseTypes#1](../code-quality/codesnippet/VisualBasic/ca1011-consider-passing-base-types-as-parameters_1.vb)]

## <a name="related-rules"></a>Связанные правила
 [CA1059: члены не должны предоставлять определенные устойчивые типы](../code-quality/ca1059-members-should-not-expose-certain-concrete-types.md)
---
title: Добавление пользовательских свойств в схемы зависимостей
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- dependency diagrams, adding custom properties
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 368d1a794f51d827aa62cc913039edda59ae7ae6
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="add-custom-properties-to-dependency-diagrams"></a>Добавление пользовательских свойств в схемы зависимостей

При написании кода расширения для схем зависимостей можно хранить значения с любым элементом на схеме зависимостей. Значения сохраняются при сохранении и повторном открытии схемы. Вы также можете эти свойства отображаются в **свойства** окна, чтобы пользователи могли просматривать и изменять их. Например, можно позволить пользователям задать регулярное выражение для каждого слоя и написать код для проверки того, соответствуют ли имена классов в каждом слое шаблону, заданному пользователем.

## <a name="non-visible-properties"></a>Невидимые свойства

Если необходимо просто код, чтобы присоединить значения на любой элемент в схеме зависимостей, не нужно определять компонент MEF. В `Properties` есть словарь <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerElement>. Просто добавьте маршалируемые значения в словарь любого элемента слоя. Они будут сохранены как часть диаграммы зависимостей. Дополнительные сведения см. в разделе [перехода и обновления уровня модели в программном коде](../modeling/navigate-and-update-layer-models-in-program-code.md).

## <a name="editable-properties"></a>Для редактирования свойства.

**Предварительная подготовка**

> [!IMPORTANT]
> Чтобы сделать отображаются свойства, необходимо сделать следующие изменения на каждом компьютере, где требуется свойства слоя, чтобы быть видимым:
>
> 1. Запустите Блокнот с помощью **Запуск от имени администратора**. Откройте *%ProgramFiles%\Microsoft Visual Studio [версия] \Common7\IDE\Extensions\Microsoft\Architecture Tools\ExtensibilityRuntime\extension.vsixmanifest*.
> 2. Внутри **содержимого** элемента, добавьте:
>
>     ```xml
>     <MefComponent>Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.Provider.dll</MefComponent>
>     ```
> 3. В разделе **набора средств Visual Studio** части Visual Studio приложения меню «Пуск» откройте **Командная строка разработчика**. Введите следующие команды:
>
>      `devenv /rootSuffix /updateConfiguration`
>
>      `devenv /rootSuffix Exp /updateConfiguration`
> 4. Перезапустите Visual Studio.

**Убедитесь, что ваш код в проект VSIX**

Если свойство является частью команд, жестов или проверки проекта, добавьте ничего не нужно. Код пользовательского свойства должен быть определен в проекте расширения Visual Studio как компонент MEF. Дополнительные сведения см. в разделе [Добавление команд и жестов в схемы зависимостей](../modeling/add-commands-and-gestures-to-layer-diagrams.md) или [Добавление пользовательской проверки архитектуры в схемы зависимостей](../modeling/add-custom-architecture-validation-to-layer-diagrams.md).

**Определение пользовательских свойств**

Чтобы создать пользовательское свойство, определите класс, как показано ниже.

```csharp
[Export(typeof(IPropertyExtension))]
public class MyProperty : PropertyExtension<ILayerElement>
{
  // Implement the interface.
}
```

Свойства можно определить для класса <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerElement> или любого из его производных классов, которые включают следующие классы:

-   `ILayerModel` — модель

-   `ILayer` — каждый слой

-   `ILayerDependencyLink` — ссылки между слоями

-   `ILayerComment`

-   `ILayerCommentLink`

## <a name="example"></a>Пример

Приведенный ниже код представляет собой типичный дескриптор пользовательского свойства. Он определяет логическое свойство в модели слоев (`ILayerModel`), которое позволяет пользователю предоставлять значения для пользовательского метода проверки.

```csharp
using System;
using System.ComponentModel.Composition;
using Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer;

namespace MyNamespace
{
  /// <summary>
  /// Custom properties are added to the Layer Designer via a custom
  /// Property Descriptor. We have to export this Property Descriptor
  /// using MEF to make it available in the Layer Designer.
  /// </summary>
  [Export(typeof(IPropertyExtension))]
  public class AllTypesMustBeReferencedProperty
      : PropertyExtension<ILayerModel>
  {
    /// <summary>
    /// Each custom property must have a unique name.
    /// Usually we use the full name of this class.
    /// </summary>
    public static readonly string FullName =
      typeof(AllTypesMustBeReferencedProperty).FullName;

    /// <summary>
    /// Construct the property. Notice the use of FullName.
    /// </summary>
    public AllTypesMustBeReferencedProperty()
            : base(FullName)
    {  }

    /// <summary>
    /// The display name is shown in the Properties window.
    /// We therefore use a localizable resource.
    /// </summary>
    public override string DisplayName
    {
      get { return Strings.AllTypesMustBeReferencedDisplayName; }
    }

    /// <summary>
    /// Description shown at the bottom of the Properties window.
    /// We use a resource string for easier localization.
    /// </summary>
    public override string Description
    {
      get { return Strings.AllTypesMustBeReferencedDescription; }
    }

    /// <summary>
    /// This is called to set a new value for this property. We must
    /// throw an exception if the value is invalid.
    /// </summary>
    /// <param name="component">The target ILayerElement</param>
    /// <param name="value">The new value</param>
    public override void SetValue(object component, object value)
    {
      ValidateValue(value);
      base.SetValue(component, value);
    }
    /// <summary>
    /// Helper to validate the value.
    /// </summary>
    /// <param name="value">The value to validate</param>
    private static void ValidateValue(object value)
    {  }

    public override Type PropertyType
    { get { return typeof(bool); } }

    /// <summary>
    /// The segment label of the properties window.
    /// </summary>
    public override string Category
    {
      get
      {
        return Strings.AllTypesMustBeReferencedCategory;
      }
    }
  }
}
```

## <a name="see-also"></a>См. также

- [Расширение схем зависимостей](../modeling/extend-layer-diagrams.md)

---
title: Создание веб-шаблонов для Visual Studio
ms.date: 01/02/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio templates, Web
- templates [Visual Studio], Web
- Web templates [Visual Studio]
- project templates [Visual Studio], Web
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: aeaeea5ee4d1d8e65cdc13ca11192a70e0459be1
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-manually-create-web-templates"></a>Практическое руководство. Создание веб-шаблонов вручную

Создание веб-шаблона отличается от создания других типов шаблонов. Так как шаблоны веб-проектов отображаются в диалоговом окне **Добавить новый веб-сайт**, а элементы веб-проекта классифицируются по языку программирования, файл *VSTEMPLATE* должен указывать, что это веб-шаблон, а также задавать язык программирования.

> [!NOTE]
> Веб-шаблоны должны содержать пустой файл *WEBPROJ*, на который должна быть добавлена ссылка в файле *VSTEMPLATE* в атрибуте `File` элемента `Project`. Несмотря на то, что для веб-проектов не требуется файл проекта *PROJ*, необходимо создать этот файл-заглушку для правильной работы веб-шаблона.

## <a name="to-manually-create-a-web-template"></a>Создание веб-шаблонов вручную

1. Создайте веб-проект.

1. Измените или удалите файлы в проекте или добавьте в него новые файлы.

1. Создайте XML-файл и сохраните его с расширением *VSTEMPLATE* в одном каталоге с проектом. Не добавляйте его в проект в Visual Studio.

1. Измените файл *VSTEMPLATE* с XML-кодом, чтобы предоставить метаданные шаблона проекта. Дополнительные сведения см. в [приведенных ниже примерах](#example).

1. Найдите в файле *VSTEMPLATE* элемент `ProjectType` и задайте `Web` в качестве текстового значения.

1. После элемента `ProjectType` добавьте элемент `ProjectSubType` и задайте язык программирования этого шаблона в качестве текстового значения. Этот язык программирования может принимать одно из следующих значений:

    - CSharp
    - VisualBasic

    Пример:

    ```xml
    <TemplateData>
        ...
        <ProjectType>Web</ProjectType>
        <ProjectSubType>CSharp</ProjectSubType>
        ...
    </TemplateData>
    ```

1. Выберите файлы в шаблоне (включая файл *VSTEMPLATE*), щелкните их правой кнопкой мыши и последовательно выберите **Отправить** > **Сжатая ZIP-папка**. Файлы сжимаются в *ZIP*-файл.

1. Поместите *ZIP*-файл шаблона в каталог шаблонов проекта Visual Studio. По умолчанию это каталог *%USERPROFILE%\Documents\Visual Studio \<версия\>\ProjectTemplates*.

## <a name="example"></a>Пример

В следующем примере показан базовый файл *VSTEMPLATE* для шаблона веб-проекта:

```xml
<VSTemplate Version="2.0.0" Type="Project"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">>
    <TemplateData>
        <Name>MyWebProjecStarterKit</Name>
        <Description>A simple Web template</Description>
        <Icon>icon.ico</Icon>
        <ProjectType>Web</ProjectType>
        <ProjectSubType>CSharp</ProjectSubType>
        <DefaultName>WebSite</DefaultName>
    </TemplateData>
    <TemplateContent>
        <Project File="WebApplication.webproj">
            <ProjectItem>icon.ico</ProjectItem>
            <ProjectItem OpenInEditor="true">Default.aspx</ProjectItem>
            <ProjectItem>Default.aspx.cs</ProjectItem>
        </Project>
    </TemplateContent>
</VSTemplate>
```

## <a name="see-also"></a>См. также

- [Создание шаблонов проектов и элементов](../ide/creating-project-and-item-templates.md)
- [Справочник по схемам шаблонов Visual Studio (расширяемость)](../extensibility/visual-studio-template-schema-reference.md)
---
title: Вставка комментариев XML-документации в Visual Studio
ms.date: 01/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: e3c38e46a5c73d1f8018f56f76b971939ba8c316
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-insert-xml-comments-for-documentation-generation"></a>Практическое руководство. Вставка XML-комментариев для создания документации

Visual Studio может помочь вам документировать элементы кода, такие как классы и методы, автоматически формируя стандартную структуру комментариев для XML-документации. Во время компиляции можно создать XML-файл, содержащий комментарии для документации. Созданный компилятором XML-файл можно распространять вместе со сборкой .NET, чтобы Visual Studio и другие интегрированные среды разработки могли использовать IntelliSense для отображения кратких сведений о типах и элементах. Кроме того, XML-файл можно запускать с помощью таких средств, как [DocFX](https://dotnet.github.io/docfx/) и [Sandcastle](https://www.microsoft.com/download/details.aspx?id=10526), и создавать веб-сайты со справочными сведениями по API.

> [!NOTE]
> Команда **Вставить комментарий**, которая автоматически вставляет комментарии XML-документации, доступна в [C#](/dotnet/csharp/programming-guide/xmldoc/xml-documentation-comments) и [Visual Basic](/dotnet/visual-basic/programming-guide/program-structure/how-to-create-xml-documentation). Однако можно вручную вставить [комментарии XML-документации в файлы C++](/cpp/ide/xml-documentation-visual-cpp) и по-прежнему создавать файлы XML-документации во время компиляции.

## <a name="to-insert-xml-comments-for-a-code-element"></a>Вставка XML-комментариев для элемента кода

1. Поместите текстовый курсор над элементом, например методом, который нужно задокументировать.

1. Выполните одно из следующих действий.

   - Введите `///` в C# или `'''` в Visual Basic

   - В меню **Правка** выберите **IntelliSense** > **Вставить комментарий**.

   - Щелкните правой кнопкой мыши или вызовите контекстное меню в редакторе кода или над ним и выберите **Фрагмент кода** > **Вставить комментарий**.

   Над элементом кода сразу же создается XML-шаблон. Например, при комментировании метода создается элемент **\<summary\>**, элемент **\<param\>** для каждого параметра и элемент **\<returns\>** для документирования возвращаемого значения.

   ![Шаблон для XML-комментариев — C#](media/doc-preview-cs.png)

   ![Шаблон для XML-комментариев — Visual Basic](media/doc-preview-vb.png)

1. Введите описание для каждого XML-элемента, чтобы полностью задокументировать элемент кода.

   ![Ввод комментариев](media/doc-result-cs.png)

> [!NOTE]
> Существует [параметр](../../ide/reference/options-text-editor-csharp-advanced.md) для переключения комментариев XML-документации после ввода `///` в C# или `'''` Visual Basic. В строке меню выберите **Сервис** > **Параметры**, чтобы открыть диалоговое окно **Параметры**. Перейдите в раздел **Текстовый редактор** > **C#** или **Basic** > **Дополнительно**. В разделе **Справка редактора** найдите параметр **Создавать комментарии XML-документации**.

## <a name="see-also"></a>См. также

- [Комментарии к XML-документации (руководство по программированию на C#)](/dotnet/csharp/programming-guide/xmldoc/xml-documentation-comments)
- [Документирование кода с помощью XML-комментариев (руководство по C#)](/dotnet/csharp/codedoc)
- [Практическое руководство. Создание XML-документации (Visual Basic)](/dotnet/visual-basic/programming-guide/program-structure/how-to-create-xml-documentation)
- [Комментарии C++](/cpp/cpp/comments-cpp)
- [XML-документация (C++)](/cpp/ide/xml-documentation-visual-cpp)
- [Создание кода](../code-generation-in-visual-studio.md)
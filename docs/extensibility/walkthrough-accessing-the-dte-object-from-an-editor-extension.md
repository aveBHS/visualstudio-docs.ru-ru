---
title: 'Пошаговое руководство: Доступ к объекту DTE из расширения редактора | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], new - getting the DTE object
ms.assetid: c1f40bab-c6ec-45b0-8333-ea5ceb02a39d
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b888136f51e7893c6ad44ab888d8079ee92d8edf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-accessing-the-dte-object-from-an-editor-extension"></a>Пошаговое руководство: Доступ к объекту DTE из расширения редактора
В пакеты VSPackage, можно получить объект DTE, вызвав <xref:Microsoft.VisualStudio.Shell.Package.GetService%2A> метода с типом объекта DTE. В расширениях Managed Extensibility Framework (MEF), можно импортировать <xref:Microsoft.VisualStudio.Shell.SVsServiceProvider> и затем вызвать <xref:Microsoft.VisualStudio.Shell.ServiceProvider.GetService%2A> метода с типом <xref:EnvDTE.DTE>.  
  
## <a name="prerequisites"></a>Предварительные требования  
 Для выполнения этого пошагового руководства необходимо установить пакет SDK для Visual Studio. Дополнительные сведения см. в разделе [пакет SDK для Visual Studio](../extensibility/visual-studio-sdk.md).  
  
## <a name="getting-the-dte-object"></a>Получить объект DTE  
  
#### <a name="to-get-the-dte-object-from-the-serviceprovider"></a>Чтобы получить объект DTE из поставщик службы  
  
1.  Создайте проект VSIX C# с именем `DTETest`. Добавление шаблона классификатора редактора элементов и назовите его `DTETest`. Дополнительные сведения см. в разделе [создания расширения с помощью шаблона элемента редактор](../extensibility/creating-an-extension-with-an-editor-item-template.md).  
  
2.  Добавьте следующие ссылки на сборки в проект:  
  
    -   EnvDTE  
  
    -   EnvDTE80  
  
    -   Microsoft.VisualStudio.Shell.Immutable.10.0  
  
3.  Перейдите к файлу DTETest.cs и добавьте следующее `using` директивы:  
  
    ```csharp  
    using EnvDTE;  
    using EnvDTE80;  
    using Microsoft.VisualStudio.Shell;  
  
    ```  
  
4.  В `GetDTEProvider` класса, импортируйте <xref:Microsoft.VisualStudio.Shell.SVsServiceProvider>.  
  
    ```csharp  
    [Import]  
    internal SVsServiceProvider ServiceProvider = null;  
  
    ```  
  
5.  Добавьте в метод `GetClassifier()` следующий код:  
  
    ```csharp  
    DTE dte = (DTE)ServiceProvider.GetService(typeof(DTE));  
  
    ```  
  
6.  Если необходимо использовать <xref:EnvDTE80.DTE2> интерфейса, можно привести объект DTE к нему.  
  
## <a name="see-also"></a>См. также  
 [Языковая служба и точки расширения редактора](../extensibility/language-service-and-editor-extension-points.md)
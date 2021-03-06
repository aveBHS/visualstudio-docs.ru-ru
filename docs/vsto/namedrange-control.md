---
title: Элемент управления NamedRange | Документы Microsoft
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VST.Toolbox.Range
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ranges, named
- NamedRange control, events
- NamedRange control, data binding
- NamedRange control
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 7ea0b0f59731f711dc32258aea31358626825f5d
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2018
ms.locfileid: "34573093"
---
# <a name="namedrange-control"></a>NamedRange - элемент управления
  Элемент управления <xref:Microsoft.Office.Tools.Excel.NamedRange> представляет собой диапазон с уникальным именем, который предоставляет события и может быть привязан к данным. Дополнительные сведения см. в разделе [Общие сведения о модели объектов Excel](../vsto/excel-object-model-overview.md).  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="create-the-control"></a>Создание элемента управления  
 Элементы управления <xref:Microsoft.Office.Tools.Excel.NamedRange> можно добавлять в лист Microsoft Office Excel во время разработки и во время выполнения в проекте на уровне документа.  
  
 Вы можете добавлять элементы управления <xref:Microsoft.Office.Tools.Excel.NamedRange> в лист во время выполнения в надстройке VSTO. Дополнительные сведения см. в разделе [как: элементы управления NamedRange, добавление к листам](../vsto/how-to-add-namedrange-controls-to-worksheets.md).  
  
> [!NOTE]  
>  По умолчанию динамически созданные именованные диапазоны не сохраняются как ведущие элементы управления в листе при его закрытии. Дополнительные сведения см. в разделе [Добавление элементов управления в документы Office во время выполнения](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
 Элементы управления<xref:Microsoft.Office.Tools.Excel.NamedRange> могут состоять только из диапазонов в определенных листах. Элементы управления<xref:Microsoft.Office.Tools.Excel.NamedRange> не могут иметь относительные имена, применимые для всех листов, и они не могут состоять из диапазонов, распространяющихся на несколько листов в книге (трехмерных диапазонов).  
  
## <a name="bind-data-to-the-control"></a>Привязка данных к элементу управления  
 Кажется, что именованный диапазон будет хорошим кандидатом для сложной привязки данных, поскольку он может иметь много ячеек. Однако диапазон — это всего лишь коллекция ячеек, которую невозможно легко сопоставить с определенным столбцом из набора данных. Таким образом, элементы управления <xref:Microsoft.Office.Tools.Excel.NamedRange> поддерживают только простую привязку данных. Элемент управления <xref:Microsoft.Office.Tools.Excel.ListObject> может использоваться для сложной привязки данных. Дополнительные сведения см. в разделе [управления ListObject](../vsto/listobject-control.md).  
  
 Элемент управления <xref:Microsoft.Office.Tools.Excel.NamedRange> может быть привязан к источнику данных с помощью свойств <xref:System.Windows.Forms.Control.DataBindings%2A> . Свойство привязки данных по умолчанию элемента управления <xref:Microsoft.Office.Tools.Excel.NamedRange> — это <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A>.  
  
 Если данные в привязанном наборе данных обновляются посредством какого-либо механизма, элемент управления <xref:Microsoft.Office.Tools.Excel.NamedRange> отражает изменения.  
  
## <a name="formatting"></a>Форматирование  
 Любое форматирование, которое можно применить к <xref:Microsoft.Office.Interop.Excel.Range> , также можно применить и к элементу управления <xref:Microsoft.Office.Tools.Excel.NamedRange> . Это включает границы, шрифты, формат чисел и стили.  
  
## <a name="rename-the-control"></a>Переименование элемента управления  
 При добавлении в лист элемента управления <xref:Microsoft.Office.Tools.Excel.NamedRange> из **панели элементов**Visual Studio автоматически создает имя для этого элемента управления. Это имя можно изменить в окне **Свойства** .  
  
## <a name="events"></a>События  
 Для элемента управления <xref:Microsoft.Office.Tools.Excel.NamedRange> доступны следующие события:  
  
-   <xref:Microsoft.Office.Tools.Excel.NamedRange.BeforeDoubleClick>  
  
-   <xref:Microsoft.Office.Tools.Excel.NamedRange.BeforeRightClick>  
  
-   <xref:Microsoft.Office.Tools.Excel.NamedRange.BindingContextChanged>  
  
-   <xref:Microsoft.Office.Tools.Excel.NamedRange.Change>  
  
-   <xref:Microsoft.Office.Tools.Excel.NamedRange.Deselected>  
  
-   <xref:System.ComponentModel.Component.Disposed>  
  
-   <xref:Microsoft.Office.Tools.Excel.NamedRange.Selected>  
  
-   <xref:Microsoft.Office.Tools.Excel.NamedRange.SelectionChange>  
  
## <a name="see-also"></a>См. также  
 [Автоматизация Excel с помощью расширенных объектов](../vsto/automating-excel-by-using-extended-objects.md)   
 [Примеры разработки решений Office и пошаговые руководства](../vsto/office-development-samples-and-walkthroughs.md)   
 [Привязка данных к элементам управления в решениях Office](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Расширение документов Word и книг Excel в надстройках VSTO во время выполнения](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Элементы управления в документах Office](../vsto/controls-on-office-documents.md)   
 [Добавление элементов управления в документы Office во время выполнения](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Как: Добавление элементов управления NamedRange на листы](../vsto/how-to-add-namedrange-controls-to-worksheets.md)   
 [Как: изменение размеров элементов управления NamedRange](../vsto/how-to-resize-namedrange-controls.md)   
 [Привязка данных к элементам управления в решениях Office](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Пошаговое руководство: Программа реакции на события элементов управления NamedRange](../vsto/walkthrough-programming-against-events-of-a-namedrange-control.md)   
 [Программные ограничения ведущих элементов и элементов управления ведущего приложения](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  
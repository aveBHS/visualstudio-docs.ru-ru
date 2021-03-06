---
title: 'Как: включаемых файлов с помощью модуля | Документы Microsoft'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, modules
- modules [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: daea134298e84e7ddddf419da2124924fe9ef121
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/22/2018
---
# <a name="how-to-include-files-by-using-a-module"></a>Практическое руководство. Включение файлов с помощью модуля
  *Модули* (не следует путать с [!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)] модулей) — это контейнеры, которые позволяют развернуть файлы, такие как главные страницы ASPX, текстовые файлы или изображения в SharePoint.  
  
 Вы можете развернуть файл в библиотеку документов или как обычный файл (например, default.aspx) вне библиотеки документов. Чтобы добавить файл в библиотеку документов, укажите `Type="GhostableInLibrary"` в качестве атрибута **файл** элемента. Этот параметр предписывает SharePoint для создания элемента списка, чтобы перейти с помощью файла при добавлении в библиотеку. Чтобы развернуть файл вне библиотеки документов, либо укажите `Type="Ghostable"` или просто пропустите **тип** атрибута.  
  
## <a name="adding-a-module-to-a-sharepoint-solution"></a>Добавление модуля в решение SharePoint  
  
#### <a name="to-add-a-module"></a>Чтобы добавить модуль  
  
1.  Откройте или создайте проект SharePoint в [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
     Дополнительные сведения см. в разделе [проект SharePoint и шаблоны элементов проекта](../sharepoint/sharepoint-project-and-project-item-templates.md).  
  
2.  В **обозревателе решений**, выберите узел проекта и затем в строке меню выберите **проекта**, **Добавление нового элемента**.  
  
     Откроется диалоговое окно **Добавление нового элемента**.  
  
3.  В списке шаблонов SharePoint выберите **модуля** шаблона, а затем выберите **добавить** кнопки.  
  
     На этом этапе в проекте будет создан новый узел с именем Module1.  
  
4.  В узле Module1 удалите файл Sample.txt.  
  
     Sample.txt включается во всех новых модулях в качестве примера и не требуется. (Обратите внимание, что удаление файла также удаляет его запись из файла модуля Elements.xml).  
  
5.  Если требуется вашего развертывания файлов в определенной структуре папок в SharePoint, создайте эти папки в узле Module1 в [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] , выбрав узел Module1, а затем в строке меню, выберите **проекта**, **New Папка**.  
  
6.  Выберите папку, в которой вы хотите добавить файл, а затем в строке меню выберите **проекта**, **Добавление существующего элемента**.  
  
7.  Выберите один или несколько файлов, которые необходимо развернуть в SharePoint, а затем выберите **добавить** кнопки.  
  
     При добавлении файла в проект, его запись автоматически добавляется в файл Elements.xml модуля. При развертывании проекта, файлы копируются на сервер SharePoint, относительно корневого каталога проекта, который задается **файл** элемента **URL-адрес** атрибут, например `Url="Module1/New Folder/SomeFile.doc`. Если вы хотите изменить место развертывания файла, либо переместите его в другую папку **обозревателе решений** или изменить его **URL-адрес** параметр.  
  
8.  Все файлы, которые должны отображаться в библиотеке документов, добавьте `Type="GhostableInLibrary"` атрибут их записи в Elements.xml. Например, примененная к объекту директива  
  
    ```xml  
    <File Path="Module1\Some Folder\SomePage.aspx" Url="Module1/Some Folder/SomePage.aspx" Type="GhostableInLibrary" />  
    ```  
  
9. Развертывание проекта.  
  
     Скопируйте файлы в указанных расположениях в SharePoint.  
  
## <a name="see-also"></a>См. также  
 [Упаковка и развертывание решений SharePoint](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)   
 [Разработка решений SharePoint](../sharepoint/developing-sharepoint-solutions.md)  
  
  
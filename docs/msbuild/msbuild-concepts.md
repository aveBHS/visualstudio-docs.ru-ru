---
title: Основные возможности MSBuild | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, concepts
ms.assetid: 083b8ba3-e4ad-45af-bb5d-3bc81d406131
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fd43d79950a39702108383f7408e1a37960e7c06
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/19/2018
---
# <a name="msbuild-concepts"></a>Основные возможности MSBuild
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] предоставляет базовую схему XML, которую можно использовать для управления процессом сборки программного обеспечения, выполняемым платформой сборки. Чтобы указать компоненты в сборке и способ ее выполнения, используйте следующие четыре составляющие MSBuild: свойства, элементы, задачи и целевые объекты.  
  
## <a name="related-topics"></a>См. также  
  
|Заголовок|Описание:|  
|-----------|-----------------|  
|[Свойства MSBuild](../msbuild/msbuild-properties.md)|Содержит вводную информацию о свойствах и коллекциях свойств. Свойства представляют собой пары "ключ — значение", с помощью которых выполняется настройка сборок.|  
|[Элементы MSBuild](../msbuild/msbuild-items.md)|Представляет элементы и коллекции элементов. Элементы — это входные данные для системы сборки, как правило, представляющие файлы.|  
|[Целевые объекты MSBuild](../msbuild/msbuild-targets.md)|Содержит объяснение группировки задач в определенном порядке и вызова разделов процесса построения из командной строки.|  
|[Задачи MSBuild](../msbuild/msbuild-tasks.md)|Описывает процесс создания блока исполняемого кода, с помощью которого [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] выполняет атомарные операции построения.|  
|[Сравнение свойств и элементов](../msbuild/comparing-properties-and-items.md)|Сравнивает свойства и элементы MSBuild. И то, и другое используется для передачи данных задачам, проверки условий и хранения значений, которые будут использоваться в файле проекта.|  
|[Специальные символы в MSBuild](../msbuild/msbuild-special-characters.md)|Объясняет, как записывать некоторые символы, зарезервированные [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] для специального применения в определенных контекстах, в виде escape-последовательностей.|  
|[Пошаговое руководство. Создание файла проекта MSBuild с нуля](../msbuild/walkthrough-creating-an-msbuild-project-file-from-scratch.md)|Содержит описание способов пошагового создания основного файла проекта путем использования только текстового редактора.|  
|[Пошаговое руководство. Использование MSBuild](../msbuild/walkthrough-using-msbuild.md)|Содержит вводную информацию о стандартных блоках MSBuild и описание способов записи, управления и отладки проектов MSBuild без выхода из интегрированной среды разработки Visual Studio.|  
|[Справочные сведения о MSBuild](../msbuild/msbuild-reference.md)|Содержит ссылки на документы, содержащие справочную информацию.|  
|[MSBuild](../msbuild/msbuild.md)|Предоставляет общие сведения о схеме XML для файла проекта и показывает способ управления процессами, осуществляющими сборку программного обеспечения.|

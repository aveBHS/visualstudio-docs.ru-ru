---
title: Определение состояния команды с помощью сборок взаимодействия | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- interop assemblies, determining command status
- command handling with interop assemblies, status
ms.assetid: 2f5104d1-7b4c-4ca0-a626-50530a8f7f5c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4989910fdec968a4a05e2459e6625ee2c15fd9a4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="determining-command-status-by-using-interop-assemblies"></a>Определение состояния команды с помощью сборок взаимодействия
Пакет VSPackage должен хранить список состояние команды, которые он может обрабатывать. Среде не может определить, когда обрабатывается в VSPackage команды становится включен или отключен. Отвечает вашего VSPackage, чтобы сообщать среде о состояниях команды, например, состояние общие команды, такие как **Вырезать**, **копирования**, и **вставить**.  
  
## <a name="status-notification-sources"></a>Состояние источников уведомлений  
 Среде получает сведения о командах через пакеты VSPackage <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> метод, который является частью VSPackage реализации из <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> интерфейса. Среда вызывает метод <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> метод VSPackage в двух случаях:  
  
-   Когда пользователь открывает главного меню или контекстное меню (щелкнув правой кнопкой мыши), в среде выполняется <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> метод для всех команд, меню, чтобы определить их состояние.  
  
-   Когда VSPackage запрашивает, что среде обновить текущий пользовательский интерфейс (UI). Это происходит в виде команд, которые видимы для пользователя, такие как **Вырезать**, **копирования**, и **вставить** группирования на стандартной панели инструментов, становятся включенных и отключенных в ответ на действия контекста и пользователя.  
  
 Поскольку оболочка содержит несколько пакетов VSPackage, производительностью оболочки будет неприемлемо снижению требовались для опроса каждого пакета VSPackage, чтобы определить состояние команды. Вместо этого VSPackage активно следует уведомить среде при изменении его пользовательского интерфейса во время изменения. Дополнительные сведения о уведомление об обновлении см. в разделе [обновление пользовательского интерфейса](../../extensibility/updating-the-user-interface.md).  
  
## <a name="status-notification-failure"></a>Сбой уведомления о состоянии  
 Сбой пакета VSPackage для уведомления среды изменение состояния команды можно разместить пользовательский Интерфейс в несогласованном состоянии. Помните, что любой команды меню или команду контекстного меню можно поместить на панели инструментов для пользователя. Таким образом обновление пользовательского интерфейса только в том случае, когда открывается меню или команду контекстного меню недостаточно.  
  
## <a name="see-also"></a>См. также  
 [Как добавить элементы пользовательского интерфейса в пакеты VSPackage](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Реализация](../../extensibility/internals/command-implementation.md)
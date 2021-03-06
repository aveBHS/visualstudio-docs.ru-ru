---
title: "Idebugapplicationnode100 — интерфейс | Документы Microsoft"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IDebugApplicationNode100 Interface
ms.assetid: 43966d4e-5f89-4a04-a08d-782347d00c2d
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: af79614d38ef55776b660329f51931be70b7f52e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2017
---
# <a name="idebugapplicationnode100-interface"></a>IDebugApplicationNode100 — интерфейс
`IDebugApplicationNode100` Интерфейс расширяет функциональность [интерфейс IDebugApplicationNode](../../winscript/reference/idebugapplicationnode-interface.md). Экземпляр этого интерфейса можно получить, вызвав QueryInterface для реализации [интерфейс IDebugApplicationNode](../../winscript/reference/idebugapplicationnode-interface.md).  
  
> [!IMPORTANT]
>  Этот интерфейс реализуется в PDM v10.0 и более. Обнаружено в activdbg100.h.  
  
## <a name="methods"></a>Методы  
 Интерфейс `IDebugApplicationNode100` предоставляет следующие методы.  
  
|Метод|Описание|  
|------------|-----------------|  
|[IDebugApplicationNode100::GetExcludedDocuments](../../winscript/reference/idebugapplicationnode100-getexcludeddocuments.md)|Возвращает текстовые документы, которые скрыты с помощью указанного фильтра.|  
|[IDebugApplicationNode100::QueryIsChildNode](../../winscript/reference/idebugapplicationnode100-queryischildnode.md)|Определяет, относится ли указанный документ на один из дочерних узлов данного узла.|  
|[IDebugApplicationNode100::SetFilterForEventSink](../../winscript/reference/idebugapplicationnode100-setfilterforeventsink.md)|Задает фильтр на определенном [интерфейс IDebugApplicationNodeEvents](../../winscript/reference/idebugapplicationnodeevents-interface.md) реализации. Она позволяет отладчики сценариев для фильтрации компилятором дочерних узлов приложения, чтобы PDM больше не будет отправлять события при создании или удалить узлы. По умолчанию будут отправляться все узлы.|
---
title: "IActiveScriptErrorDebug110::GetExceptionThrownKind | Документы Microsoft"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IActiveScriptErrorDebug110::QueryIsFirstChance
ms.assetid: ecc16e54-93e4-4322-ae13-afa7cd860032
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8306b1d4ff68fe9eec00d47d8c702278e89fc37b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescripterrordebug110getexceptionthrownkind"></a>IActiveScriptErrorDebug110::GetExceptionThrownKind
Возвращает значение, показывающее вид созданного исключения.  
  
> [!IMPORTANT]
>  [Iactivescripterrordebug110 — интерфейс](../../winscript/reference/iactivescripterrordebug110-interface.md) реализуется в PDM версии 11.0 или более поздней. Обнаружено в activdbg100.h.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetExceptionThrownKind(  
   SCRIPT_ERROR_DEBUG_EXCEPTION_THROWN_KIND*  pExceptionKind  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pExceptionKind`  
 [out] Тип исключения (например, первичном или необработанное), представленный [перечисление SCRIPT_ERROR_DEBUG_EXCEPTION_THROWN_KIND](../../winscript/reference/script-error-debug-exception-thrown-kind-enumeration.md) значение перечисления.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Метод возвращает `HRESULT`. Допустимые значения включают, но не ограничиваются, значения, приведенные в следующей таблице.  
  
|Значение|Описание|  
|-----------|-----------------|  
|`S_OK`|Метод успешно выполнен.|  
  
## <a name="see-also"></a>См. также  
 [Интерфейс IActiveScriptErrorDebug110](../../winscript/reference/iactivescripterrordebug110-interface.md)
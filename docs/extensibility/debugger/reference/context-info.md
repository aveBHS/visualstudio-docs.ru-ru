---
title: CONTEXT_INFO | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- CONTEXT_INFO
helpviewer_keywords:
- CONTEXT_INFO structure
ms.assetid: 6b513f4e-e7b0-4969-adf0-2205ccc1e09b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: fb634f59a3a7eb3b37e70dd87f48b22a07251d0e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="contextinfo"></a>CONTEXT_INFO
Эта структура описывает контекст памяти или контекст кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct _tagCONTEXT_INFO {   
   CONTEXT_INFO_FIELDS dwFields;  
   BSTR                bstrModuleUrl;  
   BSTR                bstrFunction;  
   TEXT_POSITION       posFunctionOffset;  
   BSTR                bstrAddress;  
   BSTR                bstrAddressOffset;  
   BSTR                bstrAddressAbsolute;  
} CONTEXT_INFO;  
```  
  
```csharp  
public struct CONTEXT_INFO {  
   public uint          dwFields;  
   public string        bstrModuleUrl;  
   public string        bstrFunction;  
   public TEXT_POSITION posFunctionOffset;  
   public string        bstrAddress;  
   public string        bstrAddressOffset;  
   public string        bstrAddressAbsolute;  
};  
```  
  
## <a name="members"></a>Участники  
 dwFields  
 Сочетание флагов из он [CONTEXT_INFO_FIELDS](../../../extensibility/debugger/reference/context-info-fields.md) перечисления, которое указывает, какие поля заполняются**.**  
  
 bstrModuleUrl  
 Имя модуля, в которой находится контекст.  
  
 bstrFunction  
 Имя функции, в которой находится контекст.  
  
 posFunctionOffset  
 Объект [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) структуру, которая определяет смещение строки и столбца, связанный с контекстом кода функции.  
  
 bstrAddress  
 Адрес в коде, где находится данный контекст.  
  
 bstrAddressOffset  
 Смещение по адресу в коде, где находится данный контекст.  
  
 bstrAddressAbsolute  
 Абсолютный адрес в памяти, где находится данный контекст.  
  
## <a name="remarks"></a>Примечания  
 Эта структура возвращается из вызова [GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md) метод.  
  
 Обычно эта структура используется поддержки **памяти** окон отладки.  
  
## <a name="requirements"></a>Требования  
 Заголовок: msdbg.h  
  
 Пространство имен: Microsoft.VisualStudio.Debugger.Interop  
  
 Сборка: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>См. также  
 [Структур и объединений](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md)   
 [CONTEXT_INFO_FIELDS](../../../extensibility/debugger/reference/context-info-fields.md)   
 [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md)
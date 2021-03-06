---
title: IDebugEngine2::SetRegistryRoot | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugEngine2::SetRegistryRoot
helpviewer_keywords:
- IDebugEngine2::SetRegistryRoot
ms.assetid: d0d81202-8a4a-4bc3-b297-30a047c5ec60
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 606ddb5380da2bfe0c75d20bc70bf0da911ea4e5
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="idebugengine2setregistryroot"></a>IDebugEngine2::SetRegistryRoot
Задает корневой раздел реестра для модуля отладки (DE).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetRegistryRoot(   
   LPCOLESTR pszRegistryRoot  
);  
```  
  
```csharp  
int SetRegistryRoot(   
   string pszRegistryRoot  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pszRegistryRoot`  
 [in] Корневой раздел реестра для использования.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успеха возвращает `S_OK`; в противном случае возвращается код ошибки.  
  
## <a name="remarks"></a>Примечания  
 Этот метод позволяет [!INCLUDE[vsprvs](../../../code-quality/includes/vsprvs_md.md)] для указания альтернативного корневая папка реестра, DE следует использовать для получения параметров реестра; например, «HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0Exp».  
  
## <a name="see-also"></a>См. также  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)
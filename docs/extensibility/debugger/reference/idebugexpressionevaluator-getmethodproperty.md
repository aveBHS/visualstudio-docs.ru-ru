---
title: IDebugExpressionEvaluator::GetMethodProperty | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugExpressionEvaluator::GetMethodProperty
helpviewer_keywords:
- IDebugExpressionEvaluator::GetMethodProperty method
ms.assetid: c394fe4d-eeb6-4feb-828c-098d84a6f1ba
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b5d294e401af09ec3c10fa6dabbb878c661b559e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2018
---
# <a name="idebugexpressionevaluatorgetmethodproperty"></a>IDebugExpressionEvaluator::GetMethodProperty
Этот метод возвращает объект свойства, содержит локальные переменные, аргументы и другие свойства для метода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetMethodProperty(   
   IDebugSymbolProvider* pSymbolProvider,  
   IDebugAddress*        pAddress,  
   IDebugBinder*         pBinder,  
   BOOL                  fIncludeHiddenLocals,  
   IDebugProperty2**     ppProperty  
);  
```  
  
```csharp  
int GetMethodProperty(  
   IDebugSymbolProvider pSymbolProvider,   
   IDebugAddress        pAddress,   
   IDebugBinder         pBinder,   
   int                  fIncludeHiddenLocals,   
   out IDebugProperty2  ppProperty  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pSymbolProvider`  
 [in] Поставщик символ для использования, выраженного как [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md) объекта.  
  
 `pAddress`  
 [in] Адрес в коде в виде [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) объект, то должны быть исправлены ближайшего, в котором содержится функция.  
  
 `pBinder`  
 [in] Средство привязки, которую нужно использовать, выраженного как [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md) объекта.  
  
 `fIncludeHiddenLocals`  
 [in] Ненулевое значение (`TRUE`) означает включить скрытые локальных переменных; ноль (`FALSE`) означает оставлять скрытые локальные переменные  
  
 `ppProperty`  
 [out] Возвращает [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) объект, представляющий метод.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успеха возвращает `S_OK`; в противном случае возвращается код ошибки.  
  
## <a name="remarks"></a>Примечания  
 Скрытые локальные переменные обычно являются переменные, которые создаются компилятором.  
  
## <a name="see-also"></a>См. также  
 [IDebugExpressionEvaluator](../../../extensibility/debugger/reference/idebugexpressionevaluator.md)   
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)   
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)
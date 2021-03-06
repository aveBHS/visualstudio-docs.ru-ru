---
title: IDiaDataSource::openSession | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaDataSource::openSession method
ms.assetid: a3319ed0-3979-483b-9852-c0af96852c48
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 39fe9bf3a67d3ad5f26ff7c4ccdaa9772cf1346b
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="idiadatasourceopensession"></a>IDiaDataSource::openSession
Открывается сеанс для выполнения запросов к символы.  
  
## <a name="syntax"></a>Синтаксис  
  
```C++  
HRESULT openSession (   
   IDiaSession** ppSession  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 ppSession  
 [out] Возвращает [IDiaSession](../../debugger/debug-interface-access/idiasession.md) объект, представляющий открытый сеанс.  
  
## <a name="return-value"></a>Возвращаемое значение  
 В случае успеха возвращает `S_OK`; в противном случае возвращается код ошибки. В следующей таблице показаны возможные возвращаемые значения для этого метода.  
  
|Значение|Описание|  
|-----------|-----------------|  
|E_UNEXPECTED|[IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md) объекта не ранее был инициализирован с помощью источника символы.|  
|E_INVALIDARG|Недопустимый `ppSession` параметра.|  
|E_OUTOFMEMORY|Недостаточно памяти для открытия сеанса.|  
  
## <a name="remarks"></a>Примечания  
 Этот метод открывает [IDiaSession](../../debugger/debug-interface-access/idiasession.md) объект для источника данных.  
  
 `IDiaSession` объекты реализации запросов в источник данных. Сеанс управляет одно адресное пространство для каждого набора символов отладки. Если файл .exe или .dll, описываемый символы источника данных активного в нескольких адресов в диапазоне (например, если у нескольких процессов загружены), то следует использовать один сеанс для каждого из диапазонов адресов.  
  
## <a name="example"></a>Пример  
  
```C++  
IDiaSession* pSession;  
HRESULT hr = pSource->openSession( &pSession );  
if (FAILED(hr))  
{  
   // report error  
}  
```  
  
## <a name="see-also"></a>См. также  
 [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)   
 [Обзор](../../debugger/debug-interface-access/overview-debug-interface-access-sdk.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [Запрос PDB-файла](../../debugger/debug-interface-access/querying-the-dot-pdb-file.md)
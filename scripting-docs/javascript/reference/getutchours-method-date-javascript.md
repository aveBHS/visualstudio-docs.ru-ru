---
title: "Метод getUTCHours (Date) (JavaScript) | Документы Microsoft"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- getUTCHours
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- hours
- UTC times, returning
- getUTCHours method
ms.assetid: 7c9825dd-4b3a-4614-8e09-f40df123b630
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c47fe66e6eecb9e3aaa53f0d0988631062676d17
ms.sourcegitcommit: ba29e4d37db92ec784d4acf9c6e120cf0ea677e9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2018
---
# <a name="getutchours-method-date-javascript"></a>Метод getUTCHours (Date) (JavaScript)
Возвращает значение часов в `Date` с помощью общего скоординированного времени (UTC).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
dateObj.getUTCHours()   
```  
  
#### <a name="parameters"></a>Параметры  
 Обязательная ссылка `dateObj` — это объект `Date` .  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает целое число от 0 до 23, указывающее количество часов, истекших после полуночи. Если время, до 1:00:00, то возвращается ноль. Если `Date` объект был создан без указания времени, по умолчанию часа 0 в формате UTC. Это время может быть положительной других часовых поясов.  
  
## <a name="remarks"></a>Примечания  
 Чтобы получить количество часов, истекших после полуночи с помощью локального времени, используйте `getHours` метод.  
  
## <a name="example"></a>Пример  
 В следующем примере показано использование метода `getUTCHours`.  
  
```JavaScript  
var date = new Date("1/1/2001");  
document.write(date.getUTCHours());  
document.write("<br/>");  
  
var date2 = new Date("1/1/2001 11:22:33");  
document.write(date2.getUTCHours());  
  
// Output (in the PST time zone):  
// 15 
// 2  
```  
  
## <a name="requirements"></a>Требования  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Применимо к**: [Date Object](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>См. также  
 [Метод getHours (Date)](../../javascript/reference/gethours-method-date-javascript.md)   
 [Метод setHours (Date)](../../javascript/reference/sethours-method-date-javascript.md)   
 [Метод setUTCHours (Date)](../../javascript/reference/setutchours-method-date-javascript.md)

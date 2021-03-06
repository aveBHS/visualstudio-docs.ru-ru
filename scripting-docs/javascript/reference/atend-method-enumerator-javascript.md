---
title: "Метод atEnd (Enumerator) (JavaScript) | Документы Microsoft"
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
- atEnd
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- atEnd method
ms.assetid: 326808fb-9a0f-428e-aff1-b11b237913f1
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7b5097d00c11ffafc314264f134aedda3981c8e2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2017
---
# <a name="atend-method-enumerator-javascript"></a>Метод atEnd (Enumerator) (JavaScript)
Возвращает логическое значение, указывающее, находится ли перечислитель в конце коллекции.  
  
> [!WARNING]
>  Этот объект поддерживается только в Internet Explorer.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
myEnum.atEnd()  
```  
  
## <a name="remarks"></a>Примечания  
 Обязательная ссылка *myEnum* представляет собой любой объект `Enumerator` .  
  
 Метод `atEnd` возвращает значение **true** , если текущий элемент является последним в коллекции, если коллекция пустая или если текущий элемент не определен. В противном случае возвращается значение **false**.  
  
## <a name="example"></a>Пример  
 В следующем коде метод `atEnd` используется для определения, был ли достигнут конец списка дисков.  
  
```JavaScript  
function ShowDrives()  
{  
    var s = "";  
    var bytesPerGB = 1024 * 1024 * 1024;  
  
    var fso = new ActiveXObject("Scripting.FileSystemObject");  
    var e = new Enumerator(fso.Drives);  
  
    e.moveFirst();  
    while (e.atEnd() == false)  
    {  
        var drv = e.item();  
  
        s += drv.Path + " - ";  
  
        if (drv.IsReady)  
        {  
            var freeGB = drv.FreeSpace / bytesPerGB;  
            var totalGB = drv.TotalSize / bytesPerGB;  
  
            s += freeGB.toFixed(3) + " GB free of ";  
            s += totalGB.toFixed(3) + " GB";  
        }  
        else  
        {  
            s += "Not Ready";  
        }  
  
        s += "<br />";  
  
        e.moveNext();  
    }  
    return(s);  
}  
```  
  
## <a name="requirements"></a>Требования  
 Поддерживается в следующих режимах документов: случайный режим, стандартный режим Internet Explorer 6, стандартный режим Internet Explorer 7, стандартный режим Internet Explorer 8, стандартный режим Internet Explorer 9, стандартный режим Internet Explorer 10. Не поддерживается в приложениях [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] . См. [Сведения о версии](../../javascript/reference/javascript-version-information.md).  
  
 **Применимо к**: [Enumerator Object](../../javascript/reference/enumerator-object-javascript.md)  
  
## <a name="see-also"></a>См. также  
 [Метод Item (Enumerator)](../../javascript/reference/item-method-enumerator-javascript.md)   
 [Метод moveFirst (Enumerator)](../../javascript/reference/movefirst-method-enumerator-javascript.md)   
 [Метод moveNext (Enumerator)](../../javascript/reference/movenext-method-enumerator-javascript.md)   
 [Объект Enumerator](../../javascript/reference/enumerator-object-javascript.md)
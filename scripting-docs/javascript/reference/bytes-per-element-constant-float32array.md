---
title: "Константа BYTES_PER_ELEMENT (Float32Array) | Документы Microsoft"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: faaae7ad-fea5-420e-b8af-cc051cd9b06d
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a05f81b8b65e7966f14d711d195030f54b93b163
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2017
---
# <a name="bytesperelement-constant-float32array"></a>Константа BYTES_PER_ELEMENT (Float32Array)
Размер в байтах каждого элемента массива.  
  
## <a name="syntax"></a>Синтаксис  
  
```JavaScript  
var arraySize = int8Array.BYTES_PER_ELEMENT;  
```  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как получить размер элементов массива.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            var floatArr = new Float32Array(buffer.byteLength / 4);  
            alert(floatArr.BYTES_PER_ELEMENT);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Требования  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]
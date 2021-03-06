---
title: Просмотр значений регистра в отладчике Visual Studio | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.registers
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- registers, debugging
- register contents
- flags, Registers window
- register groups
- debugging [Visual Studio], Registers window
- Registers window
ms.assetid: 2918ffa2-562f-40d6-9053-ef321bbeb767
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7630ab56ef738febcf80058916272958e267a386
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="view-register-values-and-use-the-registers-window-in-the-visual-studio-debugger"></a>Просмотреть значения регистрации и использовать окно Регистры в отладчике Visual Studio
Окно "Регистры" доступно только в том случае, если включена отладка на уровне адреса в **параметры** диалоговом **Отладка** узел, **Общие** категории.  
  
 **Регистрирует** окне отображается содержимое регистров. Если вы решите оставить **регистрирует** окно открытым, так как при пошаговой отладке программы, можно увидеть изменение значений регистров по ходу выполнения. Значения, которые недавно изменились, отображаются красным цветом. Значения регистров можно изменять. Дополнительные сведения см. в разделе [как: изменение значения зарегистрировать](../debugger/how-to-edit-a-register-value.md).  
  
 Чтобы избежать загромождения, **регистрирует** регистры организованы по группам, которые зависят от платформы и процессора типа. При желании группы можно отображать или скрывать. Дополнительные сведения см. в разделе [как: отображение и скрытие групп регистров](../debugger/how-to-display-and-hide-register-groups.md).  
  
 Высокоуровневое введение в принципы использования регистров и окна регистров в разделе [основы отладки: окно Регистры](../debugger/debugging-basics-registers-window.md).  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](../ide/personalizing-the-visual-studio-ide.md).  
  
### <a name="to-display-the-registers-window"></a>Отображение окна регистров  
  
-   На **отладки** меню, выберите **Windows**, а затем выберите **регистрирует**.  
  
     Отладчик должен быть запущен либо находиться в режиме приостановки выполнения.  
  
    > [!NOTE]
    >  Для скриптов и приложений SQL сведения о регистрах недоступны.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об отладке: окно регистров](../debugger/debugging-basics-registers-window.md)   
 [Просмотр данных в отладчике](../debugger/viewing-data-in-the-debugger.md)   
 [Общие сведения об отладке: окно регистров](../debugger/debugging-basics-registers-window.md)
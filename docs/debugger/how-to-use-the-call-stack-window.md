---
title: Просмотр стека вызовов в отладчике Visual Studio | Документы Microsoft
ms.custom: H1Hack27Feb2017
ms.date: 04/06/2017
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.callstack
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
- SQL
- aspx
helpviewer_keywords:
- threading [Visual Studio], displaying calls to or from
- functions [debugger], viewing code on call stack
- disassembly code
- breakpoints, Call Stack window
- debugging [Visual Studio], switching to another stack frame
- debugging [Visual Studio], Call Stack window
- Call Stack window, viewing source code for functions on the call stack
- stack, switching stack frames
- Call Stack window, viewing disassembly code for functions on the call stack
ms.assetid: 5154a2a1-4729-4dbb-b675-db611a72a731
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d20a1ac9f1a09b93f577c6aa90f550ccd6ff0def
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="view-the-call-stack-and-use-the-call-stack-window-in-the-visual-studio-debugger"></a>Просмотр стека вызовов и использование окна стека вызова в отладчике Visual Studio

С помощью **стек вызовов** окна, можно просматривать вызовы функций и процедур, которые в данный момент в стеке. **Стек вызовов** окна показан порядок, в котором находятся вызван методы и функции. Стек вызовов является удобным способом проверки и понимать ход выполнения приложения.
  
Когда [символы отладки](#bkmk_symbols) недоступны для части стека вызовов, **стек вызовов** окна возможно не удастся отобразить правильные сведения об этой части стека вызовов. Если это происходит, появится следующая запись:  
  
`[Frames below may be incorrect and/or missing, no symbols loaded for name.dll]`

>  [!NOTE]
> **Стек вызовов** окна аналогична отладочной перспективы в некоторых интегрированных средах разработки, таких как Eclipse. 

> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных здесь в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите **Импорт и экспорт параметров** на **средства** меню.  В разделе [Персонализация среды IDE](../ide/personalizing-the-visual-studio-ide.md)
  
## <a name="view-the-call-stack-while-in-the-debugger"></a>Просмотр стека вызовов в отладчике 
  
-   Во время отладки в **отладки** последовательно выберите пункты **Windows > стек вызовов**.

 ![Окно стека вызовов](../debugger/media/dbg_basics_callstack_window.png "CallStackWindow")

Желтая стрелка указывает на кадр стека, в котором находится указатель выполнения. По умолчанию это фрейм стека, сведения которого отображаются в источнике, **локальные**, **видимые**, **Контрольные значения**, и **Дизассемблирование** windows . Если вы хотите изменить контекст отладчика на другой кадр стека, это можно сделать с [переключение на другой кадр стека](#bkmk_switch).   
  
## <a name="display-non-user-code-in-the-call-stack-window"></a>Отображение непользовательском коде в окне стека вызовов  
  
-   Щелкните правой кнопкой мыши **стек вызовов** и выберите **Показать внешний код**.

Не принадлежащий пользователю код — это любой код, который не отображается, когда [только мой код](../debugger/just-my-code.md) включен. В управляемом коде по умолчанию скрыты кадры непользовательском коде. Следующая запись отображается вместо кадры непользовательском коде:  
  
**[\<Внешнего кода >]**  
  
## <a name="bkmk_switch"></a> Переключиться в другой кадр стека (изменение контекста отладчика)
  
1.  В **стек вызовов** окно, щелкните правой кнопкой мыши кадр стека, код и данные которого нужно просмотреть.

    Или можно дважды щелкнуть кадр в **стек вызовов** окна Переключение выбранного кадра. 
  
2.  Выберите **перейти к кадру**.  
  
     Зеленая стрелка с фигурным концом появится рядом с выбранного фрейма стека. Указатель выполнения остается в исходном кадре, который по-прежнему отмечен желтой стрелкой. При выборе **шаг** или **Продолжить** из **отладки** меню, выполнение продолжается в исходном кадре, не с выбранного фрейма.  
  
## <a name="view-the-source-code-for-a-function-on-the-call-stack"></a>Просмотреть исходный код для функции в стеке вызовов  
  
-   В **стек вызовов** окно, щелкните правой кнопкой мыши функцию, исходный код которой нужно просмотреть и выберите **к исходному коду**.

## <a name="run-to-a-specific-function-from-the-call-stack-window"></a>Выполнение до определенной функции из окна "Стек вызовов"  
  
-  В **стек вызовов** окно, выберите функцию, щелкните правой кнопкой мыши и выберите **выполнить до текущей позиции**.  
  
## <a name="set-a-breakpoint-on-the-exit-point-of-a-function-call"></a>Установите точку останова в точке выхода вызова функции  
  
-   В разделе [установите точку останова в функции в стеке вызова](../debugger/using-breakpoints.md#BKMK_Set_a_breakpoint_in_the_call_stack_window).

## <a name="display-calls-to-or-from-another-thread"></a>Отобразить вызовы в или из другого потока  
  
-   Щелкните правой кнопкой мыши **стек вызовов** и выберите **включить вызовы между потоками**.   
  
## <a name="visually-trace-the-call-stack"></a>Визуального отслеживания стека вызовов  

При использовании Visual Studio Enterprise (только) можно просмотреть код карты для стека вызовов при отладке.

- В **стек вызовов** окна, откройте контекстное меню. Выберите **Показать стек вызовов на карте кода**. (Клавиатура: **CTRL** + **SHIFT** + **`**)  
  
    Дополнительные сведения см. в разделе [сопоставление методов в стеке вызовов при отладке](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md).

![Показать стек вызовов на карте кода](../debugger/media/dbg_basics_show_call_stack_on_code_map.gif "ShowCallStackOnCodeMap")
  
## <a name="view-the-disassembly-code-for-a-function-on-the-call-stack"></a>Просмотреть дизассемблированный код функции в стеке вызовов  
  
-   В **стек вызовов** окно, щелкните правой кнопкой мыши функцию, Дизассемблированный код которой нужно просмотреть и выберите **к дизассемблированному**.    

## <a name="change-the-optional-information-displayed"></a>Изменить отображение дополнительных сведений  
  
-   Щелкните правой кнопкой мыши **стек вызовов** окна "и" set "или" снимите флажок **Показать \< ***информацией, которая должна***>**.  
  
## <a name="bkmk_symbols"></a> Загрузить символы для модуля
В **стек вызовов** окна, можно загрузить символы для кода, который в данный момент нет загруженных символов отладки. Это могут быть символы платформы .NET Framework или системные символы, загруженные с общедоступных серверов символов корпорации Microsoft, или символы в каталоге символов на компьютере, на котором производится отладка.  
  
В разделе [укажите символов (.pdb) и исходных файлов](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)  
  
### <a name="to-load-symbols"></a>Чтобы загрузить символы  
  
1.  В **стек вызовов** окно, щелкните правой кнопкой мыши кадр стека для символы не загружены. Кадр затеняется.  
  
2.  Пункты **загрузить символы** и нажмите кнопку **серверы символов Майкрософт** (если он доступен) или укажите путь к символам.  
  
### <a name="to-set-the-symbol-path"></a>Установка пути к символам  
  
1.  В **стек вызовов** окно, выберите **параметры символов** в контекстном меню.  
  
     **Параметры** откроется диалоговое окно и **символы** -страница.  
  
2.  Нажмите кнопку **символов параметры**.  
  
3.  В **параметры** диалогового окна щелкните значок папки.  
  
     В **символов (PDB)** поле появится курсор.  
  
4.  Введите путь к каталогу с символами на компьютере, на котором производится отладка. Для локальной и удаленной отладки это путь на локальном компьютере.
  
5.  Нажмите кнопку **ОК**, чтобы закрыть диалоговое окно **Параметры**.  
  
## <a name="see-also"></a>См. также  
 [Смешанный код и отсутствующие данные в окне стека вызовов](../debugger/mixed-code-and-missing-information-in-the-call-stack-window.md)  
 [Просмотр данных в отладчике](../debugger/viewing-data-in-the-debugger.md)   
 [Укажите символов (.pdb) и исходных файлов](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)   
 [Использование точек останова](../debugger/using-breakpoints.md)
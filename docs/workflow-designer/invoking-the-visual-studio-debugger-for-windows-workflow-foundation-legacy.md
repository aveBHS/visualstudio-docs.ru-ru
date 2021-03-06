---
title: Конструктор рабочих процессов - вызова отладчика Visual Studio для Windows Workflow Foundation (для прежних версий)
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- stepping
- Step Over command
- stepping, commands
- debugging, using workflow debugger
- workflows, debugger
- workflow debugger, starting
- Step In command
- debugger, workflow
- Step Out command
- debugging workflows, starting the debugger
ms.assetid: d6f58e35-5cce-4ff2-9afc-b2d9d0f819cf
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a326f8b6dc482c2adfc2caba797c38094a99f8c5
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="invoking-the-visual-studio-debugger-for-windows-workflow-foundation-legacy"></a>Вызов отладчика Visual Studio для Windows Workflow Foundation (для прежних версий)

Описывается, как использовать отладчик Visual Studio для отладки приложений Windows Workflow Foundation (WF) в конструкторе рабочих процессов прежних версий Windows. Используйте конструктор рабочих процессов прежних версий, для целевой платформы .NET Framework 3.5 или WinFX.

Как правило, отладка рабочих процессов прежних версий аналогична отладке программ, написанных на других языках программирования Visual Studio. Visual Studio отладчик для Windows Workflow Foundation можно запустить одним из следующих способов:

-   Выберите **присоединиться к процессу** на **отладки** меню, чтобы выбрать выполняющийся рабочий процесс из числа доступных процессов.

-   Нажмите клавишу **F5** будет запущен экземпляр рабочего процесса или продолжить выполнение после попадания точки останова.

## <a name="stepping-through-code"></a>Пошаговая отладка

Отладчик поддерживает одну из самых характерных процедур отладки - отладку по шагам, которая представляет собой построчное выполнение кода. Для пошаговой отладки кода существует три команды:

-   **Шаг с заходом**: можно выполнить пошаговую отладку действия с помощью **F11**. Отладчик выполняет пошаговую отладку всех заданных обработчиков. Если обработчики не заданы, то действие пропускается, а в случае составного действия, которое содержит другие действия, выполняется вход в первое выполняющееся действие. Пошаговое выполнение кода отладчиков из конструктора не поддерживается для следующих операций: **IfElseActivity**, **у операции WhileActivity**, **ConditionedActivityGroup**, или **ReplicatorActivity**. Для отладки отладчиков, связанных с этими действиями, необходимо указать в коде явные точки останова.

-   **Шаг с выходом**: можно выйти действия с помощью **Shift-F11**. Выход из пошаговой отладки действия запускает текущее действие и все родственные действия на выполнение до завершения. Далее отладчик прерывается на текущем родительском объекте действия. При выходе из пошаговой отладки из кода обработчика, отладчик прерывается на действии, с которым связан обработчик.

-   **Шаг с обходом**: можно пропустить действия с помощью **F10**. При обходе составного действия. отладчик прерывается на первом исполняемом дочернем объекте составного действия. При обходе не являющиеся составными, таких как **CodeActivity** действия, отладчик выполняет действие и связанные с ним обработчики и прерывается на следующем действии. Если выполняемое действие является последним дочерним действием в составном действии, то после выполнения отладчик прерывается на родительском действии.

## <a name="attaching-to-a-process"></a>Присоединение к процессу.
 Отладку рабочих процессов путем присоединения к процессу, выберите доступный процесс из **доступные процессы** списка в **присоединиться к процессу** диалоговое окно. Если **автоматического: код рабочего процесса** не отображается в **присоединить** текста, а затем нажмите кнопку **выберите**. В **Выбор типа кода** диалоговое окно, нажмите кнопку **отладить код следующих типов** и выберите **рабочего процесса**. Нажмите кнопку **ОК** и нажмите кнопку **присоединение**.

## <a name="debugging-with-f5"></a>Отладка по клавише F5
 Если ведущее приложение рабочего процесса и библиотека DLL рабочего процесса расположены в различных проектах Visual Studio, например, при использовании библиотеки действий, необходимо задать проект библиотеки DLL рабочего процесса как автозагружаемый проект решения Visual Studio для отладки рабочего процесса с помощью **F5**. Также необходимо задать путь к ведущему приложению в проект библиотеки DLL рабочего процесса **запуск внешней программы** свойство.

 Чтобы установить запускаемый проект в обозревателе решений, щелкните правой кнопкой мыши имя проекта и выберите **Назначить запускаемым проектом**. Чтобы задать путь к узлу в **запуск внешней программы** свойств, дважды щелкните файл проекта рабочего процесса **свойства** узел в обозревателе решений и выберите **Отладка** на вкладке. В разделе **действие при запуске**выберите **запуск внешней программы** и введите путь к файлу .exe, на котором размещается рабочий процесс, который требуется отладить.

 Если ведущее приложение задано как автозагружаемый проект, для отладки; вызывается только отладчик Visual Studio Visual Studio отладчик для Windows Workflow Foundation не вызывается. Если используется отладчик Visual Studio, то попадание будет производится только в точки останова кода C# или Visual Basic; в точки останова, заданные в конструкторе рабочих процессов, попадание не выполняется. Например, точки останова, установленного на <xref:System.Workflow.Activities.ParallelActivity> действия в конструкторе срабатывает, если используется Visual Studio отладчик для Windows Workflow Foundation, но не при использовании отладчика Visual Studio.

## <a name="see-also"></a>См. также

- [Как задать точки останова в рабочих процессах (для прежних версий)](../workflow-designer/how-to-set-breakpoints-in-workflows-legacy.md)
- [Отладка рабочих процессов прежних версий](../workflow-designer/debugging-legacy-workflows.md)
---
title: Советы по повышению продуктивности при работе в Visual Studio
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 2aaa32de4742d5c3897ec2290e77223b0d6cdd56
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34752667"
---
# <a name="productivity-tips-for-visual-studio"></a>Советы по повышению продуктивности при работе в Visual Studio

Эта статья содержит рекомендации, которые помогут вам быстрее и эффективнее создавать, изучать и отлаживать код.

Сведения о распространенных сочетаниях клавиш вы найдете в [этом списке советов](../ide/tips-and-tricks-for-visual-studio.md). Полный список сочетаний клавиш см. в статьях [Определение и настройка сочетаний клавиш](../ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio.md) и [Сочетания клавиш по умолчанию](../ide/default-keyboard-shortcuts-in-visual-studio.md).

## <a name="write-code"></a>Написание кода

Следующие возможности позволяют быстрее разрабатывать код.

- **Используйте удобные команды**. Visual Studio поддерживает разные команды, позволяющие быстрее выполнять стандартные задачи по редактированию кода. Например, **Visual Studio 2017 версии 15.6** и выше позволяет вызвать команду быстрого дублирования строки кода. При этом вам не нужно копировать строку в буфер, перемещать курсор и выполнять вставку. Выберите **Изменить** > **Дублировать** или нажмите клавиши **CTRL**+**E**,**V**. Вы также можно быстро развернуть или свернуть выделенный текст с помощью пунктов меню **Изменить** > **Дополнительно** > **Развернуть выделенный фрагмент** или **Изменить** > **Дополнительно** > **Сжать выделенный фрагмент** или клавиш **SHIFT**+**ALT**+**=** или **SHIFT**+**ALT**+**-** (в **Visual Studio 2017 версии 15.5** и выше).

- **Использование IntelliSense**. При вводе кода в редакторе отображаются данные IntelliSense, например элементы списков, сведения о параметрах, краткие сведения, справка по сигнатурам и завершение слов. Эти возможности поддерживают нечеткое соответствие текста; например, результаты для списков членов включают не только элементы, которые начинаются с введенных символов, но и элементы, содержащие это сочетание символов где-либо внутри своих имен. Дополнительные сведения см. в статье [Использование IntelliSense](../ide/using-intellisense.md).

- **Изменение параметров автоматической вставки IntelliSense при вводе кода**. Переключив IntelliSense в режим предложений, вы можете настроить IntelliSense таким образом, чтобы предлагаемые варианты вставлялись только в случае их явного выбора.

     Чтобы включить режим предложений, нажмите клавиши **CTRL**+**ALT**+**ПРОБЕЛ** или в строке меню выберите **Правка** > **IntelliSense** > **Переключить режим завершения**.

- **Использование фрагментов кода**. Вы можете использовать встроенные фрагменты кода или создавать собственные.

     Чтобы вставить фрагмент, в строке меню выберите **Правка** > **IntelliSense** > **Вставить фрагмент** или **Разместить во фрагменте** либо в любом месте файла откройте контекстное меню и выберите **Фрагмент** > **Вставить фрагмент** или **Разместить во фрагменте**. Дополнительные сведения см. в статье [Фрагменты кода](../ide/code-snippets.md).

- **Использование встроенных функций исправления ошибок в коде**. Быстрые действия позволяют легко создавать и изменять код, а также выполнять его рефакторинг одним действием. Эти действия можно применять, используя значок отвертки ![значок отвертки](media/screwdriver-icon.png), значок лампочки ![значок лампочки](media/light-bulb-icon.png) или сочетание клавиш **ALT**+**ENTER** или **CTRL**+**.** когда курсор находится на подходящей строке кода. Дополнительные сведения см. в разделе [Быстрые действия](quick-actions.md).

- **Отображение и изменение определений элементов кода**. Вы можете быстро отобразить и изменить модуль, в котором определен элемент кода, например член, переменная или локальный объект.

    Чтобы открыть определение во всплывающем окне, выделите элемент и нажмите клавиши **ALT**+**F12** или откройте контекстное меню для этого элемента и выберите пункт **Показать определение**. Чтобы открыть определение в отдельном окне с кодом, откройте контекстное меню элемента кода, а затем выберите команду **Перейти к определению**.

- **Использование примеров приложений**. Разработку приложений можно ускорить, скачав и установив примеры приложений из коллекции кода [MSDN](https://code.msdn.microsoft.com/). Кроме того, вы можете изучить ту или иную технологию или концепцию программирования, загрузив и изучив пакет примеров для этой области.

## <a name="navigate-within-your-code"></a>Перемещение по коду

 Существует множество способов быстрого поиска нужных мест в коде и перехода к этим местам.

- **Создание закладок для строк кода**. Для быстрого перехода к определенным строкам кода в файле можно использовать закладки.

    Чтобы установить закладку, в строке меню выберите **Правка** > **Закладки** > **Переключить закладку**. Все закладки в решении можно просматривать в окне **Закладки**. Дополнительные сведения см. в разделе [Установка закладок в коде](../ide/setting-bookmarks-in-code.md).

- **Поиск определений символов в файле**. Чтобы найти определения символов и имена файлов, можно выполнить поиск по решению, но результаты поиска не будут содержать пространств имен и локальных переменных.

   Для доступа к этой возможности выберите в строке меню **Правка** > **Перейти к**.

- **Просмотр общей структуры кода**. В **обозревателе решений** можно выполнять поиск и просматривать имеющиеся в проектах классы, их типы и члены. Можно также выполнять поиск символов, просматривать иерархию вызовов методов, находить ссылки на символы и выполнять другие задачи. Если выбрать элемент кода в **обозревателе решений**, связанный файл будет открыт на вкладке **Предварительный просмотр**, а курсор перемещен к элементу в файле. Дополнительные сведения см. в разделе [Просмотр структуры кода](../ide/viewing-the-structure-of-code.md).

## <a name="find-items-faster"></a>Ускоренный поиск нужных элементов

В интегрированной среде разработки можно выполнять поиск нужных команд, файлов и параметров, а также фильтровать содержимое окна инструментов для отображения только информации, необходимой для текущей задачи.

- **Фильтрация содержимого окна инструментов**. Вы можете выполнять поиск по содержимому различных окон инструментов, например **Панель элементов**, окно **Свойства** и **Обозреватель решений**, но отображать только те элементы, имена которых содержат искомые символы.

- **Отображение только тех ошибок, которые необходимо устранить**. При нажатии кнопки **Фильтр** на панели инструментов **Список ошибок** можно уменьшить количество ошибок, отображаемых в окне **Список ошибок**. Можно отображать только ошибки в файлах, открытых в редакторе, только ошибки в текущем файле или только ошибки в текущем проекте. Кроме того, можно выполнять поиск в окне **Список ошибок**, чтобы находить конкретные ошибки.

- **Поиск диалоговых окон, команд меню и параметров**. В окне [Быстрый запуск](../ide/reference/quick-launch-environment-options-dialog-box.md) введите ключевые слова или фразы, относящиеся к элементам, которые нужно найти. Например, при вводе запроса `new project` отображаются следующие результаты:

    ![Результаты быстрого запуска для нового проекта](../ide/media/productivity_quicklaunch.png)

    Панель **Быстрый запуск**, помимо прочего, содержит ссылки на диалоговое окно **Создание проекта**, диалоговое окно **Добавление нового элемента** и страницу **Проекты и решения** в диалоговом окне **Параметры**. Результаты на панели быстрого запуска также могут содержать файлы проектов и окна инструментов.

## <a name="debug-code"></a>Отладка кода

Отладка может занимать немало времени, но следующие советы помогут ускорить процесс.

- **Тестирование одних и тех же страниц, приложений и сайтов в различных браузерах**. В процессе отладки кода можно легко переключаться между установленными веб-браузерами, включая [инспектор страниц (Visual Studio)](http://msdn.microsoft.com/Library/65880969-1ad2-47be-85b9-bb12c81bf209), без необходимости открытия диалогового окна **Просмотр с помощью**. С помощью списка **Целевой объект отладки**, расположенного на панели инструментов **Стандартная** рядом с кнопкой **Начать отладку**, можно быстро узнать, какой именно браузер используется для отладки и просмотра страниц.

    ![Выбор параметров отладки веб-браузера](../ide/media/webbrowserdropdowntoolbar.png)

- **Установка временных точек останова**. Вы можете создать временную точку останова в текущей строке кода и одновременно запустить отладчик. При достижении этой строки кода отладчик входит в режим приостановки выполнения. Дополнительные сведения см. в статье [Навигация по коду с помощью отладчика](../debugger/navigating-through-code-with-the-debugger.md).

    Для использования этой возможности нажмите сочетание клавиш **CTRL**+**F10** или откройте контекстное меню строки кода, на которой требуется прервать выполнение, и выберите команду **Выполнить до текущей позиции**.

- **Перемещение точки выполнения во время отладки**. Вы можете переместить текущую точку выполнения в другой раздел кода и перезапустить отладку с этой точки. Этим приемом удобно пользоваться, если необходимо выполнить отладку раздела кода без повторного создания всех шагов, необходимых для достижения этого раздела. Дополнительные сведения см. в статье [Навигация по коду с помощью отладчика](../debugger/navigating-through-code-with-the-debugger.md).

     Чтобы переместить точку выполнения, перетащите желтую стрелку в место, где нужно задать следующий оператор в том же файле исходного кода, а затем нажмите **F5**, чтобы продолжить отладку.

- **Запись информации о значениях переменных**. К переменной в коде можно добавить подсказу по данным и прикрепить ее, чтобы легко узнать последнее значение этой переменной после завершения отладки. Дополнительные сведения см. в статье [Просмотр значений данных в подсказках по данным](../debugger/view-data-values-in-data-tips-in-the-code-editor.md).

     Для добавления подсказки по данным отладчик должен находиться в режиме приостановки. Поместите курсор на переменную, а затем нажмите кнопку закрепления в появившейся подсказке по данным. При остановке отладки в исходном файле рядом со строкой кода, которая содержит переменную, отображается значок синей булавки. При наведении указателя мыши на синюю булавку появляется значение переменной из последнего сеанса отладки.

- **Очистка окна интерпретации**. Содержимое [окна интерпретации](../ide/reference/immediate-window.md) можно очистить во время разработки, введя `>cls` или `>Edit.ClearAll`.

     Дополнительные сведения о дополнительных командах см. в статье [Псевдонимы команд Visual Studio](../ide/reference/visual-studio-command-aliases.md).

## <a name="access-visual-studio-tools"></a>Доступ к инструментам Visual Studio

Вы сможете быстро переходить к командной строке разработчика и другим инструментам Visual Studio, если закрепите их на начальном экране или на панели задач.

1. В проводнике перейдите в расположение `%ProgramData%\Microsoft\Windows\Start Menu\Programs\Visual Studio 2017\Visual Studio Tools`.

1. Откройте контекстное меню **командной строки разработчика**, а затем выберите **Закрепить на начальном экране** или **Закрепить на панели задач**.

## <a name="manage-files-toolbars-and-windows"></a>Управление файлами, панелями инструментов и окнами

В процессе разработки приложения можно одновременно работать в нескольких файлах кода и перемещаться между несколькими окнами инструментов. Чтобы держать все окна и инструменты в порядке, следуйте приведенным ниже советам.

- **Оставляйте файлы, которые используются часто, видимыми в редакторе**. Можно закрепить файлы в левой части набора вкладок, чтобы они оставались видимыми независимо от того, сколько файлов открыто в редакторе.

     Чтобы закрепить файл, выберите вкладку файла, а затем нажмите кнопку **Закрепить/открепить**.

- **Переместите документы и окна на другие мониторы**. Если при разработке приложения используется несколько мониторов, можно более эффективно работать над отдельными частями приложения, перемещая открытые в редакторе файлы на другой монитор. Можно также перемещать окна инструментов, например окна отладчика, на другой монитор и закреплять окна документов вместе с окнами инструментов с помощью вкладок для создания блоков. Дополнительные сведения см. в статье [Настройка макетов окон в Visual Studio](../ide/customizing-window-layouts-in-visual-studio.md).

     Для более эффективного управления файлами можно создать новый экземпляр **обозревателя решений** и переместить его на другой монитор. Чтобы создать еще один экземпляр **обозревателя решений**, откройте контекстное меню в **обозревателе решений** и выберите команду **Создать представление обозревателя решений**.

- **Настройка шрифтов, отображаемых в Visual Studio**. Вы можете изменять начертания, размеры и цвета шрифтов, используемых для текста в интегрированной среде разработки. Например, можно задать цвета определенных элементов кода в редакторе и начертание шрифта в отдельных окнах инструментов или во всей интегрированной среде разработки. Дополнительные сведения см. в статьях [Практическое руководство. Изменение шрифтов и цветов](../ide/how-to-change-fonts-and-colors-in-visual-studio.md) и [Практическое руководство: изменение шрифтов и цветов](../ide/reference/how-to-change-fonts-and-colors-in-the-editor.md).

## <a name="see-also"></a>См. также

- [Сочетания клавиш по умолчанию для часто используемых команд](../ide/default-keyboard-shortcuts-for-frequently-used-commands-in-visual-studio.md)
- [Практическое руководство. Настройка меню и панелей инструментов](../ide/how-to-customize-menus-and-toolbars-in-visual-studio.md)
- [Пошаговое руководство. Создание простого приложения](../ide/walkthrough-create-a-simple-application-with-visual-csharp-or-visual-basic.md)
- [Специальные возможности. Советы и рекомендации](../ide/reference/accessibility-tips-and-tricks.md)
---
title: Представление модели содержимого конструктора схемы XML
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: reference
ms.assetid: e8db7c7d-31cf-479e-9dcc-299759891795
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0d7f04c482149cbc063a3788dd6be44c643bae6a
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34751797"
---
# <a name="content-model-view"></a>Представление модели содержимого

Представление модели содержимого предоставляет графическое представление сведений о локальных и глобальных узлах схемы и их компонентах, включая простые и сложные типы, элементы, группы моделей, атрибуты и группы атрибутов. XML-комментарии и инструкции по обработке нельзя просматривать в представлении модели содержимого. Представление модели содержимого содержит две панели: **рабочей** панель, которая содержит список узлов в [рабочей области конструктора схем XML](../xml-tools/xml-schema-designer-workspace.md)и в области конструктора, где можно просмотреть схемы содержимого модели узлы, выбранные в **рабочей** панель. Представление модели содержимого также включает панель инструментов конструктора XML-схем и строку навигатора.

 На следующем рисунке **рабочей** панель содержит шесть узлов схемы. `purchaseOrder` Узел выбран **рабочей** панели и отображается в области конструктора.

 ![Представление модели содержимого конструктора схемы XML](../xml-tools/media/xsddesigner_contentmodelview.gif)

## <a name="workspace-panel"></a>Панели рабочей области

 После добавления узлов в рабочую область, отображается список узлов **рабочей** панель представления модели содержимого. При выборе узлов в **рабочей** панели, они отображаются в области конструктора представления модели содержимого. Чтобы удалить узлы из рабочей области, используйте панель инструментов конструктора XSD **рабочей** панель контекстного меню или **удалить** ключа.

 Сведения о добавлении узлов см. в разделе «Добавление узлов в рабочую область» [рабочей области конструктора схем XML](../xml-tools/xml-schema-designer-workspace.md).

## <a name="design-surface"></a>Область конструктора

 При выборе узла в **рабочей** панель, он добавляется в область конструктора представления модели содержимого, где можно просмотреть сведения узла.

 Модель содержимого узла представлена разворачиваемым графическим деревом с элементами и атрибутами, являющимися узлами дерева. По умолчанию развернут только один уровень. Дополнительные сведения, такие как компоновщики, имена типов, группы и другие контейнеры находятся в вертикальной панели (в развернутом состоянии) вместе с элементами и атрибутами, входящими в них. Если дважды щелкнуть вертикальную панель, она станет горизонтальной, а дерево будет свернуто. Если дважды щелкнуть горизонтальную панель, она станет вертикальной, а дерево будет развернуто. Выбор вертикальной панели выбирает все узлы в контейнере. Расширитель отображаются справа от узла, если элемент можно разворачивать и сворачивать.

 Если область конструктора пуста, редактор XML **обозреватель XML-схем**, и отображаются водяного знака. *Водяного знака* приведен список ссылок на все представления конструктора XSD. Если набор схем содержит ошибки, в конце списка появится следующий текст: «Воспользуйтесь списком ошибок для просмотра и устранения ошибок в наборе».

## <a name="breadcrumb-bar"></a>Строка навигатора

 Строка навигатора внизу представления модели содержимого показывает местоположение выбранного узла в наборе схем.

## <a name="context-menus"></a>Контекстные меню

 При щелчке правой кнопкой мыши элемент в области конструктора или **рабочей** панели, то появится контекстное меню. В следующей таблице приведены параметры, доступные для области конструктора представления модели содержимого.

|Параметр|Описание:|
|------------|-----------------|
|**Показать в обозревателе XML-схем**|Устанавливает фокус на обозревателе схем и выделяет узел набора схем.|
|**Показать в представлении графика**|Переключается в представление графика.|
|**Создание образца XML**|Этот метод предусмотрен только для глобальных элементов. Создает образец XML-файла для глобального элемента.|
|**Показать документацию**|Показывает или скрывает содержимое узла «Заметка/Документация».|
|**Экспортировать схему как рисунок**|Сохраняет область конструктора в XPS-файле.|
|**Просмотр кода**|Открывает в редакторе XML-файл, содержащий выбранный узел. Элемент, который выбран в **обозреватель XML-схем** также будет выделен в редакторе XML.|
|**Окно "Свойства"**|Открывает **свойства** окна (если он еще не открыт). В данном окне будут выведены сведения об узле.|

 В следующей таблице описаны параметры, доступные для **рабочей** панель.

|Параметр|Описание:|
|------------|-----------------|
|**Показать в обозревателе XML-схем**|Устанавливает фокус на обозревателе схем и выделяет узел набора схем.|
|**Показать в представлении графика**|Переключается в представление графика.|
|**Очистить рабочую область**|Очищает рабочую область и область конструктора.|
|**Удалить из рабочей области**|Удаляет выбранные узлы из рабочей области и из области конструктора.|
|**Удалите все, кроме выделенных в рабочей области**|Удаляет узлы, не выделенные в рабочей области и в области конструктора.|
|**Создание образца XML**|Этот метод предусмотрен только для глобальных элементов. Создает образец XML-файла для глобального элемента.|
|**Выбрать все**|Выбирает все узлы в **рабочей** панель.|
|**Просмотр кода**|Открывает в редакторе XML-файл, содержащий выбранный узел. Элемент, который выбран в **обозреватель XML-схем** также будет выделен в редакторе XML.|
|**Окно "Свойства"**|Открывает **свойства** окна (если он еще не открыт). В данном окне будут выведены сведения об узле.|

## <a name="properties-window"></a>Окно \"Свойства\"

 Использование контекстного меню, чтобы открыть **свойства** окна. По умолчанию **свойства** отображается в правом нижнем углу Visual Studio. При нажатии на узел, который отображается в представлении модели содержимого, свойства данного узла отображаются в **свойства** окна.

## <a name="xsd-designer-toolbar"></a>Панель инструментов конструктора XSD

 Следующие кнопки панели инструментов конструктора XSD включены, если активно представление модели содержимого.

 ![Панель инструментов конструктора схемы XML.](../xml-tools/media/xsdcontentmodelviewtoolbar.gif)

|Параметр|Описание:|
|------------|-----------------|
|**Показать начальное представление**|Переключается в [, откройте представление](../xml-tools/start-view.md). Это представление может осуществляться с помощью сочетания клавиш: **Ctrl**+**1**.|
|**Показать представление модели содержимого**|Переключается в [представление модели содержимого](../xml-tools/content-model-view.md). Это представление может осуществляться с помощью сочетания клавиш: **Ctrl**+**2**.|
|**Показать представление графика**|Переключается в [графическое представление](../xml-tools/graph-view.md). Это представление может осуществляться с помощью сочетания клавиш: **Ctrl**+**3**.|
|**Очистить рабочую область**|Очищает рабочую область и область конструктора.|
|**Удалить из рабочей области**|Удаляет выбранные узлы из рабочей области и из области конструктора.|
|**Удалите все, кроме выделенных в рабочей области**|Удаляет узлы, не выделенные в рабочей области и в области конструктора.|
|**Показать документацию**|Показывает или скрывает содержимое узла «Заметка/Документация».|

## <a name="panscroll"></a>Панорамирование/Прокрутка

 Панорамный обзор рабочей области конструктора с помощью полосы прокрутки или удерживая **Ctrl** ключа щелкните и перетащите указатель мыши. При панорамировании области конструктора с использованием перетаскивания, курсор превращается в четырех стрелок, указывающих в четыре разных направления.

## <a name="undoredo"></a>Отменить/Повторить

 Возможность «отменить/повторить» включена в представлении модели содержимого для следующих действий:

-   Добавление одного узла посредством перетаскивания.

-   Добавление нескольких узлов из окна результатов поиска в обозревателе схемы.

-   Добавление узлов из начального представления.

-   Удаление одного или нескольких узлов.

## <a name="zoom"></a>Масштаб

 Масштабирование доступно в правом нижнем углу представления модели содержимого.

 Масштабированием можно управлять следующими способами:

-   Удерживая **Ctrl** wheel ключ и прокручивая мыши при наведении указателя мыши на область представления модели содержимого.

-   Используя ползунковый элемент управления. Ползунок отображает текущий масштаб.

Ползунок масштаба является непрозрачным, если выбрать его, наведите на него или используйте **Ctrl** колесиком мыши для увеличения масштаба; в других случаях он является прозрачным.

## <a name="xml-editor-integration"></a>Интеграция редактора XML

 Можно переключиться назад и вперед между **конструктора XSD** и редактором XML с помощью контекстного меню.

 При внесении изменений в схему, заданная в редакторе XML, изменения будут синхронизированы в представлении модели содержимого. Дополнительные сведения см. в разделе [интегрирован с редактором XML](../xml-tools/integration-with-xml-editor.md).

## <a name="see-also"></a>См. также

- [Рабочая область конструктора XML-схем](../xml-tools/xml-schema-designer-workspace.md)
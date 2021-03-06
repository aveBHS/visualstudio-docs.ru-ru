---
title: Создайте параметризованные запросы адаптера таблицы
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data [Visual Studio], TableAdapters
- TableAdapters, parameterized queries
- data [Visual Studio], searching data
- queries [Visual Studio], creating
- TableAdapters, searching data
- queries [Visual Studio], TableAdapters
ms.assetid: 104d1d19-b5a9-4071-b81e-1b3af08e9c7b
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 7d3985cc8faf76c5c5767090abd5b87101ddbb45
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="create-parameterized-tableadapter-queries"></a>Создайте параметризованные запросы адаптера таблицы
Параметризированный запрос возвращает данные, удовлетворяющие условиям предложения WHERE в запросе. Например, можно параметризировать список клиентов, чтобы отображать только клиентов из определенного города, добавив `WHERE City = @City` в конец инструкции SQL, возвращающей список клиентов.

 Создайте параметризованные запросы адаптера таблицы в **конструктора наборов данных**. Их также можно создать в приложении Windows с **параметризация источника данных** на **данные** меню. **Параметризация источника данных** команда создает элементы управления формы, где ввода значений параметров и выполнения запроса.

> [!NOTE]
> При создании параметризованного запроса, используйте нотацию параметров, относящиеся к базе данных, разработки по. Например, источники данных Access и OleDb используют вопросительный знак "?" для обозначения параметров, поэтому предложение WHERE должно иметь следующий вид: `WHERE City = ?`.

> [!NOTE]
> Диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска, которую вы используете. Чтобы изменить параметры, перейдите на **средства** и выбрать пункт **Импорт и экспорт параметров**. Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](../ide/personalizing-the-visual-studio-ide.md).

## <a name="create-a-parameterized-tableadapter-query"></a>Создание параметризованного запроса адаптера таблицы

#### <a name="to-create-a-parameterized-query-in-the-dataset-designer"></a>Порядок создания параметризованного запроса в Конструкторе наборов данных

-   Создайте новый адаптер таблицы, добавив предложение WHERE с требуемыми параметрами в инструкцию SQL. Дополнительные сведения см. в разделе [создайте и настройте адаптеры таблиц TableAdapter](../data-tools/create-and-configure-tableadapters.md).

     - или -

-   Добавьте запрос в существующий адаптер таблицы, добавив предложение WHERE с требуемыми параметрами в инструкцию SQL.

#### <a name="to-create-a-parameterized-query-while-designing-a-data-bound-form"></a>Порядок создания параметризованного запроса при разработке формы с привязкой к данным

1.  Выберите на форме элемент управления, который уже привязан к набору данных. Дополнительные сведения см. в разделе [элементы управления Windows Forms, привязка к данным в Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md).

2.  На **данные** последовательно выберите пункты **добавить запрос**.

3.  Завершить **Построитель условий поиска** диалоговом, добавив предложение WHERE с требуемыми параметрами в инструкцию SQL.

### <a name="to-add-a-query-to-an-existing-data-bound-form"></a>Добавление запроса в существующую форму с привязкой к данным

1.  Откройте форму в **конструктор Windows Forms**.

2.  На **данные** последовательно выберите пункты **добавить запрос** или **данные смарт-тега**.

    > [!NOTE]
    >  Если **добавить запрос** не доступен на **данные** меню, выберите элемент управления в форме, отображающий тот источник данных вы хотите добавить параметризацию. Например, если форма отображает данные в элементе управления <xref:System.Windows.Forms.DataGridView>, выберите его. Если форма отображает данные в отдельных элементах управления, выберите любой элемент управления с привязкой к данным.

3.  В **таблицы источника данных выберите** области, выберите таблицу, которую требуется добавить параметризацию.

4.  Введите имя в **имя нового запроса** поле при создании нового запроса.

     - или -

     Выделите запрос в **имя существующего запроса** поле.

5.  В **текст запроса** введите запрос, который принимает параметры.

6.  Нажмите кнопку **ОК**.

     Элемент управления для ввода параметра, а также **нагрузки** кнопки добавляются на форму в <xref:System.Windows.Forms.ToolStrip> элемента управления.

#### <a name="querying-for-null-values"></a>Запрос значения null
Параметры адаптера таблицы можно назначить значения null, если вы хотите запросить для записей, которые не имеют текущего значения. Например, рассмотрим следующий запрос, который имеет `ShippedDate` параметр в его `WHERE` предложения:

 ```sql
SELECT CustomerID, OrderDate, ShippedDate
FROM Orders
WHERE (ShippedDate = @ShippedDate) OR (ShippedDate IS NULL)
```

 Если бы это был по запросу, может запрашивать всех заказов, которые не были отправлены с помощью следующего кода:

 [!code-csharp[VbRaddataTableAdapters#8](../data-tools/codesnippet/CSharp/create-parameterized-tableadapter-queries_1.cs)]
 [!code-vb[VbRaddataTableAdapters#8](../data-tools/codesnippet/VisualBasic/create-parameterized-tableadapter-queries_1.vb)]

 Чтобы включить запрос, чтобы принимать значения null:

1.  В **конструктора наборов данных**, выберите запрос TableAdapter, который должен принимать значения null для параметров.

2.  В **свойства** выберите **параметры**, нажмите кнопку с многоточием (**...** ) кнопку, чтобы открыть **редактор коллекции параметров**.

3.  Выберите параметр, который допускает значения null и задайте **AllowDbNull** свойства `true`.

## <a name="see-also"></a>См. также

- [Заполнение наборов данных с помощью адаптера таблицы](../data-tools/fill-datasets-by-using-tableadapters.md)
---
title: "Как: создать XML-фрагмент из XML-схемы | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2c128d2a-aaa6-4814-aa95-e07056afe338
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 1090d1509152aaa507220d3119977bb8e9252876
ms.sourcegitcommit: c0422a3d594ea5ae8fc03f1aee684b04f417522e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/02/2017
---
# <a name="how-to-generate-an-xml-snippet-from-an-xml-schema"></a>Как создать XML-фрагмент из XML-схемы
Редактор XML может создавать XML-фрагменты из схемы на языке XSD. Например, во время работы с XML-файлом, если курсор находится сразу после имени элемента, можно нажать клавишу TAB, чтобы заполнить элемент XML-данными, созданными на основе информации схемы для этого элемента.  
  
 Эта функция доступна только для элементов. При этом действуют следующие правила.  
  
-   Элемент должен иметь схему связанного с ним типа, то есть элемент должен быть правильным согласно какой-либо связанной схеме. Тип схемы не может быть абстрактным и должен содержать необходимые атрибуты или необходимые дочерние элементы.  
  
-   Текущий элемент в редакторе должен быть пустым, не имеющим атрибутов. Например, все приведенные ниже элементы являются правильными.  
  
    -   `<Account`  
  
    -   `<Account>`  
  
    -   `<Account></Account>`  
  
-   Курсор должен находиться непосредственно справа от имени элемента.  
  
Созданный фрагмент содержит все необходимые атрибуты и элементы. Если значение `minOccurs` больше единицы, во фрагмент включается необходимое минимальное количество экземпляров этого элемента. Максимум составляет 100 экземпляров. Любые фиксированные значения, обнаруженные в схеме, становятся фиксированными значениями во фрагменте. Элементы `xsd:any` и `xsd:anyAttribute` не учитываются и не увеличивают конструкцию фрагмента.  
  
Значения по умолчанию создаются и помечаются как редактируемые значения. Если в схеме указано значение по умолчанию, используется это значение. Но если в схеме значением по умолчанию является пустая строка, редактор создает значения по умолчанию следующим образом.  
  
-   Если тип схемы содержит аспекты перечисления, заданные прямо или косвенно с помощью любого из членов типа объединения, то по умолчанию используется первое перечисляемое значение, найденное в модели объектов схемы.  
  
-   Если тип схемы является атомарным, редактор получает атомарный тип и вставляет имя атомарного типа. Для производного простого типа используется базовый простой тип. Для типа списка в качестве типа `itemType` используется атомарный тип. Атомарным типом для объединения является атомарный тип первого типа `memberType`.  
  
## <a name="example"></a>Пример  
 Шаги в этом разделе показывают, как использовать в редакторе XML функцию создания XML-фрагментов из схемы.  
  
> [!NOTE]
>  Прежде чем приступать к этим процедурам, сохраните файл схемы на локальном компьютере.  
  
#### <a name="to-create-a-new-xml-file-and-associate-it-with-an-xml-schema"></a>Создание нового XML-файла и связывание его со схемой XML  
  
1.  На **файл** последовательно выберите пункты **New**и нажмите кнопку **файл**.  
  
2.  Выберите **XML-файл** в **шаблоны** панели и нажмите **откройте**.  
  
     Новый файл открывается в редакторе. Этот файл содержит XML-декларацию по умолчанию: `<?xml version="1.0" encoding="utf-8">`.  
  
3.  В окне свойств документа нажмите кнопку обзора (**...** ) на **схемы** поля.  
  
     **XSD-схемы** диалоговое окно.  
  
4.  Нажмите кнопку **Добавить**.  
  
     **Открытие XSD-схемы** диалоговое окно.  
  
5.  Выберите файл схемы и нажмите кнопку **откройте**.  
  
6.  Нажмите кнопку **ОК**.  
  
     Теперь с XML-документом связана XML-схема.  
  
#### <a name="to-generate-an-xml-snippet"></a>Создание XML-фрагмента  
  
1.  Наберите `<` на панели редактора.  
  
2.  Список членов отображает следующие возможные элементы:  
  
     **!--** для добавления комментария.  
  
     **! DOCTYPE** для добавления типа документа.  
  
     **?** для добавления инструкции обработки.  
  
     **Обратитесь к** для добавления корневого элемента.  
  
3.  Выберите **контакт** из списка членов и нажмите клавишу ВВОД.  
  
     Редактор добавляет открывающий тег, `<Contact`, и помещает курсор после имени элемента.  
  
4.  Нажмите клавишу TAB, чтобы создать XML-данные для элемента `Contact` на основании информации схемы.  
  
### <a name="input"></a>Ввод  
 В этом пошаговом руководстве используется следующий файл схемы.  
  
```xml
<?xml version="1.0" encoding="utf-8" ?>  
<xs:schema elementFormDefault="qualified"  
           xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:simpleType name="phoneType">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="Voice"/>  
      <xs:enumeration value="Fax"/>  
      <xs:enumeration value="Pager"/>  
    </xs:restriction>  
  </xs:simpleType>  
  <xs:element name="Contact">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="Name">  
          <xs:simpleType>  
            <xs:restriction base="xs:string"></xs:restriction>  
          </xs:simpleType>  
        </xs:element>  
        <xs:element name="Title"  
                    type="xs:string" />  
        <xs:element name="Phone"  
                    minOccurs="1"  
                    maxOccurs="unbounded">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="Number"  
                          minOccurs="1">  
                <xs:simpleType>  
                  <xs:restriction base="xs:string"></xs:restriction>  
                </xs:simpleType>  
              </xs:element>  
              <xs:element name="Type"  
                          default="Voice"  
                          minOccurs="1"  
                          type="phoneType"/>  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
### <a name="output"></a>Вывод  
 Далее приведены XML-данные, созданные на основе информации схемы, которая связана с элементом `Contact`. Элементы, отмеченные как `bold` обозначают редактируемые поля в XML-фрагмент.  
  
```xml
<Contact>  
  <Name>name</Name>  
  <Title>title</Title>  
  <Phone>  
    <Number>number</Number>  
    <Type>Voice</Type>  
  </Phone>  
</Contact>  
```  
  
## <a name="see-also"></a>См. также  
 [XML-фрагменты](../xml-tools/xml-snippets.md)   
 [Как использовать XML-фрагменты](../xml-tools/how-to-use-xml-snippets.md)
---
title: Практическое руководство. Изменение пространства имен доменного языка
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, namespace
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 1963502f3940fd0d17c770f111e07de14207e687
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-change-the-namespace-of-a-domain-specific-language"></a>Практическое руководство. Изменение пространства имен доменного языка
Можно изменить пространство имен доменного языка. Необходимо внести изменения в **обозреватель DSL**, в свойствах проекта Dsl пакета и сведения о сборке.

### <a name="to-change-the-namespace-of-a-domain-specific-language"></a>Чтобы изменить пространство имен доменного языка

1.  В **обозреватель DSL**, нажмите кнопку **Dsl** узла.

2.  В **свойства** измените **имен** свойство.

3.  Сохраните решение и преобразования шаблонов.

4.  На **проекта** меню, нажмите кнопку **Dsl свойства**.

     Отобразятся свойства проекта.

5.  Перейдите на вкладку **Приложение** .

6.  Изменение **пространство имен по умолчанию** новое имя пространства имен.

7.  Если требуется изменить имя сборки, измените **свойство имени сборки.**

8.  Если вы изменили имя сборки, откройте DslPackage\Package.tt и обновить эту строку:

     `string dslAssembly = "YourDSLassembly.Dsl.dll";`

9. Если вы написали настраиваемый код, убедитесь, что изменение ссылки на пространство имен и класс в файлах кода.

10. Сброс в экспериментальном экземпляре Visual Studio.

    1.  Удалить **\Users\\ ***{имя}*** \AppData\Local\Microsoft\VisualStudio\\\*Exp**

    2.  В ОС Windows **запустить** меню, выберите **все программы**, **Microsoft Visual Studio 2010 SDK**, **средства**, **сброса Экспериментальный экземпляр**.

11. На **построения** меню, выберите **Перестроить решение**.

## <a name="see-also"></a>См. также

- [Глоссарий инструменты доменного языка](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)
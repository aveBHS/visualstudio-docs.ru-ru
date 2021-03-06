---
title: Шаг 11. Запуск программы и изучение других функций
ms.custom: ''
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.assetid: 656614d0-4fe7-4a67-8edc-c10919377d09
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: c1d793e695f4a9b9fc44ef431b0e9a0ee07238f8
ms.sourcegitcommit: 04a717340b4ab4efc82945fbb25dfe58add2ee4c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="step-11-run-your-program-and-try-other-features"></a>Шаг 11. Запуск программы и изучение других функций
Разработка программа завершена и она готова для выполнения. Можно запустить программу и задать цвет фона для <xref:System.Windows.Forms.PictureBox>. В качестве дополнительного занятия, попробуйте улучшить программу с помощью изменения цвета формы, настройки кнопок и флажков, изменения свойств формы.  
  
 Скачать готовую версию примера можно на странице с [полным примером учебного руководства по созданию приложения для просмотра рисунков](http://code.msdn.microsoft.com/Complete-Picture-Viewer-7d91d3a8).  
  
 ![link to video](../data-tools/media/playvideo.gif "PlayVideo")Видеоверсию этой статьи см. на следующих страницах: [Tutorial 1: Create a Picture Viewer in Visual Basic - Video 5](http://go.microsoft.com/fwlink/?LinkId=205216) (Руководство 1. Создание приложения для просмотра рисунков на Visual Basic — видео 5) и [Tutorial 1: Create a Picture Viewer in C# - Video 4](http://go.microsoft.com/fwlink/?LinkId=205206) (Руководство 1. Создание приложения для просмотра рисунков на C# — видео 4). Эти видеоролики сняты с использованием более ранней версии Visual Studio, поэтому существуют небольшие различия в некоторых командах меню и других элементах пользовательского интерфейса. Однако концепции и процедуры аналогичны текущей версии Visual Studio.  
  
## <a name="to-run-your-program-and-set-the-background-color"></a>Запуск программы и настройка цвета фона  
  
1.  Нажмите клавишу **F5** или в строке меню выберите **Отладка** > **Начать отладку**.  
  
2.  Прежде чем открыть изображение, нажмите кнопку **Установить цвет фона**. Откроется диалоговое окно **Цвет**.  

     ![Диалоговое окно "Цвет"](../ide/media/express_colordialog.png "Express_ColorDialog")  
Диалоговое окно **Цвет** 
  
3.  Выберите цвет фона для элемента управления PictureBox. Внимательно просмотрите метод `backgroundButton_Click()`, чтобы понять, как он работает.  

    > [!NOTE]
    >  Можно загрузить рисунок из Интернета путем вставки URL-адреса в диалоговое окно **Открытие файла**. Попробуйте найти изображение с прозрачным фоном, таким образом, чтобы был показан цвет фона.  

4.  Нажмите кнопку **Очистить рисунок**, чтобы обеспечить удаление рисунка. Затем выйдите из программы, нажав кнопку **Закрыть**.  

## <a name="to-try-other-features"></a>Изучение других возможностей  

-   Измените цвет формы и кнопок с помощью свойства **BackColor**.  

-   Настройте кнопки и флажки с помощью свойств **Font** и **ForeColor**.  

-   Измените свойства формы **FormBorderStyle** и **ControlBox**.  
  
-   Используйте свойства **AcceptButton** и **CancelButton**, чтобы кнопки автоматически нажимались, когда пользователь нажимает клавишу **ВВОД** или **ESC**. Сделайте так, чтобы программа открывала диалоговое окно **Открытие файла** при нажатии пользователем клавиши **ВВОД** и закрывала окно при нажатии клавиши **ESC**.  
  
## <a name="to-continue-or-review"></a>Продолжить или повторить пройденный материал  
  
-   Дополнительные сведения о программировании в Visual Studio см. в разделе [Основные понятия программирования](http://msdn.microsoft.com/Library/65c12cca-af4f-4017-886e-2dbc00a189d6).  
  
-   Дополнительные сведения о Visual Basic см. в разделе [Разработка приложений с помощью Visual Basic](/dotnet/visual-basic/developing-apps/index).  
  
-   Дополнительные сведения о Visual C# см. в разделе [Введение в язык C# и .NET Framework](/dotnet/csharp/getting-started/introduction-to-the-csharp-language-and-the-net-framework).  
  
-   Следующий раздел: [Руководство 2. Создание ограниченной по времени математической головоломки](../ide/tutorial-2-create-a-timed-math-quiz.md).  
  
-   Предыдущий раздел: [Шаг 10. Написание кода дополнительных кнопок и флажка](../ide/step-10-write-code-for-additional-buttons-and-a-check-box.md).

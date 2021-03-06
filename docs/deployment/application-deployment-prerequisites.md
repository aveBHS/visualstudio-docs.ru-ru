---
title: Необходимые условия для развертывания приложения | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, platform detection
- ClickOnce deployment, prerequisites
- ClickOnce deployment, dependencies
- prerequisites, ClickOnce
- dependencies, ClickOnce
ms.assetid: fc6e047e-ad94-44e8-8ff5-b6d1f4ca7735
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 48f72640bdf8efc53b278e4600c6b262dc1a26bf
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/19/2018
---
# <a name="application-deployment-prerequisites"></a>Предварительные условия для развертывания приложения
Чтобы обеспечить успешную установку и запуск приложения, необходимо, в первую очередь, убедиться, что компоненты, от которых зависит приложение, уже установлены на целевом компьютере. Например, большинство приложений, которые создаются при помощи [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], имеют зависимость от [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], поэтому перед установкой приложения на целевом компьютере должна быть установлена правильная версия среды CLR.  
  
 Можно выбрать необходимые **диалоговое окно «необходимые условия»** и установить платформу .NET Framework и другие распространяемые компоненты в процессе установки. Такой подход известен как *начальную загрузку*. Далее, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] создает исполняемую программу Windows с именем Setup.exe, также известный как *загрузчика*. Начальный загрузчик установит необходимые компоненты перед запуском приложения. Дополнительные сведения о выборе необходимых компонентов см. в разделе [диалоговое окно «необходимые условия»](../ide/reference/prerequisites-dialog-box.md).  
  
 Каждый необходимый компонент является пакетом начальной загрузки. Пакет начальной загрузки — это группа директорий и файлов, в которых содержатся файлы манифеста, описывающие порядок установки необходимого компонента. Если необходимые компоненты приложения не перечислены в **диалоговое окно готовности к установке**, можно создать настраиваемые пакеты загрузчика и добавить их в Visual Studio. Затем можно выбрать необходимые компоненты в **диалоговое окно «необходимые условия»**. Дополнительные сведения см. в разделе [создание пакетов загрузчика](../deployment/creating-bootstrapper-packages.md).  
  
 По умолчанию для развертывания приложений ClickOnce начальная загрузка включена, а генерируемый для них начальный загрузчик подписан. Вы можете отключить начальную загрузку компонента, но только если точно знаете, что на всех целевых компьютерах уже установлена правильная версия компонента.  
  
## <a name="bootstrapping-and-clickonce-deployment"></a>Начальная загрузка и развертывание приложений ClickOnce  
 Перед установкой приложения на клиентском компьютере [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] проверит клиента и убедится, что он соответствует требованиям, установленным в манифесте приложения. В число этих требований входят следующие:  
  
-   Минимальная необходимая версия среды CLR, определенная в качестве зависимости от сборки в манифесте приложения.  
  
-   Минимальная версия операционной системы Windows, необходимая для приложения, согласно манифесту приложения с использованием элемента `<osVersionInfo>`. (См. [ \<зависимостей > элемент](../deployment/dependency-element-clickonce-application.md))  
  
-   Минимальная версия сборок, которые должны быть предварительно установлены в глобальном кэше сборок (GAC), как указано в декларации зависимости от сборки в манифесте сборки.  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] можно обнаружить отсутствующие необходимые компоненты и необходимые компоненты можно установить с помощью загрузчика. Дополнительные сведения см. в разделе [как: Установка необходимых компонентов с приложением ClickOnce](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md).  
  
> [!NOTE]
>  Чтобы изменить значения в манифестах, созданных такими инструментами, как [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] и MageUI.exe, необходимо отредактировать манифест приложения в текстовом редакторе, а затем снова подписать манифест приложения и манифест развертывания. Для получения дополнительной информации см. [Практическое руководство. Повторное подписание манифестов приложения и развертывания](../deployment/how-to-re-sign-application-and-deployment-manifests.md).  
  
 Если для развертывания приложения используются Visual Studio и ClickOnce, то выбираемые по умолчанию пакеты начального загрузчика будут зависеть от версии .NET Framework в решении. Однако при изменении целевой версии .NET Framework, необходимо обновить параметры в **диалоговое окно «необходимые условия»** вручную.  
  
|Целевая версия .NET Framework|Выбранные пакеты начального загрузчика|  
|---------------------------|------------------------------------|  
|Клиентский профиль .NET Framework 4|Клиентский профиль .NET Framework 4<br /><br /> Установщик Windows версии 3.1|  
|.NET Framework 4|.NET Framework 4<br /><br /> Установщик Windows версии 3.1|  
  
 При развертывании приложений [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] на странице Publish.htm, генерируемой Мастером публикации [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)], указывается либо ссылка, позволяющая установить только приложение, либо ссылка, позволяющая установить как приложение, так и компоненты начальной загрузки.  
  
 Если начальный загрузчик генерируется с помощью мастера публикации ClickOnce или страницы публикации в Visual Studio, то файл Setup.exe подписывается автоматически. Если же для подписи начального загрузчика необходимо использовать сертификат клиента, то файл можно подписать позже.  
  
## <a name="bootstrapping-and-msbuild"></a>Начальная загрузка и MSBuild  
 Если вы не используете [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], но компилируете приложения в командной строке, то приложение начальной загрузки [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] можно создать с помощью задачи Microsoft Build Engine (MSBuild). Дополнительные сведения см. в разделе [задача GenerateBootstrapper](../msbuild/generatebootstrapper-task.md).  
  
 В качестве альтернативы начальному загрузчику можно предварительно развернуть компоненты с помощью электронной системы распределения, например Microsoft Systems Management Server (SMS).  
  
## <a name="bootstrapper-setupexe-command-line-arguments"></a>Аргументы командной строки начального загрузчика (Setup.exe)  
 Файл Setup.exe, сгенерированный с помощью [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] и задач MSBuild, поддерживает описанный ниже небольшой набор аргументов командной строки. Все аргументы передаются в приложение начальной загрузки после того, как будут направлены в установщик приложения.  
  
 В случае изменения параметров начального загрузчика необходимо изменить неподписанный начальный загрузчик, а затем подписать файл начального загрузчика.  
  
|Аргумент командной строки|Описание|  
|---------------------------|-----------------|  
|**-?, -h, - Справка**|Открывает диалоговое окно "Справка".|  
|**-URL-адрес, - componentsurl**|Показывает сохраненный URL и URL-адреса компонентов для этой установки.|  
|**-URL-адрес =** `location`|Настраивает URL на то место, где Setup.exe будет искать приложение [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)].|  
|**-componentsurl =** `location`|Настраивает URL на то место, где Setup.exe будет искать зависимости, такие как [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)].|  
|**-homesite =** `true`**&#124;** `false`|Когда `true`, то зависимости загружаются из предпочтительного источника на сайте поставщика. Это значение переопределяет **- componentsurl** параметр. Когда `false`, то зависимости загружаются по URL-адресу, определяемое **- componentsurl**.|  
  
## <a name="operating-system-support"></a>Поддержка операционной системой  
 Начальный загрузчик Visual Studio не поддерживается параметром установки Server Core операционной системы Windows Server 2008 или Windows Server 2008 R2, что означает незначительную поддержку серверной среды с ограниченным функционалом. Например, параметр установки Server Core поддерживает только профиль .NET Framework 3.5 Server Core, поэтому возможности Visual Studio, которые требуют полной установки .NET Framework, работать не будут.  
  
## <a name="see-also"></a>См. также  
 [Выбор стратегии развертывания ClickOnce](../deployment/choosing-a-clickonce-deployment-strategy.md)   
 [Развертывание и безопасность технологии ClickOnce](../deployment/clickonce-security-and-deployment.md)
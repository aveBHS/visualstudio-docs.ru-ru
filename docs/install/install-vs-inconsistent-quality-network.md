---
title: Установка в сетевых средах с низкой пропускной способностью или низким уровнем надежности | Документация Майкрософт
description: Узнайте, как использовать установщик Visual Studio, если сеть работает ненадежно или имеет низкую пропускную способность, и как скачивать файлы установки с помощью командной строки.
ms.date: 01/17/2018
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- installing Visual Studio
- no internet connection
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dbe4c8a1e1aa561a8a7fca1f3b8e9e0469bf6dc9
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="install-visual-studio-2017-on-low-bandwidth-or-unreliable-network-environments"></a>Установка Visual Studio 2017 в сетевых средах с низкой пропускной способностью или низким уровнем надежности

Мы рекомендуем вам опробовать веб-установщик Visual Studio&mdash;мы уверены, что вам понравится работать с ним.

 > [!div class="button"]
 > [Скачивание Visual Studio 2017](https://aka.ms/vsdownload?utm_source=mscom&utm_campaign=msdocsOL)
<br/>

Однако если подключение к Интернету недоступно или ненадежно, вы можете создать локальный кэш файлов, необходимых для автономной установки, с помощью командной строки. Ниже описывается порядок действий.

> [!NOTE]
> Если вы являетесь администратором предприятия и вам нужно развернуть Visual Studio 2017 в сети клиентских рабочих станций, которые отделены от Интернета брандмауэром, см. руководства по [созданию сетевой установки Visual Studio 2017](../install/create-a-network-installation-of-visual-studio.md) и [установке сертификатов, требуемых для автономной установки Visual Studio](../install/install-certificates-for-visual-studio-offline.md).

## <a name="step-1---download-the-visual-studio-bootstrapper"></a>Шаг 1. Скачивание начального загрузчика Visual Studio

Прежде всего следует скачать загрузчик Visual Studio для выбранного выпуска Visual Studio.

Это будет один из следующих файлов установки &mdash;а точнее, файлов загрузчика&mdash; или что-то близкое к ним.

| Выпуск                    | Файл                                                                    |
|----------------------------|-------------------------------------------------------------------------|
| Visual Studio Community    | [vs_community.exe](https://aka.ms/vs/15/release/vs_community.exe)       |
| Visual Studio Professional | [vs_professional.exe](https://aka.ms/vs/15/release/vs_professional.exe) |
| Visual Studio Enterprise   | [vs_enterprise.exe](https://aka.ms/vs/15/release/vs_enterprise.exe)     |

## <a name="step-2---create-a-local-install-cache"></a>Шаг 2. Создание локального кэша установки

Для выполнения этого действия необходимо подключение к Интернету. Чтобы создать локальный макет, откройте командную строку и используйте одну из команд, приведенных в примерах ниже. В этих примерах предполагается, что вы используете выпуск Visual Studio Community. Для других выпусков измените команду соответствующим образом.

- Для разработки веб-приложений .NET или классических приложений .NET выполните следующую команду:

   ```vs_community.exe --layout c:\vs2017layout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional --lang en-US```

- Для разработки классических приложений .NET и решений Office выполните следующую команду:

   ```vs_community.exe --layout c:\vs2017layout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.Office --includeOptional --lang en-US```

- Для разработки классических приложений C++ выполните следующую команду:

   ```vs_community.exe --layout c:\vs2017layout --add Microsoft.VisualStudio.Workload.NativeDesktop --includeRecommended --lang en-US```

- Чтобы создать локальный макет с полным набором компонентов (это будет довольно долго&mdash;ведь компонентов у нас _очень много_), выполните следующую команду:

   ```vs_community.exe --layout c:\vs2017layout --lang en-US```

Если вы хотите установить язык, отличный от английского, выберите нужный языковой стандарт вместо `en-US` в нижней части этой страницы. Если потребуется, используйте этот [список доступных компонентов и рабочих нагрузок](workload-and-component-ids.md) для дополнительной настройки кэша установки.

> [!IMPORTANT]
> Для установки полного макета Visual Studio 2017 потребуется как минимум 35 ГБ дискового пространства. Скачивание этого макета может занять некоторое время. См. статью [Использование параметров командной строки для установки Visual Studio 2017](use-command-line-parameters-to-install-visual-studio.md), где описано, как создать макет, содержащий только выбранные компоненты для установки.

## <a name="step-3---install-visual-studio-from-the-local-cache"></a>Шаг 3. Установка Visual Studio из локального кэша

> [!TIP]
> При запуске установки из локального кэша используются локальные версии каждого из этих файлов. Но если во время установки вы выберете компоненты, которые отсутствуют в кэше, мы попытаемся скачать их из Интернета.

Чтобы устанавливать только те файлы, которые вы уже скачали, все параметры командной строки должны совпадать с теми, которые вы использовали для создания макета кэша. Предположим, что вы создали макет кэша с помощью следующей команды:

```vs_community.exe --layout c:\vs2017layout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional --lang en-US```

В этом случае используйте следующую команду для запуска установки:

```c:\vs2017layout\vs_community.exe --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional```

> [!NOTE]
> Если возникает ошибка, указывающая на недопустимую подпись, вам нужно установить обновленные сертификаты. Откройте папку "Сертификаты" в автономном кэше. Дважды щелкните каждый файл сертификата и выполните инструкции в мастере диспетчера сертификатов. Если он предложит ввести пароль, оставьте это поле пустым.

## <a name="list-of-language-locales"></a>Список языковых стандартов

| **Язык-языковой стандарт** | **Язык** |
| ----------------------- | --------------- |
| cs-CZ | Чешский |
| de-DE | Немецкий |
| en-US | Английский |
| es-ES | Испанский |
| fr-FR | Французский |
| it-IT | Итальянский |
| ja-JP | Японский |
| ko-KR | Корейский |
| pl-PL | Польский |
| pt-BR | Португальский - Бразильская |
| ru-RU | Русский |
| tr-TR | Турецкий |
| zh-CN | Китайский (упрощенное письмо) |
| zh-TW | Китайский (традиционное письмо) |

## <a name="get-support"></a>Техническая поддержка

Иногда возникают проблемы. При сбое установки Visual Studio см. инструкции по [устранению неполадок и исправлению ошибок установки и обновления Visual Studio 2017](troubleshooting-installation-issues.md). Если описанные выше действия не устраняют проблему, вы можете обратиться к нам за помощью в чате в реальном времени (только на английском языке). Дополнительные сведения см. на [странице поддержки Visual Studio](https://www.visualstudio.com/vs/support/#talktous).

Ниже приведены несколько дополнительных вариантов:

* Вы можете сообщить о проблемах с продуктом в корпорацию Майкрософт, используя средство [Сообщить о проблеме](../ide/how-to-report-a-problem-with-visual-studio-2017.md). Оно доступно как в Visual Studio Installer, так и в Visual Studio IDE.
* Вы можете оставить предложение о продукте на форуме [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Вы можете просматривать описания проблем и искать решения в [сообществе разработчиков Visual Studio](https://developercommunity.visualstudio.com/).
* Вы также можете связаться с нами и другими разработчиками Visual Studio, используя [средство для обсуждения Visual Studio в сообществе Gitter](https://gitter.im/Microsoft/VisualStudio). (Требуется учетная запись [GitHub](https://github.com/).)

## <a name="see-also"></a>См. также

* [Установка Visual Studio](install-visual-studio.md)
* [Руководство администратора Visual Studio](visual-studio-administrator-guide.md)
* [Использование параметров командной строки для установки Visual Studio](use-command-line-parameters-to-install-visual-studio.md)

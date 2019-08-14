---
title: 诊断工具概述 - .NET Core
description: 概述用于 .NET Core 应用程序的工具和技术。
author: sdmaclea
ms.author: stmaclea
ms.date: 08/05/2019
ms.topic: overview
ms.openlocfilehash: f107d15fa5584bb5a4834b5f11f1096bec7eb749
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2019
ms.locfileid: "68974145"
---
# <a name="what-diagnostic-tools-are-available-in-net-core"></a>.NET Core 中提供哪些诊断工具？

软件并非始终按预计方式运行，但 .NET Core 具有可帮助用户快速有效地诊断这些问题的工具和 API。

本文可帮助用户查找各种所需的工具。

## <a name="managed-debuggersmanaged-debuggersmd"></a>[托管调试器](managed-debuggers.md)
借助托管调试器，用户可以与程序进行交互。 暂停、增量执行、检查和恢复操作可让用户深入了解代码的行为。 调试器是诊断易于重现的功能问题的首选。

## <a name="logging-and-tracinglogging-tracingmd"></a>[日志记录和跟踪](logging-tracing.md)
日志记录和跟踪是相关技术。 它们指的是用于创建日志文件的检测代码。 这些文件记录了程序操作的详细信息。 这些细节可用于诊断最复杂的问题。 当与时间戳结合使用时，这些技术在性能调查中也非常有用。

## <a name="unit-testingtestingindexmd"></a>[单元测试](../testing/index.md)
单元测试是持续集成和部署高质量软件的关键组件。 单元测试的目的在于，在用户操作导致系统出现问题时提前向其发出警告。

---
ms.openlocfilehash: 98ec28fc1f91512a61f64a36f7749379e864fea1
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920664"
---

安装 .NET Core 包时，可能会看到类似于 `Failed to fetch ... File has unexpected size ... Mirror sync in progress?` 的错误。 一般而言，此错误表示 .NET Core 的包源正在通过更新的包版本进行更新，应稍后重试。 升级期间，包源的不可用时间不应超过 30 分钟。 如果持续收到此错误超过 30 分钟，请在 <https://github.com/dotnet/core/issues> 中提交问题。

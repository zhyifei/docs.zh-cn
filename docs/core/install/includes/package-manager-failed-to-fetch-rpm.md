---
ms.openlocfilehash: 96f3ef0160144322f77413995c842b745bb5bb1e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "76920743"
---

安装 .NET Core 包时，可能会看到类似于 `signature verification failed for file 'repomd.xml' from repository 'packages-microsoft-com-prod'` 的错误。 一般而言，此错误表示 .NET Core 的包源正在通过更新的包版本进行更新，应稍后重试。 升级期间，包源的不可用时间不应超过 2 小时。 如果持续收到此错误超过 2 小时，请在 <https://github.com/dotnet/core/issues> 中提交问题。

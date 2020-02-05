---
ms.openlocfilehash: 96f3ef0160144322f77413995c842b745bb5bb1e
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2020
ms.locfileid: "76920743"
---

<span data-ttu-id="7f644-101">安装 .NET Core 包时，可能会看到类似于 `signature verification failed for file 'repomd.xml' from repository 'packages-microsoft-com-prod'` 的错误。</span><span class="sxs-lookup"><span data-stu-id="7f644-101">While installing the .NET Core package, you may see an error similar to `signature verification failed for file 'repomd.xml' from repository 'packages-microsoft-com-prod'`.</span></span> <span data-ttu-id="7f644-102">一般而言，此错误表示 .NET Core 的包源正在通过更新的包版本进行更新，应稍后重试。</span><span class="sxs-lookup"><span data-stu-id="7f644-102">Generally speaking, this error means that the package feed for .NET Core is being upgraded with newer package versions, and that you should try again later.</span></span> <span data-ttu-id="7f644-103">升级期间，包源的不可用时间不应超过 2 小时。</span><span class="sxs-lookup"><span data-stu-id="7f644-103">During an upgrade, the package feed should not be unavailable for more than 2 hours.</span></span> <span data-ttu-id="7f644-104">如果持续收到此错误超过 2 小时，请在 <https://github.com/dotnet/core/issues> 中提交问题。</span><span class="sxs-lookup"><span data-stu-id="7f644-104">If you continually receive this error for more than 2 hours, please file an issue at <https://github.com/dotnet/core/issues>.</span></span>

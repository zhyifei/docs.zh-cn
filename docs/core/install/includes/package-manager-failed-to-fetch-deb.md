---
ms.openlocfilehash: 98ec28fc1f91512a61f64a36f7749379e864fea1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "76920664"
---

<span data-ttu-id="ca36e-101">安装 .NET Core 包时，可能会看到类似于 `Failed to fetch ... File has unexpected size ... Mirror sync in progress?` 的错误。</span><span class="sxs-lookup"><span data-stu-id="ca36e-101">While installing the .NET Core package, you may see an error similar to `Failed to fetch ... File has unexpected size ... Mirror sync in progress?`.</span></span> <span data-ttu-id="ca36e-102">一般而言，此错误表示 .NET Core 的包源正在通过更新的包版本进行更新，应稍后重试。</span><span class="sxs-lookup"><span data-stu-id="ca36e-102">Generally speaking, this error means that the package feed for .NET Core is being upgraded with newer package versions, and that you should try again later.</span></span> <span data-ttu-id="ca36e-103">升级期间，包源的不可用时间不应超过 30 分钟。</span><span class="sxs-lookup"><span data-stu-id="ca36e-103">During an upgrade, the package feed should not be unavailable for more than 30 minutes.</span></span> <span data-ttu-id="ca36e-104">如果持续收到此错误超过 30 分钟，请在 <https://github.com/dotnet/core/issues> 中提交问题。</span><span class="sxs-lookup"><span data-stu-id="ca36e-104">If you continually receive this error for more than 30 minutes, please file an issue at <https://github.com/dotnet/core/issues>.</span></span>

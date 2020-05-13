---
title: 网络中断性变更
description: 列出 .NET Core 中网络的中断性变更。
ms.date: 05/05/2020
ms.openlocfilehash: 07e0b2e062ce244cd6312bbe08bcc63db4c74347
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "82859615"
---
# <a name="networking-breaking-changes"></a><span data-ttu-id="91390-103">网络中断性变更</span><span class="sxs-lookup"><span data-stu-id="91390-103">Networking breaking changes</span></span>

<span data-ttu-id="91390-104">本页记录了以下中断性变更：</span><span class="sxs-lookup"><span data-stu-id="91390-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="91390-105">重大更改</span><span class="sxs-lookup"><span data-stu-id="91390-105">Breaking change</span></span> | <span data-ttu-id="91390-106">引入的版本</span><span class="sxs-lookup"><span data-stu-id="91390-106">Introduced version</span></span> |
| - | - |
| [<span data-ttu-id="91390-107">HttpRequestMessage.Version 的默认值已更改为 1.1</span><span class="sxs-lookup"><span data-stu-id="91390-107">Default value of HttpRequestMessage.Version changed to 1.1</span></span>](#default-value-of-httprequestmessageversion-changed-to-11) | <span data-ttu-id="91390-108">3.0</span><span class="sxs-lookup"><span data-stu-id="91390-108">3.0</span></span> |
| [<span data-ttu-id="91390-109">WebClient.CancelAsync 并不总是立即取消</span><span class="sxs-lookup"><span data-stu-id="91390-109">WebClient.CancelAsync doesn't always cancel immediately</span></span>](#webclientcancelasync-doesnt-always-cancel-immediately) | <span data-ttu-id="91390-110">2.0</span><span class="sxs-lookup"><span data-stu-id="91390-110">2.0</span></span> |

## <a name="net-core-30"></a><span data-ttu-id="91390-111">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="91390-111">.NET Core 3.0</span></span>

[!INCLUDE[Default value of HttpRequestMessage.Version changed to 1.1](~/includes/core-changes/networking/3.0/httprequestmessage-version-change.md)]

***

## <a name="net-core-20"></a><span data-ttu-id="91390-112">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="91390-112">.NET Core 2.0</span></span>

[!INCLUDE [behavior-change-webclient-cancelasync](../../../includes/core-changes/networking/2.0/behavior-change-webclient-cancelasync.md)]

***

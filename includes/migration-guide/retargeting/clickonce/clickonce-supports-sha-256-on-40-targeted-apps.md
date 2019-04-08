---
ms.openlocfilehash: 9bf6972812bdf4a385b99fe34d2cd3cd8a91c8cf
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760979"
---
### <a name="clickonce-supports-sha-256-on-40-targeted-apps"></a><span data-ttu-id="cd431-101">ClickOnce 支持面向 4.0 的应用上的 SHA-256</span><span class="sxs-lookup"><span data-stu-id="cd431-101">ClickOnce supports SHA-256 on 4.0-targeted apps</span></span>

|   |   |
|---|---|
|<span data-ttu-id="cd431-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="cd431-102">Details</span></span>|<span data-ttu-id="cd431-103">以前，如果 ClickOnce 应用具有使用 SHA-256 签名的证书，即使应用面向 4.0 版本，也需要 .NET Framework 4.5 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="cd431-103">Previously, a ClickOnce app with a certificate signed with SHA-256 would require .NET Framework 4.5 or later to be present, even if the app targeted 4.0.</span></span> <span data-ttu-id="cd431-104">现在，即使使用 SHA-256 签名，面向 .NET Framework 4.0 的 ClickOnce 应用也可在 .NET Framework 4.0 上运行。</span><span class="sxs-lookup"><span data-stu-id="cd431-104">Now, .NET Framework 4.0-targeted ClickOnce apps can run on .NET Framework 4.0, even if signed with SHA-256.</span></span>|
|<span data-ttu-id="cd431-105">建议</span><span class="sxs-lookup"><span data-stu-id="cd431-105">Suggestion</span></span>|<span data-ttu-id="cd431-106">此更改删除了该依赖项，允许将 SHA-256 证书用于为面向 .NET Framework 4 或更早版本的 ClickOnce 应用签名。</span><span class="sxs-lookup"><span data-stu-id="cd431-106">This change removes that dependency and allows SHA-256 certificates to be used to sign ClickOnce apps that target .NET Framework 4 and earlier versions.</span></span>|
|<span data-ttu-id="cd431-107">范围</span><span class="sxs-lookup"><span data-stu-id="cd431-107">Scope</span></span>|<span data-ttu-id="cd431-108">次要</span><span class="sxs-lookup"><span data-stu-id="cd431-108">Minor</span></span>|
|<span data-ttu-id="cd431-109">版本</span><span class="sxs-lookup"><span data-stu-id="cd431-109">Version</span></span>|<span data-ttu-id="cd431-110">4.6</span><span class="sxs-lookup"><span data-stu-id="cd431-110">4.6</span></span>|
|<span data-ttu-id="cd431-111">类型</span><span class="sxs-lookup"><span data-stu-id="cd431-111">Type</span></span>|<span data-ttu-id="cd431-112">重定目标</span><span class="sxs-lookup"><span data-stu-id="cd431-112">Retargeting</span></span>|


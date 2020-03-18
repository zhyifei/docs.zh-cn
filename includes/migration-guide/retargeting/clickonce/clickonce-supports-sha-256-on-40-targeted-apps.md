---
ms.openlocfilehash: 0358450024607a985f38564ec9743ba964949e8f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804435"
---
### <a name="clickonce-supports-sha-256-on-40-targeted-apps"></a><span data-ttu-id="90ed9-101">ClickOnce 支持面向 4.0 的应用上的 SHA-256</span><span class="sxs-lookup"><span data-stu-id="90ed9-101">ClickOnce supports SHA-256 on 4.0-targeted apps</span></span>

|   |   |
|---|---|
|<span data-ttu-id="90ed9-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="90ed9-102">Details</span></span>|<span data-ttu-id="90ed9-103">以前，如果 ClickOnce 应用具有使用 SHA-256 签名的证书，即使应用面向 4.0 版本，也需要 .NET Framework 4.5 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="90ed9-103">Previously, a ClickOnce app with a certificate signed with SHA-256 would require .NET Framework 4.5 or later to be present, even if the app targeted 4.0.</span></span> <span data-ttu-id="90ed9-104">现在，即使使用 SHA-256 签名，面向 .NET Framework 4.0 的 ClickOnce 应用也可在 .NET Framework 4.0 上运行。</span><span class="sxs-lookup"><span data-stu-id="90ed9-104">Now, .NET Framework 4.0-targeted ClickOnce apps can run on .NET Framework 4.0, even if signed with SHA-256.</span></span>|
|<span data-ttu-id="90ed9-105">建议</span><span class="sxs-lookup"><span data-stu-id="90ed9-105">Suggestion</span></span>|<span data-ttu-id="90ed9-106">此更改删除了该依赖项，允许将 SHA-256 证书用于为面向 .NET Framework 4 或更早版本的 ClickOnce 应用签名。</span><span class="sxs-lookup"><span data-stu-id="90ed9-106">This change removes that dependency and allows SHA-256 certificates to be used to sign ClickOnce apps that target .NET Framework 4 and earlier versions.</span></span>|
|<span data-ttu-id="90ed9-107">范围</span><span class="sxs-lookup"><span data-stu-id="90ed9-107">Scope</span></span>|<span data-ttu-id="90ed9-108">次要</span><span class="sxs-lookup"><span data-stu-id="90ed9-108">Minor</span></span>|
|<span data-ttu-id="90ed9-109">Version</span><span class="sxs-lookup"><span data-stu-id="90ed9-109">Version</span></span>|<span data-ttu-id="90ed9-110">4.6</span><span class="sxs-lookup"><span data-stu-id="90ed9-110">4.6</span></span>|
|<span data-ttu-id="90ed9-111">类型</span><span class="sxs-lookup"><span data-stu-id="90ed9-111">Type</span></span>|<span data-ttu-id="90ed9-112">重定目标</span><span class="sxs-lookup"><span data-stu-id="90ed9-112">Retargeting</span></span>|

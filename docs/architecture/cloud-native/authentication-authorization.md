---
title: 云原生应用中的身份验证和授权
description: 为 Azure 构建云本机 .NET 应用 |云本机应用中的身份验证和授权
ms.date: 03/02/2020
ms.openlocfilehash: 6261a0a72405bc1c984a04a7851aea4dd6664ddf
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805541"
---
# <a name="authentication-and-authorization-in-cloud-native-apps"></a><span data-ttu-id="80a98-103">云本机应用中的身份验证和授权</span><span class="sxs-lookup"><span data-stu-id="80a98-103">Authentication and authorization in cloud-native apps</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="80a98-104">*身份验证*是确定安全主体身份的过程。</span><span class="sxs-lookup"><span data-stu-id="80a98-104">*Authentication* is the process of determining the identity of a security principal.</span></span> <span data-ttu-id="80a98-105">*授权*是授予经过身份验证的主体权限以执行操作或访问资源的行为。</span><span class="sxs-lookup"><span data-stu-id="80a98-105">*Authorization* is the act of granting an authenticated principal permission to perform an action or access a resource.</span></span> <span data-ttu-id="80a98-106">有时身份验证将缩短为`AuthN`，授权将缩短为`AuthZ`。</span><span class="sxs-lookup"><span data-stu-id="80a98-106">Sometimes authentication is shortened to `AuthN` and authorization is shortened to `AuthZ`.</span></span> <span data-ttu-id="80a98-107">云原生应用程序需要依靠基于 HTTP 的开放式协议来验证安全主体，因为客户端和应用程序都可以在世界任何平台或设备上运行。</span><span class="sxs-lookup"><span data-stu-id="80a98-107">Cloud-native applications need to rely on open HTTP-based protocols to authenticate security principals since both clients and applications could be running anywhere in the world on any platform or device.</span></span> <span data-ttu-id="80a98-108">唯一的常见因素是 HTTP。</span><span class="sxs-lookup"><span data-stu-id="80a98-108">The only common factor is HTTP.</span></span>

<span data-ttu-id="80a98-109">许多组织仍然依赖于本地身份验证服务，如活动目录联合服务 （ADFS）。</span><span class="sxs-lookup"><span data-stu-id="80a98-109">Many organizations still rely on local authentication services like Active Directory Federation Services (ADFS).</span></span> <span data-ttu-id="80a98-110">虽然这种方法传统上为组织提供了良好的本地身份验证需求，但云原生应用程序受益于专为云设计的系统。</span><span class="sxs-lookup"><span data-stu-id="80a98-110">While this approach has traditionally served organizations well for on premises authentication needs, cloud-native applications benefit from systems designed specifically for the cloud.</span></span> <span data-ttu-id="80a98-111">最近 2019 年，英国国家网络安全中心 （NCSC） 的一份通报指出，"使用 Azure AD 作为主要身份验证源的组织实际上将降低与 ADFS 相比的风险。</span><span class="sxs-lookup"><span data-stu-id="80a98-111">A recent 2019 United Kingdom National Cyber Security Centre (NCSC) advisory states that "organizations using Azure AD as their primary authentication source will actually lower their risk compared to ADFS."</span></span> <span data-ttu-id="80a98-112">[此分析](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/)中概述的一些原因包括：</span><span class="sxs-lookup"><span data-stu-id="80a98-112">Some reasons outlined in [this analysis](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/) include:</span></span>

- <span data-ttu-id="80a98-113">访问全套 Microsoft 凭据保护技术。</span><span class="sxs-lookup"><span data-stu-id="80a98-113">Access to full set of Microsoft credential protection technologies.</span></span>
- <span data-ttu-id="80a98-114">大多数组织在某种程度上已经依赖于 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="80a98-114">Most organizations are already relying on Azure AD to some extent.</span></span>
- <span data-ttu-id="80a98-115">NTLM 哈希的双重哈希可确保折衷不会允许在本地活动目录中工作的凭据。</span><span class="sxs-lookup"><span data-stu-id="80a98-115">Double hashing of NTLM hashes ensures compromise won't allow credentials that work in local Active Directory.</span></span>

## <a name="references"></a><span data-ttu-id="80a98-116">参考</span><span class="sxs-lookup"><span data-stu-id="80a98-116">References</span></span>

- [<span data-ttu-id="80a98-117">身份验证基础知识</span><span class="sxs-lookup"><span data-stu-id="80a98-117">Authentication basics</span></span>](https://docs.microsoft.com/azure/active-directory/develop/authentication-scenarios)
- [<span data-ttu-id="80a98-118">访问令牌和声明</span><span class="sxs-lookup"><span data-stu-id="80a98-118">Access tokens and claims</span></span>](https://docs.microsoft.com/azure/active-directory/develop/access-tokens)
- [<span data-ttu-id="80a98-119">可能是时候放弃本地身份验证服务了</span><span class="sxs-lookup"><span data-stu-id="80a98-119">It may be time to ditch your on premises authentication services</span></span>](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/)

>[!div class="step-by-step"]
><span data-ttu-id="80a98-120">[上一页](identity.md)
>[下一页](azure-active-directory.md)</span><span class="sxs-lookup"><span data-stu-id="80a98-120">[Previous](identity.md)
[Next](azure-active-directory.md)</span></span>

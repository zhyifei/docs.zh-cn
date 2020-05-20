---
title: 云本机应用中的身份验证和授权
description: 构建适用于 Azure 的云本机 .NET 应用 |云本机应用中的身份验证和授权
ms.date: 05/13/2020
ms.openlocfilehash: e5254560ac82662e5e3ea6a25997516cd2b478b0
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614300"
---
# <a name="authentication-and-authorization-in-cloud-native-apps"></a><span data-ttu-id="fc8d5-103">云本机应用中的身份验证和授权</span><span class="sxs-lookup"><span data-stu-id="fc8d5-103">Authentication and authorization in cloud-native apps</span></span>

<span data-ttu-id="fc8d5-104">*身份验证*是确定安全主体的标识的过程。</span><span class="sxs-lookup"><span data-stu-id="fc8d5-104">*Authentication* is the process of determining the identity of a security principal.</span></span> <span data-ttu-id="fc8d5-105">*授权*是指向经过身份验证的主体授予执行操作或访问资源的权限。</span><span class="sxs-lookup"><span data-stu-id="fc8d5-105">*Authorization* is the act of granting an authenticated principal permission to perform an action or access a resource.</span></span> <span data-ttu-id="fc8d5-106">有时，身份验证将缩短为 `AuthN` ，授权会缩短到 `AuthZ` 。</span><span class="sxs-lookup"><span data-stu-id="fc8d5-106">Sometimes authentication is shortened to `AuthN` and authorization is shortened to `AuthZ`.</span></span> <span data-ttu-id="fc8d5-107">云本机应用程序需要依赖开放式 HTTP 协议对安全主体进行身份验证，因为客户端和应用程序都可以在任何平台或设备上的任何位置运行。</span><span class="sxs-lookup"><span data-stu-id="fc8d5-107">Cloud-native applications need to rely on open HTTP-based protocols to authenticate security principals since both clients and applications could be running anywhere in the world on any platform or device.</span></span> <span data-ttu-id="fc8d5-108">唯一的常见因素是 HTTP。</span><span class="sxs-lookup"><span data-stu-id="fc8d5-108">The only common factor is HTTP.</span></span>

<span data-ttu-id="fc8d5-109">许多组织仍依赖于本地身份验证服务，如 Active Directory 联合身份验证服务（ADFS）。</span><span class="sxs-lookup"><span data-stu-id="fc8d5-109">Many organizations still rely on local authentication services like Active Directory Federation Services (ADFS).</span></span> <span data-ttu-id="fc8d5-110">虽然这种方法在传统上能够满足本地身份验证需求，但云本机应用程序也受益于专门针对云设计的系统。</span><span class="sxs-lookup"><span data-stu-id="fc8d5-110">While this approach has traditionally served organizations well for on premises authentication needs, cloud-native applications benefit from systems designed specifically for the cloud.</span></span> <span data-ttu-id="fc8d5-111">最近的2019英国国家网络安全中心（NCSC）咨询表明 "使用 Azure AD 作为其主要身份验证源的组织实际上会降低他们与 ADFS 相比的风险。"</span><span class="sxs-lookup"><span data-stu-id="fc8d5-111">A recent 2019 United Kingdom National Cyber Security Centre (NCSC) advisory states that "organizations using Azure AD as their primary authentication source will actually lower their risk compared to ADFS."</span></span> <span data-ttu-id="fc8d5-112">[此分析](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/)概述的一些原因包括：</span><span class="sxs-lookup"><span data-stu-id="fc8d5-112">Some reasons outlined in [this analysis](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/) include:</span></span>

- <span data-ttu-id="fc8d5-113">访问全套 Microsoft 凭据保护技术。</span><span class="sxs-lookup"><span data-stu-id="fc8d5-113">Access to full set of Microsoft credential protection technologies.</span></span>
- <span data-ttu-id="fc8d5-114">大多数组织已经依赖于 Azure AD 一定程度上。</span><span class="sxs-lookup"><span data-stu-id="fc8d5-114">Most organizations are already relying on Azure AD to some extent.</span></span>
- <span data-ttu-id="fc8d5-115">NTLM 哈希的双重哈希可确保泄露不会允许在本地 Active Directory 中使用的凭据。</span><span class="sxs-lookup"><span data-stu-id="fc8d5-115">Double hashing of NTLM hashes ensures compromise won't allow credentials that work in local Active Directory.</span></span>

## <a name="references"></a><span data-ttu-id="fc8d5-116">参考</span><span class="sxs-lookup"><span data-stu-id="fc8d5-116">References</span></span>

- [<span data-ttu-id="fc8d5-117">身份验证基础知识</span><span class="sxs-lookup"><span data-stu-id="fc8d5-117">Authentication basics</span></span>](https://docs.microsoft.com/azure/active-directory/develop/authentication-scenarios)
- [<span data-ttu-id="fc8d5-118">访问令牌和声明</span><span class="sxs-lookup"><span data-stu-id="fc8d5-118">Access tokens and claims</span></span>](https://docs.microsoft.com/azure/active-directory/develop/access-tokens)
- [<span data-ttu-id="fc8d5-119">可能需要 ditch 本地身份验证服务</span><span class="sxs-lookup"><span data-stu-id="fc8d5-119">It may be time to ditch your on premises authentication services</span></span>](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/)

>[!div class="step-by-step"]
><span data-ttu-id="fc8d5-120">[上一页](identity.md)
>[下一页](azure-active-directory.md)</span><span class="sxs-lookup"><span data-stu-id="fc8d5-120">[Previous](identity.md)
[Next](azure-active-directory.md)</span></span>

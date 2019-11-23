---
title: Azure Active Directory
description: 构建适用于 Azure 的云本机 .NET 应用 |Azure Active Directory
ms.date: 06/30/2019
ms.openlocfilehash: 207043507a9052c47683383a98cef6417a1a2740
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2019
ms.locfileid: "73840729"
---
# <a name="azure-active-directory"></a><span data-ttu-id="06d53-103">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="06d53-103">Azure Active Directory</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="06d53-104">Microsoft Azure Active Directory （Azure AD）以服务的形式提供标识和访问管理。</span><span class="sxs-lookup"><span data-stu-id="06d53-104">Microsoft Azure Active Directory (Azure AD) offers identity and access management as a service.</span></span> <span data-ttu-id="06d53-105">客户使用它来配置和维护用户是谁、存储他们的信息、谁可以访问该信息、谁可以管理该信息以及哪些应用程序可以访问它。</span><span class="sxs-lookup"><span data-stu-id="06d53-105">Customers use it to configure and maintain who users are, what information to store about them, who can access that information, who can manage it, and what apps can access it.</span></span> <span data-ttu-id="06d53-106">AAD 可以对配置为使用的应用程序的用户进行身份验证，从而提供单一登录（SSO）体验。</span><span class="sxs-lookup"><span data-stu-id="06d53-106">AAD can authenticate users for applications configured to use it, providing a single sign-on (SSO) experience.</span></span> <span data-ttu-id="06d53-107">它可以单独使用，也可以与在本地运行的 Windows AD 集成。</span><span class="sxs-lookup"><span data-stu-id="06d53-107">It can be used on its own or be integrated with Windows AD running on premises.</span></span>

<span data-ttu-id="06d53-108">为云构建 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="06d53-108">Azure AD is built for the cloud.</span></span> <span data-ttu-id="06d53-109">它确实是一种云本机标识解决方案，它使用基于 REST 的图形 API 和 OData 语法进行查询，这与使用 LDAP 的 Windows AD 不同。</span><span class="sxs-lookup"><span data-stu-id="06d53-109">It's truly a cloud-native identity solution that uses a REST-based Graph API and OData syntax for queries, unlike Windows AD, which uses LDAP.</span></span> <span data-ttu-id="06d53-110">本地 Active Directory 可以使用标识同步服务将用户属性同步到云，允许在云中使用 Azure AD 进行所有身份验证。</span><span class="sxs-lookup"><span data-stu-id="06d53-110">On premises Active Directory can sync user attributes to the cloud using Identity Sync Services, allowing all authentication to take place in the cloud using Azure AD.</span></span> <span data-ttu-id="06d53-111">或者，可以通过 "连接" 配置身份验证，通过 ADFS 传递回本地 Active Directory 以通过 Windows AD 本地完成。</span><span class="sxs-lookup"><span data-stu-id="06d53-111">Alternately, authentication can be configured via Connect to pass back to local Active Directory via ADFS to be completed by Windows AD on premises.</span></span>

<span data-ttu-id="06d53-112">Azure AD 支持公司品牌的登录屏幕、多工厂身份验证以及用于为本地托管的应用程序提供 SSO 的基于云的应用程序代理。</span><span class="sxs-lookup"><span data-stu-id="06d53-112">Azure AD supports company branded sign-in screens, multi-factory authentication, and cloud-based application proxies that are used to provide SSO for applications hosted on premises.</span></span> <span data-ttu-id="06d53-113">它提供不同类型的安全报告和警报功能。</span><span class="sxs-lookup"><span data-stu-id="06d53-113">It offers different kinds of security reporting and alert capabilities.</span></span>

## <a name="references"></a><span data-ttu-id="06d53-114">参考</span><span class="sxs-lookup"><span data-stu-id="06d53-114">References</span></span>

- [<span data-ttu-id="06d53-115">Microsoft 标识平台</span><span class="sxs-lookup"><span data-stu-id="06d53-115">Microsoft identity platform</span></span>](https://docs.microsoft.com/azure/active-directory/develop/)

>[!div class="step-by-step"]
><span data-ttu-id="06d53-116">[上一页](authentication-authorization.md)
>[下一页](identity-server.md)</span><span class="sxs-lookup"><span data-stu-id="06d53-116">[Previous](authentication-authorization.md)
[Next](identity-server.md)</span></span>

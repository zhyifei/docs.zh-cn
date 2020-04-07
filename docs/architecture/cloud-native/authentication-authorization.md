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
# <a name="authentication-and-authorization-in-cloud-native-apps"></a>云本机应用中的身份验证和授权

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

*身份验证*是确定安全主体身份的过程。 *授权*是授予经过身份验证的主体权限以执行操作或访问资源的行为。 有时身份验证将缩短为`AuthN`，授权将缩短为`AuthZ`。 云原生应用程序需要依靠基于 HTTP 的开放式协议来验证安全主体，因为客户端和应用程序都可以在世界任何平台或设备上运行。 唯一的常见因素是 HTTP。

许多组织仍然依赖于本地身份验证服务，如活动目录联合服务 （ADFS）。 虽然这种方法传统上为组织提供了良好的本地身份验证需求，但云原生应用程序受益于专为云设计的系统。 最近 2019 年，英国国家网络安全中心 （NCSC） 的一份通报指出，"使用 Azure AD 作为主要身份验证源的组织实际上将降低与 ADFS 相比的风险。 [此分析](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/)中概述的一些原因包括：

- 访问全套 Microsoft 凭据保护技术。
- 大多数组织在某种程度上已经依赖于 Azure AD。
- NTLM 哈希的双重哈希可确保折衷不会允许在本地活动目录中工作的凭据。

## <a name="references"></a>参考

- [身份验证基础知识](https://docs.microsoft.com/azure/active-directory/develop/authentication-scenarios)
- [访问令牌和声明](https://docs.microsoft.com/azure/active-directory/develop/access-tokens)
- [可能是时候放弃本地身份验证服务了](https://oxfordcomputergroup.com/resources/o365-security-native-cloud-authentication/)

>[!div class="step-by-step"]
>[上一页](identity.md)
>[下一页](azure-active-directory.md)

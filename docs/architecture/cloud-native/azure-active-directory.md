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
# <a name="azure-active-directory"></a>Azure Active Directory

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Microsoft Azure Active Directory （Azure AD）以服务的形式提供标识和访问管理。 客户使用它来配置和维护用户是谁、存储他们的信息、谁可以访问该信息、谁可以管理该信息以及哪些应用程序可以访问它。 AAD 可以对配置为使用的应用程序的用户进行身份验证，从而提供单一登录（SSO）体验。 它可以单独使用，也可以与在本地运行的 Windows AD 集成。

为云构建 Azure AD。 它确实是一种云本机标识解决方案，它使用基于 REST 的图形 API 和 OData 语法进行查询，这与使用 LDAP 的 Windows AD 不同。 本地 Active Directory 可以使用标识同步服务将用户属性同步到云，允许在云中使用 Azure AD 进行所有身份验证。 或者，可以通过 "连接" 配置身份验证，通过 ADFS 传递回本地 Active Directory 以通过 Windows AD 本地完成。

Azure AD 支持公司品牌的登录屏幕、多工厂身份验证以及用于为本地托管的应用程序提供 SSO 的基于云的应用程序代理。 它提供不同类型的安全报告和警报功能。

## <a name="references"></a>参考

- [Microsoft 标识平台](https://docs.microsoft.com/azure/active-directory/develop/)

>[!div class="step-by-step"]
>[上一页](authentication-authorization.md)
>[下一页](identity-server.md)

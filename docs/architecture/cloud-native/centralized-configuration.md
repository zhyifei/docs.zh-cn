---
title: 集中式配置
description: 使用 Azure Key Vault 进行集中配置可以更轻松地管理云本机应用。
ms.date: 06/30/2019
ms.openlocfilehash: 4c516b6773d913acd71ff06742302e9766a141e2
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2019
ms.locfileid: "73841137"
---
# <a name="centralized-configuration"></a>集中式配置

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

与传统的单实例应用程序相比，云本机应用程序需要运行更多的服务。 管理数十个相互依赖的服务的配置设置可能很困难，这就是通常为分布式应用程序实现集中式配置存储的原因。

如[第1章](introduction.md)所述，十二因素应用建议要求严格分隔代码和配置。 这意味着，将配置设置存储为代码中的常量或文本值是一个冲突。 存在此建议是因为应跨多个环境（包括开发、测试、暂存和生产）使用相同的代码。 但是，每个环境中的配置值可能会有所不同。 因此，配置值应存储在环境本身中，否则环境应将凭据存储到集中式配置存储中。

EShopOnContainers 应用程序包含每个微服务的本地应用程序设置文件。 这些文件签入到源代码管理中，但不包括诸如连接字符串或 API 密钥之类的生产机密。 在生产环境中，可能会覆盖每个服务环境变量的各个设置。 这种做法通常适用于托管应用程序，但不提供中央配置存储。 为了支持集中管理的配置设置，每个微服务都包含一个设置以在其使用本地设置或 Azure Key Vault 设置之间切换。

## <a name="azure-key-vault"></a>Azure 密钥保管库

Azure Key Vault 提供令牌、密码、证书、API 密钥和其他敏感机密的安全存储。 访问 Key Vault 需要正确的调用方身份验证和授权，在这种情况下，eShopOnContainers 微服务意味着使用 ClientId/ClientSecret 组合。 请勿将这些凭据签入源控件，而是在应用程序的环境中进行设置。 使用[Key Vault FlexVolume](https://github.com/Azure/kubernetes-keyvault-flexvol)可以实现从 AKS 的直接访问 Key Vault。

使用集中式配置，适用于整个应用程序的设置（例如集中式日志记录终结点）只能设置一次，并由分布式应用程序的每个部分使用。 尽管微服务应该彼此独立，但通常仍有一些共享依赖项，其配置详细信息可从集中式配置存储中获益。

>[!div class="step-by-step"]
>[上一页](deploy-eshoponcontainers-azure.md)
>[下一页](scale-applications.md)

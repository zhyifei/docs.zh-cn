---
title: 配置加密类
ms.date: 03/30/2017
helpviewer_keywords:
- configuration files [.NET Framework], cryptography
- cryptographic algorithms
- security [.NET Framework], encryption
- cryptography, classes
- .NET Framework application configuration, cryptography
- default cryptography
ms.assetid: eee3ccb8-2c0d-4f35-b38d-6892a46c14e5
ms.openlocfilehash: ba11eed316e227ceae4cb5acecb2b081fa8868f2
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2019
ms.locfileid: "55084401"
---
# <a name="configuring-cryptography-classes"></a><span data-ttu-id="7b537-102">配置加密类</span><span class="sxs-lookup"><span data-stu-id="7b537-102">Configuring Cryptography Classes</span></span>
<span data-ttu-id="7b537-103">[!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]允许计算机管理员配置的默认加密算法和.NET Framework 和相应地编写的应用程序使用的算法实现。</span><span class="sxs-lookup"><span data-stu-id="7b537-103">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] allows computer administrators to configure the default cryptographic algorithms and algorithm implementations that the .NET Framework and appropriately written applications use.</span></span>  <span data-ttu-id="7b537-104">例如，具有其自己的加密算法的实现的企业可以使该实现而不是实现中提供默认[!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7b537-104">For example, an enterprise that has its own implementation of a cryptographic algorithm can make that implementation the default instead of the implementation shipped in the [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].</span></span> <span data-ttu-id="7b537-105">尽管使用加密的托管应用程序始终可以选择显式绑定到特定的实现，但建议他们使用的加密配置系统创建加密对象。</span><span class="sxs-lookup"><span data-stu-id="7b537-105">Although managed applications that use cryptography can always choose to explicitly bind to a particular implementation, it is recommended that they create cryptographic objects by using the crypto configuration system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7b537-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="7b537-106">In This Section</span></span>  
 [<span data-ttu-id="7b537-107">将算法名称映射到加密类</span><span class="sxs-lookup"><span data-stu-id="7b537-107">Mapping Algorithm Names to Cryptography Classes</span></span>](../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md)  
 <span data-ttu-id="7b537-108">介绍如何将算法名称映射到加密类。</span><span class="sxs-lookup"><span data-stu-id="7b537-108">Describes how to map an algorithm name to a cryptography class.</span></span>  
  
 [<span data-ttu-id="7b537-109">将对象标识符映射到加密算法</span><span class="sxs-lookup"><span data-stu-id="7b537-109">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)  
 <span data-ttu-id="7b537-110">介绍如何将对象标识符映射到加密算法。</span><span class="sxs-lookup"><span data-stu-id="7b537-110">Describes how to map an object identifier to a cryptography algorithm.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7b537-111">相关章节</span><span class="sxs-lookup"><span data-stu-id="7b537-111">Related Sections</span></span>  
 [<span data-ttu-id="7b537-112">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="7b537-112">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)  
 <span data-ttu-id="7b537-113">提供的加密服务提供的概述[!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7b537-113">Provides an overview of cryptographic services provided by the [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].</span></span>  
  
 [<span data-ttu-id="7b537-114">加密设置架构</span><span class="sxs-lookup"><span data-stu-id="7b537-114">Cryptography Settings Schema</span></span>](../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 <span data-ttu-id="7b537-115">描述将友好算法名映射到实现密码算法的类的元素。</span><span class="sxs-lookup"><span data-stu-id="7b537-115">Describes elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>

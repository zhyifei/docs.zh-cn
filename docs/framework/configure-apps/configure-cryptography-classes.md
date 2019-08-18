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
ms.openlocfilehash: 77f26405792ac782f2a04e174e8165a09b7f22f6
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/17/2019
ms.locfileid: "69567333"
---
# <a name="configuring-cryptography-classes"></a><span data-ttu-id="22b58-102">配置加密类</span><span class="sxs-lookup"><span data-stu-id="22b58-102">Configuring Cryptography Classes</span></span>
<span data-ttu-id="22b58-103">Windows SDK 允许计算机管理员配置 .NET Framework 和适当编写的应用程序使用的默认加密算法和算法实现。</span><span class="sxs-lookup"><span data-stu-id="22b58-103">The Windows SDK allows computer administrators to configure the default cryptographic algorithms and algorithm implementations that the .NET Framework and appropriately written applications use.</span></span>  <span data-ttu-id="22b58-104">例如, 具有自己的加密算法实现的企业可以使该实现成为默认实现, 而不是在 Windows SDK 中提供的实现。</span><span class="sxs-lookup"><span data-stu-id="22b58-104">For example, an enterprise that has its own implementation of a cryptographic algorithm can make that implementation the default instead of the implementation shipped in the Windows SDK.</span></span> <span data-ttu-id="22b58-105">尽管使用加密的托管应用程序始终可以选择显式绑定到特定的实现, 但建议使用加密配置系统来创建加密对象。</span><span class="sxs-lookup"><span data-stu-id="22b58-105">Although managed applications that use cryptography can always choose to explicitly bind to a particular implementation, it is recommended that they create cryptographic objects by using the crypto configuration system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="22b58-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="22b58-106">In This Section</span></span>  
 [<span data-ttu-id="22b58-107">将算法名称映射到加密类</span><span class="sxs-lookup"><span data-stu-id="22b58-107">Mapping Algorithm Names to Cryptography Classes</span></span>](../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md)  
 <span data-ttu-id="22b58-108">介绍如何将算法名称映射到加密类。</span><span class="sxs-lookup"><span data-stu-id="22b58-108">Describes how to map an algorithm name to a cryptography class.</span></span>  
  
 [<span data-ttu-id="22b58-109">将对象标识符映射到加密算法</span><span class="sxs-lookup"><span data-stu-id="22b58-109">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)  
 <span data-ttu-id="22b58-110">介绍如何将对象标识符映射到加密算法。</span><span class="sxs-lookup"><span data-stu-id="22b58-110">Describes how to map an object identifier to a cryptography algorithm.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="22b58-111">相关章节</span><span class="sxs-lookup"><span data-stu-id="22b58-111">Related Sections</span></span>  
 [<span data-ttu-id="22b58-112">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="22b58-112">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)  
 <span data-ttu-id="22b58-113">概述 Windows SDK 提供的加密服务。</span><span class="sxs-lookup"><span data-stu-id="22b58-113">Provides an overview of cryptographic services provided by the Windows SDK.</span></span>  
  
 [<span data-ttu-id="22b58-114">加密设置架构</span><span class="sxs-lookup"><span data-stu-id="22b58-114">Cryptography Settings Schema</span></span>](../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 <span data-ttu-id="22b58-115">描述将友好算法名映射到实现密码算法的类的元素。</span><span class="sxs-lookup"><span data-stu-id="22b58-115">Describes elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>

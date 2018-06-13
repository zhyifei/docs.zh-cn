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
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: b12d5d95a17439308d79d094e8c22206778f3128
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32743246"
---
# <a name="configuring-cryptography-classes"></a><span data-ttu-id="55fd0-102">配置加密类</span><span class="sxs-lookup"><span data-stu-id="55fd0-102">Configuring Cryptography Classes</span></span>
<span data-ttu-id="55fd0-103">[!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)]允许计算机管理员配置的默认加密算法和.NET Framework 和相应地编写的应用程序使用的算法实现。</span><span class="sxs-lookup"><span data-stu-id="55fd0-103">The [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] allows computer administrators to configure the default cryptographic algorithms and algorithm implementations that the .NET Framework and appropriately written applications use.</span></span>  <span data-ttu-id="55fd0-104">例如，具有自己的加密算法的实现的企业可以将该实现作为默认而不是在中提供实现[!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="55fd0-104">For example, an enterprise that has its own implementation of a cryptographic algorithm can make that implementation the default instead of the implementation shipped in the [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].</span></span> <span data-ttu-id="55fd0-105">虽然使用加密的托管应用程序始终可以选择显式地绑定到特定的实现，但建议他们通过使用加密配置系统创建加密对象。</span><span class="sxs-lookup"><span data-stu-id="55fd0-105">Although managed applications that use cryptography can always choose to explicitly bind to a particular implementation, it is recommended that they create cryptographic objects by using the crypto configuration system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="55fd0-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="55fd0-106">In This Section</span></span>  
 [<span data-ttu-id="55fd0-107">将算法名称映射到加密类</span><span class="sxs-lookup"><span data-stu-id="55fd0-107">Mapping Algorithm Names to Cryptography Classes</span></span>](../../../docs/framework/configure-apps/map-algorithm-names-to-cryptography-classes.md)  
 <span data-ttu-id="55fd0-108">描述如何将算法名称映射到加密类。</span><span class="sxs-lookup"><span data-stu-id="55fd0-108">Describes how to map an algorithm name to a cryptography class.</span></span>  
  
 [<span data-ttu-id="55fd0-109">将对象标识符映射到加密算法</span><span class="sxs-lookup"><span data-stu-id="55fd0-109">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)  
 <span data-ttu-id="55fd0-110">描述如何将对象标识符映射到加密算法。</span><span class="sxs-lookup"><span data-stu-id="55fd0-110">Describes how to map an object identifier to a cryptography algorithm.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="55fd0-111">相关章节</span><span class="sxs-lookup"><span data-stu-id="55fd0-111">Related Sections</span></span>  
 [<span data-ttu-id="55fd0-112">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="55fd0-112">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)  
 <span data-ttu-id="55fd0-113">提供的加密服务提供的概述[!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="55fd0-113">Provides an overview of cryptographic services provided by the [!INCLUDE[winsdkshort](../../../includes/winsdkshort-md.md)].</span></span>  
  
 [<span data-ttu-id="55fd0-114">加密设置架构</span><span class="sxs-lookup"><span data-stu-id="55fd0-114">Cryptography Settings Schema</span></span>](../../../docs/framework/configure-apps/file-schema/cryptography/index.md)  
 <span data-ttu-id="55fd0-115">描述将友好算法名映射到实现密码算法的类的元素。</span><span class="sxs-lookup"><span data-stu-id="55fd0-115">Describes elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>

---
title: "密码设置架构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuration schema [.NET Framework], cryptography
- elements [.NET Framework], cryptography
- schema configuration settings
- cryptography, settings schema
- cryptography, mapping algorithm names
- configuration sections [.NET Framework]
- configuration settings [.NET Framework], cryptography
ms.assetid: 1f55050a-b2a3-4868-a3c0-da20826150f3
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 6b6d9eeacb38531ced5768f29bf26de3c9294b71
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="cryptography-settings-schema"></a><span data-ttu-id="de8f8-102">密码设置架构</span><span class="sxs-lookup"><span data-stu-id="de8f8-102">Cryptography Settings Schema</span></span>
<span data-ttu-id="de8f8-103">加密设置架构包含元素，这些元素指定如何将友好算法名称映射到实现加密算法的类。</span><span class="sxs-lookup"><span data-stu-id="de8f8-103">The cryptography settings schema contains elements that specify how to map friendly algorithm names to classes that implement cryptography algorithms.</span></span>  
  
 [<span data-ttu-id="de8f8-104">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="de8f8-104">**\<configuration>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="de8f8-105">**\<mscorlib>**</span><span class="sxs-lookup"><span data-stu-id="de8f8-105">**\<mscorlib>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/mscorlib-element-for-cryptography-settings.md)  
  
 [<span data-ttu-id="de8f8-106">**\<cryptographySettings>**</span><span class="sxs-lookup"><span data-stu-id="de8f8-106">**\<cryptographySettings>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md)  
  
 [<span data-ttu-id="de8f8-107">**\<cryptoNameMapping>**</span><span class="sxs-lookup"><span data-stu-id="de8f8-107">**\<cryptoNameMapping>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptonamemapping-element.md)  
  
 [<span data-ttu-id="de8f8-108">**\<cryptoClasses>**</span><span class="sxs-lookup"><span data-stu-id="de8f8-108">**\<cryptoClasses>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclasses-element.md)  
  
 [<span data-ttu-id="de8f8-109">**\<cryptoClass>**</span><span class="sxs-lookup"><span data-stu-id="de8f8-109">**\<cryptoClass>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)  
  
 [<span data-ttu-id="de8f8-110">**\<nameEntry>**</span><span class="sxs-lookup"><span data-stu-id="de8f8-110">**\<nameEntry>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md)  
  
 [<span data-ttu-id="de8f8-111">**\<oidMap>**</span><span class="sxs-lookup"><span data-stu-id="de8f8-111">**\<oidMap>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidmap-element.md)  
  
 [<span data-ttu-id="de8f8-112">**\<oidEntry>**</span><span class="sxs-lookup"><span data-stu-id="de8f8-112">**\<oidEntry>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)  
  
|<span data-ttu-id="de8f8-113">元素</span><span class="sxs-lookup"><span data-stu-id="de8f8-113">Element</span></span>|<span data-ttu-id="de8f8-114">描述</span><span class="sxs-lookup"><span data-stu-id="de8f8-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="de8f8-115">**\<cryptoClasses**></span><span class="sxs-lookup"><span data-stu-id="de8f8-115">**\<cryptoClasses**></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclasses-element.md)|<span data-ttu-id="de8f8-116">包含密码类的列表，这些类具有到 **\<nameEntry>** 元素中的友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="de8f8-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="de8f8-117">**\<cryptoClass**></span><span class="sxs-lookup"><span data-stu-id="de8f8-117">**\<cryptoClass**></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)|<span data-ttu-id="de8f8-118">包含一个密码类，该类具有到 **\<nameEntry>** 元素中的友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="de8f8-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="de8f8-119">**\<cryptographySettings**></span><span class="sxs-lookup"><span data-stu-id="de8f8-119">**\<cryptographySettings**></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md)|<span data-ttu-id="de8f8-120">包含加密设置。</span><span class="sxs-lookup"><span data-stu-id="de8f8-120">Contains cryptography settings.</span></span>|  
|[<span data-ttu-id="de8f8-121">**\<cryptoNameMapping**></span><span class="sxs-lookup"><span data-stu-id="de8f8-121">**\<cryptoNameMapping**></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptonamemapping-element.md)|<span data-ttu-id="de8f8-122">包含类到友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="de8f8-122">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="de8f8-123">加密设置的 **\<mscorlib>** 元素</span><span class="sxs-lookup"><span data-stu-id="de8f8-123">**\<mscorlib>** element for cryptography settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/mscorlib-element-for-cryptography-settings.md)|<span data-ttu-id="de8f8-124">包含 **\<cryptographySettings>** 元素。</span><span class="sxs-lookup"><span data-stu-id="de8f8-124">Contains the **\<cryptographySettings>** element.</span></span>|  
|[<span data-ttu-id="de8f8-125">**\<nameEntry>**</span><span class="sxs-lookup"><span data-stu-id="de8f8-125">**\<nameEntry>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md)|<span data-ttu-id="de8f8-126">将类名称映射到友好算法名称，允许一个类具有多个友好名称。</span><span class="sxs-lookup"><span data-stu-id="de8f8-126">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
|[<span data-ttu-id="de8f8-127">**\<oidEntry>**</span><span class="sxs-lookup"><span data-stu-id="de8f8-127">**\<oidEntry>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)|<span data-ttu-id="de8f8-128">将 ASN.1 对象标识符 (OID) 映射到友好名称。</span><span class="sxs-lookup"><span data-stu-id="de8f8-128">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>|  
|[<span data-ttu-id="de8f8-129">**\<oidMap>**</span><span class="sxs-lookup"><span data-stu-id="de8f8-129">**\<oidMap>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidmap-element.md)|<span data-ttu-id="de8f8-130">包含映射到类的 ASN.1 OID。</span><span class="sxs-lookup"><span data-stu-id="de8f8-130">Contains ASN.1 OID mappings to classes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="de8f8-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="de8f8-131">See Also</span></span>  
 [<span data-ttu-id="de8f8-132">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="de8f8-132">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="de8f8-133">加密服务</span><span class="sxs-lookup"><span data-stu-id="de8f8-133">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)

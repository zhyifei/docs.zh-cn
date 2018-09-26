---
title: 密码设置架构
ms.date: 03/30/2017
helpviewer_keywords:
- configuration schema [.NET Framework], cryptography
- elements [.NET Framework], cryptography
- schema configuration settings
- cryptography, settings schema
- cryptography, mapping algorithm names
- configuration sections [.NET Framework]
- configuration settings [.NET Framework], cryptography
ms.assetid: 1f55050a-b2a3-4868-a3c0-da20826150f3
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 71d2edac1dd9a84c9d3c92049d2494c7c5bd54b0
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "47216339"
---
# <a name="cryptography-settings-schema"></a><span data-ttu-id="22410-102">密码设置架构</span><span class="sxs-lookup"><span data-stu-id="22410-102">Cryptography Settings Schema</span></span>
<span data-ttu-id="22410-103">加密设置架构包含元素，这些元素指定如何将友好算法名称映射到实现加密算法的类。</span><span class="sxs-lookup"><span data-stu-id="22410-103">The cryptography settings schema contains elements that specify how to map friendly algorithm names to classes that implement cryptography algorithms.</span></span>  
  
 [<span data-ttu-id="22410-104">**\<configuration>**</span><span class="sxs-lookup"><span data-stu-id="22410-104">**\<configuration>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [<span data-ttu-id="22410-105">**\<mscorlib>**</span><span class="sxs-lookup"><span data-stu-id="22410-105">**\<mscorlib>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/mscorlib-element-for-cryptography-settings.md)  
  
 [<span data-ttu-id="22410-106">**\<cryptographySettings>**</span><span class="sxs-lookup"><span data-stu-id="22410-106">**\<cryptographySettings>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md)  
  
 [<span data-ttu-id="22410-107">**\<cryptoNameMapping>**</span><span class="sxs-lookup"><span data-stu-id="22410-107">**\<cryptoNameMapping>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptonamemapping-element.md)  
  
 [<span data-ttu-id="22410-108">**\<cryptoClasses>**</span><span class="sxs-lookup"><span data-stu-id="22410-108">**\<cryptoClasses>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclasses-element.md)  
  
 [<span data-ttu-id="22410-109">**\<cryptoClass>**</span><span class="sxs-lookup"><span data-stu-id="22410-109">**\<cryptoClass>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)  
  
 [<span data-ttu-id="22410-110">**\<nameEntry>**</span><span class="sxs-lookup"><span data-stu-id="22410-110">**\<nameEntry>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md)  
  
 [<span data-ttu-id="22410-111">**\<oidMap>**</span><span class="sxs-lookup"><span data-stu-id="22410-111">**\<oidMap>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidmap-element.md)  
  
 [<span data-ttu-id="22410-112">**\<oidEntry>**</span><span class="sxs-lookup"><span data-stu-id="22410-112">**\<oidEntry>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)  
  
|<span data-ttu-id="22410-113">元素</span><span class="sxs-lookup"><span data-stu-id="22410-113">Element</span></span>|<span data-ttu-id="22410-114">描述</span><span class="sxs-lookup"><span data-stu-id="22410-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="22410-115">**\<cryptoClasses**></span><span class="sxs-lookup"><span data-stu-id="22410-115">**\<cryptoClasses**></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclasses-element.md)|<span data-ttu-id="22410-116">包含密码类的列表，这些类具有到 **\<nameEntry>** 元素中的友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="22410-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="22410-117">**\<cryptoClass**></span><span class="sxs-lookup"><span data-stu-id="22410-117">**\<cryptoClass**></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)|<span data-ttu-id="22410-118">包含一个密码类，该类具有到 **\<nameEntry>** 元素中的友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="22410-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="22410-119">**\<cryptographySettings**></span><span class="sxs-lookup"><span data-stu-id="22410-119">**\<cryptographySettings**></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md)|<span data-ttu-id="22410-120">包含加密设置。</span><span class="sxs-lookup"><span data-stu-id="22410-120">Contains cryptography settings.</span></span>|  
|[<span data-ttu-id="22410-121">**\<cryptoNameMapping**></span><span class="sxs-lookup"><span data-stu-id="22410-121">**\<cryptoNameMapping**></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptonamemapping-element.md)|<span data-ttu-id="22410-122">包含类到友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="22410-122">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="22410-123">加密设置的 **\<mscorlib>** 元素</span><span class="sxs-lookup"><span data-stu-id="22410-123">**\<mscorlib>** element for cryptography settings</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/mscorlib-element-for-cryptography-settings.md)|<span data-ttu-id="22410-124">包含 **\<cryptographySettings>** 元素。</span><span class="sxs-lookup"><span data-stu-id="22410-124">Contains the **\<cryptographySettings>** element.</span></span>|  
|[<span data-ttu-id="22410-125">**\<nameEntry>**</span><span class="sxs-lookup"><span data-stu-id="22410-125">**\<nameEntry>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md)|<span data-ttu-id="22410-126">将类名称映射到友好算法名称，允许一个类具有多个友好名称。</span><span class="sxs-lookup"><span data-stu-id="22410-126">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
|[<span data-ttu-id="22410-127">**\<oidEntry>**</span><span class="sxs-lookup"><span data-stu-id="22410-127">**\<oidEntry>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)|<span data-ttu-id="22410-128">将 ASN.1 对象标识符 (OID) 映射到友好名称。</span><span class="sxs-lookup"><span data-stu-id="22410-128">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>|  
|[<span data-ttu-id="22410-129">**\<oidMap>**</span><span class="sxs-lookup"><span data-stu-id="22410-129">**\<oidMap>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidmap-element.md)|<span data-ttu-id="22410-130">包含映射到类的 ASN.1 OID。</span><span class="sxs-lookup"><span data-stu-id="22410-130">Contains ASN.1 OID mappings to classes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="22410-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="22410-131">See Also</span></span>  
 [<span data-ttu-id="22410-132">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="22410-132">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="22410-133">加密服务</span><span class="sxs-lookup"><span data-stu-id="22410-133">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)

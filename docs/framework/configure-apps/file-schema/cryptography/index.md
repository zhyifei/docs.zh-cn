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
ms.openlocfilehash: a7964d01905be4e3dd6e8149e5533e9a2cfd9a71
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927635"
---
# <a name="cryptography-settings-schema"></a><span data-ttu-id="19073-102">密码设置架构</span><span class="sxs-lookup"><span data-stu-id="19073-102">Cryptography Settings Schema</span></span>
<span data-ttu-id="19073-103">加密设置架构包含元素，这些元素指定如何将友好算法名称映射到实现加密算法的类。</span><span class="sxs-lookup"><span data-stu-id="19073-103">The cryptography settings schema contains elements that specify how to map friendly algorithm names to classes that implement cryptography algorithms.</span></span>  
  
 [<span data-ttu-id="19073-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="19073-104">**\<configuration>**</span></span>](../configuration-element.md)  
  
 [<span data-ttu-id="19073-105"> **\<mscorlib>** </span><span class="sxs-lookup"><span data-stu-id="19073-105">**\<mscorlib>**</span></span>](mscorlib-element-for-cryptography-settings.md)  
  
 [<span data-ttu-id="19073-106"> **\<cryptographySettings>** </span><span class="sxs-lookup"><span data-stu-id="19073-106">**\<cryptographySettings>**</span></span>](cryptographysettings-element.md)  
  
 [<span data-ttu-id="19073-107"> **\<cryptoNameMapping>** </span><span class="sxs-lookup"><span data-stu-id="19073-107">**\<cryptoNameMapping>**</span></span>](cryptonamemapping-element.md)  
  
 [<span data-ttu-id="19073-108"> **\<cryptoClasses>** </span><span class="sxs-lookup"><span data-stu-id="19073-108">**\<cryptoClasses>**</span></span>](cryptoclasses-element.md)  
  
 [<span data-ttu-id="19073-109"> **\<cryptoClass>** </span><span class="sxs-lookup"><span data-stu-id="19073-109">**\<cryptoClass>**</span></span>](cryptoclass-element.md)  
  
 [<span data-ttu-id="19073-110"> **\<nameEntry>** </span><span class="sxs-lookup"><span data-stu-id="19073-110">**\<nameEntry>**</span></span>](nameentry-element.md)  
  
 [<span data-ttu-id="19073-111"> **\<oidMap>** </span><span class="sxs-lookup"><span data-stu-id="19073-111">**\<oidMap>**</span></span>](oidmap-element.md)  
  
 [<span data-ttu-id="19073-112"> **\<oidEntry>** </span><span class="sxs-lookup"><span data-stu-id="19073-112">**\<oidEntry>**</span></span>](oidentry-element.md)  
  
|<span data-ttu-id="19073-113">元素</span><span class="sxs-lookup"><span data-stu-id="19073-113">Element</span></span>|<span data-ttu-id="19073-114">描述</span><span class="sxs-lookup"><span data-stu-id="19073-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="19073-115"> **\<cryptoClasses**></span><span class="sxs-lookup"><span data-stu-id="19073-115">**\<cryptoClasses**></span></span>](cryptoclasses-element.md)|<span data-ttu-id="19073-116">包含密码类的列表，这些类具有到 **\<nameEntry>** 元素中的友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="19073-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="19073-117"> **\<cryptoClass**></span><span class="sxs-lookup"><span data-stu-id="19073-117">**\<cryptoClass**></span></span>](cryptoclass-element.md)|<span data-ttu-id="19073-118">包含一个密码类，该类具有到 **\<nameEntry>** 元素中的友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="19073-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="19073-119"> **\<cryptographySettings**></span><span class="sxs-lookup"><span data-stu-id="19073-119">**\<cryptographySettings**></span></span>](cryptographysettings-element.md)|<span data-ttu-id="19073-120">包含加密设置。</span><span class="sxs-lookup"><span data-stu-id="19073-120">Contains cryptography settings.</span></span>|  
|[<span data-ttu-id="19073-121"> **\<cryptoNameMapping**></span><span class="sxs-lookup"><span data-stu-id="19073-121">**\<cryptoNameMapping**></span></span>](cryptonamemapping-element.md)|<span data-ttu-id="19073-122">包含类到友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="19073-122">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="19073-123">加密设置的 **\<mscorlib>** 元素</span><span class="sxs-lookup"><span data-stu-id="19073-123">**\<mscorlib>** element for cryptography settings</span></span>](mscorlib-element-for-cryptography-settings.md)|<span data-ttu-id="19073-124">包含 **\<cryptographySettings>** 元素。</span><span class="sxs-lookup"><span data-stu-id="19073-124">Contains the **\<cryptographySettings>** element.</span></span>|  
|[<span data-ttu-id="19073-125"> **\<nameEntry>** </span><span class="sxs-lookup"><span data-stu-id="19073-125">**\<nameEntry>**</span></span>](nameentry-element.md)|<span data-ttu-id="19073-126">将类名称映射到友好算法名称，允许一个类具有多个友好名称。</span><span class="sxs-lookup"><span data-stu-id="19073-126">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
|[<span data-ttu-id="19073-127"> **\<oidEntry>** </span><span class="sxs-lookup"><span data-stu-id="19073-127">**\<oidEntry>**</span></span>](oidentry-element.md)|<span data-ttu-id="19073-128">将 ASN.1 对象标识符 (OID) 映射到友好名称。</span><span class="sxs-lookup"><span data-stu-id="19073-128">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>|  
|[<span data-ttu-id="19073-129"> **\<oidMap>** </span><span class="sxs-lookup"><span data-stu-id="19073-129">**\<oidMap>**</span></span>](oidmap-element.md)|<span data-ttu-id="19073-130">包含映射到类的 ASN.1 OID。</span><span class="sxs-lookup"><span data-stu-id="19073-130">Contains ASN.1 OID mappings to classes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="19073-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="19073-131">See also</span></span>

- [<span data-ttu-id="19073-132">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="19073-132">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="19073-133">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="19073-133">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)

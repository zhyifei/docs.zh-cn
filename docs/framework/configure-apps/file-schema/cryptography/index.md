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
ms.openlocfilehash: c632a15552c8ba5743aac1309098b7d7ef949bbd
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2019
ms.locfileid: "74087996"
---
# <a name="cryptography-settings-schema"></a><span data-ttu-id="d4a24-102">密码设置架构</span><span class="sxs-lookup"><span data-stu-id="d4a24-102">Cryptography Settings Schema</span></span>
<span data-ttu-id="d4a24-103">加密设置架构包含元素，这些元素指定如何将友好算法名称映射到实现加密算法的类。</span><span class="sxs-lookup"><span data-stu-id="d4a24-103">The cryptography settings schema contains elements that specify how to map friendly algorithm names to classes that implement cryptography algorithms.</span></span>  
  
<span data-ttu-id="d4a24-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d4a24-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d4a24-105">&nbsp;&nbsp;[ **\<mscorlib >** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d4a24-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>\
<span data-ttu-id="d4a24-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<g s >** ](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="d4a24-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>\
<span data-ttu-id="d4a24-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptoNameMapping >** ](cryptonamemapping-element.md)</span><span class="sxs-lookup"><span data-stu-id="d4a24-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)</span></span>\
<span data-ttu-id="d4a24-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptoClasses >** ](cryptoclasses-element.md)</span><span class="sxs-lookup"><span data-stu-id="d4a24-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClasses>**](cryptoclasses-element.md)</span></span>\
<span data-ttu-id="d4a24-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cryptoClass >** ](cryptoclass-element.md)</span><span class="sxs-lookup"><span data-stu-id="d4a24-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClass>**](cryptoclass-element.md)</span></span>\
<span data-ttu-id="d4a24-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<y >** ](nameentry-element.md)</span><span class="sxs-lookup"><span data-stu-id="d4a24-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<nameEntry>**](nameentry-element.md)</span></span>\
<span data-ttu-id="d4a24-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<oidMap >** ](oidmap-element.md)</span><span class="sxs-lookup"><span data-stu-id="d4a24-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidMap>**](oidmap-element.md)</span></span>\
<span data-ttu-id="d4a24-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<y >** ](oidentry-element.md)</span><span class="sxs-lookup"><span data-stu-id="d4a24-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidEntry>**](oidentry-element.md)</span></span>

|<span data-ttu-id="d4a24-113">元素</span><span class="sxs-lookup"><span data-stu-id="d4a24-113">Element</span></span>|<span data-ttu-id="d4a24-114">描述</span><span class="sxs-lookup"><span data-stu-id="d4a24-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d4a24-115"> **\<cryptoClasses**></span><span class="sxs-lookup"><span data-stu-id="d4a24-115">**\<cryptoClasses**></span></span>](cryptoclasses-element.md)|<span data-ttu-id="d4a24-116">包含密码类的列表，这些类具有到 **\<nameEntry>** 元素中的友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="d4a24-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="d4a24-117"> **\<cryptoClass**></span><span class="sxs-lookup"><span data-stu-id="d4a24-117">**\<cryptoClass**></span></span>](cryptoclass-element.md)|<span data-ttu-id="d4a24-118">包含一个密码类，该类具有到 **\<nameEntry>** 元素中的友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="d4a24-118">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|[<span data-ttu-id="d4a24-119"> **\<cryptographySettings**></span><span class="sxs-lookup"><span data-stu-id="d4a24-119">**\<cryptographySettings**></span></span>](cryptographysettings-element.md)|<span data-ttu-id="d4a24-120">包含加密设置。</span><span class="sxs-lookup"><span data-stu-id="d4a24-120">Contains cryptography settings.</span></span>|  
|[<span data-ttu-id="d4a24-121"> **\<cryptoNameMapping**></span><span class="sxs-lookup"><span data-stu-id="d4a24-121">**\<cryptoNameMapping**></span></span>](cryptonamemapping-element.md)|<span data-ttu-id="d4a24-122">包含类到友好名称的映射。</span><span class="sxs-lookup"><span data-stu-id="d4a24-122">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="d4a24-123">加密设置的 **\<mscorlib>** 元素</span><span class="sxs-lookup"><span data-stu-id="d4a24-123">**\<mscorlib>** element for cryptography settings</span></span>](mscorlib-element-for-cryptography-settings.md)|<span data-ttu-id="d4a24-124">包含 **\<cryptographySettings>** 元素。</span><span class="sxs-lookup"><span data-stu-id="d4a24-124">Contains the **\<cryptographySettings>** element.</span></span>|  
|[<span data-ttu-id="d4a24-125"> **\<nameEntry>** </span><span class="sxs-lookup"><span data-stu-id="d4a24-125">**\<nameEntry>**</span></span>](nameentry-element.md)|<span data-ttu-id="d4a24-126">将类名称映射到友好算法名称，允许一个类具有多个友好名称。</span><span class="sxs-lookup"><span data-stu-id="d4a24-126">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
|[<span data-ttu-id="d4a24-127"> **\<oidEntry>** </span><span class="sxs-lookup"><span data-stu-id="d4a24-127">**\<oidEntry>**</span></span>](oidentry-element.md)|<span data-ttu-id="d4a24-128">将 ASN.1 对象标识符 (OID) 映射到友好名称。</span><span class="sxs-lookup"><span data-stu-id="d4a24-128">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>|  
|[<span data-ttu-id="d4a24-129"> **\<oidMap>** </span><span class="sxs-lookup"><span data-stu-id="d4a24-129">**\<oidMap>**</span></span>](oidmap-element.md)|<span data-ttu-id="d4a24-130">包含映射到类的 ASN.1 OID。</span><span class="sxs-lookup"><span data-stu-id="d4a24-130">Contains ASN.1 OID mappings to classes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d4a24-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="d4a24-131">See also</span></span>

- [<span data-ttu-id="d4a24-132">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="d4a24-132">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="d4a24-133">加密服务</span><span class="sxs-lookup"><span data-stu-id="d4a24-133">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)

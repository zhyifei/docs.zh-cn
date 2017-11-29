---
title: "&lt;enforceFIPSPolicy&gt;元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- enforceFIPSPolicy element
- FIPS
- <enforceFIPSPolicy> element
- Federal Information Processing Standards (FIPS)
ms.assetid: c35509c4-35cf-43c0-bb47-75e4208aa24e
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9bd593c17d752b35919985aad37f675c62e6ce34
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltenforcefipspolicygt-element"></a><span data-ttu-id="da554-102">&lt;enforceFIPSPolicy&gt;元素</span><span class="sxs-lookup"><span data-stu-id="da554-102">&lt;enforceFIPSPolicy&gt; Element</span></span>
<span data-ttu-id="da554-103">指定是否强制执行以下计算机配置要求：加密算法必须符合美国联邦信息处理标准 (FIPS)。</span><span class="sxs-lookup"><span data-stu-id="da554-103">Specifies whether to enforce a computer configuration requirement that cryptographic algorithms must comply with the Federal Information Processing Standards (FIPS).</span></span>  
  
 <span data-ttu-id="da554-104">\<配置 > 元素</span><span class="sxs-lookup"><span data-stu-id="da554-104">\<configuration> Element</span></span>  
<span data-ttu-id="da554-105">\<运行时 > 元素</span><span class="sxs-lookup"><span data-stu-id="da554-105">\<runtime> Element</span></span>  
<span data-ttu-id="da554-106">\<enforceFIPSPolicy > 元素</span><span class="sxs-lookup"><span data-stu-id="da554-106">\<enforceFIPSPolicy> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da554-107">语法</span><span class="sxs-lookup"><span data-stu-id="da554-107">Syntax</span></span>  
  
```xml  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="da554-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="da554-108">Attributes and Elements</span></span>  
 <span data-ttu-id="da554-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="da554-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="da554-110">特性</span><span class="sxs-lookup"><span data-stu-id="da554-110">Attributes</span></span>  
  
|<span data-ttu-id="da554-111">特性</span><span class="sxs-lookup"><span data-stu-id="da554-111">Attribute</span></span>|<span data-ttu-id="da554-112">描述</span><span class="sxs-lookup"><span data-stu-id="da554-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="da554-113">enabled</span><span class="sxs-lookup"><span data-stu-id="da554-113">enabled</span></span>|<span data-ttu-id="da554-114">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="da554-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="da554-115">指定是否启用强制实施的加密算法必须与 FIPS 兼容的计算机配置要求。</span><span class="sxs-lookup"><span data-stu-id="da554-115">Specifies whether to enable the enforcement of a computer configuration requirement that cryptographic algorithms must be compliant with FIPS.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="da554-116">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="da554-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="da554-117">值</span><span class="sxs-lookup"><span data-stu-id="da554-117">Value</span></span>|<span data-ttu-id="da554-118">描述</span><span class="sxs-lookup"><span data-stu-id="da554-118">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="da554-119">如果你的计算机配置为要求要符合 FIPS 标准的加密算法，强制实施该要求。</span><span class="sxs-lookup"><span data-stu-id="da554-119">If your computer is configured to require cryptographic algorithms to be FIPS compliant, that requirement is enforced.</span></span> <span data-ttu-id="da554-120">如果一个类实现的算法的不符合 FIPS，构造函数或`Create`为该类的方法会引发异常，在运行时在该计算机上。</span><span class="sxs-lookup"><span data-stu-id="da554-120">If a class implements an algorithm that is not compliant with FIPS, the constructors or `Create` methods for that class throw exceptions when they are run on that computer.</span></span> <span data-ttu-id="da554-121">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="da554-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="da554-122">应用程序使用的加密算法不需要要符合 FIPS，而不考虑计算机配置。</span><span class="sxs-lookup"><span data-stu-id="da554-122">Cryptographic algorithms that are used by the application are not required to be compliant with FIPS, regardless of computer configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="da554-123">子元素</span><span class="sxs-lookup"><span data-stu-id="da554-123">Child Elements</span></span>  
 <span data-ttu-id="da554-124">无。</span><span class="sxs-lookup"><span data-stu-id="da554-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="da554-125">父元素</span><span class="sxs-lookup"><span data-stu-id="da554-125">Parent Elements</span></span>  
  
|<span data-ttu-id="da554-126">元素</span><span class="sxs-lookup"><span data-stu-id="da554-126">Element</span></span>|<span data-ttu-id="da554-127">描述</span><span class="sxs-lookup"><span data-stu-id="da554-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="da554-128">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="da554-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="da554-129">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="da554-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da554-130">备注</span><span class="sxs-lookup"><span data-stu-id="da554-130">Remarks</span></span>  
 <span data-ttu-id="da554-131">从.NET Framework 2.0 开始，将由计算机的配置控制实现加密算法的类创建。</span><span class="sxs-lookup"><span data-stu-id="da554-131">Starting with the .NET Framework 2.0, the creation of classes that implement cryptographic algorithms is controlled by the configuration of the computer.</span></span> <span data-ttu-id="da554-132">如果计算机配置为需要算法要符合 FIPS，并且一个类可实现不符合 FIPS 的算法，任何创建此类的实例尝试将引发异常。</span><span class="sxs-lookup"><span data-stu-id="da554-132">If the computer is configured to require algorithms to be compliant with FIPS, and a class implements an algorithm that is not compliant with FIPS, any attempt to create an instance of that class throws an exception.</span></span> <span data-ttu-id="da554-133">构造函数引发<xref:System.InvalidOperationException>异常，和`Create`方法将引发<xref:System.Reflection.TargetInvocationException>内部的异常<xref:System.InvalidOperationException>异常。</span><span class="sxs-lookup"><span data-stu-id="da554-133">Constructors throw an <xref:System.InvalidOperationException> exception, and `Create` methods throw a <xref:System.Reflection.TargetInvocationException> exception with an inner <xref:System.InvalidOperationException> exception.</span></span>  
  
 <span data-ttu-id="da554-134">如果你的应用程序在其配置需要与 FIPS，符合性的计算机上运行，并且你的应用程序使用不符合 FIPS 的算法，你可以使用此元素在配置文件以防止公共语言运行时 (CLR) 从强制 FIPS 符合性。</span><span class="sxs-lookup"><span data-stu-id="da554-134">If your application runs on computers whose configurations require compliance with FIPS, and your application uses an algorithm that is not compliant with FIPS, you can use this element in your configuration file to prevent the common language runtime (CLR) from enforcing FIPS compliance.</span></span> <span data-ttu-id="da554-135">此元素已引入中[!INCLUDE[net_v20SP1_long](../../../../../includes/net-v20sp1-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="da554-135">This element was introduced in the [!INCLUDE[net_v20SP1_long](../../../../../includes/net-v20sp1-long-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="da554-136">示例</span><span class="sxs-lookup"><span data-stu-id="da554-136">Example</span></span>  
 <span data-ttu-id="da554-137">下面的示例演示如何防止 CLR 强制 FIPS 符合性。</span><span class="sxs-lookup"><span data-stu-id="da554-137">The following example shows how to prevent the CLR from enforcing FIPS compliance.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="da554-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="da554-138">See Also</span></span>  
 [<span data-ttu-id="da554-139">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="da554-139">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="da554-140">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="da554-140">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="da554-141">加密模型</span><span class="sxs-lookup"><span data-stu-id="da554-141">Cryptography Model</span></span>](../../../../../docs/standard/security/cryptography-model.md)

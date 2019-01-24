---
title: '&lt;enforceFIPSPolicy&gt;元素'
ms.date: 03/30/2017
helpviewer_keywords:
- enforceFIPSPolicy element
- FIPS
- <enforceFIPSPolicy> element
- Federal Information Processing Standards (FIPS)
ms.assetid: c35509c4-35cf-43c0-bb47-75e4208aa24e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 990add41d5f48da19f6bc20e4bbff19f36132df6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54742102"
---
# <a name="ltenforcefipspolicygt-element"></a><span data-ttu-id="59b8f-102">&lt;enforceFIPSPolicy&gt;元素</span><span class="sxs-lookup"><span data-stu-id="59b8f-102">&lt;enforceFIPSPolicy&gt; Element</span></span>
<span data-ttu-id="59b8f-103">指定是否强制执行以下计算机配置要求：加密算法必须符合美国联邦信息处理标准 (FIPS)。</span><span class="sxs-lookup"><span data-stu-id="59b8f-103">Specifies whether to enforce a computer configuration requirement that cryptographic algorithms must comply with the Federal Information Processing Standards (FIPS).</span></span>  
  
 <span data-ttu-id="59b8f-104">\<配置 > 元素</span><span class="sxs-lookup"><span data-stu-id="59b8f-104">\<configuration> Element</span></span>  
<span data-ttu-id="59b8f-105">\<运行时 > 元素</span><span class="sxs-lookup"><span data-stu-id="59b8f-105">\<runtime> Element</span></span>  
<span data-ttu-id="59b8f-106">\<enforceFIPSPolicy > 元素</span><span class="sxs-lookup"><span data-stu-id="59b8f-106">\<enforceFIPSPolicy> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59b8f-107">语法</span><span class="sxs-lookup"><span data-stu-id="59b8f-107">Syntax</span></span>  
  
```xml  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59b8f-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="59b8f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="59b8f-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="59b8f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59b8f-110">特性</span><span class="sxs-lookup"><span data-stu-id="59b8f-110">Attributes</span></span>  
  
|<span data-ttu-id="59b8f-111">特性</span><span class="sxs-lookup"><span data-stu-id="59b8f-111">Attribute</span></span>|<span data-ttu-id="59b8f-112">描述</span><span class="sxs-lookup"><span data-stu-id="59b8f-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="59b8f-113">enabled</span><span class="sxs-lookup"><span data-stu-id="59b8f-113">enabled</span></span>|<span data-ttu-id="59b8f-114">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="59b8f-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="59b8f-115">指定是否启用强制执行的计算机配置要求，必须符合 FIPS 的加密算法。</span><span class="sxs-lookup"><span data-stu-id="59b8f-115">Specifies whether to enable the enforcement of a computer configuration requirement that cryptographic algorithms must be compliant with FIPS.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="59b8f-116">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="59b8f-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="59b8f-117">值</span><span class="sxs-lookup"><span data-stu-id="59b8f-117">Value</span></span>|<span data-ttu-id="59b8f-118">描述</span><span class="sxs-lookup"><span data-stu-id="59b8f-118">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="59b8f-119">如果您的计算机配置为要求要符合 FIPS 的加密算法，则强制实施该要求。</span><span class="sxs-lookup"><span data-stu-id="59b8f-119">If your computer is configured to require cryptographic algorithms to be FIPS compliant, that requirement is enforced.</span></span> <span data-ttu-id="59b8f-120">如果一个类实现一种算法，不符合 FIPS，构造函数或`Create`为该类的方法会引发异常，该计算机上运行时。</span><span class="sxs-lookup"><span data-stu-id="59b8f-120">If a class implements an algorithm that is not compliant with FIPS, the constructors or `Create` methods for that class throw exceptions when they are run on that computer.</span></span> <span data-ttu-id="59b8f-121">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="59b8f-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="59b8f-122">应用程序使用的加密算法不需要为符合 FIPS，而不考虑计算机配置。</span><span class="sxs-lookup"><span data-stu-id="59b8f-122">Cryptographic algorithms that are used by the application are not required to be compliant with FIPS, regardless of computer configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="59b8f-123">子元素</span><span class="sxs-lookup"><span data-stu-id="59b8f-123">Child Elements</span></span>  
 <span data-ttu-id="59b8f-124">无。</span><span class="sxs-lookup"><span data-stu-id="59b8f-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="59b8f-125">父元素</span><span class="sxs-lookup"><span data-stu-id="59b8f-125">Parent Elements</span></span>  
  
|<span data-ttu-id="59b8f-126">元素</span><span class="sxs-lookup"><span data-stu-id="59b8f-126">Element</span></span>|<span data-ttu-id="59b8f-127">描述</span><span class="sxs-lookup"><span data-stu-id="59b8f-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="59b8f-128">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="59b8f-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="59b8f-129">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="59b8f-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59b8f-130">备注</span><span class="sxs-lookup"><span data-stu-id="59b8f-130">Remarks</span></span>  
 <span data-ttu-id="59b8f-131">从.NET Framework 2.0 开始，由计算机的配置控制的实现加密算法的类创建。</span><span class="sxs-lookup"><span data-stu-id="59b8f-131">Starting with the .NET Framework 2.0, the creation of classes that implement cryptographic algorithms is controlled by the configuration of the computer.</span></span> <span data-ttu-id="59b8f-132">如果计算机配置为要求算法来为符合 FIPS，并且一个类实现不符合 FIPS 的算法，任何尝试创建该类的实例将引发异常。</span><span class="sxs-lookup"><span data-stu-id="59b8f-132">If the computer is configured to require algorithms to be compliant with FIPS, and a class implements an algorithm that is not compliant with FIPS, any attempt to create an instance of that class throws an exception.</span></span> <span data-ttu-id="59b8f-133">构造函数引发<xref:System.InvalidOperationException>异常，并`Create`方法抛出<xref:System.Reflection.TargetInvocationException>内部异常<xref:System.InvalidOperationException>异常。</span><span class="sxs-lookup"><span data-stu-id="59b8f-133">Constructors throw an <xref:System.InvalidOperationException> exception, and `Create` methods throw a <xref:System.Reflection.TargetInvocationException> exception with an inner <xref:System.InvalidOperationException> exception.</span></span>  
  
 <span data-ttu-id="59b8f-134">如果你的应用程序在其配置要求符合 FIPS，计算机上运行并且你的应用程序使用不符合 FIPS 的算法，您可以使用此元素在配置文件中以防止公共语言运行时 (CLR) 从强制实施的 FIPS 符合性。</span><span class="sxs-lookup"><span data-stu-id="59b8f-134">If your application runs on computers whose configurations require compliance with FIPS, and your application uses an algorithm that is not compliant with FIPS, you can use this element in your configuration file to prevent the common language runtime (CLR) from enforcing FIPS compliance.</span></span> <span data-ttu-id="59b8f-135">中引入了此元素[!INCLUDE[net_v20SP1_long](../../../../../includes/net-v20sp1-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="59b8f-135">This element was introduced in the [!INCLUDE[net_v20SP1_long](../../../../../includes/net-v20sp1-long-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="59b8f-136">示例</span><span class="sxs-lookup"><span data-stu-id="59b8f-136">Example</span></span>  
 <span data-ttu-id="59b8f-137">下面的示例显示了如何防止 CLR 强制实施 FIPS 符合性。</span><span class="sxs-lookup"><span data-stu-id="59b8f-137">The following example shows how to prevent the CLR from enforcing FIPS compliance.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="59b8f-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="59b8f-138">See also</span></span>
- [<span data-ttu-id="59b8f-139">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="59b8f-139">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="59b8f-140">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="59b8f-140">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="59b8f-141">加密模型</span><span class="sxs-lookup"><span data-stu-id="59b8f-141">Cryptography Model</span></span>](../../../../../docs/standard/security/cryptography-model.md)

---
title: <enforceFIPSPolicy> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- enforceFIPSPolicy element
- FIPS
- <enforceFIPSPolicy> element
- Federal Information Processing Standards (FIPS)
ms.assetid: c35509c4-35cf-43c0-bb47-75e4208aa24e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f13243ddef7020f4d7a50e519ae8281702b0d261
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927421"
---
# <a name="enforcefipspolicy-element"></a><span data-ttu-id="03de4-102">\<enforceFIPSPolicy > 元素</span><span class="sxs-lookup"><span data-stu-id="03de4-102">\<enforceFIPSPolicy> Element</span></span>
<span data-ttu-id="03de4-103">指定是否强制执行以下计算机配置要求：加密算法必须符合美国联邦信息处理标准 (FIPS)。</span><span class="sxs-lookup"><span data-stu-id="03de4-103">Specifies whether to enforce a computer configuration requirement that cryptographic algorithms must comply with the Federal Information Processing Standards (FIPS).</span></span>  
  
 <span data-ttu-id="03de4-104">\<配置 > 元素</span><span class="sxs-lookup"><span data-stu-id="03de4-104">\<configuration> Element</span></span>  
<span data-ttu-id="03de4-105">\<运行时 > 元素</span><span class="sxs-lookup"><span data-stu-id="03de4-105">\<runtime> Element</span></span>  
<span data-ttu-id="03de4-106">\<enforceFIPSPolicy > 元素</span><span class="sxs-lookup"><span data-stu-id="03de4-106">\<enforceFIPSPolicy> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03de4-107">语法</span><span class="sxs-lookup"><span data-stu-id="03de4-107">Syntax</span></span>  
  
```xml  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="03de4-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="03de4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="03de4-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="03de4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="03de4-110">特性</span><span class="sxs-lookup"><span data-stu-id="03de4-110">Attributes</span></span>  
  
|<span data-ttu-id="03de4-111">特性</span><span class="sxs-lookup"><span data-stu-id="03de4-111">Attribute</span></span>|<span data-ttu-id="03de4-112">描述</span><span class="sxs-lookup"><span data-stu-id="03de4-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="03de4-113">enabled</span><span class="sxs-lookup"><span data-stu-id="03de4-113">enabled</span></span>|<span data-ttu-id="03de4-114">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="03de4-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="03de4-115">指定是否允许强制执行计算机配置要求, 要求加密算法必须符合 FIPS。</span><span class="sxs-lookup"><span data-stu-id="03de4-115">Specifies whether to enable the enforcement of a computer configuration requirement that cryptographic algorithms must be compliant with FIPS.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="03de4-116">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="03de4-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="03de4-117">值</span><span class="sxs-lookup"><span data-stu-id="03de4-117">Value</span></span>|<span data-ttu-id="03de4-118">描述</span><span class="sxs-lookup"><span data-stu-id="03de4-118">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="03de4-119">如果你的计算机配置为要求加密算法符合 FIPS 标准, 则强制实施此要求。</span><span class="sxs-lookup"><span data-stu-id="03de4-119">If your computer is configured to require cryptographic algorithms to be FIPS compliant, that requirement is enforced.</span></span> <span data-ttu-id="03de4-120">如果某个类实现了不符合 FIPS 的算法, 则该类的构造函数`Create`或方法将在该计算机上运行时引发异常。</span><span class="sxs-lookup"><span data-stu-id="03de4-120">If a class implements an algorithm that is not compliant with FIPS, the constructors or `Create` methods for that class throw exceptions when they are run on that computer.</span></span> <span data-ttu-id="03de4-121">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="03de4-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="03de4-122">无论计算机配置如何, 应用程序使用的加密算法都无需符合 FIPS。</span><span class="sxs-lookup"><span data-stu-id="03de4-122">Cryptographic algorithms that are used by the application are not required to be compliant with FIPS, regardless of computer configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="03de4-123">子元素</span><span class="sxs-lookup"><span data-stu-id="03de4-123">Child Elements</span></span>  
 <span data-ttu-id="03de4-124">无。</span><span class="sxs-lookup"><span data-stu-id="03de4-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="03de4-125">父元素</span><span class="sxs-lookup"><span data-stu-id="03de4-125">Parent Elements</span></span>  
  
|<span data-ttu-id="03de4-126">元素</span><span class="sxs-lookup"><span data-stu-id="03de4-126">Element</span></span>|<span data-ttu-id="03de4-127">描述</span><span class="sxs-lookup"><span data-stu-id="03de4-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="03de4-128">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="03de4-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="03de4-129">包含有关程序集绑定和垃圾回收的信息。</span><span class="sxs-lookup"><span data-stu-id="03de4-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03de4-130">备注</span><span class="sxs-lookup"><span data-stu-id="03de4-130">Remarks</span></span>  
 <span data-ttu-id="03de4-131">从 .NET Framework 2.0 开始, 实现加密算法的类的创建由计算机的配置控制。</span><span class="sxs-lookup"><span data-stu-id="03de4-131">Starting with the .NET Framework 2.0, the creation of classes that implement cryptographic algorithms is controlled by the configuration of the computer.</span></span> <span data-ttu-id="03de4-132">如果计算机配置为要求算法符合 FIPS, 并且类实现了不符合 FIPS 的算法, 则创建该类的实例的任何尝试都将引发异常。</span><span class="sxs-lookup"><span data-stu-id="03de4-132">If the computer is configured to require algorithms to be compliant with FIPS, and a class implements an algorithm that is not compliant with FIPS, any attempt to create an instance of that class throws an exception.</span></span> <span data-ttu-id="03de4-133">构造函数引发<xref:System.InvalidOperationException>异常, 并且`Create`方法引发<xref:System.Reflection.TargetInvocationException>异常, 并出现内部<xref:System.InvalidOperationException>异常。</span><span class="sxs-lookup"><span data-stu-id="03de4-133">Constructors throw an <xref:System.InvalidOperationException> exception, and `Create` methods throw a <xref:System.Reflection.TargetInvocationException> exception with an inner <xref:System.InvalidOperationException> exception.</span></span>  
  
 <span data-ttu-id="03de4-134">如果你的应用程序运行在其配置要求符合 FIPS 的计算机上, 并且你的应用程序使用不符合 FIPS 的算法, 则可以使用配置文件中的此元素来阻止公共语言运行时 (CLR)强制执行 FIPS 相容性。</span><span class="sxs-lookup"><span data-stu-id="03de4-134">If your application runs on computers whose configurations require compliance with FIPS, and your application uses an algorithm that is not compliant with FIPS, you can use this element in your configuration file to prevent the common language runtime (CLR) from enforcing FIPS compliance.</span></span> <span data-ttu-id="03de4-135">此元素是在 .NET Framework 2.0 Service Pack 1 中引入的。</span><span class="sxs-lookup"><span data-stu-id="03de4-135">This element was introduced in the .NET Framework 2.0 Service Pack 1.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03de4-136">示例</span><span class="sxs-lookup"><span data-stu-id="03de4-136">Example</span></span>  
 <span data-ttu-id="03de4-137">下面的示例演示如何阻止 CLR 强制实施 FIPS 相容性。</span><span class="sxs-lookup"><span data-stu-id="03de4-137">The following example shows how to prevent the CLR from enforcing FIPS compliance.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="03de4-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="03de4-138">See also</span></span>

- [<span data-ttu-id="03de4-139">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="03de4-139">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="03de4-140">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="03de4-140">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="03de4-141">加密模型</span><span class="sxs-lookup"><span data-stu-id="03de4-141">Cryptography Model</span></span>](../../../../standard/security/cryptography-model.md)

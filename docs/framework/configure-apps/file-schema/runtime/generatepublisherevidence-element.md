---
title: <generatePublisherEvidence> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a5314fe5927abf2d3855acb45c763507ab6cb3c8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920752"
---
# <a name="generatepublisherevidence-element"></a><span data-ttu-id="75a42-102">\<generatePublisherEvidence > 元素</span><span class="sxs-lookup"><span data-stu-id="75a42-102">\<generatePublisherEvidence> Element</span></span>
<span data-ttu-id="75a42-103">指定运行时是否为<xref:System.Security.Policy.Publisher>代码访问安全性 (CAS) 创建证据。</span><span class="sxs-lookup"><span data-stu-id="75a42-103">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence for code access security (CAS).</span></span>  
  
 <span data-ttu-id="75a42-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="75a42-104">\<configuration></span></span>  
<span data-ttu-id="75a42-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="75a42-105">\<runtime></span></span>  
<span data-ttu-id="75a42-106">\<generatePublisherEvidence></span><span class="sxs-lookup"><span data-stu-id="75a42-106">\<generatePublisherEvidence></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75a42-107">语法</span><span class="sxs-lookup"><span data-stu-id="75a42-107">Syntax</span></span>  
  
```xml  
<generatePublisherEvidence    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="75a42-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="75a42-108">Attributes and Elements</span></span>  
 <span data-ttu-id="75a42-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="75a42-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="75a42-110">特性</span><span class="sxs-lookup"><span data-stu-id="75a42-110">Attributes</span></span>  
  
|<span data-ttu-id="75a42-111">特性</span><span class="sxs-lookup"><span data-stu-id="75a42-111">Attribute</span></span>|<span data-ttu-id="75a42-112">描述</span><span class="sxs-lookup"><span data-stu-id="75a42-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="75a42-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="75a42-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="75a42-114">指定运行时是否创建<xref:System.Security.Policy.Publisher>证据。</span><span class="sxs-lookup"><span data-stu-id="75a42-114">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="75a42-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="75a42-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="75a42-116">值</span><span class="sxs-lookup"><span data-stu-id="75a42-116">Value</span></span>|<span data-ttu-id="75a42-117">描述</span><span class="sxs-lookup"><span data-stu-id="75a42-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="75a42-118">不创建<xref:System.Security.Policy.Publisher>证据。</span><span class="sxs-lookup"><span data-stu-id="75a42-118">Does not create <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
|`true`|<span data-ttu-id="75a42-119">创建<xref:System.Security.Policy.Publisher>证据。</span><span class="sxs-lookup"><span data-stu-id="75a42-119">Creates <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="75a42-120">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="75a42-120">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="75a42-121">子元素</span><span class="sxs-lookup"><span data-stu-id="75a42-121">Child Elements</span></span>  
 <span data-ttu-id="75a42-122">无。</span><span class="sxs-lookup"><span data-stu-id="75a42-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="75a42-123">父元素</span><span class="sxs-lookup"><span data-stu-id="75a42-123">Parent Elements</span></span>  
  
|<span data-ttu-id="75a42-124">元素</span><span class="sxs-lookup"><span data-stu-id="75a42-124">Element</span></span>|<span data-ttu-id="75a42-125">描述</span><span class="sxs-lookup"><span data-stu-id="75a42-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="75a42-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="75a42-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="75a42-127">包含有关运行时初始化选项的信息。</span><span class="sxs-lookup"><span data-stu-id="75a42-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75a42-128">备注</span><span class="sxs-lookup"><span data-stu-id="75a42-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="75a42-129">在 .NET Framework 4 及更高版本中, 此元素对程序集加载时间没有影响。</span><span class="sxs-lookup"><span data-stu-id="75a42-129">In the .NET Framework 4 and later, this element has no effect on assembly load times.</span></span> <span data-ttu-id="75a42-130">有关详细信息, 请参阅[安全更改](../../../security/security-changes.md)中的 "安全策略简化" 部分。</span><span class="sxs-lookup"><span data-stu-id="75a42-130">For more information, see the "Security Policy Simplification" section in [Security Changes](../../../security/security-changes.md).</span></span>  
  
 <span data-ttu-id="75a42-131">公共语言运行时 (CLR) 尝试在加载时验证 Authenticode 签名, 以创建<xref:System.Security.Policy.Publisher>程序集的证据。</span><span class="sxs-lookup"><span data-stu-id="75a42-131">The common language runtime (CLR) tries to verify the Authenticode signature at load time to create <xref:System.Security.Policy.Publisher> evidence for the assembly.</span></span> <span data-ttu-id="75a42-132">但是, 默认情况下, 大多数应用程序不<xref:System.Security.Policy.Publisher>需要证据。</span><span class="sxs-lookup"><span data-stu-id="75a42-132">However, by default, most applications do not need <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="75a42-133">标准 CAS 策略不依赖<xref:System.Security.Policy.PublisherMembershipCondition>于。</span><span class="sxs-lookup"><span data-stu-id="75a42-133">Standard CAS policy does not rely on the <xref:System.Security.Policy.PublisherMembershipCondition>.</span></span> <span data-ttu-id="75a42-134">除非你的应用程序在具有自定义 CAS 策略的计算机上执行, 或者要在部分信任环境中满足的<xref:System.Security.Permissions.PublisherIdentityPermission>要求, 否则, 应避免与验证发行者签名相关的不必要的启动成本。</span><span class="sxs-lookup"><span data-stu-id="75a42-134">You should avoid the unnecessary startup cost associated with verifying the publisher signature unless your application executes on a computer with custom CAS policy, or is intending to satisfy demands for <xref:System.Security.Permissions.PublisherIdentityPermission> in a partial-trust environment.</span></span> <span data-ttu-id="75a42-135">(在完全信任的环境中, 标识权限的要求始终成功。)</span><span class="sxs-lookup"><span data-stu-id="75a42-135">(Demands for identity permissions always succeed in a full-trust environment.)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="75a42-136">建议服务使用`<generatePublisherEvidence>`元素以提高启动性能。</span><span class="sxs-lookup"><span data-stu-id="75a42-136">We recommend that services use the `<generatePublisherEvidence>` element to improve startup performance.</span></span>  <span data-ttu-id="75a42-137">使用此元素还有助于避免可能导致超时和取消服务启动的延迟。</span><span class="sxs-lookup"><span data-stu-id="75a42-137">Using this element can also help avoid delays that can cause a time-out and the cancellation of the service startup.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="75a42-138">配置文件</span><span class="sxs-lookup"><span data-stu-id="75a42-138">Configuration File</span></span>  
 <span data-ttu-id="75a42-139">此元素只能在应用程序配置文件中使用。</span><span class="sxs-lookup"><span data-stu-id="75a42-139">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75a42-140">示例</span><span class="sxs-lookup"><span data-stu-id="75a42-140">Example</span></span>  
 <span data-ttu-id="75a42-141">下面的示例演示如何使用`<generatePublisherEvidence>`元素禁用应用程序的 CAS 发行者策略检查。</span><span class="sxs-lookup"><span data-stu-id="75a42-141">The following example shows how to use the `<generatePublisherEvidence>` element to disable checking for CAS publisher policy for an application.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="75a42-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="75a42-142">See also</span></span>

- [<span data-ttu-id="75a42-143">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="75a42-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="75a42-144">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="75a42-144">Configuration File Schema</span></span>](../index.md)

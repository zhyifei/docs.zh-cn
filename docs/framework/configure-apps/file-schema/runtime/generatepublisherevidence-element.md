---
title: <generatePublisherEvidence> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1a0861436ca727d63cdae58e3222826bf6414610
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489443"
---
# <a name="generatepublisherevidence-element"></a><span data-ttu-id="35b44-102">\<generatePublisherEvidence > 元素</span><span class="sxs-lookup"><span data-stu-id="35b44-102">\<generatePublisherEvidence> Element</span></span>
<span data-ttu-id="35b44-103">指定是否在运行时创建<xref:System.Security.Policy.Publisher>代码访问安全性 (CAS) 的证据。</span><span class="sxs-lookup"><span data-stu-id="35b44-103">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence for code access security (CAS).</span></span>  
  
 <span data-ttu-id="35b44-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="35b44-104">\<configuration></span></span>  
<span data-ttu-id="35b44-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="35b44-105">\<runtime></span></span>  
<span data-ttu-id="35b44-106">\<generatePublisherEvidence></span><span class="sxs-lookup"><span data-stu-id="35b44-106">\<generatePublisherEvidence></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35b44-107">语法</span><span class="sxs-lookup"><span data-stu-id="35b44-107">Syntax</span></span>  
  
```xml  
<generatePublisherEvidence    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="35b44-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="35b44-108">Attributes and Elements</span></span>  
 <span data-ttu-id="35b44-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="35b44-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="35b44-110">特性</span><span class="sxs-lookup"><span data-stu-id="35b44-110">Attributes</span></span>  
  
|<span data-ttu-id="35b44-111">特性</span><span class="sxs-lookup"><span data-stu-id="35b44-111">Attribute</span></span>|<span data-ttu-id="35b44-112">描述</span><span class="sxs-lookup"><span data-stu-id="35b44-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="35b44-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="35b44-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="35b44-114">指定是否在运行时创建<xref:System.Security.Policy.Publisher>证据。</span><span class="sxs-lookup"><span data-stu-id="35b44-114">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="35b44-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="35b44-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="35b44-116">值</span><span class="sxs-lookup"><span data-stu-id="35b44-116">Value</span></span>|<span data-ttu-id="35b44-117">描述</span><span class="sxs-lookup"><span data-stu-id="35b44-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="35b44-118">不会创建<xref:System.Security.Policy.Publisher>证据。</span><span class="sxs-lookup"><span data-stu-id="35b44-118">Does not create <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
|`true`|<span data-ttu-id="35b44-119">创建<xref:System.Security.Policy.Publisher>证据。</span><span class="sxs-lookup"><span data-stu-id="35b44-119">Creates <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="35b44-120">这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="35b44-120">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="35b44-121">子元素</span><span class="sxs-lookup"><span data-stu-id="35b44-121">Child Elements</span></span>  
 <span data-ttu-id="35b44-122">无。</span><span class="sxs-lookup"><span data-stu-id="35b44-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="35b44-123">父元素</span><span class="sxs-lookup"><span data-stu-id="35b44-123">Parent Elements</span></span>  
  
|<span data-ttu-id="35b44-124">元素</span><span class="sxs-lookup"><span data-stu-id="35b44-124">Element</span></span>|<span data-ttu-id="35b44-125">描述</span><span class="sxs-lookup"><span data-stu-id="35b44-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="35b44-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="35b44-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="35b44-127">包含有关运行时初始化选项的信息。</span><span class="sxs-lookup"><span data-stu-id="35b44-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35b44-128">备注</span><span class="sxs-lookup"><span data-stu-id="35b44-128">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="35b44-129">在.NET Framework 4 及更高版本，此元素将具有对程序集加载时间没有影响。</span><span class="sxs-lookup"><span data-stu-id="35b44-129">In the .NET Framework 4 and later, this element has no effect on assembly load times.</span></span> <span data-ttu-id="35b44-130">有关详细信息，请参阅中的"安全策略简化"一节[安全更改](../../../../../docs/framework/security/security-changes.md)。</span><span class="sxs-lookup"><span data-stu-id="35b44-130">For more information, see the "Security Policy Simplification" section in [Security Changes](../../../../../docs/framework/security/security-changes.md).</span></span>  
  
 <span data-ttu-id="35b44-131">公共语言运行时 (CLR) 尝试在加载时，若要创建验证 Authenticode 签名<xref:System.Security.Policy.Publisher>程序集证据。</span><span class="sxs-lookup"><span data-stu-id="35b44-131">The common language runtime (CLR) tries to verify the Authenticode signature at load time to create <xref:System.Security.Policy.Publisher> evidence for the assembly.</span></span> <span data-ttu-id="35b44-132">但是，默认情况下，大多数应用程序不需要<xref:System.Security.Policy.Publisher>证据。</span><span class="sxs-lookup"><span data-stu-id="35b44-132">However, by default, most applications do not need <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="35b44-133">标准 CAS 策略不依赖于<xref:System.Security.Policy.PublisherMembershipCondition>。</span><span class="sxs-lookup"><span data-stu-id="35b44-133">Standard CAS policy does not rely on the <xref:System.Security.Policy.PublisherMembershipCondition>.</span></span> <span data-ttu-id="35b44-134">应避免与验证发布者签名，除非你的应用程序使用的自定义 CA 策略的计算机上执行，或要满足的需求关联的不必要的启动成本<xref:System.Security.Permissions.PublisherIdentityPermission>在部分信任环境中。</span><span class="sxs-lookup"><span data-stu-id="35b44-134">You should avoid the unnecessary startup cost associated with verifying the publisher signature unless your application executes on a computer with custom CAS policy, or is intending to satisfy demands for <xref:System.Security.Permissions.PublisherIdentityPermission> in a partial-trust environment.</span></span> <span data-ttu-id="35b44-135">（标识权限的要求总是在完全信任环境中成功。）</span><span class="sxs-lookup"><span data-stu-id="35b44-135">(Demands for identity permissions always succeed in a full-trust environment.)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="35b44-136">我们建议服务使用`<generatePublisherEvidence>`元素以提高启动性能。</span><span class="sxs-lookup"><span data-stu-id="35b44-136">We recommend that services use the `<generatePublisherEvidence>` element to improve startup performance.</span></span>  <span data-ttu-id="35b44-137">使用此元素还有助于避免可能导致超时和取消的服务启动的延迟。</span><span class="sxs-lookup"><span data-stu-id="35b44-137">Using this element can also help avoid delays that can cause a time-out and the cancellation of the service startup.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="35b44-138">配置文件</span><span class="sxs-lookup"><span data-stu-id="35b44-138">Configuration File</span></span>  
 <span data-ttu-id="35b44-139">仅在应用程序配置文件中，可以使用此元素。</span><span class="sxs-lookup"><span data-stu-id="35b44-139">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35b44-140">示例</span><span class="sxs-lookup"><span data-stu-id="35b44-140">Example</span></span>  
 <span data-ttu-id="35b44-141">下面的示例演示如何使用`<generatePublisherEvidence>`要禁用检查应用程序的 CA 发布服务器策略元素。</span><span class="sxs-lookup"><span data-stu-id="35b44-141">The following example shows how to use the `<generatePublisherEvidence>` element to disable checking for CAS publisher policy for an application.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="35b44-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="35b44-142">See also</span></span>

- [<span data-ttu-id="35b44-143">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="35b44-143">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="35b44-144">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="35b44-144">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)

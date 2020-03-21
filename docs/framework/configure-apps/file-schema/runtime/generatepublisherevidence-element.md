---
title: <generatePublisherEvidence> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- generatePublisherEvidence element
- <generatePublisherEvidence> element
ms.assetid: 7d208f50-e8d5-4a42-bc1a-1cf3590706a8
ms.openlocfilehash: 24a5ea02992a5bce681b5bab4fb7f75505bd225d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154097"
---
# <a name="generatepublisherevidence-element"></a><span data-ttu-id="e9b94-102">\<generatePublisherEvidence> 元素</span><span class="sxs-lookup"><span data-stu-id="e9b94-102">\<generatePublisherEvidence> Element</span></span>
<span data-ttu-id="e9b94-103">指定运行时是否为代码访问<xref:System.Security.Policy.Publisher>安全性 （CAS） 创建证据。</span><span class="sxs-lookup"><span data-stu-id="e9b94-103">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence for code access security (CAS).</span></span>  
  
<span data-ttu-id="e9b94-104">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e9b94-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e9b94-105">&nbsp;&nbsp;[**\<运行时>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="e9b94-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="e9b94-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<生成发布者证据>**</span><span class="sxs-lookup"><span data-stu-id="e9b94-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<generatePublisherEvidence>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9b94-107">语法</span><span class="sxs-lookup"><span data-stu-id="e9b94-107">Syntax</span></span>  
  
```xml  
<generatePublisherEvidence
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9b94-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e9b94-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e9b94-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e9b94-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9b94-110">属性</span><span class="sxs-lookup"><span data-stu-id="e9b94-110">Attributes</span></span>  
  
|<span data-ttu-id="e9b94-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="e9b94-111">Attribute</span></span>|<span data-ttu-id="e9b94-112">说明</span><span class="sxs-lookup"><span data-stu-id="e9b94-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="e9b94-113">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="e9b94-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="e9b94-114">指定运行时是否创建<xref:System.Security.Policy.Publisher>证据。</span><span class="sxs-lookup"><span data-stu-id="e9b94-114">Specifies whether the runtime creates <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="e9b94-115">enabled 特性</span><span class="sxs-lookup"><span data-stu-id="e9b94-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="e9b94-116">值</span><span class="sxs-lookup"><span data-stu-id="e9b94-116">Value</span></span>|<span data-ttu-id="e9b94-117">说明</span><span class="sxs-lookup"><span data-stu-id="e9b94-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="e9b94-118">不创建<xref:System.Security.Policy.Publisher>证据。</span><span class="sxs-lookup"><span data-stu-id="e9b94-118">Does not create <xref:System.Security.Policy.Publisher> evidence.</span></span>|  
|`true`|<span data-ttu-id="e9b94-119">创建<xref:System.Security.Policy.Publisher>证据。</span><span class="sxs-lookup"><span data-stu-id="e9b94-119">Creates <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="e9b94-120">这是默认值。</span><span class="sxs-lookup"><span data-stu-id="e9b94-120">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e9b94-121">子元素</span><span class="sxs-lookup"><span data-stu-id="e9b94-121">Child Elements</span></span>  
 <span data-ttu-id="e9b94-122">无。</span><span class="sxs-lookup"><span data-stu-id="e9b94-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e9b94-123">父元素</span><span class="sxs-lookup"><span data-stu-id="e9b94-123">Parent Elements</span></span>  
  
|<span data-ttu-id="e9b94-124">元素</span><span class="sxs-lookup"><span data-stu-id="e9b94-124">Element</span></span>|<span data-ttu-id="e9b94-125">说明</span><span class="sxs-lookup"><span data-stu-id="e9b94-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e9b94-126">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="e9b94-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="e9b94-127">包含有关运行时初始化选项的信息。</span><span class="sxs-lookup"><span data-stu-id="e9b94-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9b94-128">备注</span><span class="sxs-lookup"><span data-stu-id="e9b94-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e9b94-129">在 .NET 框架 4 及更高版本中，此元素对程序集加载时间没有影响。</span><span class="sxs-lookup"><span data-stu-id="e9b94-129">In the .NET Framework 4 and later, this element has no effect on assembly load times.</span></span> <span data-ttu-id="e9b94-130">有关详细信息，请参阅[安全更改](../../../security/security-changes.md)中的"安全策略简化"部分。</span><span class="sxs-lookup"><span data-stu-id="e9b94-130">For more information, see the "Security Policy Simplification" section in [Security Changes](../../../security/security-changes.md).</span></span>  
  
 <span data-ttu-id="e9b94-131">通用语言运行时 （CLR） 尝试在加载时验证身份验证签名，以创建程序集<xref:System.Security.Policy.Publisher>的证据。</span><span class="sxs-lookup"><span data-stu-id="e9b94-131">The common language runtime (CLR) tries to verify the Authenticode signature at load time to create <xref:System.Security.Policy.Publisher> evidence for the assembly.</span></span> <span data-ttu-id="e9b94-132">但是，默认情况下，大多数应用程序不需要<xref:System.Security.Policy.Publisher>证据。</span><span class="sxs-lookup"><span data-stu-id="e9b94-132">However, by default, most applications do not need <xref:System.Security.Policy.Publisher> evidence.</span></span> <span data-ttu-id="e9b94-133">标准 CAS 策略不依赖于<xref:System.Security.Policy.PublisherMembershipCondition>。</span><span class="sxs-lookup"><span data-stu-id="e9b94-133">Standard CAS policy does not rely on the <xref:System.Security.Policy.PublisherMembershipCondition>.</span></span> <span data-ttu-id="e9b94-134">您应该避免与验证发布者签名相关的不必要的启动成本，除非您的应用程序在具有自定义 CAS 策略的计算机上执行，或者打算满足部分信任环境中的需求<xref:System.Security.Permissions.PublisherIdentityPermission>。</span><span class="sxs-lookup"><span data-stu-id="e9b94-134">You should avoid the unnecessary startup cost associated with verifying the publisher signature unless your application executes on a computer with custom CAS policy, or is intending to satisfy demands for <xref:System.Security.Permissions.PublisherIdentityPermission> in a partial-trust environment.</span></span> <span data-ttu-id="e9b94-135">（对标识权限的要求总是在完全信任的环境中成功。</span><span class="sxs-lookup"><span data-stu-id="e9b94-135">(Demands for identity permissions always succeed in a full-trust environment.)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e9b94-136">我们建议服务使用 元素`<generatePublisherEvidence>`来提高启动性能。</span><span class="sxs-lookup"><span data-stu-id="e9b94-136">We recommend that services use the `<generatePublisherEvidence>` element to improve startup performance.</span></span>  <span data-ttu-id="e9b94-137">使用此元素还有助于避免可能导致超时和服务启动取消的延迟。</span><span class="sxs-lookup"><span data-stu-id="e9b94-137">Using this element can also help avoid delays that can cause a time-out and the cancellation of the service startup.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="e9b94-138">配置文件</span><span class="sxs-lookup"><span data-stu-id="e9b94-138">Configuration File</span></span>  
 <span data-ttu-id="e9b94-139">此元素只能在应用程序配置文件中使用。</span><span class="sxs-lookup"><span data-stu-id="e9b94-139">This element can be used only in the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9b94-140">示例</span><span class="sxs-lookup"><span data-stu-id="e9b94-140">Example</span></span>  
 <span data-ttu-id="e9b94-141">下面的示例演示如何使用 元素`<generatePublisherEvidence>`来禁用检查应用程序的 CAS 发布者策略。</span><span class="sxs-lookup"><span data-stu-id="e9b94-141">The following example shows how to use the `<generatePublisherEvidence>` element to disable checking for CAS publisher policy for an application.</span></span>  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e9b94-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e9b94-142">See also</span></span>

- [<span data-ttu-id="e9b94-143">运行时设置架构</span><span class="sxs-lookup"><span data-stu-id="e9b94-143">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e9b94-144">配置文件架构</span><span class="sxs-lookup"><span data-stu-id="e9b94-144">Configuration File Schema</span></span>](../index.md)

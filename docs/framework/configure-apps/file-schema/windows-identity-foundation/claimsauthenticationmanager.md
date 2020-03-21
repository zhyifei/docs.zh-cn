---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: a54fc2cea84bb9d08a9725d846fe38efd7b5475a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152744"
---
# <a name="claimsauthenticationmanager"></a><span data-ttu-id="e85ee-101">\<声明身份验证管理器></span><span class="sxs-lookup"><span data-stu-id="e85ee-101">\<claimsAuthenticationManager></span></span>
<span data-ttu-id="e85ee-102">注册传入声明的声明身份验证管理器。</span><span class="sxs-lookup"><span data-stu-id="e85ee-102">Registers a claims authentication manager for the incoming claims.</span></span>  
  
<span data-ttu-id="e85ee-103">[**\<配置>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e85ee-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e85ee-104">&nbsp;&nbsp;[**\<系统.身份模型>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="e85ee-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="e85ee-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<身份配置>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="e85ee-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="e85ee-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<声明身份验证管理器>**</span><span class="sxs-lookup"><span data-stu-id="e85ee-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthenticationManager>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e85ee-107">语法</span><span class="sxs-lookup"><span data-stu-id="e85ee-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e85ee-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e85ee-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e85ee-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e85ee-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e85ee-110">属性</span><span class="sxs-lookup"><span data-stu-id="e85ee-110">Attributes</span></span>  
  
|<span data-ttu-id="e85ee-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="e85ee-111">Attribute</span></span>|<span data-ttu-id="e85ee-112">说明</span><span class="sxs-lookup"><span data-stu-id="e85ee-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e85ee-113">type</span><span class="sxs-lookup"><span data-stu-id="e85ee-113">type</span></span>|<span data-ttu-id="e85ee-114">指定派生自类的<xref:System.Security.Claims.ClaimsAuthenticationManager>自定义类型。</span><span class="sxs-lookup"><span data-stu-id="e85ee-114">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="e85ee-115">有关如何指定属性的详细信息，`type`请参阅 [自定义类型引用]。</span><span class="sxs-lookup"><span data-stu-id="e85ee-115">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e85ee-116">子元素</span><span class="sxs-lookup"><span data-stu-id="e85ee-116">Child Elements</span></span>  
 <span data-ttu-id="e85ee-117">如果没有`type`属性，或者该`type`属性引用该<xref:System.Security.Claims.ClaimsAuthenticationManager>类，则`<claimsAuthenticationManager>`元素不会采用子元素;如果该属性引用该类，则元素不会采用子元素。但是，派生自的<xref:System.Security.Claims.ClaimsAuthenticationManager>类可以定义子配置元素。</span><span class="sxs-lookup"><span data-stu-id="e85ee-117">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e85ee-118">父元素</span><span class="sxs-lookup"><span data-stu-id="e85ee-118">Parent Elements</span></span>  
  
|<span data-ttu-id="e85ee-119">元素</span><span class="sxs-lookup"><span data-stu-id="e85ee-119">Element</span></span>|<span data-ttu-id="e85ee-120">说明</span><span class="sxs-lookup"><span data-stu-id="e85ee-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e85ee-121">\<身份配置></span><span class="sxs-lookup"><span data-stu-id="e85ee-121">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="e85ee-122">指定服务级别标识设置。</span><span class="sxs-lookup"><span data-stu-id="e85ee-122">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e85ee-123">备注</span><span class="sxs-lookup"><span data-stu-id="e85ee-123">Remarks</span></span>  
 <span data-ttu-id="e85ee-124">通过<xref:System.Security.Claims.ClaimsAuthenticationManager>类提供的默认行为与传入的声明相呼应。</span><span class="sxs-lookup"><span data-stu-id="e85ee-124">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="e85ee-125">如果未`type`指定属性或`type`属性指定类，<xref:System.Security.Claims.ClaimsAuthenticationManager>则`<claimsAuthenticationManager>`元素不会采用子元素。</span><span class="sxs-lookup"><span data-stu-id="e85ee-125">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="e85ee-126">可以指定属性`type`以注册从<xref:System.Security.Claims.ClaimsAuthenticationManager>类派生的类型以实现自定义行为。</span><span class="sxs-lookup"><span data-stu-id="e85ee-126">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="e85ee-127">派生类可以通过重写`<claimsAuthenticationManager>`<xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A>处理这些元素的方法来支持通过元素的子元素进行配置。</span><span class="sxs-lookup"><span data-stu-id="e85ee-127">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="e85ee-128">为子元素定义的架构由类的设计器决定。</span><span class="sxs-lookup"><span data-stu-id="e85ee-128">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="e85ee-129">元素`<claimsAuthenticationManager>`设置<xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="e85ee-129">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e85ee-130">示例</span><span class="sxs-lookup"><span data-stu-id="e85ee-130">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>
    </identityConfiguration>  
</system.identityModel>  
```

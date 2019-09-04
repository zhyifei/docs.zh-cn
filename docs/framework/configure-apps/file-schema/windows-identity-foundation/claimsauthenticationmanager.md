---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: c901daf4d442a206345301795c7a4bdc076329cd
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252093"
---
# <a name="claimsauthenticationmanager"></a><span data-ttu-id="5a106-101">\<claimsAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="5a106-101">\<claimsAuthenticationManager></span></span>
<span data-ttu-id="5a106-102">为传入声明注册声明身份验证管理器。</span><span class="sxs-lookup"><span data-stu-id="5a106-102">Registers a claims authentication manager for the incoming claims.</span></span>  
  
<span data-ttu-id="5a106-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5a106-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5a106-104">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="5a106-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="5a106-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="5a106-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="5a106-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<claimsAuthenticationManager >**</span><span class="sxs-lookup"><span data-stu-id="5a106-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<claimsAuthenticationManager>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a106-107">语法</span><span class="sxs-lookup"><span data-stu-id="5a106-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5a106-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5a106-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5a106-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5a106-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5a106-110">特性</span><span class="sxs-lookup"><span data-stu-id="5a106-110">Attributes</span></span>  
  
|<span data-ttu-id="5a106-111">特性</span><span class="sxs-lookup"><span data-stu-id="5a106-111">Attribute</span></span>|<span data-ttu-id="5a106-112">描述</span><span class="sxs-lookup"><span data-stu-id="5a106-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5a106-113">type</span><span class="sxs-lookup"><span data-stu-id="5a106-113">type</span></span>|<span data-ttu-id="5a106-114">指定从<xref:System.Security.Claims.ClaimsAuthenticationManager>类派生的自定义类型。</span><span class="sxs-lookup"><span data-stu-id="5a106-114">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="5a106-115">有关如何指定`type`属性的详细信息，请参阅 [自定义类型引用]。</span><span class="sxs-lookup"><span data-stu-id="5a106-115">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5a106-116">子元素</span><span class="sxs-lookup"><span data-stu-id="5a106-116">Child Elements</span></span>  
 <span data-ttu-id="5a106-117"><xref:System.Security.Claims.ClaimsAuthenticationManager> `<claimsAuthenticationManager>` <xref:System.Security.Claims.ClaimsAuthenticationManager>如果没有`type`属性，或者如果特性引用类，则元素不采用子元素; 但是，从派生的类可以定义子配置元素。 `type`</span><span class="sxs-lookup"><span data-stu-id="5a106-117">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5a106-118">父元素</span><span class="sxs-lookup"><span data-stu-id="5a106-118">Parent Elements</span></span>  
  
|<span data-ttu-id="5a106-119">元素</span><span class="sxs-lookup"><span data-stu-id="5a106-119">Element</span></span>|<span data-ttu-id="5a106-120">描述</span><span class="sxs-lookup"><span data-stu-id="5a106-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5a106-121">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="5a106-121">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="5a106-122">指定服务级别标识设置。</span><span class="sxs-lookup"><span data-stu-id="5a106-122">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a106-123">备注</span><span class="sxs-lookup"><span data-stu-id="5a106-123">Remarks</span></span>  
 <span data-ttu-id="5a106-124">通过<xref:System.Security.Claims.ClaimsAuthenticationManager>类提供的默认行为会回显传入声明。</span><span class="sxs-lookup"><span data-stu-id="5a106-124">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="5a106-125">如果未`type`指定任何特性或`type`特性指定了<xref:System.Security.Claims.ClaimsAuthenticationManager>类，则`<claimsAuthenticationManager>`元素不采用子元素。</span><span class="sxs-lookup"><span data-stu-id="5a106-125">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="5a106-126">可以指定`type`用于注册派生<xref:System.Security.Claims.ClaimsAuthenticationManager>自类的类型的属性，以实现自定义行为。</span><span class="sxs-lookup"><span data-stu-id="5a106-126">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="5a106-127">派生类可以通过`<claimsAuthenticationManager>` <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A>重写方法来处理这些元素，从而支持通过元素的子元素进行的配置。</span><span class="sxs-lookup"><span data-stu-id="5a106-127">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="5a106-128">为子元素定义的架构位于类的设计器中。</span><span class="sxs-lookup"><span data-stu-id="5a106-128">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="5a106-129">`<claimsAuthenticationManager>` 元素<xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType>设置属性。</span><span class="sxs-lookup"><span data-stu-id="5a106-129">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a106-130">示例</span><span class="sxs-lookup"><span data-stu-id="5a106-130">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</system.identityModel>  
```

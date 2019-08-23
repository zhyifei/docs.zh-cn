---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: 3602a4805e86833ba6070d801cef6758aaee8a5c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941826"
---
# <a name="claimsauthenticationmanager"></a><span data-ttu-id="28471-101">\<claimsAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="28471-101">\<claimsAuthenticationManager></span></span>
<span data-ttu-id="28471-102">为传入声明注册声明身份验证管理器。</span><span class="sxs-lookup"><span data-stu-id="28471-102">Registers a claims authentication manager for the incoming claims.</span></span>  
  
 <span data-ttu-id="28471-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="28471-103">\<system.identityModel></span></span>  
<span data-ttu-id="28471-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="28471-104">\<identityConfiguration></span></span>  
<span data-ttu-id="28471-105">\<claimsAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="28471-105">\<claimsAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28471-106">语法</span><span class="sxs-lookup"><span data-stu-id="28471-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="28471-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="28471-107">Attributes and Elements</span></span>  
 <span data-ttu-id="28471-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="28471-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="28471-109">特性</span><span class="sxs-lookup"><span data-stu-id="28471-109">Attributes</span></span>  
  
|<span data-ttu-id="28471-110">特性</span><span class="sxs-lookup"><span data-stu-id="28471-110">Attribute</span></span>|<span data-ttu-id="28471-111">描述</span><span class="sxs-lookup"><span data-stu-id="28471-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="28471-112">type</span><span class="sxs-lookup"><span data-stu-id="28471-112">type</span></span>|<span data-ttu-id="28471-113">指定从<xref:System.Security.Claims.ClaimsAuthenticationManager>类派生的自定义类型。</span><span class="sxs-lookup"><span data-stu-id="28471-113">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="28471-114">有关如何指定`type`属性的详细信息, 请参阅 [自定义类型引用]。</span><span class="sxs-lookup"><span data-stu-id="28471-114">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="28471-115">子元素</span><span class="sxs-lookup"><span data-stu-id="28471-115">Child Elements</span></span>  
 <span data-ttu-id="28471-116"><xref:System.Security.Claims.ClaimsAuthenticationManager> `<claimsAuthenticationManager>` <xref:System.Security.Claims.ClaimsAuthenticationManager>如果没有`type`属性, 或者如果特性引用类, 则元素不采用子元素; 但是, 从派生的类可以定义子配置元素。 `type`</span><span class="sxs-lookup"><span data-stu-id="28471-116">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="28471-117">父元素</span><span class="sxs-lookup"><span data-stu-id="28471-117">Parent Elements</span></span>  
  
|<span data-ttu-id="28471-118">元素</span><span class="sxs-lookup"><span data-stu-id="28471-118">Element</span></span>|<span data-ttu-id="28471-119">描述</span><span class="sxs-lookup"><span data-stu-id="28471-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="28471-120">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="28471-120">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="28471-121">指定服务级别标识设置。</span><span class="sxs-lookup"><span data-stu-id="28471-121">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28471-122">备注</span><span class="sxs-lookup"><span data-stu-id="28471-122">Remarks</span></span>  
 <span data-ttu-id="28471-123">通过<xref:System.Security.Claims.ClaimsAuthenticationManager>类提供的默认行为会回显传入声明。</span><span class="sxs-lookup"><span data-stu-id="28471-123">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="28471-124">如果未`type`指定任何特性或`type`特性指定了<xref:System.Security.Claims.ClaimsAuthenticationManager>类, 则`<claimsAuthenticationManager>`元素不采用子元素。</span><span class="sxs-lookup"><span data-stu-id="28471-124">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="28471-125">可以指定`type`用于注册派生<xref:System.Security.Claims.ClaimsAuthenticationManager>自类的类型的属性, 以实现自定义行为。</span><span class="sxs-lookup"><span data-stu-id="28471-125">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="28471-126">派生类可以通过`<claimsAuthenticationManager>` <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A>重写方法来处理这些元素, 从而支持通过元素的子元素进行的配置。</span><span class="sxs-lookup"><span data-stu-id="28471-126">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="28471-127">为子元素定义的架构位于类的设计器中。</span><span class="sxs-lookup"><span data-stu-id="28471-127">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="28471-128">`<claimsAuthenticationManager>` 元素<xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType>设置属性。</span><span class="sxs-lookup"><span data-stu-id="28471-128">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28471-129">示例</span><span class="sxs-lookup"><span data-stu-id="28471-129">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</system.identityModel>  
```

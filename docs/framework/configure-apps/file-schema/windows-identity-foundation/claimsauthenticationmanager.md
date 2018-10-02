---
title: '&lt;claimsAuthenticationManager&gt;'
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: 0ec7e44363f87e54eae97b70352f520fe87540be
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2018
ms.locfileid: "48032287"
---
# <a name="ltclaimsauthenticationmanagergt"></a><span data-ttu-id="5d5e7-102">&lt;claimsAuthenticationManager&gt;</span><span class="sxs-lookup"><span data-stu-id="5d5e7-102">&lt;claimsAuthenticationManager&gt;</span></span>
<span data-ttu-id="5d5e7-103">注册的传入声明的声明身份验证管理器。</span><span class="sxs-lookup"><span data-stu-id="5d5e7-103">Registers a claims authentication manager for the incoming claims.</span></span>  
  
 <span data-ttu-id="5d5e7-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="5d5e7-104">\<system.identityModel></span></span>  
<span data-ttu-id="5d5e7-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="5d5e7-105">\<identityConfiguration></span></span>  
<span data-ttu-id="5d5e7-106">\<claimsAuthenticationManager ></span><span class="sxs-lookup"><span data-stu-id="5d5e7-106">\<claimsAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d5e7-107">语法</span><span class="sxs-lookup"><span data-stu-id="5d5e7-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5d5e7-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="5d5e7-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5d5e7-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="5d5e7-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5d5e7-110">特性</span><span class="sxs-lookup"><span data-stu-id="5d5e7-110">Attributes</span></span>  
  
|<span data-ttu-id="5d5e7-111">特性</span><span class="sxs-lookup"><span data-stu-id="5d5e7-111">Attribute</span></span>|<span data-ttu-id="5d5e7-112">描述</span><span class="sxs-lookup"><span data-stu-id="5d5e7-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5d5e7-113">类型</span><span class="sxs-lookup"><span data-stu-id="5d5e7-113">type</span></span>|<span data-ttu-id="5d5e7-114">指定派生的自定义类型<xref:System.Security.Claims.ClaimsAuthenticationManager>类。</span><span class="sxs-lookup"><span data-stu-id="5d5e7-114">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="5d5e7-115">详细了解如何指定`type`属性，请参阅 [自定义类型引用]。</span><span class="sxs-lookup"><span data-stu-id="5d5e7-115">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5d5e7-116">子元素</span><span class="sxs-lookup"><span data-stu-id="5d5e7-116">Child Elements</span></span>  
 <span data-ttu-id="5d5e7-117">如果没有任何`type`属性，或者如果`type`属性引用<xref:System.Security.Claims.ClaimsAuthenticationManager>类，`<claimsAuthenticationManager>`元素不接受子元素; 但是，类派生自<xref:System.Security.Claims.ClaimsAuthenticationManager>可以定义子配置元素。</span><span class="sxs-lookup"><span data-stu-id="5d5e7-117">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5d5e7-118">父元素</span><span class="sxs-lookup"><span data-stu-id="5d5e7-118">Parent Elements</span></span>  
  
|<span data-ttu-id="5d5e7-119">元素</span><span class="sxs-lookup"><span data-stu-id="5d5e7-119">Element</span></span>|<span data-ttu-id="5d5e7-120">描述</span><span class="sxs-lookup"><span data-stu-id="5d5e7-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d5e7-121">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="5d5e7-121">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="5d5e7-122">指定服务级别标识设置。</span><span class="sxs-lookup"><span data-stu-id="5d5e7-122">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d5e7-123">备注</span><span class="sxs-lookup"><span data-stu-id="5d5e7-123">Remarks</span></span>  
 <span data-ttu-id="5d5e7-124">通过提供的默认行为<xref:System.Security.Claims.ClaimsAuthenticationManager>类将回显传入声明。</span><span class="sxs-lookup"><span data-stu-id="5d5e7-124">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="5d5e7-125">如果没有`type`指定属性或如果`type`特性指定<xref:System.Security.Claims.ClaimsAuthenticationManager>类，`<claimsAuthenticationManager>`元素不接受子元素。</span><span class="sxs-lookup"><span data-stu-id="5d5e7-125">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="5d5e7-126">您可以指定`type`属性来注册一个类型派生自<xref:System.Security.Claims.ClaimsAuthenticationManager>类，以实现自定义行为。</span><span class="sxs-lookup"><span data-stu-id="5d5e7-126">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="5d5e7-127">派生的类可以支持的子元素通过配置`<claimsAuthenticationManager>`通过重写元素<xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A>方法来处理这些元素。</span><span class="sxs-lookup"><span data-stu-id="5d5e7-127">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="5d5e7-128">为子元素定义的架构由类的设计器。</span><span class="sxs-lookup"><span data-stu-id="5d5e7-128">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="5d5e7-129">`<claimsAuthenticationManager>`元素集<xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="5d5e7-129">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d5e7-130">示例</span><span class="sxs-lookup"><span data-stu-id="5d5e7-130">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</microsoft.identityModel>  
```

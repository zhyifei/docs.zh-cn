---
title: <claimsAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 6d30a450-6d13-4671-81a8-77e0204500c5
author: BrucePerlerMS
ms.openlocfilehash: ecf26263bf47e8b4609e7adc208f0a59a2fa795b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667322"
---
# <a name="claimsauthenticationmanager"></a><span data-ttu-id="07712-101">\<claimsAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="07712-101">\<claimsAuthenticationManager></span></span>
<span data-ttu-id="07712-102">注册的传入声明的声明身份验证管理器。</span><span class="sxs-lookup"><span data-stu-id="07712-102">Registers a claims authentication manager for the incoming claims.</span></span>  
  
 <span data-ttu-id="07712-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="07712-103">\<system.identityModel></span></span>  
<span data-ttu-id="07712-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="07712-104">\<identityConfiguration></span></span>  
<span data-ttu-id="07712-105">\<claimsAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="07712-105">\<claimsAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07712-106">语法</span><span class="sxs-lookup"><span data-stu-id="07712-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthenticationManager type=xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthenticationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="07712-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="07712-107">Attributes and Elements</span></span>  
 <span data-ttu-id="07712-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="07712-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="07712-109">特性</span><span class="sxs-lookup"><span data-stu-id="07712-109">Attributes</span></span>  
  
|<span data-ttu-id="07712-110">特性</span><span class="sxs-lookup"><span data-stu-id="07712-110">Attribute</span></span>|<span data-ttu-id="07712-111">描述</span><span class="sxs-lookup"><span data-stu-id="07712-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="07712-112">类型</span><span class="sxs-lookup"><span data-stu-id="07712-112">type</span></span>|<span data-ttu-id="07712-113">指定派生的自定义类型<xref:System.Security.Claims.ClaimsAuthenticationManager>类。</span><span class="sxs-lookup"><span data-stu-id="07712-113">Specifies a custom type that derives from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class.</span></span> <span data-ttu-id="07712-114">详细了解如何指定`type`属性，请参阅 [自定义类型引用]。</span><span class="sxs-lookup"><span data-stu-id="07712-114">For more information about how to specify the `type` attribute, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="07712-115">子元素</span><span class="sxs-lookup"><span data-stu-id="07712-115">Child Elements</span></span>  
 <span data-ttu-id="07712-116">如果没有任何`type`属性，或者如果`type`属性引用<xref:System.Security.Claims.ClaimsAuthenticationManager>类，`<claimsAuthenticationManager>`元素不接受子元素; 但是，类派生自<xref:System.Security.Claims.ClaimsAuthenticationManager>可以定义子配置元素。</span><span class="sxs-lookup"><span data-stu-id="07712-116">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthenticationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="07712-117">父元素</span><span class="sxs-lookup"><span data-stu-id="07712-117">Parent Elements</span></span>  
  
|<span data-ttu-id="07712-118">元素</span><span class="sxs-lookup"><span data-stu-id="07712-118">Element</span></span>|<span data-ttu-id="07712-119">描述</span><span class="sxs-lookup"><span data-stu-id="07712-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="07712-120">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="07712-120">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="07712-121">指定服务级别标识设置。</span><span class="sxs-lookup"><span data-stu-id="07712-121">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07712-122">备注</span><span class="sxs-lookup"><span data-stu-id="07712-122">Remarks</span></span>  
 <span data-ttu-id="07712-123">通过提供的默认行为<xref:System.Security.Claims.ClaimsAuthenticationManager>类将回显传入声明。</span><span class="sxs-lookup"><span data-stu-id="07712-123">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthenticationManager> class echoes the incoming claims.</span></span> <span data-ttu-id="07712-124">如果没有`type`指定属性或如果`type`特性指定<xref:System.Security.Claims.ClaimsAuthenticationManager>类，`<claimsAuthenticationManager>`元素不接受子元素。</span><span class="sxs-lookup"><span data-stu-id="07712-124">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthenticationManager>` element does not take child elements.</span></span> <span data-ttu-id="07712-125">您可以指定`type`属性来注册一个类型派生自<xref:System.Security.Claims.ClaimsAuthenticationManager>类，以实现自定义行为。</span><span class="sxs-lookup"><span data-stu-id="07712-125">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthenticationManager> class to implement custom behavior.</span></span> <span data-ttu-id="07712-126">派生的类可以支持的子元素通过配置`<claimsAuthenticationManager>`通过重写元素<xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A>方法来处理这些元素。</span><span class="sxs-lookup"><span data-stu-id="07712-126">Derived classes can support configuration through child elements of the `<claimsAuthenticationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthenticationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="07712-127">为子元素定义的架构由类的设计器。</span><span class="sxs-lookup"><span data-stu-id="07712-127">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
 <span data-ttu-id="07712-128">`<claimsAuthenticationManager>`元素集<xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="07712-128">The `<claimsAuthenticationManager>` element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthenticationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07712-129">示例</span><span class="sxs-lookup"><span data-stu-id="07712-129">Example</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration name="MyIdentity">  
      <claimsAuthenticationManager type="MyNamespace.CustomClaimsAuthenticationManager, MyAssembly"/>          
    </identityConfiguration>  
</system.identityModel>  
```

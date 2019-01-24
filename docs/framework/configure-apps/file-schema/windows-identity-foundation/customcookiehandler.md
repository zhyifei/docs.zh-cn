---
title: '&lt;customCookieHandler&gt;'
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: a3d032279d0b568d7072dbbe020344365c341c1b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54724013"
---
# <a name="ltcustomcookiehandlergt"></a><span data-ttu-id="f699d-102">&lt;customCookieHandler&gt;</span><span class="sxs-lookup"><span data-stu-id="f699d-102">&lt;customCookieHandler&gt;</span></span>
<span data-ttu-id="f699d-103">设置自定义 cookie 处理程序类型。</span><span class="sxs-lookup"><span data-stu-id="f699d-103">Sets the custom cookie handler type.</span></span> <span data-ttu-id="f699d-104">此元素仅可能存在如果`mode`属性的`<cookieHandler>`元素是"自定义"。</span><span class="sxs-lookup"><span data-stu-id="f699d-104">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="f699d-105">自定义的类型必须派生自<xref:System.IdentityModel.Services.CookieHandler>类。</span><span class="sxs-lookup"><span data-stu-id="f699d-105">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="f699d-106">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="f699d-106">\<system.identityModel.services></span></span>  
<span data-ttu-id="f699d-107">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="f699d-107">\<federationConfiguration></span></span>  
<span data-ttu-id="f699d-108">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="f699d-108">\<cookieHandler></span></span>  
<span data-ttu-id="f699d-109">\<customCookieHandler></span><span class="sxs-lookup"><span data-stu-id="f699d-109">\<customCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f699d-110">语法</span><span class="sxs-lookup"><span data-stu-id="f699d-110">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Custom">  
      <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" >  
      </customCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f699d-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="f699d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="f699d-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="f699d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f699d-113">特性</span><span class="sxs-lookup"><span data-stu-id="f699d-113">Attributes</span></span>  
  
|<span data-ttu-id="f699d-114">特性</span><span class="sxs-lookup"><span data-stu-id="f699d-114">Attribute</span></span>|<span data-ttu-id="f699d-115">描述</span><span class="sxs-lookup"><span data-stu-id="f699d-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f699d-116">类型</span><span class="sxs-lookup"><span data-stu-id="f699d-116">type</span></span>|<span data-ttu-id="f699d-117">指定派生的自定义类型<xref:System.IdentityModel.Services.CookieHandler>类。</span><span class="sxs-lookup"><span data-stu-id="f699d-117">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="f699d-118">有关如何指定详细信息`type`属性，请参阅[自定义类型引用](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)。</span><span class="sxs-lookup"><span data-stu-id="f699d-118">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f699d-119">子元素</span><span class="sxs-lookup"><span data-stu-id="f699d-119">Child Elements</span></span>  
 <span data-ttu-id="f699d-120">无</span><span class="sxs-lookup"><span data-stu-id="f699d-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f699d-121">父元素</span><span class="sxs-lookup"><span data-stu-id="f699d-121">Parent Elements</span></span>  
  
|<span data-ttu-id="f699d-122">元素</span><span class="sxs-lookup"><span data-stu-id="f699d-122">Element</span></span>|<span data-ttu-id="f699d-123">描述</span><span class="sxs-lookup"><span data-stu-id="f699d-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f699d-124">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="f699d-124">\<cookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|<span data-ttu-id="f699d-125">配置<xref:System.IdentityModel.Services.CookieHandler>的<xref:System.IdentityModel.Services.SessionAuthenticationModule>用于读取和写入 cookie。</span><span class="sxs-lookup"><span data-stu-id="f699d-125">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f699d-126">备注</span><span class="sxs-lookup"><span data-stu-id="f699d-126">Remarks</span></span>  
 <span data-ttu-id="f699d-127">通过设置指定自定义 cookie 处理程序时`mode`的属性`<cookieHandler>`元素为"Custom"，必须指定自定义 cookie 处理程序的类型，通过包括`<customCookieHandler>`引用 cookie 处理程序类型的子元素。</span><span class="sxs-lookup"><span data-stu-id="f699d-127">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="f699d-128">不能为此元素时指定`mode`属性设置为"Chunked"或"Default"。</span><span class="sxs-lookup"><span data-stu-id="f699d-128">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="f699d-129">自定义 cookie 处理程序必须派生自<xref:System.IdentityModel.Services.CookieHandler>类。</span><span class="sxs-lookup"><span data-stu-id="f699d-129">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="f699d-130">`<customCookieHandler>`元素表示由<xref:System.IdentityModel.Configuration.CustomTypeElement>类。</span><span class="sxs-lookup"><span data-stu-id="f699d-130">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f699d-131">示例</span><span class="sxs-lookup"><span data-stu-id="f699d-131">Example</span></span>  
 <span data-ttu-id="f699d-132">下面的示例配置 SAM 使用的类型的自定义 cookie 处理程序`MyNamespace.MyCustomCookieHandler`。</span><span class="sxs-lookup"><span data-stu-id="f699d-132">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f699d-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="f699d-133">See also</span></span>
- <xref:System.IdentityModel.Services.CookieHandler>

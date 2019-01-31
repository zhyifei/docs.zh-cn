---
title: <customCookieHandler>
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: 752b1188fccb6f09cdcab6a50653abf26e8e2a53
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55288179"
---
# <a name="customcookiehandler"></a><span data-ttu-id="79578-101">\<customCookieHandler></span><span class="sxs-lookup"><span data-stu-id="79578-101">\<customCookieHandler></span></span>
<span data-ttu-id="79578-102">设置自定义 cookie 处理程序类型。</span><span class="sxs-lookup"><span data-stu-id="79578-102">Sets the custom cookie handler type.</span></span> <span data-ttu-id="79578-103">此元素仅可能存在如果`mode`属性的`<cookieHandler>`元素是"自定义"。</span><span class="sxs-lookup"><span data-stu-id="79578-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="79578-104">自定义的类型必须派生自<xref:System.IdentityModel.Services.CookieHandler>类。</span><span class="sxs-lookup"><span data-stu-id="79578-104">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="79578-105">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="79578-105">\<system.identityModel.services></span></span>  
<span data-ttu-id="79578-106">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="79578-106">\<federationConfiguration></span></span>  
<span data-ttu-id="79578-107">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="79578-107">\<cookieHandler></span></span>  
<span data-ttu-id="79578-108">\<customCookieHandler></span><span class="sxs-lookup"><span data-stu-id="79578-108">\<customCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79578-109">语法</span><span class="sxs-lookup"><span data-stu-id="79578-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="79578-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="79578-110">Attributes and Elements</span></span>  
 <span data-ttu-id="79578-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="79578-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="79578-112">特性</span><span class="sxs-lookup"><span data-stu-id="79578-112">Attributes</span></span>  
  
|<span data-ttu-id="79578-113">特性</span><span class="sxs-lookup"><span data-stu-id="79578-113">Attribute</span></span>|<span data-ttu-id="79578-114">描述</span><span class="sxs-lookup"><span data-stu-id="79578-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="79578-115">类型</span><span class="sxs-lookup"><span data-stu-id="79578-115">type</span></span>|<span data-ttu-id="79578-116">指定派生的自定义类型<xref:System.IdentityModel.Services.CookieHandler>类。</span><span class="sxs-lookup"><span data-stu-id="79578-116">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="79578-117">有关如何指定详细信息`type`属性，请参阅[自定义类型引用](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)。</span><span class="sxs-lookup"><span data-stu-id="79578-117">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="79578-118">子元素</span><span class="sxs-lookup"><span data-stu-id="79578-118">Child Elements</span></span>  
 <span data-ttu-id="79578-119">无</span><span class="sxs-lookup"><span data-stu-id="79578-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="79578-120">父元素</span><span class="sxs-lookup"><span data-stu-id="79578-120">Parent Elements</span></span>  
  
|<span data-ttu-id="79578-121">元素</span><span class="sxs-lookup"><span data-stu-id="79578-121">Element</span></span>|<span data-ttu-id="79578-122">描述</span><span class="sxs-lookup"><span data-stu-id="79578-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="79578-123">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="79578-123">\<cookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|<span data-ttu-id="79578-124">配置<xref:System.IdentityModel.Services.CookieHandler>的<xref:System.IdentityModel.Services.SessionAuthenticationModule>用于读取和写入 cookie。</span><span class="sxs-lookup"><span data-stu-id="79578-124">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="79578-125">备注</span><span class="sxs-lookup"><span data-stu-id="79578-125">Remarks</span></span>  
 <span data-ttu-id="79578-126">通过设置指定自定义 cookie 处理程序时`mode`的属性`<cookieHandler>`元素为"Custom"，必须指定自定义 cookie 处理程序的类型，通过包括`<customCookieHandler>`引用 cookie 处理程序类型的子元素。</span><span class="sxs-lookup"><span data-stu-id="79578-126">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="79578-127">不能为此元素时指定`mode`属性设置为"Chunked"或"Default"。</span><span class="sxs-lookup"><span data-stu-id="79578-127">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="79578-128">自定义 cookie 处理程序必须派生自<xref:System.IdentityModel.Services.CookieHandler>类。</span><span class="sxs-lookup"><span data-stu-id="79578-128">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="79578-129">`<customCookieHandler>`元素表示由<xref:System.IdentityModel.Configuration.CustomTypeElement>类。</span><span class="sxs-lookup"><span data-stu-id="79578-129">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79578-130">示例</span><span class="sxs-lookup"><span data-stu-id="79578-130">Example</span></span>  
 <span data-ttu-id="79578-131">下面的示例配置 SAM 使用的类型的自定义 cookie 处理程序`MyNamespace.MyCustomCookieHandler`。</span><span class="sxs-lookup"><span data-stu-id="79578-131">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="79578-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="79578-132">See also</span></span>
- <xref:System.IdentityModel.Services.CookieHandler>

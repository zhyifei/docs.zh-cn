---
title: '&lt;customCookieHandler&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 61b128d5856fd8e35516949b637177dc38a17164
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltcustomcookiehandlergt"></a><span data-ttu-id="d9215-102">&lt;customCookieHandler&gt;</span><span class="sxs-lookup"><span data-stu-id="d9215-102">&lt;customCookieHandler&gt;</span></span>
<span data-ttu-id="d9215-103">设置自定义 cookie 处理程序类型。</span><span class="sxs-lookup"><span data-stu-id="d9215-103">Sets the custom cookie handler type.</span></span> <span data-ttu-id="d9215-104">此元素仅可呈现如果`mode`属性`<cookieHandler>`元素是"自定义"。</span><span class="sxs-lookup"><span data-stu-id="d9215-104">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="d9215-105">自定义的类型必须派生自<xref:System.IdentityModel.Services.CookieHandler>类。</span><span class="sxs-lookup"><span data-stu-id="d9215-105">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="d9215-106">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="d9215-106">\<system.identityModel.services></span></span>  
<span data-ttu-id="d9215-107">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="d9215-107">\<federationConfiguration></span></span>  
<span data-ttu-id="d9215-108">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="d9215-108">\<cookieHandler></span></span>  
<span data-ttu-id="d9215-109">\<customCookieHandler ></span><span class="sxs-lookup"><span data-stu-id="d9215-109">\<customCookieHandler></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9215-110">语法</span><span class="sxs-lookup"><span data-stu-id="d9215-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d9215-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d9215-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d9215-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d9215-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d9215-113">特性</span><span class="sxs-lookup"><span data-stu-id="d9215-113">Attributes</span></span>  
  
|<span data-ttu-id="d9215-114">特性</span><span class="sxs-lookup"><span data-stu-id="d9215-114">Attribute</span></span>|<span data-ttu-id="d9215-115">描述</span><span class="sxs-lookup"><span data-stu-id="d9215-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d9215-116">类型</span><span class="sxs-lookup"><span data-stu-id="d9215-116">type</span></span>|<span data-ttu-id="d9215-117">指定自定义类型派生自<xref:System.IdentityModel.Services.CookieHandler>类。</span><span class="sxs-lookup"><span data-stu-id="d9215-117">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="d9215-118">有关如何指定详细信息`type`属性，请参阅[自定义类型引用](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md)。</span><span class="sxs-lookup"><span data-stu-id="d9215-118">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d9215-119">子元素</span><span class="sxs-lookup"><span data-stu-id="d9215-119">Child Elements</span></span>  
 <span data-ttu-id="d9215-120">无</span><span class="sxs-lookup"><span data-stu-id="d9215-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d9215-121">父元素</span><span class="sxs-lookup"><span data-stu-id="d9215-121">Parent Elements</span></span>  
  
|<span data-ttu-id="d9215-122">元素</span><span class="sxs-lookup"><span data-stu-id="d9215-122">Element</span></span>|<span data-ttu-id="d9215-123">描述</span><span class="sxs-lookup"><span data-stu-id="d9215-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d9215-124">\<cookieHandler ></span><span class="sxs-lookup"><span data-stu-id="d9215-124">\<cookieHandler></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/cookiehandler.md)|<span data-ttu-id="d9215-125">配置<xref:System.IdentityModel.Services.CookieHandler>，<xref:System.IdentityModel.Services.SessionAuthenticationModule>用于读取和写入 cookie。</span><span class="sxs-lookup"><span data-stu-id="d9215-125">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d9215-126">备注</span><span class="sxs-lookup"><span data-stu-id="d9215-126">Remarks</span></span>  
 <span data-ttu-id="d9215-127">当你通过设置指定的自定义 cookie 处理`mode`属性`<cookieHandler>`元素为"Custom"，必须指定自定义 cookie 处理程序的类型，通过包括`<customCookieHandler>`引用该 cookie 处理程序类型的子元素。</span><span class="sxs-lookup"><span data-stu-id="d9215-127">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="d9215-128">此元素不能为时指定`mode`属性设置为"Chunked"或"默认"。</span><span class="sxs-lookup"><span data-stu-id="d9215-128">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="d9215-129">自定义 cookie 处理程序必须派生自<xref:System.IdentityModel.Services.CookieHandler>类。</span><span class="sxs-lookup"><span data-stu-id="d9215-129">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="d9215-130">`<customCookieHandler>`元素表示由<xref:System.IdentityModel.Configuration.CustomTypeElement>类。</span><span class="sxs-lookup"><span data-stu-id="d9215-130">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9215-131">示例</span><span class="sxs-lookup"><span data-stu-id="d9215-131">Example</span></span>  
 <span data-ttu-id="d9215-132">下面的示例将配置 SAM 若要使用的类型的自定义 cookie 处理`MyNamespace.MyCustomCookieHandler`。</span><span class="sxs-lookup"><span data-stu-id="d9215-132">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d9215-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="d9215-133">See Also</span></span>  
 <xref:System.IdentityModel.Services.CookieHandler>

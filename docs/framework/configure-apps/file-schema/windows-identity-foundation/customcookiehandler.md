---
title: <customCookieHandler>
ms.date: 03/30/2017
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: BrucePerlerMS
ms.openlocfilehash: e1f32e17cf0da5e948d778e8b61aca6053eff4ef
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252022"
---
# <a name="customcookiehandler"></a><span data-ttu-id="3f4ae-101">\<customCookieHandler></span><span class="sxs-lookup"><span data-stu-id="3f4ae-101">\<customCookieHandler></span></span>
<span data-ttu-id="3f4ae-102">设置自定义 cookie 处理程序类型。</span><span class="sxs-lookup"><span data-stu-id="3f4ae-102">Sets the custom cookie handler type.</span></span> <span data-ttu-id="3f4ae-103">仅当`mode` `<cookieHandler>`元素的属性为 "Custom" 时，此元素才能存在。</span><span class="sxs-lookup"><span data-stu-id="3f4ae-103">This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom".</span></span> <span data-ttu-id="3f4ae-104">自定义类型必须派生<xref:System.IdentityModel.Services.CookieHandler>自类。</span><span class="sxs-lookup"><span data-stu-id="3f4ae-104">The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
<span data-ttu-id="3f4ae-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3f4ae-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3f4ae-106">&nbsp;&nbsp;[ **\<System.identitymodel >** ](system-identitymodel-services.md)</span><span class="sxs-lookup"><span data-stu-id="3f4ae-106">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span></span>\
<span data-ttu-id="3f4ae-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<federationConfiguration >** ](federationconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="3f4ae-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)</span></span>\
<span data-ttu-id="3f4ae-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<cookieHandler >** ](cookiehandler.md)</span><span class="sxs-lookup"><span data-stu-id="3f4ae-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cookieHandler>**](cookiehandler.md)</span></span>\
<span data-ttu-id="3f4ae-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<customCookieHandler >**</span><span class="sxs-lookup"><span data-stu-id="3f4ae-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customCookieHandler>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f4ae-110">语法</span><span class="sxs-lookup"><span data-stu-id="3f4ae-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3f4ae-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="3f4ae-111">Attributes and Elements</span></span>  
 <span data-ttu-id="3f4ae-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="3f4ae-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3f4ae-113">特性</span><span class="sxs-lookup"><span data-stu-id="3f4ae-113">Attributes</span></span>  
  
|<span data-ttu-id="3f4ae-114">特性</span><span class="sxs-lookup"><span data-stu-id="3f4ae-114">Attribute</span></span>|<span data-ttu-id="3f4ae-115">描述</span><span class="sxs-lookup"><span data-stu-id="3f4ae-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3f4ae-116">type</span><span class="sxs-lookup"><span data-stu-id="3f4ae-116">type</span></span>|<span data-ttu-id="3f4ae-117">指定从<xref:System.IdentityModel.Services.CookieHandler>类派生的自定义类型。</span><span class="sxs-lookup"><span data-stu-id="3f4ae-117">Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span> <span data-ttu-id="3f4ae-118">有关如何指定`type`属性的详细信息，请参阅[自定义类型引用](../windows-workflow-foundation/index.md)。</span><span class="sxs-lookup"><span data-stu-id="3f4ae-118">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3f4ae-119">子元素</span><span class="sxs-lookup"><span data-stu-id="3f4ae-119">Child Elements</span></span>  
 <span data-ttu-id="3f4ae-120">无</span><span class="sxs-lookup"><span data-stu-id="3f4ae-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3f4ae-121">父元素</span><span class="sxs-lookup"><span data-stu-id="3f4ae-121">Parent Elements</span></span>  
  
|<span data-ttu-id="3f4ae-122">元素</span><span class="sxs-lookup"><span data-stu-id="3f4ae-122">Element</span></span>|<span data-ttu-id="3f4ae-123">描述</span><span class="sxs-lookup"><span data-stu-id="3f4ae-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3f4ae-124">\<cookieHandler></span><span class="sxs-lookup"><span data-stu-id="3f4ae-124">\<cookieHandler></span></span>](cookiehandler.md)|<span data-ttu-id="3f4ae-125"><xref:System.IdentityModel.Services.CookieHandler> 配置用于读取<xref:System.IdentityModel.Services.SessionAuthenticationModule>和写入 cookie 的。</span><span class="sxs-lookup"><span data-stu-id="3f4ae-125">Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f4ae-126">备注</span><span class="sxs-lookup"><span data-stu-id="3f4ae-126">Remarks</span></span>  
 <span data-ttu-id="3f4ae-127">如果通过将`mode` `<cookieHandler>`元素的属性设置为 "custom" 来指定自定义 cookie 处理程序，则必须通过包含引用 cookie 处理程序类型的`<customCookieHandler>`子元素来指定自定义 cookie 处理程序的类型。</span><span class="sxs-lookup"><span data-stu-id="3f4ae-127">When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type.</span></span> <span data-ttu-id="3f4ae-128">当特性设置为 "分块" `mode`或 "Default" 时，不能指定此元素。</span><span class="sxs-lookup"><span data-stu-id="3f4ae-128">This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default".</span></span> <span data-ttu-id="3f4ae-129">自定义 cookie 处理程序必须派生<xref:System.IdentityModel.Services.CookieHandler>自类。</span><span class="sxs-lookup"><span data-stu-id="3f4ae-129">Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.</span></span>  
  
 <span data-ttu-id="3f4ae-130">元素由<xref:System.IdentityModel.Configuration.CustomTypeElement>类表示。 `<customCookieHandler>`</span><span class="sxs-lookup"><span data-stu-id="3f4ae-130">The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f4ae-131">示例</span><span class="sxs-lookup"><span data-stu-id="3f4ae-131">Example</span></span>  
 <span data-ttu-id="3f4ae-132">下面的示例将 SAM 配置为使用类型`MyNamespace.MyCustomCookieHandler`的自定义 cookie 处理程序。</span><span class="sxs-lookup"><span data-stu-id="3f4ae-132">The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.</span></span>  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3f4ae-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="3f4ae-133">See also</span></span>

- <xref:System.IdentityModel.Services.CookieHandler>

---
title: <windowsAuthentication> 的 <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: e0709473-0997-4de3-8f49-783527309a48
ms.openlocfilehash: ded04f6e87fce2e12dac8f681ba2d4178f8fd204
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399115"
---
# <a name="windowsauthentication-of-servicecredentials"></a><span data-ttu-id="1a88a-102">\<windowsAuthentication > \<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="1a88a-102">\<windowsAuthentication> of \<serviceCredentials></span></span>
<span data-ttu-id="1a88a-103">指定 Windows 服务凭据的设置。</span><span class="sxs-lookup"><span data-stu-id="1a88a-103">Specifies the settings of a Windows service credential.</span></span>  
  
<span data-ttu-id="1a88a-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1a88a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1a88a-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="1a88a-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="1a88a-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="1a88a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="1a88a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="1a88a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="1a88a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="1a88a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="1a88a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCredentials >** ](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="1a88a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="1a88a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<windowsAuthentication >**</span><span class="sxs-lookup"><span data-stu-id="1a88a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windowsAuthentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a88a-111">语法</span><span class="sxs-lookup"><span data-stu-id="1a88a-111">Syntax</span></span>  
  
```xml  
<windowsAuthentication allowAnonymousLogons="Boolean"
                       includeWindowsGroups="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1a88a-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1a88a-112">Attributes and Elements</span></span>  
 <span data-ttu-id="1a88a-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1a88a-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1a88a-114">特性</span><span class="sxs-lookup"><span data-stu-id="1a88a-114">Attributes</span></span>  
  
|<span data-ttu-id="1a88a-115">特性</span><span class="sxs-lookup"><span data-stu-id="1a88a-115">Attribute</span></span>|<span data-ttu-id="1a88a-116">描述</span><span class="sxs-lookup"><span data-stu-id="1a88a-116">Description</span></span>|  
|---------------|-----------------|  
|`includeWindowsGroups`|<span data-ttu-id="1a88a-117">一个可选的布尔值属性，指定系统是否将 Windows 组包含在安全上下文中。</span><span class="sxs-lookup"><span data-stu-id="1a88a-117">An optional Boolean attribute that specifies whether the system includes Windows groups in the security context.</span></span> <span data-ttu-id="1a88a-118">默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="1a88a-118">The default is `true`.</span></span><br /><br /> <span data-ttu-id="1a88a-119">将此属性设置为 `true` 会影响性能，因为这会导致完全组扩展。</span><span class="sxs-lookup"><span data-stu-id="1a88a-119">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="1a88a-120">如果不需要建立用户所属组的列表，请将此属性设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="1a88a-120">Set this attribute to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`allowAnonymousLogons`|<span data-ttu-id="1a88a-121">一个可选的布尔值属性，指定是否允许匿名的未经过身份验证的调用方。</span><span class="sxs-lookup"><span data-stu-id="1a88a-121">An optional Boolean attribute that specifies whether anonymous, unauthenticated callers are allowed.</span></span> <span data-ttu-id="1a88a-122">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="1a88a-122">The default is `false`.</span></span><br /><br /> <span data-ttu-id="1a88a-123">如果将绑定的 `clientCredentialType` 属性设置为 `Windows`，则系统不允许匿名的调用方。</span><span class="sxs-lookup"><span data-stu-id="1a88a-123">When the `clientCredentialType` attribute of a binding is set to `Windows`, the system does not allow anonymous callers.</span></span> <span data-ttu-id="1a88a-124">这意味着，只有经过身份验证的域或工作组调用方才可以访问系统。</span><span class="sxs-lookup"><span data-stu-id="1a88a-124">This means that only domain or workgroup authenticated callers are allowed to access the system.</span></span> <span data-ttu-id="1a88a-125">可以使用此属性重写此行为。</span><span class="sxs-lookup"><span data-stu-id="1a88a-125">You can override this behavior by using this attribute.</span></span><br /><br /> <span data-ttu-id="1a88a-126">使用此设置应特别小心。</span><span class="sxs-lookup"><span data-stu-id="1a88a-126">Use this setting with extreme caution.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1a88a-127">子元素</span><span class="sxs-lookup"><span data-stu-id="1a88a-127">Child Elements</span></span>  
 <span data-ttu-id="1a88a-128">无。</span><span class="sxs-lookup"><span data-stu-id="1a88a-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1a88a-129">父元素</span><span class="sxs-lookup"><span data-stu-id="1a88a-129">Parent Elements</span></span>  
  
|<span data-ttu-id="1a88a-130">元素</span><span class="sxs-lookup"><span data-stu-id="1a88a-130">Element</span></span>|<span data-ttu-id="1a88a-131">描述</span><span class="sxs-lookup"><span data-stu-id="1a88a-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1a88a-132">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="1a88a-132">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="1a88a-133">指定要用于对服务进行身份验证的凭据以及与客户端凭据验证相关的设置。</span><span class="sxs-lookup"><span data-stu-id="1a88a-133">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1a88a-134">备注</span><span class="sxs-lookup"><span data-stu-id="1a88a-134">Remarks</span></span>  
 <span data-ttu-id="1a88a-135">通过设置 `allowAnonymousLogons` 属性，使用此元素可指定是否允许匿名 Windows 用户访问。</span><span class="sxs-lookup"><span data-stu-id="1a88a-135">Use this element to specify whether to allow anonymous Windows users access by setting the `allowAnonymousLogons` attribute.</span></span> <span data-ttu-id="1a88a-136">此外，通过设置 `includeWindowsGroups` 属性还可以指定是否在 AuthorizationContext 中包含用户所属的组信息。</span><span class="sxs-lookup"><span data-stu-id="1a88a-136">You can also specify whether to include group information to which users belong in the AuthorizationContext by setting the `includeWindowsGroups` attribute.</span></span> <span data-ttu-id="1a88a-137">如果将它设置为 `true`（默认设置），服务就可以确定客户端所属的 Windows 组。</span><span class="sxs-lookup"><span data-stu-id="1a88a-137">If it is set to `true` (the default setting), the service can determine the Windows groups to which the client belongs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a88a-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="1a88a-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.WindowsServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.WindowsAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.WindowsAuthentication%2A>
- <xref:System.ServiceModel.Security.WindowsServiceCredential>

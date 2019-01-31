---
title: <windowsAuthentication> 的 <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: e0709473-0997-4de3-8f49-783527309a48
ms.openlocfilehash: f366c85f895356594cf8bd9049ca41c8fb458c4c
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55280951"
---
# <a name="windowsauthentication-of-servicecredentials"></a><span data-ttu-id="b7749-102">\<windowsAuthentication> of \<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="b7749-102">\<windowsAuthentication> of \<serviceCredentials></span></span>
<span data-ttu-id="b7749-103">指定 Windows 服务凭据的设置。</span><span class="sxs-lookup"><span data-stu-id="b7749-103">Specifies the settings of a Windows service credential.</span></span>  
  
 <span data-ttu-id="b7749-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="b7749-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b7749-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="b7749-105">\<behaviors></span></span>  
<span data-ttu-id="b7749-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="b7749-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="b7749-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="b7749-107">\<behavior></span></span>  
<span data-ttu-id="b7749-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="b7749-108">\<serviceCredentials></span></span>  
<span data-ttu-id="b7749-109">\<windowsAuthentication></span><span class="sxs-lookup"><span data-stu-id="b7749-109">\<windowsAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7749-110">语法</span><span class="sxs-lookup"><span data-stu-id="b7749-110">Syntax</span></span>  
  
```xml  
<windowsAuthentication allowAnonymousLogons="Boolean"
                       includeWindowsGroups="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b7749-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b7749-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b7749-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b7749-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b7749-113">特性</span><span class="sxs-lookup"><span data-stu-id="b7749-113">Attributes</span></span>  
  
|<span data-ttu-id="b7749-114">特性</span><span class="sxs-lookup"><span data-stu-id="b7749-114">Attribute</span></span>|<span data-ttu-id="b7749-115">描述</span><span class="sxs-lookup"><span data-stu-id="b7749-115">Description</span></span>|  
|---------------|-----------------|  
|`includeWindowsGroups`|<span data-ttu-id="b7749-116">一个可选的布尔值属性，指定系统是否将 Windows 组包含在安全上下文中。</span><span class="sxs-lookup"><span data-stu-id="b7749-116">An optional Boolean attribute that specifies whether the system includes Windows groups in the security context.</span></span> <span data-ttu-id="b7749-117">默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="b7749-117">The default is `true`.</span></span><br /><br /> <span data-ttu-id="b7749-118">将此属性设置为 `true` 会影响性能，因为这会导致完全组扩展。</span><span class="sxs-lookup"><span data-stu-id="b7749-118">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="b7749-119">如果不需要建立用户所属组的列表，请将此属性设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="b7749-119">Set this attribute to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`allowAnonymousLogons`|<span data-ttu-id="b7749-120">一个可选的布尔值属性，指定是否允许匿名的未经过身份验证的调用方。</span><span class="sxs-lookup"><span data-stu-id="b7749-120">An optional Boolean attribute that specifies whether anonymous, unauthenticated callers are allowed.</span></span> <span data-ttu-id="b7749-121">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="b7749-121">The default is `false`.</span></span><br /><br /> <span data-ttu-id="b7749-122">如果将绑定的 `clientCredentialType` 属性设置为 `Windows`，则系统不允许匿名的调用方。</span><span class="sxs-lookup"><span data-stu-id="b7749-122">When the `clientCredentialType` attribute of a binding is set to `Windows`, the system does not allow anonymous callers.</span></span> <span data-ttu-id="b7749-123">这意味着，只有经过身份验证的域或工作组调用方才可以访问系统。</span><span class="sxs-lookup"><span data-stu-id="b7749-123">This means that only domain or workgroup authenticated callers are allowed to access the system.</span></span> <span data-ttu-id="b7749-124">可以使用此属性重写此行为。</span><span class="sxs-lookup"><span data-stu-id="b7749-124">You can override this behavior by using this attribute.</span></span><br /><br /> <span data-ttu-id="b7749-125">使用此设置应特别小心。</span><span class="sxs-lookup"><span data-stu-id="b7749-125">Use this setting with extreme caution.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b7749-126">子元素</span><span class="sxs-lookup"><span data-stu-id="b7749-126">Child Elements</span></span>  
 <span data-ttu-id="b7749-127">无。</span><span class="sxs-lookup"><span data-stu-id="b7749-127">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b7749-128">父元素</span><span class="sxs-lookup"><span data-stu-id="b7749-128">Parent Elements</span></span>  
  
|<span data-ttu-id="b7749-129">元素</span><span class="sxs-lookup"><span data-stu-id="b7749-129">Element</span></span>|<span data-ttu-id="b7749-130">描述</span><span class="sxs-lookup"><span data-stu-id="b7749-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b7749-131">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="b7749-131">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="b7749-132">指定要用于对服务进行身份验证的凭据以及与客户端凭据验证相关的设置。</span><span class="sxs-lookup"><span data-stu-id="b7749-132">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7749-133">备注</span><span class="sxs-lookup"><span data-stu-id="b7749-133">Remarks</span></span>  
 <span data-ttu-id="b7749-134">通过设置 `allowAnonymousLogons` 属性，使用此元素可指定是否允许匿名 Windows 用户访问。</span><span class="sxs-lookup"><span data-stu-id="b7749-134">Use this element to specify whether to allow anonymous Windows users access by setting the `allowAnonymousLogons` attribute.</span></span> <span data-ttu-id="b7749-135">此外，通过设置 `includeWindowsGroups` 属性还可以指定是否在 AuthorizationContext 中包含用户所属的组信息。</span><span class="sxs-lookup"><span data-stu-id="b7749-135">You can also specify whether to include group information to which users belong in the AuthorizationContext by setting the `includeWindowsGroups` attribute.</span></span> <span data-ttu-id="b7749-136">如果将它设置为 `true`（默认设置），服务就可以确定客户端所属的 Windows 组。</span><span class="sxs-lookup"><span data-stu-id="b7749-136">If it is set to `true` (the default setting), the service can determine the Windows groups to which the client belongs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7749-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="b7749-137">See also</span></span>
- <xref:System.ServiceModel.Configuration.WindowsServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.WindowsAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.WindowsAuthentication%2A>
- <xref:System.ServiceModel.Security.WindowsServiceCredential>

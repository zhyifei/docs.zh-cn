---
title: <userNameAuthentication>
ms.date: 03/30/2017
ms.assetid: 24d8b398-770f-418f-ba23-c4325419cfa6
ms.openlocfilehash: 05aa326c50823810caee5d6552af4d50424251dd
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55273999"
---
# <a name="usernameauthentication"></a><span data-ttu-id="443a8-101">\<userNameAuthentication></span><span class="sxs-lookup"><span data-stu-id="443a8-101">\<userNameAuthentication></span></span>
<span data-ttu-id="443a8-102">指定基于用户名和密码的服务凭据。</span><span class="sxs-lookup"><span data-stu-id="443a8-102">Specifies a service's credentials based on user name and password.</span></span>  
  
 <span data-ttu-id="443a8-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="443a8-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="443a8-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="443a8-104">\<behaviors></span></span>  
<span data-ttu-id="443a8-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="443a8-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="443a8-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="443a8-106">\<behavior></span></span>  
<span data-ttu-id="443a8-107">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="443a8-107">\<serviceCredentials></span></span>  
<span data-ttu-id="443a8-108">\<userNameAuthentication></span><span class="sxs-lookup"><span data-stu-id="443a8-108">\<userNameAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="443a8-109">语法</span><span class="sxs-lookup"><span data-stu-id="443a8-109">Syntax</span></span>  
  
```xml  
<userNameAuthentication cacheLogonTokenLifetime="TimeSpan"
                        cacheLogonTokens="Boolean"
                        customUserNamePasswordValidatorType="String"
                        includeWindowsGroups="Boolean"
                        maxCacheLogonTokens="Integer"
                        membershipProviderName="String"
                        userNamePasswordValidationMode="Windows/MembershipProvider/Custom" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="443a8-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="443a8-110">Attributes and Elements</span></span>  
 <span data-ttu-id="443a8-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="443a8-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="443a8-112">特性</span><span class="sxs-lookup"><span data-stu-id="443a8-112">Attributes</span></span>  
  
|<span data-ttu-id="443a8-113">特性</span><span class="sxs-lookup"><span data-stu-id="443a8-113">Attribute</span></span>|<span data-ttu-id="443a8-114">描述</span><span class="sxs-lookup"><span data-stu-id="443a8-114">Description</span></span>|  
|---------------|-----------------|  
|`cacheLogonTokenLifetime`|<span data-ttu-id="443a8-115">一个 <xref:System.TimeSpan>，指定缓存令牌的最大时间长度。</span><span class="sxs-lookup"><span data-stu-id="443a8-115">A <xref:System.TimeSpan> that specifies the maximum length of time a token is cached.</span></span> <span data-ttu-id="443a8-116">默认值为 00:15:00。</span><span class="sxs-lookup"><span data-stu-id="443a8-116">The default is 00:15:00.</span></span>|  
|`cacheLogonTokens`|<span data-ttu-id="443a8-117">一个布尔值，指定是否缓存登录令牌。</span><span class="sxs-lookup"><span data-stu-id="443a8-117">A Boolean value that specifies whether logon tokens are cached.</span></span> <span data-ttu-id="443a8-118">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="443a8-118">The default is `false`.</span></span>|  
|`customUserNamePasswordValidatorType`|<span data-ttu-id="443a8-119">一个字符串，指定要使用的自定义用户名密码验证程序的类型。</span><span class="sxs-lookup"><span data-stu-id="443a8-119">A string that specifies the type of custom username password validator to be used.</span></span> <span data-ttu-id="443a8-120">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="443a8-120">The default is an empty string.</span></span>|  
|`includeWindowsGroups`|<span data-ttu-id="443a8-121">一个布尔值，指定 Windows 组是否包含在安全上下文中。</span><span class="sxs-lookup"><span data-stu-id="443a8-121">A Boolean value that specifies whether Windows groups are included in the security context.</span></span> <span data-ttu-id="443a8-122">默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="443a8-122">The default is `true`.</span></span><br /><br /> <span data-ttu-id="443a8-123">将此属性设置为 `true` 会影响性能，因为这会导致完全组扩展。</span><span class="sxs-lookup"><span data-stu-id="443a8-123">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="443a8-124">如果不需要建立用户所属组的列表，请将此属性设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="443a8-124">Set this property to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`maxCacheLogonTokens`|<span data-ttu-id="443a8-125">一个整数，指定要缓存的最大登录令牌数。</span><span class="sxs-lookup"><span data-stu-id="443a8-125">An integer that specifies the maximum number of logon tokens to cache.</span></span> <span data-ttu-id="443a8-126">此值应大于零。</span><span class="sxs-lookup"><span data-stu-id="443a8-126">This value should be larger than zero.</span></span> <span data-ttu-id="443a8-127">默认值为 128。</span><span class="sxs-lookup"><span data-stu-id="443a8-127">The default is 128.</span></span>|  
|`membershipProviderName`|<span data-ttu-id="443a8-128">如果将绑定的 `clientCredentialType` 属性设置为 `username`，则用户名将映射到 Windows 帐户。</span><span class="sxs-lookup"><span data-stu-id="443a8-128">When the `clientCredentialType` attribute of a binding is set to `username`, the username is mapped to Windows accounts.</span></span> <span data-ttu-id="443a8-129">可以使用此属性重写此行为，此属性是一个包含 <xref:System.Web.Security.MembershipProvider> 值的名称的字符串，该值提供相关的密码验证机制。</span><span class="sxs-lookup"><span data-stu-id="443a8-129">You can override this behavior using this attribute, which is a string that contains the name of the <xref:System.Web.Security.MembershipProvider> value that provides the relevant password validation mechanism.</span></span>|  
|`userNamePasswordValidationMode`|<span data-ttu-id="443a8-130">指定对用户名密码进行验证的方式。</span><span class="sxs-lookup"><span data-stu-id="443a8-130">Specifies the manner in which username password is validated.</span></span> <span data-ttu-id="443a8-131">有效值为：</span><span class="sxs-lookup"><span data-stu-id="443a8-131">Valid values are:</span></span><br /><br /> <span data-ttu-id="443a8-132">-   Windows</span><span class="sxs-lookup"><span data-stu-id="443a8-132">-   Windows</span></span><br /><span data-ttu-id="443a8-133">-   MembershipProvider</span><span class="sxs-lookup"><span data-stu-id="443a8-133">-   MembershipProvider</span></span><br /><span data-ttu-id="443a8-134">自定义</span><span class="sxs-lookup"><span data-stu-id="443a8-134">-   Custom</span></span><br /><br /> <span data-ttu-id="443a8-135">默认值为 Windows。</span><span class="sxs-lookup"><span data-stu-id="443a8-135">The default is Windows.</span></span> <span data-ttu-id="443a8-136">此属性的类型为 <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>。</span><span class="sxs-lookup"><span data-stu-id="443a8-136">This attribute is of type <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="443a8-137">子元素</span><span class="sxs-lookup"><span data-stu-id="443a8-137">Child Elements</span></span>  
 <span data-ttu-id="443a8-138">无。</span><span class="sxs-lookup"><span data-stu-id="443a8-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="443a8-139">父元素</span><span class="sxs-lookup"><span data-stu-id="443a8-139">Parent Elements</span></span>  
  
|<span data-ttu-id="443a8-140">元素</span><span class="sxs-lookup"><span data-stu-id="443a8-140">Element</span></span>|<span data-ttu-id="443a8-141">描述</span><span class="sxs-lookup"><span data-stu-id="443a8-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="443a8-142">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="443a8-142">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="443a8-143">指定要用于对服务进行身份验证的凭据以及与客户端凭据验证相关的设置。</span><span class="sxs-lookup"><span data-stu-id="443a8-143">Specifies the credential to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="443a8-144">备注</span><span class="sxs-lookup"><span data-stu-id="443a8-144">Remarks</span></span>  
 <span data-ttu-id="443a8-145">如果没有为基于用户名/密码的身份验证配置服务所用的任何绑定，则忽略此元素的一些属性，</span><span class="sxs-lookup"><span data-stu-id="443a8-145">If none of the bindings used by a service is configured for user name/password-based authentication, the attributes for this element are ignored.</span></span> <span data-ttu-id="443a8-146">其中包括 `customUserNamePasswordValidatorType`、`includeWindowsGroups`、`membershipProviderName` 和 `userNamePasswordValidationMode`。</span><span class="sxs-lookup"><span data-stu-id="443a8-146">These include `customUserNamePasswordValidatorType`, `includeWindowsGroups`, `membershipProviderName`, and `userNamePasswordValidationMode`.</span></span>  
  
 <span data-ttu-id="443a8-147">如果没有配置服务所用的绑定，以使用 Windows 用户名/密码身份验证，则忽略与登录令牌的缓存相关的设置。</span><span class="sxs-lookup"><span data-stu-id="443a8-147">If none of the bindings used by a service is configured to use Windows authentication for user name/password, the settings related to caching of logon tokens are ignored.</span></span> <span data-ttu-id="443a8-148">这些设置包括 `cacheLogonTokenLifetime`、`cacheLogonTokens` 和 `maxCacheLogonTokens`。</span><span class="sxs-lookup"><span data-stu-id="443a8-148">These include the `cacheLogonTokenLifetime`, `cacheLogonTokens`, and `maxCacheLogonTokens`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="443a8-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="443a8-149">See also</span></span>
- <xref:System.ServiceModel.Configuration.UserNameServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.UserNameAuthentication%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.UserNameAuthentication%2A>

---
title: <userNameAuthentication>
ms.date: 03/30/2017
ms.assetid: 24d8b398-770f-418f-ba23-c4325419cfa6
ms.openlocfilehash: dc5c00a2204646863ae2570bb97b8d70e22a72d4
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399187"
---
# <a name="usernameauthentication"></a><span data-ttu-id="e39b6-101">\<userNameAuthentication></span><span class="sxs-lookup"><span data-stu-id="e39b6-101">\<userNameAuthentication></span></span>
<span data-ttu-id="e39b6-102">指定基于用户名和密码的服务凭据。</span><span class="sxs-lookup"><span data-stu-id="e39b6-102">Specifies a service's credentials based on user name and password.</span></span>  
  
<span data-ttu-id="e39b6-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e39b6-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e39b6-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="e39b6-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="e39b6-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e39b6-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="e39b6-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e39b6-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="e39b6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="e39b6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="e39b6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCredentials >** ](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="e39b6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="e39b6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<userNameAuthentication >**</span><span class="sxs-lookup"><span data-stu-id="e39b6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userNameAuthentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e39b6-110">语法</span><span class="sxs-lookup"><span data-stu-id="e39b6-110">Syntax</span></span>  
  
```xml  
<userNameAuthentication cacheLogonTokenLifetime="TimeSpan"
                        cacheLogonTokens="Boolean"
                        customUserNamePasswordValidatorType="String"
                        includeWindowsGroups="Boolean"
                        maxCacheLogonTokens="Integer"
                        membershipProviderName="String"
                        userNamePasswordValidationMode="Windows/MembershipProvider/Custom" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e39b6-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e39b6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e39b6-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e39b6-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e39b6-113">特性</span><span class="sxs-lookup"><span data-stu-id="e39b6-113">Attributes</span></span>  
  
|<span data-ttu-id="e39b6-114">特性</span><span class="sxs-lookup"><span data-stu-id="e39b6-114">Attribute</span></span>|<span data-ttu-id="e39b6-115">描述</span><span class="sxs-lookup"><span data-stu-id="e39b6-115">Description</span></span>|  
|---------------|-----------------|  
|`cacheLogonTokenLifetime`|<span data-ttu-id="e39b6-116">一个 <xref:System.TimeSpan>，指定缓存令牌的最大时间长度。</span><span class="sxs-lookup"><span data-stu-id="e39b6-116">A <xref:System.TimeSpan> that specifies the maximum length of time a token is cached.</span></span> <span data-ttu-id="e39b6-117">默认值为 00:15:00。</span><span class="sxs-lookup"><span data-stu-id="e39b6-117">The default is 00:15:00.</span></span>|  
|`cacheLogonTokens`|<span data-ttu-id="e39b6-118">一个布尔值，指定是否缓存登录令牌。</span><span class="sxs-lookup"><span data-stu-id="e39b6-118">A Boolean value that specifies whether logon tokens are cached.</span></span> <span data-ttu-id="e39b6-119">默认值为 `false`。</span><span class="sxs-lookup"><span data-stu-id="e39b6-119">The default is `false`.</span></span>|  
|`customUserNamePasswordValidatorType`|<span data-ttu-id="e39b6-120">一个字符串，指定要使用的自定义用户名密码验证程序的类型。</span><span class="sxs-lookup"><span data-stu-id="e39b6-120">A string that specifies the type of custom username password validator to be used.</span></span> <span data-ttu-id="e39b6-121">默认值为一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="e39b6-121">The default is an empty string.</span></span>|  
|`includeWindowsGroups`|<span data-ttu-id="e39b6-122">一个布尔值，指定 Windows 组是否包含在安全上下文中。</span><span class="sxs-lookup"><span data-stu-id="e39b6-122">A Boolean value that specifies whether Windows groups are included in the security context.</span></span> <span data-ttu-id="e39b6-123">默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="e39b6-123">The default is `true`.</span></span><br /><br /> <span data-ttu-id="e39b6-124">将此属性设置为 `true` 会影响性能，因为这会导致完全组扩展。</span><span class="sxs-lookup"><span data-stu-id="e39b6-124">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="e39b6-125">如果不需要建立用户所属组的列表，请将此属性设置为 `false`。</span><span class="sxs-lookup"><span data-stu-id="e39b6-125">Set this property to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`maxCacheLogonTokens`|<span data-ttu-id="e39b6-126">一个整数，指定要缓存的最大登录令牌数。</span><span class="sxs-lookup"><span data-stu-id="e39b6-126">An integer that specifies the maximum number of logon tokens to cache.</span></span> <span data-ttu-id="e39b6-127">此值应大于零。</span><span class="sxs-lookup"><span data-stu-id="e39b6-127">This value should be larger than zero.</span></span> <span data-ttu-id="e39b6-128">默认值为 128。</span><span class="sxs-lookup"><span data-stu-id="e39b6-128">The default is 128.</span></span>|  
|`membershipProviderName`|<span data-ttu-id="e39b6-129">如果将绑定的 `clientCredentialType` 属性设置为 `username`，则用户名将映射到 Windows 帐户。</span><span class="sxs-lookup"><span data-stu-id="e39b6-129">When the `clientCredentialType` attribute of a binding is set to `username`, the username is mapped to Windows accounts.</span></span> <span data-ttu-id="e39b6-130">可以使用此属性重写此行为，此属性是一个包含 <xref:System.Web.Security.MembershipProvider> 值的名称的字符串，该值提供相关的密码验证机制。</span><span class="sxs-lookup"><span data-stu-id="e39b6-130">You can override this behavior using this attribute, which is a string that contains the name of the <xref:System.Web.Security.MembershipProvider> value that provides the relevant password validation mechanism.</span></span>|  
|`userNamePasswordValidationMode`|<span data-ttu-id="e39b6-131">指定对用户名密码进行验证的方式。</span><span class="sxs-lookup"><span data-stu-id="e39b6-131">Specifies the manner in which username password is validated.</span></span> <span data-ttu-id="e39b6-132">有效值包括：</span><span class="sxs-lookup"><span data-stu-id="e39b6-132">Valid values are:</span></span><br /><br /> <span data-ttu-id="e39b6-133">-   Windows</span><span class="sxs-lookup"><span data-stu-id="e39b6-133">-   Windows</span></span><br /><span data-ttu-id="e39b6-134">-MembershipProvider</span><span class="sxs-lookup"><span data-stu-id="e39b6-134">-   MembershipProvider</span></span><br /><span data-ttu-id="e39b6-135">-Custom</span><span class="sxs-lookup"><span data-stu-id="e39b6-135">-   Custom</span></span><br /><br /> <span data-ttu-id="e39b6-136">默认值为 Windows。</span><span class="sxs-lookup"><span data-stu-id="e39b6-136">The default is Windows.</span></span> <span data-ttu-id="e39b6-137">此属性的类型为 <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>。</span><span class="sxs-lookup"><span data-stu-id="e39b6-137">This attribute is of type <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e39b6-138">子元素</span><span class="sxs-lookup"><span data-stu-id="e39b6-138">Child Elements</span></span>  
 <span data-ttu-id="e39b6-139">无。</span><span class="sxs-lookup"><span data-stu-id="e39b6-139">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e39b6-140">父元素</span><span class="sxs-lookup"><span data-stu-id="e39b6-140">Parent Elements</span></span>  
  
|<span data-ttu-id="e39b6-141">元素</span><span class="sxs-lookup"><span data-stu-id="e39b6-141">Element</span></span>|<span data-ttu-id="e39b6-142">描述</span><span class="sxs-lookup"><span data-stu-id="e39b6-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e39b6-143">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="e39b6-143">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="e39b6-144">指定要用于对服务进行身份验证的凭据以及与客户端凭据验证相关的设置。</span><span class="sxs-lookup"><span data-stu-id="e39b6-144">Specifies the credential to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e39b6-145">备注</span><span class="sxs-lookup"><span data-stu-id="e39b6-145">Remarks</span></span>  
 <span data-ttu-id="e39b6-146">如果没有为基于用户名/密码的身份验证配置服务所用的任何绑定，则忽略此元素的一些属性，</span><span class="sxs-lookup"><span data-stu-id="e39b6-146">If none of the bindings used by a service is configured for user name/password-based authentication, the attributes for this element are ignored.</span></span> <span data-ttu-id="e39b6-147">其中包括 `customUserNamePasswordValidatorType`、`includeWindowsGroups`、`membershipProviderName` 和 `userNamePasswordValidationMode`。</span><span class="sxs-lookup"><span data-stu-id="e39b6-147">These include `customUserNamePasswordValidatorType`, `includeWindowsGroups`, `membershipProviderName`, and `userNamePasswordValidationMode`.</span></span>  
  
 <span data-ttu-id="e39b6-148">如果没有配置服务所用的绑定，以使用 Windows 用户名/密码身份验证，则忽略与登录令牌的缓存相关的设置。</span><span class="sxs-lookup"><span data-stu-id="e39b6-148">If none of the bindings used by a service is configured to use Windows authentication for user name/password, the settings related to caching of logon tokens are ignored.</span></span> <span data-ttu-id="e39b6-149">这些设置包括 `cacheLogonTokenLifetime`、`cacheLogonTokens` 和 `maxCacheLogonTokens`。</span><span class="sxs-lookup"><span data-stu-id="e39b6-149">These include the `cacheLogonTokenLifetime`, `cacheLogonTokens`, and `maxCacheLogonTokens`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e39b6-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="e39b6-150">See also</span></span>

- <xref:System.ServiceModel.Configuration.UserNameServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.UserNameAuthentication%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.UserNameAuthentication%2A>

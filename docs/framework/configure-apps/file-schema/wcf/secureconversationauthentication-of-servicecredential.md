---
title: <secureConversationAuthentication> 的 <serviceCredential>
ms.date: 03/30/2017
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
ms.openlocfilehash: 336969c654f332ae3d838d8fd6d1c4243838539c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399948"
---
# <a name="secureconversationauthentication-of-servicecredential"></a><span data-ttu-id="7e54e-102">\<secureConversationAuthentication > \<serviceCredential ></span><span class="sxs-lookup"><span data-stu-id="7e54e-102">\<secureConversationAuthentication> of \<serviceCredential></span></span>
<span data-ttu-id="7e54e-103">指定安全对话服务的设置。</span><span class="sxs-lookup"><span data-stu-id="7e54e-103">Specifies the settings for a secure conversation service.</span></span>  
  
<span data-ttu-id="7e54e-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7e54e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7e54e-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="7e54e-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7e54e-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7e54e-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="7e54e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7e54e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="7e54e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7e54e-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="7e54e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCredentials >** ](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="7e54e-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="7e54e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<secureConversationAuthentication >**</span><span class="sxs-lookup"><span data-stu-id="7e54e-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<secureConversationAuthentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e54e-111">语法</span><span class="sxs-lookup"><span data-stu-id="7e54e-111">Syntax</span></span>  
  
```xml  
<secureConversationAuthentication securityStateEncoderType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7e54e-112">特性和元素</span><span class="sxs-lookup"><span data-stu-id="7e54e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="7e54e-113">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="7e54e-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7e54e-114">特性</span><span class="sxs-lookup"><span data-stu-id="7e54e-114">Attributes</span></span>  
  
|<span data-ttu-id="7e54e-115">特性</span><span class="sxs-lookup"><span data-stu-id="7e54e-115">Attribute</span></span>|<span data-ttu-id="7e54e-116">描述</span><span class="sxs-lookup"><span data-stu-id="7e54e-116">Description</span></span>|  
|---------------|-----------------|  
|`securityStateEncoderType`|<span data-ttu-id="7e54e-117">一个字符串，指定要使用的 <xref:System.ServiceModel.Security.SecurityStateEncoder> 的类型。</span><span class="sxs-lookup"><span data-stu-id="7e54e-117">A string that specifies the type of <xref:System.ServiceModel.Security.SecurityStateEncoder> to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7e54e-118">子元素</span><span class="sxs-lookup"><span data-stu-id="7e54e-118">Child Elements</span></span>  
 <span data-ttu-id="7e54e-119">无。</span><span class="sxs-lookup"><span data-stu-id="7e54e-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7e54e-120">父元素</span><span class="sxs-lookup"><span data-stu-id="7e54e-120">Parent Elements</span></span>  
  
|<span data-ttu-id="7e54e-121">元素</span><span class="sxs-lookup"><span data-stu-id="7e54e-121">Element</span></span>|<span data-ttu-id="7e54e-122">描述</span><span class="sxs-lookup"><span data-stu-id="7e54e-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7e54e-123">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="7e54e-123">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="7e54e-124">指定要用于对服务进行身份验证的凭据以及与客户端凭据验证相关的设置。</span><span class="sxs-lookup"><span data-stu-id="7e54e-124">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e54e-125">备注</span><span class="sxs-lookup"><span data-stu-id="7e54e-125">Remarks</span></span>  
 <span data-ttu-id="7e54e-126">使用此配置元素可指定用于安全上下文令牌 (SCT) Cookie 序列化的已知声明类型的列表和用于编码和保护 Cookie 信息的编码器。</span><span class="sxs-lookup"><span data-stu-id="7e54e-126">Use this configuration element to specify a list of known claim types for the Security Context Token (SCT) cookies serialization, as well as an encoder to encode and secure cookies information.</span></span> <span data-ttu-id="7e54e-127">有关 SCT 的更多信息，请参见 <xref:System.ServiceModel.Security.SecureConversationServiceCredential>。</span><span class="sxs-lookup"><span data-stu-id="7e54e-127">For more information on SCT, see <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e54e-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="7e54e-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Security.SecureConversationServiceCredential>

---
title: '&lt;serviceCredential&gt; 的 &lt;secureConversationAuthentication&gt;'
ms.date: 03/30/2017
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
ms.openlocfilehash: 2c8479c4d8a321c822d49bdc24f359ffad5500e9
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147182"
---
# <a name="ltsecureconversationauthenticationgt-of-ltservicecredentialgt"></a><span data-ttu-id="31521-102">&lt;serviceCredential&gt; 的 &lt;secureConversationAuthentication&gt;</span><span class="sxs-lookup"><span data-stu-id="31521-102">&lt;secureConversationAuthentication&gt; of &lt;serviceCredential&gt;</span></span>
<span data-ttu-id="31521-103">指定安全对话服务的设置。</span><span class="sxs-lookup"><span data-stu-id="31521-103">Specifies the settings for a secure conversation service.</span></span>  
  
 <span data-ttu-id="31521-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="31521-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="31521-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="31521-105">\<behaviors></span></span>  
<span data-ttu-id="31521-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="31521-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="31521-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="31521-107">\<behavior></span></span>  
<span data-ttu-id="31521-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="31521-108">\<serviceCredentials></span></span>  
<span data-ttu-id="31521-109">\<secureConversationAuthentication ></span><span class="sxs-lookup"><span data-stu-id="31521-109">\<secureConversationAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31521-110">语法</span><span class="sxs-lookup"><span data-stu-id="31521-110">Syntax</span></span>  
  
```xml  
<secureConversationAuthentication securityStateEncoderType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="31521-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="31521-111">Attributes and Elements</span></span>  
 <span data-ttu-id="31521-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="31521-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="31521-113">特性</span><span class="sxs-lookup"><span data-stu-id="31521-113">Attributes</span></span>  
  
|<span data-ttu-id="31521-114">特性</span><span class="sxs-lookup"><span data-stu-id="31521-114">Attribute</span></span>|<span data-ttu-id="31521-115">描述</span><span class="sxs-lookup"><span data-stu-id="31521-115">Description</span></span>|  
|---------------|-----------------|  
|`securityStateEncoderType`|<span data-ttu-id="31521-116">一个字符串，指定要使用的 <xref:System.ServiceModel.Security.SecurityStateEncoder> 的类型。</span><span class="sxs-lookup"><span data-stu-id="31521-116">A string that specifies the type of <xref:System.ServiceModel.Security.SecurityStateEncoder> to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="31521-117">子元素</span><span class="sxs-lookup"><span data-stu-id="31521-117">Child Elements</span></span>  
 <span data-ttu-id="31521-118">无。</span><span class="sxs-lookup"><span data-stu-id="31521-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="31521-119">父元素</span><span class="sxs-lookup"><span data-stu-id="31521-119">Parent Elements</span></span>  
  
|<span data-ttu-id="31521-120">元素</span><span class="sxs-lookup"><span data-stu-id="31521-120">Element</span></span>|<span data-ttu-id="31521-121">描述</span><span class="sxs-lookup"><span data-stu-id="31521-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="31521-122">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="31521-122">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="31521-123">指定要用于对服务进行身份验证的凭据以及与客户端凭据验证相关的设置。</span><span class="sxs-lookup"><span data-stu-id="31521-123">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="31521-124">备注</span><span class="sxs-lookup"><span data-stu-id="31521-124">Remarks</span></span>  
 <span data-ttu-id="31521-125">使用此配置元素可指定用于安全上下文令牌 (SCT) Cookie 序列化的已知声明类型的列表和用于编码和保护 Cookie 信息的编码器。</span><span class="sxs-lookup"><span data-stu-id="31521-125">Use this configuration element to specify a list of known claim types for the Security Context Token (SCT) cookies serialization, as well as an encoder to encode and secure cookies information.</span></span> <span data-ttu-id="31521-126">有关 SCT 的更多信息，请参见 <xref:System.ServiceModel.Security.SecureConversationServiceCredential>。</span><span class="sxs-lookup"><span data-stu-id="31521-126">For more information on SCT, see <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31521-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="31521-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>  
 <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>  
 <xref:System.ServiceModel.Security.SecureConversationServiceCredential>

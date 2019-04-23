---
title: <secureConversationAuthentication> 的 <serviceCredential>
ms.date: 03/30/2017
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
ms.openlocfilehash: f35392b91d047c46e65ce433ef544b86cf6c88c6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083694"
---
# <a name="secureconversationauthentication-of-servicecredential"></a><span data-ttu-id="0e001-102">\<secureConversationAuthentication> of \<serviceCredential></span><span class="sxs-lookup"><span data-stu-id="0e001-102">\<secureConversationAuthentication> of \<serviceCredential></span></span>
<span data-ttu-id="0e001-103">指定安全对话服务的设置。</span><span class="sxs-lookup"><span data-stu-id="0e001-103">Specifies the settings for a secure conversation service.</span></span>  
  
 <span data-ttu-id="0e001-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0e001-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0e001-105">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="0e001-105">\<behaviors></span></span>  
<span data-ttu-id="0e001-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="0e001-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="0e001-107">\<behavior></span><span class="sxs-lookup"><span data-stu-id="0e001-107">\<behavior></span></span>  
<span data-ttu-id="0e001-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="0e001-108">\<serviceCredentials></span></span>  
<span data-ttu-id="0e001-109">\<secureConversationAuthentication></span><span class="sxs-lookup"><span data-stu-id="0e001-109">\<secureConversationAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e001-110">语法</span><span class="sxs-lookup"><span data-stu-id="0e001-110">Syntax</span></span>  
  
```xml  
<secureConversationAuthentication securityStateEncoderType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0e001-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="0e001-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0e001-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="0e001-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0e001-113">特性</span><span class="sxs-lookup"><span data-stu-id="0e001-113">Attributes</span></span>  
  
|<span data-ttu-id="0e001-114">特性</span><span class="sxs-lookup"><span data-stu-id="0e001-114">Attribute</span></span>|<span data-ttu-id="0e001-115">描述</span><span class="sxs-lookup"><span data-stu-id="0e001-115">Description</span></span>|  
|---------------|-----------------|  
|`securityStateEncoderType`|<span data-ttu-id="0e001-116">一个字符串，指定要使用的 <xref:System.ServiceModel.Security.SecurityStateEncoder> 的类型。</span><span class="sxs-lookup"><span data-stu-id="0e001-116">A string that specifies the type of <xref:System.ServiceModel.Security.SecurityStateEncoder> to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0e001-117">子元素</span><span class="sxs-lookup"><span data-stu-id="0e001-117">Child Elements</span></span>  
 <span data-ttu-id="0e001-118">无。</span><span class="sxs-lookup"><span data-stu-id="0e001-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0e001-119">父元素</span><span class="sxs-lookup"><span data-stu-id="0e001-119">Parent Elements</span></span>  
  
|<span data-ttu-id="0e001-120">元素</span><span class="sxs-lookup"><span data-stu-id="0e001-120">Element</span></span>|<span data-ttu-id="0e001-121">描述</span><span class="sxs-lookup"><span data-stu-id="0e001-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0e001-122">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="0e001-122">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="0e001-123">指定要用于对服务进行身份验证的凭据以及与客户端凭据验证相关的设置。</span><span class="sxs-lookup"><span data-stu-id="0e001-123">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e001-124">备注</span><span class="sxs-lookup"><span data-stu-id="0e001-124">Remarks</span></span>  
 <span data-ttu-id="0e001-125">使用此配置元素可指定用于安全上下文令牌 (SCT) Cookie 序列化的已知声明类型的列表和用于编码和保护 Cookie 信息的编码器。</span><span class="sxs-lookup"><span data-stu-id="0e001-125">Use this configuration element to specify a list of known claim types for the Security Context Token (SCT) cookies serialization, as well as an encoder to encode and secure cookies information.</span></span> <span data-ttu-id="0e001-126">有关 SCT 的更多信息，请参见 <xref:System.ServiceModel.Security.SecureConversationServiceCredential>。</span><span class="sxs-lookup"><span data-stu-id="0e001-126">For more information on SCT, see <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e001-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="0e001-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Security.SecureConversationServiceCredential>

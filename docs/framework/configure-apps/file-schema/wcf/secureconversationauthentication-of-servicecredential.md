---
title: '&lt;serviceCredential&gt; 的 &lt;secureConversationAuthentication&gt;'
ms.date: 03/30/2017
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
author: BrucePerlerMS
ms.openlocfilehash: 3adcf7ba9814bcf494d345cf0e3f47c57df2152c
ms.sourcegitcommit: 700b9003ea6bdd83a53458bbc436c9b5778344f1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "48266099"
---
# <a name="ltsecureconversationauthenticationgt-of-ltservicecredentialgt"></a><span data-ttu-id="34829-102">&lt;serviceCredential&gt; 的 &lt;secureConversationAuthentication&gt;</span><span class="sxs-lookup"><span data-stu-id="34829-102">&lt;secureConversationAuthentication&gt; of &lt;serviceCredential&gt;</span></span>
<span data-ttu-id="34829-103">指定安全对话服务的设置。</span><span class="sxs-lookup"><span data-stu-id="34829-103">Specifies the settings for a secure conversation service.</span></span>  
  
 <span data-ttu-id="34829-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="34829-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="34829-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="34829-105">\<behaviors></span></span>  
<span data-ttu-id="34829-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="34829-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="34829-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="34829-107">\<behavior></span></span>  
<span data-ttu-id="34829-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="34829-108">\<serviceCredentials></span></span>  
<span data-ttu-id="34829-109">\<secureConversationAuthentication ></span><span class="sxs-lookup"><span data-stu-id="34829-109">\<secureConversationAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34829-110">语法</span><span class="sxs-lookup"><span data-stu-id="34829-110">Syntax</span></span>  
  
```xml  
<secureConversationAuthentication securityStateEncoderType="String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34829-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="34829-111">Attributes and Elements</span></span>  
 <span data-ttu-id="34829-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="34829-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34829-113">特性</span><span class="sxs-lookup"><span data-stu-id="34829-113">Attributes</span></span>  
  
|<span data-ttu-id="34829-114">特性</span><span class="sxs-lookup"><span data-stu-id="34829-114">Attribute</span></span>|<span data-ttu-id="34829-115">描述</span><span class="sxs-lookup"><span data-stu-id="34829-115">Description</span></span>|  
|---------------|-----------------|  
|`securityStateEncoderType`|<span data-ttu-id="34829-116">一个字符串，指定要使用的 <xref:System.ServiceModel.Security.SecurityStateEncoder> 的类型。</span><span class="sxs-lookup"><span data-stu-id="34829-116">A string that specifies the type of <xref:System.ServiceModel.Security.SecurityStateEncoder> to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="34829-117">子元素</span><span class="sxs-lookup"><span data-stu-id="34829-117">Child Elements</span></span>  
 <span data-ttu-id="34829-118">无。</span><span class="sxs-lookup"><span data-stu-id="34829-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="34829-119">父元素</span><span class="sxs-lookup"><span data-stu-id="34829-119">Parent Elements</span></span>  
  
|<span data-ttu-id="34829-120">元素</span><span class="sxs-lookup"><span data-stu-id="34829-120">Element</span></span>|<span data-ttu-id="34829-121">描述</span><span class="sxs-lookup"><span data-stu-id="34829-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="34829-122">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="34829-122">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="34829-123">指定要用于对服务进行身份验证的凭据以及与客户端凭据验证相关的设置。</span><span class="sxs-lookup"><span data-stu-id="34829-123">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34829-124">备注</span><span class="sxs-lookup"><span data-stu-id="34829-124">Remarks</span></span>  
 <span data-ttu-id="34829-125">使用此配置元素可指定用于安全上下文令牌 (SCT) Cookie 序列化的已知声明类型的列表和用于编码和保护 Cookie 信息的编码器。</span><span class="sxs-lookup"><span data-stu-id="34829-125">Use this configuration element to specify a list of known claim types for the Security Context Token (SCT) cookies serialization, as well as an encoder to encode and secure cookies information.</span></span> <span data-ttu-id="34829-126">有关 SCT 的更多信息，请参见 <xref:System.ServiceModel.Security.SecureConversationServiceCredential>。</span><span class="sxs-lookup"><span data-stu-id="34829-126">For more information on SCT, see <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34829-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="34829-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>  
 <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>  
 <xref:System.ServiceModel.Security.SecureConversationServiceCredential>

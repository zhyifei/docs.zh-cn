---
title: "&lt;serviceCredential&gt; 的 &lt;secureConversationAuthentication&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 0fb9ff476812b6b889750e8eb7b80efce801f041
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltsecureconversationauthenticationgt-of-ltservicecredentialgt"></a><span data-ttu-id="c6a84-102">&lt;serviceCredential&gt; 的 &lt;secureConversationAuthentication&gt;</span><span class="sxs-lookup"><span data-stu-id="c6a84-102">&lt;secureConversationAuthentication&gt; of &lt;serviceCredential&gt;</span></span>
<span data-ttu-id="c6a84-103">指定安全对话服务的设置。</span><span class="sxs-lookup"><span data-stu-id="c6a84-103">Specifies the settings for a secure conversation service.</span></span>  
  
 <span data-ttu-id="c6a84-104">\<系统。ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="c6a84-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="c6a84-105">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="c6a84-105">\<behaviors></span></span>  
<span data-ttu-id="c6a84-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="c6a84-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="c6a84-107">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="c6a84-107">\<behavior></span></span>  
<span data-ttu-id="c6a84-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="c6a84-108">\<serviceCredentials></span></span>  
<span data-ttu-id="c6a84-109">\<secureConversationAuthentication ></span><span class="sxs-lookup"><span data-stu-id="c6a84-109">\<secureConversationAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6a84-110">语法</span><span class="sxs-lookup"><span data-stu-id="c6a84-110">Syntax</span></span>  
  
```xml  
<secureConversationAuthentication securityStateEncoderType="String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c6a84-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c6a84-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c6a84-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c6a84-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c6a84-113">特性</span><span class="sxs-lookup"><span data-stu-id="c6a84-113">Attributes</span></span>  
  
|<span data-ttu-id="c6a84-114">特性</span><span class="sxs-lookup"><span data-stu-id="c6a84-114">Attribute</span></span>|<span data-ttu-id="c6a84-115">描述</span><span class="sxs-lookup"><span data-stu-id="c6a84-115">Description</span></span>|  
|---------------|-----------------|  
|`securityStateEncoderType`|<span data-ttu-id="c6a84-116">一个字符串，指定要使用的 <xref:System.ServiceModel.Security.SecurityStateEncoder> 的类型。</span><span class="sxs-lookup"><span data-stu-id="c6a84-116">A string that specifies the type of <xref:System.ServiceModel.Security.SecurityStateEncoder> to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c6a84-117">子元素</span><span class="sxs-lookup"><span data-stu-id="c6a84-117">Child Elements</span></span>  
 <span data-ttu-id="c6a84-118">无。</span><span class="sxs-lookup"><span data-stu-id="c6a84-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c6a84-119">父元素</span><span class="sxs-lookup"><span data-stu-id="c6a84-119">Parent Elements</span></span>  
  
|<span data-ttu-id="c6a84-120">元素</span><span class="sxs-lookup"><span data-stu-id="c6a84-120">Element</span></span>|<span data-ttu-id="c6a84-121">描述</span><span class="sxs-lookup"><span data-stu-id="c6a84-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c6a84-122">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="c6a84-122">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="c6a84-123">指定要用于对服务进行身份验证的凭据以及与客户端凭据验证相关的设置。</span><span class="sxs-lookup"><span data-stu-id="c6a84-123">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6a84-124">备注</span><span class="sxs-lookup"><span data-stu-id="c6a84-124">Remarks</span></span>  
 <span data-ttu-id="c6a84-125">使用此配置元素可指定用于安全上下文令牌 (SCT) Cookie 序列化的已知声明类型的列表和用于编码和保护 Cookie 信息的编码器。</span><span class="sxs-lookup"><span data-stu-id="c6a84-125">Use this configuration element to specify a list of known claim types for the Security Context Token (SCT) cookies serialization, as well as an encoder to encode and secure cookies information.</span></span> <span data-ttu-id="c6a84-126">有关 SCT 的更多信息，请参见 <xref:System.ServiceModel.Security.SecureConversationServiceCredential>。</span><span class="sxs-lookup"><span data-stu-id="c6a84-126">For more information on SCT, see <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6a84-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c6a84-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>  
 <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>  
 <xref:System.ServiceModel.Security.SecureConversationServiceCredential>

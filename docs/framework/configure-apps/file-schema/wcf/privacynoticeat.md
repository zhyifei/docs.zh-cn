---
title: '&lt;privacyNoticeAt&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 63501539db4dc01d86eb675c28001dc960f1bf7f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltprivacynoticeatgt"></a><span data-ttu-id="8a15d-102">&lt;privacyNoticeAt&gt;</span><span class="sxs-lookup"><span data-stu-id="8a15d-102">&lt;privacyNoticeAt&gt;</span></span>
<span data-ttu-id="8a15d-103">表示一个配置元素，该元素指定 `wsFederationHttp` 绑定中使用的隐私声明。</span><span class="sxs-lookup"><span data-stu-id="8a15d-103">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
 <span data-ttu-id="8a15d-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="8a15d-104">\<system.serviceModel></span></span>  
<span data-ttu-id="8a15d-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="8a15d-105">\<bindings></span></span>  
<span data-ttu-id="8a15d-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="8a15d-106">\<customBinding></span></span>  
<span data-ttu-id="8a15d-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="8a15d-107">\<binding></span></span>  
<span data-ttu-id="8a15d-108">\<privacyNotice ></span><span class="sxs-lookup"><span data-stu-id="8a15d-108">\<privacyNotice></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a15d-109">语法</span><span class="sxs-lookup"><span data-stu-id="8a15d-109">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"  
        version="Integer" />  
```  
  
## <a name="type"></a><span data-ttu-id="8a15d-110">类型</span><span class="sxs-lookup"><span data-stu-id="8a15d-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8a15d-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8a15d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="8a15d-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="8a15d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8a15d-113">特性</span><span class="sxs-lookup"><span data-stu-id="8a15d-113">Attributes</span></span>  
  
|<span data-ttu-id="8a15d-114">特性</span><span class="sxs-lookup"><span data-stu-id="8a15d-114">Attribute</span></span>|<span data-ttu-id="8a15d-115">描述</span><span class="sxs-lookup"><span data-stu-id="8a15d-115">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="8a15d-116">一个字符串，指定隐私声明位于的 URI。</span><span class="sxs-lookup"><span data-stu-id="8a15d-116">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="8a15d-117">一个整数，指定此隐私声明的版本。</span><span class="sxs-lookup"><span data-stu-id="8a15d-117">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8a15d-118">子元素</span><span class="sxs-lookup"><span data-stu-id="8a15d-118">Child Elements</span></span>  
 <span data-ttu-id="8a15d-119">无。</span><span class="sxs-lookup"><span data-stu-id="8a15d-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8a15d-120">父元素</span><span class="sxs-lookup"><span data-stu-id="8a15d-120">Parent Elements</span></span>  
  
|<span data-ttu-id="8a15d-121">元素</span><span class="sxs-lookup"><span data-stu-id="8a15d-121">Element</span></span>|<span data-ttu-id="8a15d-122">描述</span><span class="sxs-lookup"><span data-stu-id="8a15d-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8a15d-123">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="8a15d-123">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="8a15d-124">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="8a15d-124">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8a15d-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8a15d-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>  
 <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="8a15d-126">绑定</span><span class="sxs-lookup"><span data-stu-id="8a15d-126">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="8a15d-127">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="8a15d-127">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="8a15d-128">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="8a15d-128">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="8a15d-129">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="8a15d-129">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

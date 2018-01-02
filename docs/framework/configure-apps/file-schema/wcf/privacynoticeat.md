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
ms.workload: dotnet
ms.openlocfilehash: 30b3f0bdd1aa02473470c354a730bcfa450f0264
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="ltprivacynoticeatgt"></a><span data-ttu-id="ee0d0-102">&lt;privacyNoticeAt&gt;</span><span class="sxs-lookup"><span data-stu-id="ee0d0-102">&lt;privacyNoticeAt&gt;</span></span>
<span data-ttu-id="ee0d0-103">表示一个配置元素，该元素指定 `wsFederationHttp` 绑定中使用的隐私声明。</span><span class="sxs-lookup"><span data-stu-id="ee0d0-103">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
 <span data-ttu-id="ee0d0-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="ee0d0-104">\<system.serviceModel></span></span>  
<span data-ttu-id="ee0d0-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="ee0d0-105">\<bindings></span></span>  
<span data-ttu-id="ee0d0-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="ee0d0-106">\<customBinding></span></span>  
<span data-ttu-id="ee0d0-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="ee0d0-107">\<binding></span></span>  
<span data-ttu-id="ee0d0-108">\<privacyNotice ></span><span class="sxs-lookup"><span data-stu-id="ee0d0-108">\<privacyNotice></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee0d0-109">语法</span><span class="sxs-lookup"><span data-stu-id="ee0d0-109">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"  
        version="Integer" />  
```  
  
## <a name="type"></a><span data-ttu-id="ee0d0-110">类型</span><span class="sxs-lookup"><span data-stu-id="ee0d0-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ee0d0-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ee0d0-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ee0d0-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ee0d0-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ee0d0-113">特性</span><span class="sxs-lookup"><span data-stu-id="ee0d0-113">Attributes</span></span>  
  
|<span data-ttu-id="ee0d0-114">特性</span><span class="sxs-lookup"><span data-stu-id="ee0d0-114">Attribute</span></span>|<span data-ttu-id="ee0d0-115">描述</span><span class="sxs-lookup"><span data-stu-id="ee0d0-115">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="ee0d0-116">一个字符串，指定隐私声明位于的 URI。</span><span class="sxs-lookup"><span data-stu-id="ee0d0-116">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="ee0d0-117">一个整数，指定此隐私声明的版本。</span><span class="sxs-lookup"><span data-stu-id="ee0d0-117">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ee0d0-118">子元素</span><span class="sxs-lookup"><span data-stu-id="ee0d0-118">Child Elements</span></span>  
 <span data-ttu-id="ee0d0-119">无。</span><span class="sxs-lookup"><span data-stu-id="ee0d0-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ee0d0-120">父元素</span><span class="sxs-lookup"><span data-stu-id="ee0d0-120">Parent Elements</span></span>  
  
|<span data-ttu-id="ee0d0-121">元素</span><span class="sxs-lookup"><span data-stu-id="ee0d0-121">Element</span></span>|<span data-ttu-id="ee0d0-122">描述</span><span class="sxs-lookup"><span data-stu-id="ee0d0-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ee0d0-123">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="ee0d0-123">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="ee0d0-124">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="ee0d0-124">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ee0d0-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="ee0d0-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>  
 <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="ee0d0-126">绑定</span><span class="sxs-lookup"><span data-stu-id="ee0d0-126">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="ee0d0-127">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="ee0d0-127">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="ee0d0-128">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="ee0d0-128">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="ee0d0-129">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="ee0d0-129">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

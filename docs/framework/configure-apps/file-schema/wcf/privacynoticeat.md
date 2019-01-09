---
title: '&lt;privacyNoticeAt&gt;'
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: 104b2b6399ea31273045e43be716947db110715d
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147312"
---
# <a name="ltprivacynoticeatgt"></a><span data-ttu-id="2fc9b-102">&lt;privacyNoticeAt&gt;</span><span class="sxs-lookup"><span data-stu-id="2fc9b-102">&lt;privacyNoticeAt&gt;</span></span>
<span data-ttu-id="2fc9b-103">表示一个配置元素，该元素指定 `wsFederationHttp` 绑定中使用的隐私声明。</span><span class="sxs-lookup"><span data-stu-id="2fc9b-103">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
 <span data-ttu-id="2fc9b-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2fc9b-104">\<system.serviceModel></span></span>  
<span data-ttu-id="2fc9b-105">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="2fc9b-105">\<bindings></span></span>  
<span data-ttu-id="2fc9b-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="2fc9b-106">\<customBinding></span></span>  
<span data-ttu-id="2fc9b-107">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="2fc9b-107">\<binding></span></span>  
<span data-ttu-id="2fc9b-108">\<privacyNotice ></span><span class="sxs-lookup"><span data-stu-id="2fc9b-108">\<privacyNotice></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fc9b-109">语法</span><span class="sxs-lookup"><span data-stu-id="2fc9b-109">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="2fc9b-110">类型</span><span class="sxs-lookup"><span data-stu-id="2fc9b-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2fc9b-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2fc9b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="2fc9b-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2fc9b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2fc9b-113">特性</span><span class="sxs-lookup"><span data-stu-id="2fc9b-113">Attributes</span></span>  
  
|<span data-ttu-id="2fc9b-114">特性</span><span class="sxs-lookup"><span data-stu-id="2fc9b-114">Attribute</span></span>|<span data-ttu-id="2fc9b-115">描述</span><span class="sxs-lookup"><span data-stu-id="2fc9b-115">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="2fc9b-116">一个字符串，指定隐私声明位于的 URI。</span><span class="sxs-lookup"><span data-stu-id="2fc9b-116">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="2fc9b-117">一个整数，指定此隐私声明的版本。</span><span class="sxs-lookup"><span data-stu-id="2fc9b-117">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2fc9b-118">子元素</span><span class="sxs-lookup"><span data-stu-id="2fc9b-118">Child Elements</span></span>  
 <span data-ttu-id="2fc9b-119">无。</span><span class="sxs-lookup"><span data-stu-id="2fc9b-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2fc9b-120">父元素</span><span class="sxs-lookup"><span data-stu-id="2fc9b-120">Parent Elements</span></span>  
  
|<span data-ttu-id="2fc9b-121">元素</span><span class="sxs-lookup"><span data-stu-id="2fc9b-121">Element</span></span>|<span data-ttu-id="2fc9b-122">描述</span><span class="sxs-lookup"><span data-stu-id="2fc9b-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2fc9b-123">\<绑定 ></span><span class="sxs-lookup"><span data-stu-id="2fc9b-123">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="2fc9b-124">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="2fc9b-124">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2fc9b-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="2fc9b-125">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>  
 <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="2fc9b-126">绑定</span><span class="sxs-lookup"><span data-stu-id="2fc9b-126">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="2fc9b-127">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="2fc9b-127">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="2fc9b-128">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="2fc9b-128">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="2fc9b-129">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="2fc9b-129">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

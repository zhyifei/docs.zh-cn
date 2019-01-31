---
title: <privacyNoticeAt>
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: b1de2a304a5dc4295497ea1f3b395240cb5ca9bc
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254907"
---
# <a name="privacynoticeat"></a><span data-ttu-id="9ced6-101">\<privacyNoticeAt></span><span class="sxs-lookup"><span data-stu-id="9ced6-101">\<privacyNoticeAt></span></span>
<span data-ttu-id="9ced6-102">表示一个配置元素，该元素指定 `wsFederationHttp` 绑定中使用的隐私声明。</span><span class="sxs-lookup"><span data-stu-id="9ced6-102">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
 <span data-ttu-id="9ced6-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9ced6-103">\<system.serviceModel></span></span>  
<span data-ttu-id="9ced6-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="9ced6-104">\<bindings></span></span>  
<span data-ttu-id="9ced6-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="9ced6-105">\<customBinding></span></span>  
<span data-ttu-id="9ced6-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="9ced6-106">\<binding></span></span>  
<span data-ttu-id="9ced6-107">\<privacyNotice></span><span class="sxs-lookup"><span data-stu-id="9ced6-107">\<privacyNotice></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ced6-108">语法</span><span class="sxs-lookup"><span data-stu-id="9ced6-108">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="9ced6-109">类型</span><span class="sxs-lookup"><span data-stu-id="9ced6-109">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ced6-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="9ced6-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9ced6-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="9ced6-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ced6-112">特性</span><span class="sxs-lookup"><span data-stu-id="9ced6-112">Attributes</span></span>  
  
|<span data-ttu-id="9ced6-113">特性</span><span class="sxs-lookup"><span data-stu-id="9ced6-113">Attribute</span></span>|<span data-ttu-id="9ced6-114">描述</span><span class="sxs-lookup"><span data-stu-id="9ced6-114">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="9ced6-115">一个字符串，指定隐私声明位于的 URI。</span><span class="sxs-lookup"><span data-stu-id="9ced6-115">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="9ced6-116">一个整数，指定此隐私声明的版本。</span><span class="sxs-lookup"><span data-stu-id="9ced6-116">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9ced6-117">子元素</span><span class="sxs-lookup"><span data-stu-id="9ced6-117">Child Elements</span></span>  
 <span data-ttu-id="9ced6-118">无。</span><span class="sxs-lookup"><span data-stu-id="9ced6-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9ced6-119">父元素</span><span class="sxs-lookup"><span data-stu-id="9ced6-119">Parent Elements</span></span>  
  
|<span data-ttu-id="9ced6-120">元素</span><span class="sxs-lookup"><span data-stu-id="9ced6-120">Element</span></span>|<span data-ttu-id="9ced6-121">描述</span><span class="sxs-lookup"><span data-stu-id="9ced6-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9ced6-122">\<binding></span><span class="sxs-lookup"><span data-stu-id="9ced6-122">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="9ced6-123">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="9ced6-123">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9ced6-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="9ced6-124">See also</span></span>
- <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="9ced6-125">绑定</span><span class="sxs-lookup"><span data-stu-id="9ced6-125">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="9ced6-126">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="9ced6-126">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="9ced6-127">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="9ced6-127">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="9ced6-128">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="9ced6-128">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

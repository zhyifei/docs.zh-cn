---
title: <privacyNoticeAt>
ms.date: 03/30/2017
ms.assetid: 4cc96942-4eb9-4241-b2fd-45aa239915e8
ms.openlocfilehash: 2ff70d3a8636970434582e417e4549ab6b433fc1
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738760"
---
# <a name="privacynoticeat"></a><span data-ttu-id="741b7-101">\<privacyNoticeAt ></span><span class="sxs-lookup"><span data-stu-id="741b7-101">\<privacyNoticeAt></span></span>
<span data-ttu-id="741b7-102">表示一个配置元素，该元素指定 `wsFederationHttp` 绑定中使用的隐私声明。</span><span class="sxs-lookup"><span data-stu-id="741b7-102">Represents a configuration element that specifies a privacy notice used in `wsFederationHttp` binding.</span></span>  
  
<span data-ttu-id="741b7-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="741b7-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="741b7-104">\<system &nbsp; &nbsp;[ **>** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="741b7-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="741b7-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="741b7-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="741b7-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="741b7-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="741b7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** </span><span class="sxs-lookup"><span data-stu-id="741b7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="741b7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<privacyNotice >**</span><span class="sxs-lookup"><span data-stu-id="741b7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<privacyNotice>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="741b7-109">语法</span><span class="sxs-lookup"><span data-stu-id="741b7-109">Syntax</span></span>  
  
```xml  
<privacyNotice url="String"
               version="Integer" />
```  
  
## <a name="type"></a><span data-ttu-id="741b7-110">键入</span><span class="sxs-lookup"><span data-stu-id="741b7-110">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="741b7-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="741b7-111">Attributes and Elements</span></span>  
 <span data-ttu-id="741b7-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="741b7-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="741b7-113">特性</span><span class="sxs-lookup"><span data-stu-id="741b7-113">Attributes</span></span>  
  
|<span data-ttu-id="741b7-114">特性</span><span class="sxs-lookup"><span data-stu-id="741b7-114">Attribute</span></span>|<span data-ttu-id="741b7-115">描述</span><span class="sxs-lookup"><span data-stu-id="741b7-115">Description</span></span>|  
|---------------|-----------------|  
|`url`|<span data-ttu-id="741b7-116">一个字符串，指定隐私声明位于的 URI。</span><span class="sxs-lookup"><span data-stu-id="741b7-116">A string that specifies the URI at which the privacy notice is located.</span></span>|  
|`version`|<span data-ttu-id="741b7-117">一个整数，指定此隐私声明的版本。</span><span class="sxs-lookup"><span data-stu-id="741b7-117">An integer that specifies the version of this privacy notice.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="741b7-118">子元素</span><span class="sxs-lookup"><span data-stu-id="741b7-118">Child Elements</span></span>  
 <span data-ttu-id="741b7-119">无。</span><span class="sxs-lookup"><span data-stu-id="741b7-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="741b7-120">父元素</span><span class="sxs-lookup"><span data-stu-id="741b7-120">Parent Elements</span></span>  
  
|<span data-ttu-id="741b7-121">元素</span><span class="sxs-lookup"><span data-stu-id="741b7-121">Element</span></span>|<span data-ttu-id="741b7-122">描述</span><span class="sxs-lookup"><span data-stu-id="741b7-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="741b7-123">\<binding ></span><span class="sxs-lookup"><span data-stu-id="741b7-123">\<binding></span></span>](bindings.md)|<span data-ttu-id="741b7-124">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="741b7-124">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="741b7-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="741b7-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.PrivacyNoticeElement>
- <xref:System.ServiceModel.Channels.PrivacyNoticeBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="741b7-126">绑定</span><span class="sxs-lookup"><span data-stu-id="741b7-126">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="741b7-127">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="741b7-127">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="741b7-128">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="741b7-128">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="741b7-129">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="741b7-129">\<customBinding></span></span>](custombinding.md)

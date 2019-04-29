---
title: <useManagedPresentation>
ms.date: 03/30/2017
ms.assetid: 17a0dd77-af54-41db-a9d0-4b17ff42878f
ms.openlocfilehash: eedf0ce6cf75b8fb56daf98f2005e66162ce10d8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769845"
---
# <a name="usemanagedpresentation"></a><span data-ttu-id="a51e4-101">\<useManagedPresentation></span><span class="sxs-lookup"><span data-stu-id="a51e4-101">\<useManagedPresentation></span></span>
<span data-ttu-id="a51e4-102">一个绑定元素，用于与支持 WS-Trust 的 CardSpace 配置文件的 CardSpace 安全令牌服务进行通信。</span><span class="sxs-lookup"><span data-stu-id="a51e4-102">A binding element used to communicate with a CardSpace Security Token Service that supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="a51e4-103">此元素没有属性并且以空开关形式存在。</span><span class="sxs-lookup"><span data-stu-id="a51e4-103">This element has no attribute and is present as an empty switch.</span></span>  
  
 <span data-ttu-id="a51e4-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a51e4-104">\<system.serviceModel></span></span>  
<span data-ttu-id="a51e4-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="a51e4-105">\<bindings></span></span>  
<span data-ttu-id="a51e4-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="a51e4-106">\<customBinding></span></span>  
<span data-ttu-id="a51e4-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="a51e4-107">\<binding></span></span>  
<span data-ttu-id="a51e4-108">\<useManagedPresentation></span><span class="sxs-lookup"><span data-stu-id="a51e4-108">\<useManagedPresentation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a51e4-109">语法</span><span class="sxs-lookup"><span data-stu-id="a51e4-109">Syntax</span></span>  
  
```xml  
<useManagedPresentation />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a51e4-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="a51e4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a51e4-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="a51e4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a51e4-112">特性</span><span class="sxs-lookup"><span data-stu-id="a51e4-112">Attributes</span></span>  
 <span data-ttu-id="a51e4-113">无。</span><span class="sxs-lookup"><span data-stu-id="a51e4-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a51e4-114">子元素</span><span class="sxs-lookup"><span data-stu-id="a51e4-114">Child Elements</span></span>  
 <span data-ttu-id="a51e4-115">None</span><span class="sxs-lookup"><span data-stu-id="a51e4-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a51e4-116">父元素</span><span class="sxs-lookup"><span data-stu-id="a51e4-116">Parent Elements</span></span>  
  
|<span data-ttu-id="a51e4-117">元素</span><span class="sxs-lookup"><span data-stu-id="a51e4-117">Element</span></span>|<span data-ttu-id="a51e4-118">描述</span><span class="sxs-lookup"><span data-stu-id="a51e4-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a51e4-119">\<binding></span><span class="sxs-lookup"><span data-stu-id="a51e4-119">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="a51e4-120">定义自定义绑定的所有绑定功能。</span><span class="sxs-lookup"><span data-stu-id="a51e4-120">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a51e4-121">备注</span><span class="sxs-lookup"><span data-stu-id="a51e4-121">Remarks</span></span>  
 <span data-ttu-id="a51e4-122">标识提供程序使用此元素，用以在它的策略中表明它支持 WS-Trust 的 CardSpace 配置文件这一事实。</span><span class="sxs-lookup"><span data-stu-id="a51e4-122">This element is used by an identity provider to express in its policy the fact that it supports the CardSpace profile of WS-Trust.</span></span> <span data-ttu-id="a51e4-123">发布这种策略断言的标识提供程序应该能够基于该 CardSpace 配置文件颁发令牌。</span><span class="sxs-lookup"><span data-stu-id="a51e4-123">Identity providers that publish such a policy assertion should be able to issue tokens based on that CardSpace profile.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a51e4-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="a51e4-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.UseManagedPresentationElement>
- <xref:System.ServiceModel.Channels.UseManagedPresentationBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="a51e4-125">绑定</span><span class="sxs-lookup"><span data-stu-id="a51e4-125">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="a51e4-126">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="a51e4-126">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="a51e4-127">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="a51e4-127">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="a51e4-128">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="a51e4-128">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)

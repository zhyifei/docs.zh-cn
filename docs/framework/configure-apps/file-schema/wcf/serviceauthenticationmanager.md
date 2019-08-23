---
title: <serviceAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: 65488c34931f6d7c424ece58a4855e746ea455bc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936416"
---
# <a name="serviceauthenticationmanager"></a><span data-ttu-id="90c41-101">\<serviceAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="90c41-101">\<serviceAuthenticationManager></span></span>
<span data-ttu-id="90c41-102">提供一个工作流配置元素，该元素在服务级别建立传输、消息或发起方的有效性。</span><span class="sxs-lookup"><span data-stu-id="90c41-102">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
<span data-ttu-id="90c41-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="90c41-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="90c41-104">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="90c41-104">\<behaviors></span></span>  
<span data-ttu-id="90c41-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="90c41-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="90c41-106">\<行为 ></span><span class="sxs-lookup"><span data-stu-id="90c41-106">\<behavior></span></span>  
<span data-ttu-id="90c41-107">\<serviceAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="90c41-107">\<serviceAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90c41-108">语法</span><span class="sxs-lookup"><span data-stu-id="90c41-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="90c41-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="90c41-109">Attributes and Elements</span></span>  
 <span data-ttu-id="90c41-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="90c41-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="90c41-111">特性</span><span class="sxs-lookup"><span data-stu-id="90c41-111">Attributes</span></span>  
  
|<span data-ttu-id="90c41-112">特性</span><span class="sxs-lookup"><span data-stu-id="90c41-112">Attribute</span></span>|<span data-ttu-id="90c41-113">描述</span><span class="sxs-lookup"><span data-stu-id="90c41-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="90c41-114">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="90c41-114">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="90c41-115">一个字符串，指定当前行为的身份验证策略类型。</span><span class="sxs-lookup"><span data-stu-id="90c41-115">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="90c41-116">子元素</span><span class="sxs-lookup"><span data-stu-id="90c41-116">Child Elements</span></span>  
 <span data-ttu-id="90c41-117">无。</span><span class="sxs-lookup"><span data-stu-id="90c41-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="90c41-118">父元素</span><span class="sxs-lookup"><span data-stu-id="90c41-118">Parent Elements</span></span>  
  
|<span data-ttu-id="90c41-119">元素</span><span class="sxs-lookup"><span data-stu-id="90c41-119">Element</span></span>|<span data-ttu-id="90c41-120">描述</span><span class="sxs-lookup"><span data-stu-id="90c41-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="90c41-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="90c41-121">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="90c41-122">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="90c41-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="90c41-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="90c41-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>

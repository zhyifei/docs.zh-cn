---
title: <serviceAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: cc5ebcf36a10e88d48ed14f1f10dac6396d7b242
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399711"
---
# <a name="serviceauthenticationmanager"></a><span data-ttu-id="486ca-101">\<serviceAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="486ca-101">\<serviceAuthenticationManager></span></span>
<span data-ttu-id="486ca-102">提供一个工作流配置元素，该元素在服务级别建立传输、消息或发起方的有效性。</span><span class="sxs-lookup"><span data-stu-id="486ca-102">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
<span data-ttu-id="486ca-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="486ca-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="486ca-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="486ca-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="486ca-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="486ca-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="486ca-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="486ca-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="486ca-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<行为 >** ](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="486ca-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="486ca-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<v >**</span><span class="sxs-lookup"><span data-stu-id="486ca-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<serviceAuthenticationManager>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="486ca-109">语法</span><span class="sxs-lookup"><span data-stu-id="486ca-109">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="486ca-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="486ca-110">Attributes and Elements</span></span>  
 <span data-ttu-id="486ca-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="486ca-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="486ca-112">特性</span><span class="sxs-lookup"><span data-stu-id="486ca-112">Attributes</span></span>  
  
|<span data-ttu-id="486ca-113">特性</span><span class="sxs-lookup"><span data-stu-id="486ca-113">Attribute</span></span>|<span data-ttu-id="486ca-114">描述</span><span class="sxs-lookup"><span data-stu-id="486ca-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="486ca-115">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="486ca-115">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="486ca-116">一个字符串，指定当前行为的身份验证策略类型。</span><span class="sxs-lookup"><span data-stu-id="486ca-116">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="486ca-117">子元素</span><span class="sxs-lookup"><span data-stu-id="486ca-117">Child Elements</span></span>  
 <span data-ttu-id="486ca-118">无。</span><span class="sxs-lookup"><span data-stu-id="486ca-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="486ca-119">父元素</span><span class="sxs-lookup"><span data-stu-id="486ca-119">Parent Elements</span></span>  
  
|<span data-ttu-id="486ca-120">元素</span><span class="sxs-lookup"><span data-stu-id="486ca-120">Element</span></span>|<span data-ttu-id="486ca-121">描述</span><span class="sxs-lookup"><span data-stu-id="486ca-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="486ca-122">\<behavior></span><span class="sxs-lookup"><span data-stu-id="486ca-122">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="486ca-123">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="486ca-123">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="486ca-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="486ca-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>

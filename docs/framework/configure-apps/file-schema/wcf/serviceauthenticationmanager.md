---
title: <serviceAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: 7708dd8a572dd24c2852410b1781fce2807efab9
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55263480"
---
# <a name="serviceauthenticationmanager"></a><span data-ttu-id="30a42-101">\<serviceAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="30a42-101">\<serviceAuthenticationManager></span></span>
<span data-ttu-id="30a42-102">提供一个工作流配置元素，该元素在服务级别建立传输、消息或发起方的有效性。</span><span class="sxs-lookup"><span data-stu-id="30a42-102">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
<span data-ttu-id="30a42-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="30a42-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="30a42-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="30a42-104">\<behaviors></span></span>  
<span data-ttu-id="30a42-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="30a42-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="30a42-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="30a42-106">\<behavior></span></span>  
<span data-ttu-id="30a42-107">\<serviceAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="30a42-107">\<serviceAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30a42-108">语法</span><span class="sxs-lookup"><span data-stu-id="30a42-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="30a42-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="30a42-109">Attributes and Elements</span></span>  
 <span data-ttu-id="30a42-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="30a42-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="30a42-111">特性</span><span class="sxs-lookup"><span data-stu-id="30a42-111">Attributes</span></span>  
  
|<span data-ttu-id="30a42-112">特性</span><span class="sxs-lookup"><span data-stu-id="30a42-112">Attribute</span></span>|<span data-ttu-id="30a42-113">描述</span><span class="sxs-lookup"><span data-stu-id="30a42-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="30a42-114">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="30a42-114">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="30a42-115">一个字符串，指定当前行为的身份验证策略类型。</span><span class="sxs-lookup"><span data-stu-id="30a42-115">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="30a42-116">子元素</span><span class="sxs-lookup"><span data-stu-id="30a42-116">Child Elements</span></span>  
 <span data-ttu-id="30a42-117">无。</span><span class="sxs-lookup"><span data-stu-id="30a42-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="30a42-118">父元素</span><span class="sxs-lookup"><span data-stu-id="30a42-118">Parent Elements</span></span>  
  
|<span data-ttu-id="30a42-119">元素</span><span class="sxs-lookup"><span data-stu-id="30a42-119">Element</span></span>|<span data-ttu-id="30a42-120">描述</span><span class="sxs-lookup"><span data-stu-id="30a42-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="30a42-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="30a42-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="30a42-122">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="30a42-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="30a42-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="30a42-123">See also</span></span>
- <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>

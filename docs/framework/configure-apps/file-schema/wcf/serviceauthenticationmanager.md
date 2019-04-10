---
title: <serviceAuthenticationManager>
ms.date: 03/30/2017
ms.assetid: 5d69e64f-f325-4d55-8e2d-0fb30f222dda
ms.openlocfilehash: 0940248364488bb38a329c5e461d72463c574e74
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59192038"
---
# <a name="serviceauthenticationmanager"></a><span data-ttu-id="10374-101">\<serviceAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="10374-101">\<serviceAuthenticationManager></span></span>
<span data-ttu-id="10374-102">提供一个工作流配置元素，该元素在服务级别建立传输、消息或发起方的有效性。</span><span class="sxs-lookup"><span data-stu-id="10374-102">Provides a workflow configuration element that establishes at the service level the validity of a transmission, message, or originator.</span></span>  
  
<span data-ttu-id="10374-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="10374-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="10374-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="10374-104">\<behaviors></span></span>  
<span data-ttu-id="10374-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="10374-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="10374-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="10374-106">\<behavior></span></span>  
<span data-ttu-id="10374-107">\<serviceAuthenticationManager></span><span class="sxs-lookup"><span data-stu-id="10374-107">\<serviceAuthenticationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10374-108">语法</span><span class="sxs-lookup"><span data-stu-id="10374-108">Syntax</span></span>  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <serviceAuthenticationManager serviceAuthenticationManagerType="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="10374-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="10374-109">Attributes and Elements</span></span>  
 <span data-ttu-id="10374-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="10374-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="10374-111">特性</span><span class="sxs-lookup"><span data-stu-id="10374-111">Attributes</span></span>  
  
|<span data-ttu-id="10374-112">特性</span><span class="sxs-lookup"><span data-stu-id="10374-112">Attribute</span></span>|<span data-ttu-id="10374-113">描述</span><span class="sxs-lookup"><span data-stu-id="10374-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="10374-114">serviceAuthenticationManagerType</span><span class="sxs-lookup"><span data-stu-id="10374-114">serviceAuthenticationManagerType</span></span>|<span data-ttu-id="10374-115">一个字符串，指定当前行为的身份验证策略类型。</span><span class="sxs-lookup"><span data-stu-id="10374-115">A string that specifies the type of the authentication policy for the current behavior.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="10374-116">子元素</span><span class="sxs-lookup"><span data-stu-id="10374-116">Child Elements</span></span>  
 <span data-ttu-id="10374-117">无。</span><span class="sxs-lookup"><span data-stu-id="10374-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="10374-118">父元素</span><span class="sxs-lookup"><span data-stu-id="10374-118">Parent Elements</span></span>  
  
|<span data-ttu-id="10374-119">元素</span><span class="sxs-lookup"><span data-stu-id="10374-119">Element</span></span>|<span data-ttu-id="10374-120">描述</span><span class="sxs-lookup"><span data-stu-id="10374-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="10374-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="10374-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="10374-122">指定行为元素。</span><span class="sxs-lookup"><span data-stu-id="10374-122">Specifies a behavior element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="10374-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="10374-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthenticationElement>

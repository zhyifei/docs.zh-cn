---
title: "&lt;backupList&gt; 的 &lt;add&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b93b442d21d34eea5031cea565bdcf62139abc81
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="ltaddgt-of-ltbackuplistgt"></a><span data-ttu-id="81cbf-102">&lt;backupList&gt; 的 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="81cbf-102">&lt;add&gt; of &lt;backupList&gt;</span></span>
<span data-ttu-id="81cbf-103">表示定义备份终结点元素的配置元素。</span><span class="sxs-lookup"><span data-stu-id="81cbf-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
 <span data-ttu-id="81cbf-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="81cbf-104">\<system.serviceModel></span></span>  
<span data-ttu-id="81cbf-105">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="81cbf-105">\<routing></span></span>  
<span data-ttu-id="81cbf-106">\<backupLists ></span><span class="sxs-lookup"><span data-stu-id="81cbf-106">\<backupLists></span></span>  
<span data-ttu-id="81cbf-107">\<backupList ></span><span class="sxs-lookup"><span data-stu-id="81cbf-107">\<backupList></span></span>  
<span data-ttu-id="81cbf-108">\<add></span><span class="sxs-lookup"><span data-stu-id="81cbf-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81cbf-109">语法</span><span class="sxs-lookup"><span data-stu-id="81cbf-109">Syntax</span></span>  
  
```xml  
   <routing>  <backupLists>    <backupList name="String">      <add endpointName="String" />    </backupList>    </backupLists></routing>  
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="81cbf-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="81cbf-110">Attributes and Elements</span></span>  
 <span data-ttu-id="81cbf-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="81cbf-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="81cbf-112">特性</span><span class="sxs-lookup"><span data-stu-id="81cbf-112">Attributes</span></span>  
  
|<span data-ttu-id="81cbf-113">特性</span><span class="sxs-lookup"><span data-stu-id="81cbf-113">Attribute</span></span>|<span data-ttu-id="81cbf-114">描述</span><span class="sxs-lookup"><span data-stu-id="81cbf-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="81cbf-115">name</span><span class="sxs-lookup"><span data-stu-id="81cbf-115">name</span></span>|<span data-ttu-id="81cbf-116">一个字符串，指定备份终结点的名称。</span><span class="sxs-lookup"><span data-stu-id="81cbf-116">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="81cbf-117">子元素</span><span class="sxs-lookup"><span data-stu-id="81cbf-117">Child Elements</span></span>  
 <span data-ttu-id="81cbf-118">无。</span><span class="sxs-lookup"><span data-stu-id="81cbf-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="81cbf-119">父元素</span><span class="sxs-lookup"><span data-stu-id="81cbf-119">Parent Elements</span></span>  
  
|<span data-ttu-id="81cbf-120">元素</span><span class="sxs-lookup"><span data-stu-id="81cbf-120">Element</span></span>|<span data-ttu-id="81cbf-121">描述</span><span class="sxs-lookup"><span data-stu-id="81cbf-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="81cbf-122">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="81cbf-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="81cbf-123">包含你想要用于在的情况下无法访问主终结点的路由服务的终结点的列表。</span><span class="sxs-lookup"><span data-stu-id="81cbf-123">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="81cbf-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="81cbf-124">See Also</span></span>  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType> 

---
title: '&lt;backupList&gt; 的 &lt;add&gt;'
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 2cc7cce62082317bb86218d68bd2881b74649771
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54670181"
---
# <a name="ltaddgt-of-ltbackuplistgt"></a><span data-ttu-id="2b3ef-102">&lt;backupList&gt; 的 &lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="2b3ef-102">&lt;add&gt; of &lt;backupList&gt;</span></span>
<span data-ttu-id="2b3ef-103">表示定义备份终结点元素的配置元素。</span><span class="sxs-lookup"><span data-stu-id="2b3ef-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
 <span data-ttu-id="2b3ef-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="2b3ef-104">\<system.serviceModel></span></span>  
<span data-ttu-id="2b3ef-105">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="2b3ef-105">\<routing></span></span>  
<span data-ttu-id="2b3ef-106">\<backupLists></span><span class="sxs-lookup"><span data-stu-id="2b3ef-106">\<backupLists></span></span>  
<span data-ttu-id="2b3ef-107">\<backupList></span><span class="sxs-lookup"><span data-stu-id="2b3ef-107">\<backupList></span></span>  
<span data-ttu-id="2b3ef-108">\<add></span><span class="sxs-lookup"><span data-stu-id="2b3ef-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b3ef-109">语法</span><span class="sxs-lookup"><span data-stu-id="2b3ef-109">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2b3ef-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="2b3ef-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2b3ef-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="2b3ef-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2b3ef-112">特性</span><span class="sxs-lookup"><span data-stu-id="2b3ef-112">Attributes</span></span>  
  
|<span data-ttu-id="2b3ef-113">特性</span><span class="sxs-lookup"><span data-stu-id="2b3ef-113">Attribute</span></span>|<span data-ttu-id="2b3ef-114">描述</span><span class="sxs-lookup"><span data-stu-id="2b3ef-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2b3ef-115">name</span><span class="sxs-lookup"><span data-stu-id="2b3ef-115">name</span></span>|<span data-ttu-id="2b3ef-116">一个字符串，指定备份终结点的名称。</span><span class="sxs-lookup"><span data-stu-id="2b3ef-116">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2b3ef-117">子元素</span><span class="sxs-lookup"><span data-stu-id="2b3ef-117">Child Elements</span></span>  
 <span data-ttu-id="2b3ef-118">无。</span><span class="sxs-lookup"><span data-stu-id="2b3ef-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2b3ef-119">父元素</span><span class="sxs-lookup"><span data-stu-id="2b3ef-119">Parent Elements</span></span>  
  
|<span data-ttu-id="2b3ef-120">元素</span><span class="sxs-lookup"><span data-stu-id="2b3ef-120">Element</span></span>|<span data-ttu-id="2b3ef-121">描述</span><span class="sxs-lookup"><span data-stu-id="2b3ef-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2b3ef-122">\<routing></span><span class="sxs-lookup"><span data-stu-id="2b3ef-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="2b3ef-123">包含你想要使用在的情况下无法访问主终结点的路由服务的终结点的列表。</span><span class="sxs-lookup"><span data-stu-id="2b3ef-123">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2b3ef-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="2b3ef-124">See also</span></span>
- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>

---
title: <add> 的 <backupList>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: c590dbd671807b32e08ad5d871d376a0dc51e611
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926874"
---
# <a name="add-of-backuplist"></a><span data-ttu-id="40973-102">\<添加 backupList > \<的 ></span><span class="sxs-lookup"><span data-stu-id="40973-102">\<add> of \<backupList></span></span>
<span data-ttu-id="40973-103">表示定义备份终结点元素的配置元素。</span><span class="sxs-lookup"><span data-stu-id="40973-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
 <span data-ttu-id="40973-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="40973-104">\<system.serviceModel></span></span>  
<span data-ttu-id="40973-105">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="40973-105">\<routing></span></span>  
<span data-ttu-id="40973-106">\<backupLists></span><span class="sxs-lookup"><span data-stu-id="40973-106">\<backupLists></span></span>  
<span data-ttu-id="40973-107">\<backupList></span><span class="sxs-lookup"><span data-stu-id="40973-107">\<backupList></span></span>  
<span data-ttu-id="40973-108">\<add></span><span class="sxs-lookup"><span data-stu-id="40973-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40973-109">语法</span><span class="sxs-lookup"><span data-stu-id="40973-109">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="40973-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="40973-110">Attributes and Elements</span></span>  
 <span data-ttu-id="40973-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="40973-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="40973-112">特性</span><span class="sxs-lookup"><span data-stu-id="40973-112">Attributes</span></span>  
  
|<span data-ttu-id="40973-113">特性</span><span class="sxs-lookup"><span data-stu-id="40973-113">Attribute</span></span>|<span data-ttu-id="40973-114">描述</span><span class="sxs-lookup"><span data-stu-id="40973-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="40973-115">NAME</span><span class="sxs-lookup"><span data-stu-id="40973-115">name</span></span>|<span data-ttu-id="40973-116">一个字符串，指定备份终结点的名称。</span><span class="sxs-lookup"><span data-stu-id="40973-116">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="40973-117">子元素</span><span class="sxs-lookup"><span data-stu-id="40973-117">Child Elements</span></span>  
 <span data-ttu-id="40973-118">无。</span><span class="sxs-lookup"><span data-stu-id="40973-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="40973-119">父元素</span><span class="sxs-lookup"><span data-stu-id="40973-119">Parent Elements</span></span>  
  
|<span data-ttu-id="40973-120">元素</span><span class="sxs-lookup"><span data-stu-id="40973-120">Element</span></span>|<span data-ttu-id="40973-121">描述</span><span class="sxs-lookup"><span data-stu-id="40973-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="40973-122">\<routing></span><span class="sxs-lookup"><span data-stu-id="40973-122">\<routing></span></span>](routing.md)|<span data-ttu-id="40973-123">包含当无法访问主终结点时路由服务将使用的终结点的列表。</span><span class="sxs-lookup"><span data-stu-id="40973-123">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="40973-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="40973-124">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>

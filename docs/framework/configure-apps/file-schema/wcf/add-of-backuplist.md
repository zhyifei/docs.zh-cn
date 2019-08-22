---
title: <add> 的 <backupList>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 53af01a519c244376b262db1f6515a438dcc554f
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663369"
---
# <a name="add-of-backuplist"></a><span data-ttu-id="1129d-102">\<添加 backupList > \<的 ></span><span class="sxs-lookup"><span data-stu-id="1129d-102">\<add> of \<backupList></span></span>
<span data-ttu-id="1129d-103">表示定义备份终结点元素的配置元素。</span><span class="sxs-lookup"><span data-stu-id="1129d-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
 <span data-ttu-id="1129d-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="1129d-104">\<system.serviceModel></span></span>  
<span data-ttu-id="1129d-105">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="1129d-105">\<routing></span></span>  
<span data-ttu-id="1129d-106">\<backupLists></span><span class="sxs-lookup"><span data-stu-id="1129d-106">\<backupLists></span></span>  
<span data-ttu-id="1129d-107">\<backupList></span><span class="sxs-lookup"><span data-stu-id="1129d-107">\<backupList></span></span>  
<span data-ttu-id="1129d-108">\<add></span><span class="sxs-lookup"><span data-stu-id="1129d-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1129d-109">语法</span><span class="sxs-lookup"><span data-stu-id="1129d-109">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1129d-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="1129d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1129d-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="1129d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1129d-112">特性</span><span class="sxs-lookup"><span data-stu-id="1129d-112">Attributes</span></span>  
  
|<span data-ttu-id="1129d-113">特性</span><span class="sxs-lookup"><span data-stu-id="1129d-113">Attribute</span></span>|<span data-ttu-id="1129d-114">描述</span><span class="sxs-lookup"><span data-stu-id="1129d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1129d-115">NAME</span><span class="sxs-lookup"><span data-stu-id="1129d-115">name</span></span>|<span data-ttu-id="1129d-116">一个字符串，指定备份终结点的名称。</span><span class="sxs-lookup"><span data-stu-id="1129d-116">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1129d-117">子元素</span><span class="sxs-lookup"><span data-stu-id="1129d-117">Child Elements</span></span>  
 <span data-ttu-id="1129d-118">无。</span><span class="sxs-lookup"><span data-stu-id="1129d-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1129d-119">父元素</span><span class="sxs-lookup"><span data-stu-id="1129d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="1129d-120">元素</span><span class="sxs-lookup"><span data-stu-id="1129d-120">Element</span></span>|<span data-ttu-id="1129d-121">描述</span><span class="sxs-lookup"><span data-stu-id="1129d-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1129d-122">\<routing></span><span class="sxs-lookup"><span data-stu-id="1129d-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="1129d-123">包含当无法访问主终结点时路由服务将使用的终结点的列表。</span><span class="sxs-lookup"><span data-stu-id="1129d-123">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1129d-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="1129d-124">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>

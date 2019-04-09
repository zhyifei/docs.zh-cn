---
title: <add> 的 <backupList>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 03bf1bbb8156e4722d987e171d9034747ac6bb61
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089531"
---
# <a name="add-of-backuplist"></a><span data-ttu-id="17ca0-102">\<添加 > 的\<backupList ></span><span class="sxs-lookup"><span data-stu-id="17ca0-102">\<add> of \<backupList></span></span>
<span data-ttu-id="17ca0-103">表示定义备份终结点元素的配置元素。</span><span class="sxs-lookup"><span data-stu-id="17ca0-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
 <span data-ttu-id="17ca0-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="17ca0-104">\<system.serviceModel></span></span>  
<span data-ttu-id="17ca0-105">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="17ca0-105">\<routing></span></span>  
<span data-ttu-id="17ca0-106">\<backupLists></span><span class="sxs-lookup"><span data-stu-id="17ca0-106">\<backupLists></span></span>  
<span data-ttu-id="17ca0-107">\<backupList></span><span class="sxs-lookup"><span data-stu-id="17ca0-107">\<backupList></span></span>  
<span data-ttu-id="17ca0-108">\<add></span><span class="sxs-lookup"><span data-stu-id="17ca0-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17ca0-109">语法</span><span class="sxs-lookup"><span data-stu-id="17ca0-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="17ca0-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="17ca0-110">Attributes and Elements</span></span>  
 <span data-ttu-id="17ca0-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="17ca0-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="17ca0-112">特性</span><span class="sxs-lookup"><span data-stu-id="17ca0-112">Attributes</span></span>  
  
|<span data-ttu-id="17ca0-113">特性</span><span class="sxs-lookup"><span data-stu-id="17ca0-113">Attribute</span></span>|<span data-ttu-id="17ca0-114">描述</span><span class="sxs-lookup"><span data-stu-id="17ca0-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="17ca0-115">name</span><span class="sxs-lookup"><span data-stu-id="17ca0-115">name</span></span>|<span data-ttu-id="17ca0-116">一个字符串，指定备份终结点的名称。</span><span class="sxs-lookup"><span data-stu-id="17ca0-116">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="17ca0-117">子元素</span><span class="sxs-lookup"><span data-stu-id="17ca0-117">Child Elements</span></span>  
 <span data-ttu-id="17ca0-118">无。</span><span class="sxs-lookup"><span data-stu-id="17ca0-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="17ca0-119">父元素</span><span class="sxs-lookup"><span data-stu-id="17ca0-119">Parent Elements</span></span>  
  
|<span data-ttu-id="17ca0-120">元素</span><span class="sxs-lookup"><span data-stu-id="17ca0-120">Element</span></span>|<span data-ttu-id="17ca0-121">描述</span><span class="sxs-lookup"><span data-stu-id="17ca0-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="17ca0-122">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="17ca0-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="17ca0-123">包含你想要使用在的情况下无法访问主终结点的路由服务的终结点的列表。</span><span class="sxs-lookup"><span data-stu-id="17ca0-123">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="17ca0-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="17ca0-124">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>

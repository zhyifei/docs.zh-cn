---
title: <add> 的 <backupList>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: e61ee275a7e98f13370504f5f15fdbe62a8221bd
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55285787"
---
# <a name="add-of-backuplist"></a><span data-ttu-id="8c426-102">\<添加 > 的\<backupList ></span><span class="sxs-lookup"><span data-stu-id="8c426-102">\<add> of \<backupList></span></span>
<span data-ttu-id="8c426-103">表示定义备份终结点元素的配置元素。</span><span class="sxs-lookup"><span data-stu-id="8c426-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
 <span data-ttu-id="8c426-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="8c426-104">\<system.serviceModel></span></span>  
<span data-ttu-id="8c426-105">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="8c426-105">\<routing></span></span>  
<span data-ttu-id="8c426-106">\<backupLists></span><span class="sxs-lookup"><span data-stu-id="8c426-106">\<backupLists></span></span>  
<span data-ttu-id="8c426-107">\<backupList></span><span class="sxs-lookup"><span data-stu-id="8c426-107">\<backupList></span></span>  
<span data-ttu-id="8c426-108">\<add></span><span class="sxs-lookup"><span data-stu-id="8c426-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c426-109">语法</span><span class="sxs-lookup"><span data-stu-id="8c426-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c426-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="8c426-110">Attributes and Elements</span></span>  
 <span data-ttu-id="8c426-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="8c426-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c426-112">特性</span><span class="sxs-lookup"><span data-stu-id="8c426-112">Attributes</span></span>  
  
|<span data-ttu-id="8c426-113">特性</span><span class="sxs-lookup"><span data-stu-id="8c426-113">Attribute</span></span>|<span data-ttu-id="8c426-114">描述</span><span class="sxs-lookup"><span data-stu-id="8c426-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8c426-115">name</span><span class="sxs-lookup"><span data-stu-id="8c426-115">name</span></span>|<span data-ttu-id="8c426-116">一个字符串，指定备份终结点的名称。</span><span class="sxs-lookup"><span data-stu-id="8c426-116">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8c426-117">子元素</span><span class="sxs-lookup"><span data-stu-id="8c426-117">Child Elements</span></span>  
 <span data-ttu-id="8c426-118">无。</span><span class="sxs-lookup"><span data-stu-id="8c426-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8c426-119">父元素</span><span class="sxs-lookup"><span data-stu-id="8c426-119">Parent Elements</span></span>  
  
|<span data-ttu-id="8c426-120">元素</span><span class="sxs-lookup"><span data-stu-id="8c426-120">Element</span></span>|<span data-ttu-id="8c426-121">描述</span><span class="sxs-lookup"><span data-stu-id="8c426-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c426-122">\<routing></span><span class="sxs-lookup"><span data-stu-id="8c426-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="8c426-123">包含你想要使用在的情况下无法访问主终结点的路由服务的终结点的列表。</span><span class="sxs-lookup"><span data-stu-id="8c426-123">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8c426-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="8c426-124">See also</span></span>
- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>

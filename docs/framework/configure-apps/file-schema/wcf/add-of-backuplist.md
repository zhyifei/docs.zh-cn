---
title: <add> 的 <backupList>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 03bf1bbb8156e4722d987e171d9034747ac6bb61
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701198"
---
# <a name="add-of-backuplist"></a><span data-ttu-id="ca496-102">\<添加 > 的\<backupList ></span><span class="sxs-lookup"><span data-stu-id="ca496-102">\<add> of \<backupList></span></span>
<span data-ttu-id="ca496-103">表示定义备份终结点元素的配置元素。</span><span class="sxs-lookup"><span data-stu-id="ca496-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
 <span data-ttu-id="ca496-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="ca496-104">\<system.serviceModel></span></span>  
<span data-ttu-id="ca496-105">\<路由 ></span><span class="sxs-lookup"><span data-stu-id="ca496-105">\<routing></span></span>  
<span data-ttu-id="ca496-106">\<backupLists></span><span class="sxs-lookup"><span data-stu-id="ca496-106">\<backupLists></span></span>  
<span data-ttu-id="ca496-107">\<backupList></span><span class="sxs-lookup"><span data-stu-id="ca496-107">\<backupList></span></span>  
<span data-ttu-id="ca496-108">\<add></span><span class="sxs-lookup"><span data-stu-id="ca496-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca496-109">语法</span><span class="sxs-lookup"><span data-stu-id="ca496-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ca496-110">特性和元素</span><span class="sxs-lookup"><span data-stu-id="ca496-110">Attributes and Elements</span></span>  
 <span data-ttu-id="ca496-111">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="ca496-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ca496-112">特性</span><span class="sxs-lookup"><span data-stu-id="ca496-112">Attributes</span></span>  
  
|<span data-ttu-id="ca496-113">特性</span><span class="sxs-lookup"><span data-stu-id="ca496-113">Attribute</span></span>|<span data-ttu-id="ca496-114">描述</span><span class="sxs-lookup"><span data-stu-id="ca496-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ca496-115">name</span><span class="sxs-lookup"><span data-stu-id="ca496-115">name</span></span>|<span data-ttu-id="ca496-116">一个字符串，指定备份终结点的名称。</span><span class="sxs-lookup"><span data-stu-id="ca496-116">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ca496-117">子元素</span><span class="sxs-lookup"><span data-stu-id="ca496-117">Child Elements</span></span>  
 <span data-ttu-id="ca496-118">无。</span><span class="sxs-lookup"><span data-stu-id="ca496-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ca496-119">父元素</span><span class="sxs-lookup"><span data-stu-id="ca496-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ca496-120">元素</span><span class="sxs-lookup"><span data-stu-id="ca496-120">Element</span></span>|<span data-ttu-id="ca496-121">描述</span><span class="sxs-lookup"><span data-stu-id="ca496-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ca496-122">\<routing></span><span class="sxs-lookup"><span data-stu-id="ca496-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="ca496-123">包含你想要使用在的情况下无法访问主终结点的路由服务的终结点的列表。</span><span class="sxs-lookup"><span data-stu-id="ca496-123">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ca496-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="ca496-124">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>

---
title: <add> 的 <backupList>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 80726cc22cb56013c85c7704c28579b1337666c9
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850553"
---
# <a name="add-of-backuplist"></a><span data-ttu-id="c96a7-102">\<添加 backupList > \<的 ></span><span class="sxs-lookup"><span data-stu-id="c96a7-102">\<add> of \<backupList></span></span>
<span data-ttu-id="c96a7-103">表示定义备份终结点元素的配置元素。</span><span class="sxs-lookup"><span data-stu-id="c96a7-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
<span data-ttu-id="c96a7-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c96a7-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c96a7-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="c96a7-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="c96a7-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<路由 >** ](routing.md)</span><span class="sxs-lookup"><span data-stu-id="c96a7-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="c96a7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<backupLists >** ](backuplists.md)</span><span class="sxs-lookup"><span data-stu-id="c96a7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupLists>**](backuplists.md)</span></span>\
<span data-ttu-id="c96a7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<backupList >** ](backuplist.md)</span><span class="sxs-lookup"><span data-stu-id="c96a7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupList>**](backuplist.md)</span></span>\
<span data-ttu-id="c96a7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<添加 >**</span><span class="sxs-lookup"><span data-stu-id="c96a7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c96a7-110">语法</span><span class="sxs-lookup"><span data-stu-id="c96a7-110">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c96a7-111">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c96a7-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c96a7-112">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c96a7-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c96a7-113">特性</span><span class="sxs-lookup"><span data-stu-id="c96a7-113">Attributes</span></span>  
  
|<span data-ttu-id="c96a7-114">特性</span><span class="sxs-lookup"><span data-stu-id="c96a7-114">Attribute</span></span>|<span data-ttu-id="c96a7-115">描述</span><span class="sxs-lookup"><span data-stu-id="c96a7-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c96a7-116">NAME</span><span class="sxs-lookup"><span data-stu-id="c96a7-116">name</span></span>|<span data-ttu-id="c96a7-117">一个字符串，指定备份终结点的名称。</span><span class="sxs-lookup"><span data-stu-id="c96a7-117">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c96a7-118">子元素</span><span class="sxs-lookup"><span data-stu-id="c96a7-118">Child Elements</span></span>  
 <span data-ttu-id="c96a7-119">无。</span><span class="sxs-lookup"><span data-stu-id="c96a7-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c96a7-120">父元素</span><span class="sxs-lookup"><span data-stu-id="c96a7-120">Parent Elements</span></span>  
  
|<span data-ttu-id="c96a7-121">元素</span><span class="sxs-lookup"><span data-stu-id="c96a7-121">Element</span></span>|<span data-ttu-id="c96a7-122">描述</span><span class="sxs-lookup"><span data-stu-id="c96a7-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c96a7-123">\<routing></span><span class="sxs-lookup"><span data-stu-id="c96a7-123">\<routing></span></span>](routing.md)|<span data-ttu-id="c96a7-124">包含当无法访问主终结点时路由服务将使用的终结点的列表。</span><span class="sxs-lookup"><span data-stu-id="c96a7-124">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c96a7-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="c96a7-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>

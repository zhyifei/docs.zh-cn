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
# <a name="add-of-backuplist"></a>\<添加 backupList > \<的 >
表示定义备份终结点元素的配置元素。  
  
 \<system.serviceModel>  
\<路由 >  
\<backupLists>  
\<backupList>  
\<add>  
  
## <a name="syntax"></a>语法  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|NAME|一个字符串，指定备份终结点的名称。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<routing>](routing.md)|包含当无法访问主终结点时路由服务将使用的终结点的列表。|  
  
## <a name="see-also"></a>请参阅

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>

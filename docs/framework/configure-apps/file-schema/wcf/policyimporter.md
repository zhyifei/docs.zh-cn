---
title: <policyImporter>
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 273bd0d5e68a661c639b82264b440b83d8127427
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933793"
---
# <a name="policyimporter"></a>\<policyImporter>
指定一个策略导入程序，用于控制有关绑定的自定义策略断言的导入。  
  
 \<system.ServiceModel>  
\<客户端 >  
\<元数据 >  
\<policyImporters>  
\<policyImporter>  
  
## <a name="syntax"></a>语法  
  
```xml  
<metadata>
  <policyImporters>
    <policyImporter type="String" />
  </policyImporters>
</metadata>
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`type`|此元素的类型。|  
  
### <a name="child-elements"></a>子元素  
 无  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<policyImporters>](policyimporters.md)|指定用于控制有关绑定的自定义策略断言的导入的所有策略导入程序。|  
  
## <a name="remarks"></a>备注  
 策略导入程序用于搜索有关绑定功能的自定义策略断言，并附加一个实现断言所需功能的自定义绑定元素。  
  
## <a name="see-also"></a>请参阅

- <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>
- <xref:System.ServiceModel.Configuration.PolicyImporterElement>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- <xref:System.ServiceModel.Description.MetadataImporter>
- [WCF 客户端配置](../../../wcf/feature-details/client-configuration.md)
- [客户端](../../../wcf/feature-details/clients.md)

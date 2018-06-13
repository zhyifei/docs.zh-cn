---
title: '&lt;policyImporter&gt;'
ms.date: 03/30/2017
ms.assetid: b0d03456-546f-44bb-ab12-1b2ce7f98fca
ms.openlocfilehash: 7483a95accef0a4bc956d919087379363b4762ca
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32753022"
---
# <a name="ltpolicyimportergt"></a>&lt;policyImporter&gt;
指定一个策略导入程序，用于控制有关绑定的自定义策略断言的导入。  
  
 \<system.ServiceModel>  
\<客户端 >  
\<元数据 >  
\<policyImporters >  
\<policyImporter >  
  
## <a name="syntax"></a>语法  
  
```xml  
<metadata>  
   <policyImporters>  
      <policyImporter type="string" />  
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
|[\<policyImporters >](../../../../../docs/framework/configure-apps/file-schema/wcf/policyimporters.md)|指定用于控制有关绑定的自定义策略断言的导入的所有策略导入程序。|  
  
## <a name="remarks"></a>备注  
 策略导入程序用于搜索有关绑定功能的自定义策略断言，并附加一个实现断言所需功能的自定义绑定元素。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Configuration.PolicyImporterElementCollection>  
 <xref:System.ServiceModel.Configuration.PolicyImporterElement>  
 <xref:System.ServiceModel.Configuration.MetadataElement>  
 <xref:System.ServiceModel.Description.MetadataImporter>  
 [WCF 客户端配置](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [客户端](../../../../../docs/framework/wcf/feature-details/clients.md)

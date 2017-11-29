---
title: dataContractSerializer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4044e81b7c33c7a755678e79586dd4f37cf54ed5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="datacontractserializer"></a>dataContractSerializer
包含 <xref:System.Runtime.Serialization.DataContractSerializer> 的配置数据。  
  
 \<系统。ServiceModel >  
\<行为 >  
\<endpointBehaviors >  
\<行为 >  
\<dataContractSerializer >  
  
## <a name="syntax"></a>语法  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"  
      maxItemsInObjectGraph="Integer" />  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|元素|描述|  
|-------------|-----------------|  
|ignoreExtensionDataObject|一个布尔值，指定在对终结点进行序列化或反序列化时，是否要忽略由该终结点提供的数据。|  
|maxItemsInObjectGraph|一个整数，指定要序列化或反序列化的最大项数。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<行为 >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|指定终结点行为。|  
  
## <a name="remarks"></a>备注  
 有关已知类型的更多信息，请参见 <xref:System.Runtime.Serialization.DataContractSerializer> 文档。  
  
> [!CAUTION]
>  在配置文件中，`<dataContractSerializer>` 行为元素（如果有）应始终在 `<enableWebScript>` 行为元素之前出现。 否则，产生的行为将是不确定的。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>  
 <xref:System.ServiceModel.Configuration.DataContractSerializerElement>  
 [数据协定已知的类型](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [数据传输和序列化](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)

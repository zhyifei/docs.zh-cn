---
title: <system.runtime.serialization>
ms.date: 03/30/2017
ms.assetid: a8cebf4c-06d2-4667-8f5b-c3e1fc90df6f
ms.openlocfilehash: c93a1f482882cc8cd9d229d82597efa64ba209bc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152965"
---
# <a name="systemruntimeserialization"></a>\<系统.运行时.序列化>
表示 <xref:System.Runtime.Serialization> 命名空间节的根元素，并包含 <xref:System.Runtime.Serialization.DataContractSerializer> 的设置选项的元素。  

[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;**\<系统.运行时.序列化>**  
  
## <a name="syntax"></a>语法  
  
```xml  
<configuration>
  <system.runtime.serialization>
    <dataContractSerializer ignoreExtensionDataObject="Boolean"
                            maxItemsInObjectGraph="Integer">
      <declaredTypes>
        <add type="String">
          <knownType type="String">
            <parameter index="Integer" />
          </knownType>
        </add>
      </declaredTypes>
    <dataContractSerializer>
  </system.runtime.serialization>
</configuration>
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 以下几节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  
 无。  
  
### <a name="child-elements"></a>子元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<数据合同序列化器>](datacontractserializer-of-system-runtime-serialization.md)|使得可以在反序列化时添加要使用的已知类型。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<配置>元素](../configuration-element.md)|配置的顶级元素。|  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Runtime.Serialization>
- [使用数据协定](../../../wcf/feature-details/using-data-contracts.md)
- [数据协定 已知类型](../../../wcf/feature-details/data-contract-known-types.md)

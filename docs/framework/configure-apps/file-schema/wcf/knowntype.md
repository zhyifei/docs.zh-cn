---
title: <knownType>
ms.date: 03/30/2017
ms.assetid: ee2b7be3-7148-4a3a-b861-48e7330615e5
ms.openlocfilehash: a0794314cfcb87df00d66b6832356fb130787eba
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928867"
---
# <a name="knowntype"></a>\<knownType>
指定在反序列化过程中将由 <xref:System.Runtime.Serialization.DataContractSerializer> 使用的类型。 该元素指定由某个“声明的类型”的字段或属性返回到“已知类型”。 有关详细信息, 请参阅[数据协定已知类型](../../../wcf/feature-details/data-contract-known-types.md)。  
  
 \<system.runtime.serialization>  
\<dataContractSerializer>  
\<declaredTypes > 元素  
\<添加 declaredTypes > \<的 >  
\<knownType > 元素  
  
## <a name="syntax"></a>语法  
  
```xml  
<knownType type="String">
  <parameter index="Integer"
             type="String" />
</knownType>
```  
  
## <a name="type"></a>类型  
 `string`  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|type|指定类型（包括命名空间）、程序集名称、版本、区域性和公钥标记。|  
  
### <a name="child-elements"></a>子元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<parameter>](parameter.md)|当声明类型为泛型类型时指定参数索引。|  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<add>](add-of-declaredtypes-element.md)|向声明类型的集合中添加一个声明类型。|  
  
## <a name="remarks"></a>备注  
 有关已知类型的详细信息, 请参阅[数据协定已知类型](../../../wcf/feature-details/data-contract-known-types.md)和<xref:System.Runtime.Serialization.DataContractSerializer>。  
  
 有关使用此元素的示例, 请参阅[ dataContractSerializer>。\<](datacontractserializer-element.md)  
  
## <a name="example"></a>示例  
  
```xml  
<add type="MyCompany.Library.Shape,
           MyAssembly, Version=2.0.0.0, Culture=neutral,
           PublicKeyToken=XXXXXX, processorArchitecture=MSIL">
  <knownType type="MyCompany.Library.Circle,
                   MyAssembly, Version=2.0.0.0, Culture=neutral,
                   PublicKeyToken=XXXXXX,
                   processorArchitecture=MSIL"/>
</add>
```  
  
## <a name="see-also"></a>请参阅

- <xref:System.Runtime.Serialization.DataContractSerializer>
- [数据协定已知类型](../../../wcf/feature-details/data-contract-known-types.md)
- [\<dataContractSerializer>](datacontractserializer-element.md)
- [\<add>](add-of-declaredtypes-element.md)

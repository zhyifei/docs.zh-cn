---
title: <unrecognizedPolicyAssertion>
ms.date: 03/30/2017
ms.assetid: 043c3c8f-f263-4ac7-a1af-945d03413f0b
ms.openlocfilehash: 82a221c549efb68532a7a6f85446c5774d4a4d6a
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732485"
---
# <a name="unrecognizedpolicyassertion"></a>\<unrecognizedPolicyAssertion >
表示用于指定策略断言的绑定元素。 此元素没有属性并且以空开关形式存在。  
  
[ **\<configuration>** ](../configuration-element.md)\
\<system &nbsp; &nbsp;[ **>** ](system-servicemodel.md) \
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<绑定**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<绑定 >** \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<unrecognizedPolicyAssertion >**  
  
## <a name="syntax"></a>语法  
  
```xml  
<unrecognizedPolicyAssertion />
```  
  
## <a name="type"></a>键入  
 `Type`  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无。  
  
### <a name="child-elements"></a>子元素  
 None  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<binding >](bindings.md)|定义自定义绑定的所有绑定功能。|  
  
## <a name="see-also"></a>请参阅

- <xref:System.ServiceModel.Channels.CustomBinding>
- [绑定](../../../wcf/bindings.md)
- [扩展绑定](../../../wcf/extending/extending-bindings.md)
- [自定义绑定](../../../wcf/extending/custom-bindings.md)
- [\<customBinding >](custombinding.md)

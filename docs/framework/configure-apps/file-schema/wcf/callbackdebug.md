---
title: '&lt;callbackDebug&gt;'
ms.date: 03/30/2017
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
ms.openlocfilehash: 1aa292a3fe06af9cf1dbc53ebf5bbdf9841be8d9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54687370"
---
# <a name="ltcallbackdebuggt"></a>&lt;callbackDebug&gt;
指定服务调试 Windows Communication Foundation (WCF) 回调对象。  
  
 \<system.ServiceModel>  
\<behaviors>  
\<endpointBehaviors>  
\<behavior>  
\<callbackDebug>  
  
## <a name="syntax"></a>语法  
  
```xml  
<callbackDebug includeExceptionDetailInFaults="Boolean" />
```  
  
## <a name="type"></a>类型  
 `Type`  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`includeExceptionDetailInFaults`|一个值，指定客户端回调对象是否向服务返回 SOAP 错误中的托管异常信息。<br /><br /> 如果以编程方式将此属性设置为 `true`，则可以将客户端回调对象中的托管异常信息回流到服务，以便进行调试。 注意：向客户端返回托管异常信息可能具有安全风险。 这是因为，异常详细信息公开了有关内部服务实现的信息，这些信息可能被未经授权的客户端使用。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<behavior>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|指定终结点行为。|  
  
## <a name="see-also"></a>请参阅
- <xref:System.ServiceModel.Configuration.CallbackDebugElement>
- <xref:System.ServiceModel.Description.CallbackDebugBehavior>

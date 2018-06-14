---
title: '&lt;synchronousReceive&gt; 元素'
ms.date: 03/30/2017
ms.assetid: cc070387-3d11-4b02-a952-bc08ad2df05a
ms.openlocfilehash: af1ca2ee1fe3c03c33f05e0c30c7b843b3720a36
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32753256"
---
# <a name="ltsynchronousreceivegt-element"></a>&lt;synchronousReceive&gt; 元素
此配置元素用于指定服务或客户端应用程序中用来接收消息的运行时行为。 它不具有任何属性或子元素。  
  
 \<system.ServiceModel>  
\<行为 >  
\<endpointBehaviors>  
\<行为 >  
\<v e >  
  
## <a name="syntax"></a>语法  
  
```xml  
<synchronousReceive />  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
 无。  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<行为 >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|指定终结点行为。|  
  
## <a name="remarks"></a>备注  
 使用此行为可指示通道侦听器使用同步接收，而非默认的异步接受。 Windows Communication Foundation (WCF) 发出一个新线程，以为每个接受通道进行抽取。 如果有许多通道，则可能出现线程溢出的情况。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.ServiceModel.Configuration.SynchronousReceiveElement>  
 <xref:System.ServiceModel.Description.SynchronousReceiveBehavior>

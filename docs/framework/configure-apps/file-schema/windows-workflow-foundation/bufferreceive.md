---
title: '&lt;bufferReceive&gt;'
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: b23c3a54-10d4-4f13-ab6d-98b26b76f22a
ms.openlocfilehash: 07d5b66b14d9495808f972734cdce4476efaefde
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltbufferreceivegt"></a>&lt;bufferReceive&gt;
一种服务行为，允许服务使用缓冲接收处理，以使工作流服务能够处理无序消息。  
  
\<system.ServiceModel>  
\<行为 >  
\<serviceBehaviors>  
\<行为 >  
\<bufferReceive >  
  
## <a name="syntax"></a>语法  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <bufferReceive maxPendingMessagesPerChannel="Integer" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|maxPendingMessagesPerChannel|一个整数，指定每个通道允许的最大挂起消息数。 默认值为 512。 此属性限制工作流服务可接收的无序消息数。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<行为 > 的\<serviceBehaviors >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|指定行为元素。|  
  
## <a name="see-also"></a>请参阅  
<!-- <xref:System.ServiceModel.Activities.Description.BufferReceiveServiceBehavior>  -->
 <xref:System.ServiceModel.Activities.Configuration.BufferedReceiveElement>

---
title: <etwTracking>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: cb45c82e-6ea1-4c4d-924c-118a25ae1f35
ms.openlocfilehash: d562bd4e3d46a1bdf41fc4065fee926850a49aa1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152166"
---
# <a name="etwtracking"></a>\<etw 跟踪>
一种服务行为，允许服务使用 <xref:System.Activities.Tracking.EtwTrackingParticipant> 来利用 ETW 跟踪。  
  
[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<系统。服务模式>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<行为>**](behaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<服务行为>**](servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<行为>**](behavior-of-servicebehaviors-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<etw 跟踪>**  
  
## <a name="syntax"></a>语法  
  
```xml  
<behaviors>
  <serviceBehaviors>
    <behavior name="String">
      <etwTracking profileName="String" />
    </behavior>
  </serviceBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  
  
|Attribute|说明|  
|---------------|-----------------|  
|profileName|一个字符串，指定与此行为关联的跟踪配置文件的名称。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|[\<服务行为行为\<>>](behavior-of-servicebehaviors-of-workflow.md)|指定行为元素。|  
  
## <a name="remarks"></a>备注  
 在添加到服务的行为配置后，此配置元素对工作流服务配置跟踪参与者。  
  
 跟踪参与者用于获取从工作流发出的跟踪数据并将其存储在不同的媒体中。 同样，也可以在跟踪参与者中执行对跟踪记录的任何后续处理。  
  
## <a name="example"></a>示例  
 下面的配置示例演示在 Web.config 文件中配置的标准 ETW 跟踪参与者。  
  
 ETW 跟踪参与者用于将跟踪记录写入 ETW 的提供程序 ID 在**\<诊断>** 部分中定义。 跟踪参与者具有一个与其关联的配置文件，用来指定跟踪参与者已订阅的跟踪记录。 这由**\<添加>** 元素的**配置文件名称**属性定义。 定义这些后，跟踪参与者将添加到**\<etw 跟踪>** 服务行为。 这会将所选跟踪参与者添加到工作流实例的扩展中，以便它们开始接收跟踪记录。  
  
```xml  
<configuration>
  <system.web>
    <compilation targetFrameworkMoniker=".NETFramework,Version=v4.0"/>
  </system.web>
  <system.serviceModel>
    <diagnostics etwProviderId="52A3165D-4AD9-405C-B1E8-7D9A257EAC9F" />
    <tracking>
      <participants>
        <add name="EtwTrackingParticipant"
             type="System.Activities.Tracking.EtwTrackingParticipant, System.Activities, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
             profileName="HealthMonitoring_Tracking_Profile"/>
      </participants>
    </tracking>
    <behaviors>
      <serviceBehaviors>
        <behavior>
          <etwTracking profileName="Sample Tracking Profile"/>  
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>  
```  
  
## <a name="see-also"></a>另请参阅

- <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>
- <xref:System.ServiceModel.Activities.Configuration.EtwTrackingBehaviorElement>
- [工作流跟踪](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [跟踪参与者](../../../windows-workflow-foundation/tracking-participants.md)

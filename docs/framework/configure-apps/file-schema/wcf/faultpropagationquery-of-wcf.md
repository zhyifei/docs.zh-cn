---
title: WCF 的 &lt;faultPropagationQuery&gt;
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: c3853c470a9243835e071d35008dfff5b885591d
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "49123314"
---
# <a name="ltfaultpropagationquerygt-of-wcf"></a>WCF 的 &lt;faultPropagationQuery&gt;

表示一个用于跟踪在活动中发生的错误的处理的查询。  每次 FaultHandler 处理错误时，都会发生此事件。 应使用此类查询来跟踪对在活动中出现的错误进行的处理。 跟踪参与者需要用此查询来订阅错误传播记录。  
  
有关跟踪配置文件查询的详细信息，请参阅[跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。  
  
\<system.serviceModel>  
\<跟踪 >  
\<配置文件 >  
\<trackingProfile>  
\<工作流 >  
\<faultPropagationQueries >  
\<faultPropagationQuery >  
  
## <a name="syntax"></a>语法  
  
```xml
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <faultPropagationQueries>
          <faultPropagationQuery faultSourceActivityName="String"
                                 faultHandlerActivityName="String"/>
        </faultPropagationQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```
  
## <a name="attributes-and-elements"></a>特性和元素

下列各节描述了特性、子元素和父元素。

### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`faultSourceActivityName`|一个字符串，指定传播错误的错误处理程序活动的名称。 默认值是\*，这指示为所有活动返回错误传播记录。|  
|`faultHandlerActivityName`|一个字符串，指定导致错误的活动的名称。|  
  
### <a name="child-elements"></a>子元素

无。
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<faultPropagationQueries>](faultpropagationqueries-of-wcf.md)|表示一个配置元素列表，这些元素用于跟踪某个活动中发生的错误的处理。  每次 FaultHandler 处理错误时，都会发生此事件。|
  
## <a name="see-also"></a>请参阅  
 
- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [工作流跟踪](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [跟踪配置文件](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)

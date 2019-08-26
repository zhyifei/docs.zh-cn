---
title: <diagnostics>用于激活
ms.date: 03/30/2017
ms.assetid: 1486e0eb-fe2a-46c3-b584-c924889477dd
ms.openlocfilehash: 543c41936921eda39017e07f1c97294b268a9141
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919221"
---
# <a name="diagnostics-for-activation"></a>\<用于激活的诊断 >
配置 Windows Communication Foundation (WCF) 侦听器的诊断功能。  
  
 \<system.serviceModel.activation>  
\<diagnostics>  
  
## <a name="syntax"></a>语法  
  
```xml  
<configuration>
  <system.serviceModel.activation>
    <diagnostics performanceCountersEnabled="Boolean" />
  </system.serviceModel.activation>
</configuration>
```  
  
## <a name="type"></a>类型  
 `Type`  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`performanceCountersEnabled`|一个布尔值，指示是否启用用于诊断目的的性能计数器。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<system.serviceModel.activation>](system-servicemodel-activation.md)|包含侦听器进程 SMSvcHost.exe 的配置设置。|  
  
## <a name="see-also"></a>请参阅

- <xref:System.ServiceModel.Activation.Configuration.DiagnosticSection>

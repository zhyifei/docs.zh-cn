---
title: <performanceCounter> 元素（网络设置）
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounter element
- <performanceCounter> element
ms.assetid: 3afa1586-e1b8-473d-8985-c3fc90cf561b
ms.openlocfilehash: 05aac6c1ed3c04bce263a45cafdb9bec906bd75b
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69664065"
---
# <a name="performancecounter-element-network-settings"></a>\<performanceCounter > 元素 (网络设置)
启用或禁用网络性能计数器。  
  
 \<configuration>  
\<system.net>  
\<设置 >  
\<performanceCounters>  
  
## <a name="syntax"></a>语法  
  
```xml  
<performanceCounters  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`enabled`|指定是否启用网络性能计数器。 默认值为 `false`。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[设置](settings-element-network-settings.md)|配置 <xref:System.Net> 命名空间的基本网络选项。|  
  
## <a name="remarks"></a>备注  
 此元素可在应用程序配置文件或计算机配置文件 (Machine.config) 中使用。  
  
 需要在要使用的配置文件中启用网络性能计数器。 通过配置文件中的单个设置即可启用或禁用所有网络性能计数器。 不能启用或禁用单个网络性能计数器。 有关特定的网络性能计数器的详细信息, 请参阅[联网性能计数器](../../../debug-trace-profile/performance-counters.md#networking)。  
  
 默认值是禁用网络性能计数器。  
  
 属性可用于从适用的配置文件中获取**已启用**属性的当前值。 <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType>  
  
## <a name="example"></a>示例  
 下面的示例演示如何配置<xref:System.Net>和相关命名空间, 以启用网络性能计数器。  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <performanceCounters  
        enabled="true"  
      />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅

- <xref:System.Net.Configuration.PerformanceCountersElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.PerformanceCountersElement.Enabled%2A?displayProperty=nameWithType>
- [网络设置架构](index.md)
- [网络性能计数器](../../../debug-trace-profile/performance-counters.md#networking)

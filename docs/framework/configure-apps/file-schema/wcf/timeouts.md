---
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: b159488efa2a80a9dea625e4c6dfe2f215dfc457
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939189"
---
# <a name="timeouts"></a>\<timeOuts>
表示一个配置元素，该元素指定允许服务主机打开或关闭的时间间隔。  
  
 \<system.ServiceModel>  
\<客户端 >  
\<终结点 >  
\<主机 >  
\<timeOuts>  
  
## <a name="syntax"></a>语法  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`closeTimeout`|一个 <xref:System.TimeSpan> 值，指定为关闭服务主机预留的时间间隔。|  
|`openTimeout`|一个 <xref:System.TimeSpan> 值，指定为打开或关闭服务主机预留的时间间隔。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|[\<host>](host.md)|一个指定服务主机设置的配置元素。|  
  
## <a name="see-also"></a>请参阅

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [承载](../../../wcf/feature-details/hosting.md)

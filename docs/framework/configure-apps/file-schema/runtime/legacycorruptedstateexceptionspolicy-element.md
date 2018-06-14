---
title: '&lt;legacyCorruptedStateExceptionsPolicy&gt;元素'
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6228aaf4c7da70337d9d1a99adcb78f71a0039b2
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32744611"
---
# <a name="ltlegacycorruptedstateexceptionspolicygt-element"></a>&lt;legacyCorruptedStateExceptionsPolicy&gt;元素
指定公共语言运行时是否允许托管的代码获取访问冲突和其他损坏的状态异常。  
  
 \<configuration>  
\<运行时 >  
\<legacyCorruptedStateExceptionsPolicy >  
  
## <a name="syntax"></a>语法  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`enabled`|必需的特性。<br /><br /> 指定应用程序将捕获损坏状态异常失败，例如访问冲突。|  
  
## <a name="enabled-attribute"></a>enabled 特性  
  
|值|描述|  
|-----------|-----------------|  
|`false`|应用程序将不会捕获损坏状态异常失败，例如访问冲突。 这是默认设置。|  
|`true`|应用程序将捕获损坏状态异常失败，例如访问冲突。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关程序集绑定和垃圾回收的信息。|  
  
## <a name="remarks"></a>备注  
 在.NET Framework 版本 3.5 及更早版本中，公共语言运行时允许托管的代码，若要捕捉由损坏的进程状态引发的异常。 访问冲突是这种异常的示例。  
  
 从开始[!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]，托管代码将不再捕获这些类型中的异常的`catch`块。 但是，你可以重写此更改和维护的两种方式的损坏的状态异常的处理方式：  
  
-   设置`<legacyCorruptedStateExceptionsPolicy>`元素的`enabled`属性设为`true`。 此配置设置是适用，并且会影响所有方法。  
  
 -或-  
  
-   应用<xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType>属性设为包含异常的方法`catch`块。  
  
 此配置元素可仅用于[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]及更高版本。  
  
## <a name="example"></a>示例  
 下面的示例演示如何指定应用程序应恢复到之前的行为[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]，并捕获所有损坏状态异常失败。  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>  
 [运行时设置架构](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [配置文件架构](../../../../../docs/framework/configure-apps/file-schema/index.md)

---
title: '&lt;enforceFIPSPolicy&gt;元素'
ms.date: 03/30/2017
helpviewer_keywords:
- enforceFIPSPolicy element
- FIPS
- <enforceFIPSPolicy> element
- Federal Information Processing Standards (FIPS)
ms.assetid: c35509c4-35cf-43c0-bb47-75e4208aa24e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9040bf2548964cf6df5f4fd87ee9f6d979c7df1e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32746210"
---
# <a name="ltenforcefipspolicygt-element"></a>&lt;enforceFIPSPolicy&gt;元素
指定是否强制执行以下计算机配置要求：加密算法必须符合美国联邦信息处理标准 (FIPS)。  
  
 \<配置 > 元素  
\<运行时 > 元素  
\<enforceFIPSPolicy > 元素  
  
## <a name="syntax"></a>语法  
  
```xml  
<enforceFIPSPolicy enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|enabled|必需的特性。<br /><br /> 指定是否启用强制实施的加密算法必须与 FIPS 兼容的计算机配置要求。|  
  
## <a name="enabled-attribute"></a>enabled 特性  
  
|值|描述|  
|-----------|-----------------|  
|`true`|如果你的计算机配置为要求要符合 FIPS 标准的加密算法，强制实施该要求。 如果一个类实现的算法的不符合 FIPS，构造函数或`Create`为该类的方法会引发异常，在运行时在该计算机上。 这是默认设置。|  
|`false`|应用程序使用的加密算法不需要要符合 FIPS，而不考虑计算机配置。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关程序集绑定和垃圾回收的信息。|  
  
## <a name="remarks"></a>备注  
 从.NET Framework 2.0 开始，将由计算机的配置控制实现加密算法的类创建。 如果计算机配置为需要算法要符合 FIPS，并且一个类可实现不符合 FIPS 的算法，任何创建此类的实例尝试将引发异常。 构造函数引发<xref:System.InvalidOperationException>异常，和`Create`方法将引发<xref:System.Reflection.TargetInvocationException>内部的异常<xref:System.InvalidOperationException>异常。  
  
 如果你的应用程序在其配置需要与 FIPS，符合性的计算机上运行，并且你的应用程序使用不符合 FIPS 的算法，你可以使用此元素在配置文件以防止公共语言运行时 (CLR) 从强制 FIPS 符合性。 此元素已引入中[!INCLUDE[net_v20SP1_long](../../../../../includes/net-v20sp1-long-md.md)]。  
  
## <a name="example"></a>示例  
 下面的示例演示如何防止 CLR 强制 FIPS 符合性。  
  
```xml  
<configuration>  
    <runtime>  
        <enforceFIPSPolicy enabled="false"/>  
    </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅  
 [运行时设置架构](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [配置文件架构](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [加密模型](../../../../../docs/standard/security/cryptography-model.md)

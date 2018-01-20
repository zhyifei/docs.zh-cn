---
title: "&lt;requiredRuntime&gt;元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requiredRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/requiredRuntime
helpviewer_keywords:
- requiredRuntime element
- <requiredRuntime> element
- container tags, <requiredRuntime> element
ms.assetid: 9fa1639e-beb8-43be-b7a4-12f7b229c34b
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 2e864eec2ddf51d5cc88110654f6c23f146938d5
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="ltrequiredruntimegt-element"></a>&lt;requiredRuntime&gt;元素
指定应用程序仅支持 1.0 版本的公共语言运行时。 此元素已弃用，并应不再使用。 [ `supportedRuntime` ](supportedruntime-element.md)元素应改为使用。
  
 \<configuration>  
\<startup>  
\<requiredRuntime>  
  
## <a name="syntax"></a>语法  
  
```xml  
   <requiredRuntime    
version="runtime version"  
safemode="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`version`|可选特性。<br /><br /> 一个字符串值，指定此应用程序支持的.NET framework 的版本。 字符串值必须与在.NET Framework 安装根目录下找到的目录名称匹配。 未分析的字符串值的内容。|  
|`safemode`|可选特性。<br /><br /> 指定运行时启动代码是否搜索注册表项以确定运行时版本。|  
  
## <a name="safemode-attribute"></a>安全模式属性  
  
|“值”|描述|  
|-----------|-----------------|  
|`false`|在注册表中查找运行时启动代码。 这是默认值。|  
|`true`|运行时启动代码不会在注册表中查找。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`startup`|包含`<requiredRuntime>`元素。|  
  
## <a name="remarks"></a>备注  
 为支持仅运行时 1.0 版而生成的应用程序必须使用`<requiredRuntime>`元素。 使用版本 1.1 或更高版本的运行时生成的应用程序必须使用`<supportedRuntime>`元素。  
  
> [!NOTE]
>  如果你使用[CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)函数来指定配置文件，必须使用`<requiredRuntime>`所有的运行时版本的元素。 `<supportedRuntime>`元素将被忽略，当你使用[CorBindToRuntimeByCfg](../../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)。  
  
 `version`属性字符串必须匹配的指定版本的.NET framework 的安装文件夹名。 此字符串不会被解释。 如果运行时启动代码未找到匹配的文件夹，则不会加载运行时;启动代码将显示一条错误消息并退出。  
  
> [!NOTE]
>  Microsoft Internet Explorer 中承载的应用程序的启动代码将忽略`<requiredRuntime>`元素。  
  
## <a name="example"></a>示例  
 下面的示例演示如何在配置文件中指定的运行时版本。  
  
```xml  
<configuration>  
   <startup>  
      <requiredRuntime version="v1.0.3705" safemode="true"/>  
   </startup>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅  
 [启动设置架构](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)  
 [配置文件架构](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [\<PaveOver> 指定要使用的运行时版本](http://msdn.microsoft.com/library/c376208d-980d-42b4-865b-fbe0d9cc97c2)

---
title: '&lt;loadFromRemoteSources&gt;元素'
ms.date: 03/30/2017
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f0d442f71a0e2fc7deacd9aaa02cfba7b66f2349
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="ltloadfromremotesourcesgt-element"></a>&lt;loadFromRemoteSources&gt;元素
指定是否从远程数据源的程序集应被授予完全信任。  
  
> [!NOTE]
>  如果你已由于采用 Visual Studio 项目错误列表或生成错误的错误消息定向到本主题，请参阅[如何： 使用 Visual Studio 中的来自 Web 的程序集](http://msdn.microsoft.com/library/d8635b63-89a0-41aa-90f4-f351b2111070)。  
  
 \<configuration>  
\<运行时 >  
\<loadFromRemoteSources>  
  
## <a name="syntax"></a>语法  
  
```xml  
<loadFromRemoteSources    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|`enabled`|必需的特性。<br /><br /> 指定是否从远程数据源加载程序集应被授予完全信任。|  
  
## <a name="enabled-attribute"></a>enabled 特性  
  
|值|描述|  
|-----------|-----------------|  
|`false`|不要授予完全信任应用程序从远程数据源。 这是默认设置。|  
|`true`|从远程数据源，请向应用程序授予完全信任。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关运行时初始化选项的信息。|  
  
## <a name="remarks"></a>备注  
 在.NET Framework 版本 3.5 和更早版本中，如果从远程位置，加载程序集的程序集将运行部分受信任的依赖在已加载它区域上的授予集。 例如，如果从网站加载程序集，则会将其加载到 Internet 区域中并被授予 Internet 权限集。 换而言之，它在中执行 Internet 沙盒。 如果你尝试在运行该程序集[!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]和更高版本，将引发异常; 您必须显式创建沙盒的程序集 (请参阅[如何： 运行部分受信任的代码在沙盒中](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md))，或在完全信任中运行它。  
  
 通过 `<loadFromRemoteSources>` 元素，可以指定那些在先前版本的 .NET Framework 中以部分信任方式运行的程序集在 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] 和更高版本以完全信任的方式运行。 默认情况下，远程程序集不在 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] 和更高版本中运行。 若要运行远程程序集，则必须以完全信任方式运行它，或者创建沙盒 <xref:System.AppDomain> 来运行它。  
  
> [!NOTE]
>  在 [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)] 中，本地网络共享中的程序集默认以完全信任方式运行；您不必启用 `<loadFromRemoteSources>` 元素。  
  
> [!NOTE]
>  如果应用程序是从 Web 复制而来，Windows 会将其标记为 Web 应用程序，即使它驻留在本地计算机上也不例外。 你可以更改该标记通过更改文件属性，或者可以使用`<loadFromRemoteSources>`元素对程序集授予完全信任。 对于操作系统标记为从 Web 加载的本地程序集，也可以使用 <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> 方法进行加载。  
  
 `enabled`属性仅当禁用代码访问安全性 (CAS) 时，此元素时有效。 默认情况下，CAS 策略中禁用[!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]及更高版本。 如果你设置`enabled`到`true`，远程应用程序被授予完全信任。  
  
 如果`<loadFromRemoteSources>``enabled`未设置为`true`，以下情况下引发异常：  
  
-   当前域的沙盒处理行为是不同于在其行为[!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)]。 这要求 CAS 策略被禁用，并且不进行沙盒处理的当前域。  
  
-   正在加载的程序集不是来自`MyComputer`区域。  
  
> [!NOTE]
>  你可能会收到<xref:System.IO.FileLoadException>在 Windows Virtual PC 应用程序尝试以从托管计算机上的链接文件夹加载文件时。 当你尝试从通过链接的文件夹加载文件时，也可能发生此错误[远程桌面服务](http://go.microsoft.com/fwlink/?LinkId=182775)（终端服务）。 若要避免此异常，设置`enabled`到`true`。  
  
 设置`<loadFromRemoteSources>`元素`true`可防止引发此异常。 它可用于指定，你将不依赖于公共语言运行时沙盒为安全起见，已加载程序集和它们可以有权以执行完全信任。  
  
> [!IMPORTANT]
>  如果程序集不应以完全信任权限运行，则不要设置此配置元素。 相反，创建沙盒<xref:System.AppDomain>要在其中加载程序集。  
  
## <a name="configuration-file"></a>配置文件  
 此元素通常用在应用程序配置文件中，但可根据上下文用于其他配置文件。 有关详细信息，请参阅文章[详细隐式使用的 CAS 策略： loadFromRemoteSources](http://go.microsoft.com/fwlink/p/?LinkId=266839) .NET 安全博客中。  
  
## <a name="example"></a>示例  
 下面的示例演示如何从远程数据源向应用程序授予完全信任。  
  
```xml  
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅  
 [更多隐式使用 CAS 策略： loadFromRemoteSources](http://go.microsoft.com/fwlink/p/?LinkId=266839)  
 [如何：运行沙盒中部分受信任的代码](../../../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)  
 [运行时设置架构](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [配置文件架构](../../../../../docs/framework/configure-apps/file-schema/index.md)

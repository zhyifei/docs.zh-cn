---
title: <loadFromRemoteSources> 元素
ms.date: 05/24/2018
helpviewer_keywords:
- loadFromRemoteSources element
- <loadFromRemoteSources> element
ms.assetid: 006d1280-2ac3-4db6-a984-a3d4e275046a
ms.openlocfilehash: a0dcffe378cdd09de0fbd8f0a6ef0635c033fd9c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154057"
---
# <a name="loadfromremotesources-element"></a>\<负载从远程源>元素
指定是否应授予从远程源加载的程序集对 .NET 框架 4 和更高版本完全信任。
  
> [!NOTE]
> 如果您因为 Visual Studio 项目错误列表中的错误消息或生成错误而被定向到本文，请参阅["如何：在可视化工作室中的 Web 中使用程序集](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee890038(v=vs.100))"。  
  
[**\<配置>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<运行时>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<负载从远程源>**  
  
## <a name="syntax"></a>语法  
  
```xml  
<loadFromRemoteSources
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>属性  
  
|Attribute|说明|  
|---------------|-----------------|  
|`enabled`|必需的特性。<br /><br /> 指定是否应授予从远程源加载的程序集完全信任。|  
  
## <a name="enabled-attribute"></a>启用的属性  
  
|值|说明|  
|-----------|-----------------|  
|`false`|不要对来自远程源的应用程序授予完全信任。 这是默认值。|  
|`true`|完全信任来自远程源的应用程序。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|说明|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关运行时初始化选项的信息。|  
  
## <a name="remarks"></a>备注

在 .NET Framework 3.5 和早期版本中，如果从远程位置加载程序集，则程序集中的代码将部分信任地运行，授予集取决于加载该程序集的区域。 例如，如果从网站加载程序集，则程序集将加载到 Internet 区域并授予 Internet 权限集。 换句话说，它在一个互联网沙盒中执行。

从 .NET 框架 4 开始，代码访问安全 （CAS） 策略被禁用，程序集完全信任地加载。 通常，这将完全信任加载以前已沙盒<xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>的方法的程序集。 为了防止这种情况，默认情况下禁用在从远程源加载的程序集中运行代码的能力。 默认情况下，如果尝试加载远程程序集，则会引发如下所示的<xref:System.IO.FileLoadException>异常消息：

```text
System.IO.FileNotFoundException: Could not load file or assembly 'file:assem.dll' or one of its dependencies. Operation is not supported.
(Exception from HRESULT: 0x80131515)
File name: 'file:assem.dll' --->
System.NotSupportedException: An attempt was made to load an assembly from a network location which would have caused the assembly
to be sandboxed in previous versions of the .NET Framework. This release of the .NET Framework does not enable CAS policy by default,
so this load may be dangerous. If this load is not intended to sandbox the assembly, please enable the loadFromRemoteSources switch.
```

要加载程序集并执行其代码，必须：

- 显式为程序集创建沙盒（[请参阅如何：在沙盒中运行部分受信任的代码](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)）。

- 完全信任运行程序集的代码。 通过配置元素来`<loadFromRemoteSources>`执行此操作。 它允许您指定在 .NET Framework 的早期版本中以部分信任方式运行的程序集现在完全信任 .NET 框架 4 和更高版本。

> [!IMPORTANT]
> 如果程序集不应完全信任地运行，请不要设置此配置元素。 相反，请创建一个装沙<xref:System.AppDomain>盒以加载程序集。

仅当`enabled`禁用代码访问`<loadFromRemoteSources>`安全性 （CAS） 时，元素的属性才有效。 默认情况下，在 .NET 框架 4 和更高版本中禁用 CAS 策略。 如果设置为`enabled``true`，则远程程序集将被授予完全信任。

如果未`enabled`设置为`true`，<xref:System.IO.FileLoadException>则 在以下任一条件下引发 ：

- 当前域的沙盒行为不同于其在 .NET 框架 3.5 中的行为。 这要求禁用 CAS 策略，并且当前域不得沙盒化。

- 正在加载的程序集不来自`MyComputer`区域。

设置元素`<loadFromRemoteSources>`以防止`true`引发此异常。 它使您能够指定您不依赖通用语言运行时来对加载的程序集进行沙盒，以确保安全性，并且可以允许它们完全信任地执行。

## <a name="notes"></a>说明

- 在 .NET 框架 4.5 和更高版本中，本地网络共享上的程序集默认完全信任运行;您不必启用该`<loadFromRemoteSources>`元素。

- 如果应用程序是从 Web 复制而来，Windows 会将其标记为 Web 应用程序，即使它驻留在本地计算机上也不例外。 您可以通过更改其文件属性来更改该名称，也可以使用 元素`<loadFromRemoteSources>`授予程序集完全信任。 对于操作系统标记为从 Web 加载的本地程序集，也可以使用 <xref:System.Reflection.Assembly.UnsafeLoadFrom%2A> 方法进行加载。

- 您可以在 Windows<xref:System.IO.FileLoadException>虚拟 PC 应用程序中运行的 应用程序中获取 。 当您尝试从托管计算机上的链接文件夹中加载文件时，可能会发生这种情况。 当您尝试从通过[远程桌面服务](/windows/win32/termserv/terminal-services-portal)（终端服务）链接的文件夹中加载文件时，也会发生这种情况。 为了避免异常，请设置为`enabled``true`。

## <a name="configuration-file"></a>配置文件

此元素通常用在应用程序配置文件中，但可根据上下文用于其他配置文件。 有关详细信息，请参阅文章["CAS 策略的更多隐式使用：在](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources).NET 安全博客中加载从远程资源"。  

## <a name="example"></a>示例

下面的示例演示如何对从远程源加载的程序集授予完全信任。

```xml
<configuration>  
   <runtime>  
      <loadFromRemoteSources enabled="true"/>  
   </runtime>  
</configuration>  
```

## <a name="see-also"></a>另请参阅

- [CAS 策略的更多隐式使用：从远程源加载](https://docs.microsoft.com/archive/blogs/shawnfa/more-implicit-uses-of-cas-policy-loadfromremotesources)
- [如何：运行沙盒中部分受信任的代码](../../../misc/how-to-run-partially-trusted-code-in-a-sandbox.md)
- [运行时设置架构](index.md)
- [配置文件架构](../index.md)
- <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>

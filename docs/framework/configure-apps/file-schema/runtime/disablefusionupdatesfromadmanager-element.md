---
title: <disableFusionUpdatesFromADManager> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- disableFusionUpdatesFromADManager element
- <disableFusionUpdatesFromADManager> element
ms.assetid: 58d2866c-37bd-4ffa-abaf-ff35926a2939
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b65711ad8c404d1c4f54a6197faf598e2215226f
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252654"
---
# <a name="disablefusionupdatesfromadmanager-element"></a>\<disableFusionUpdatesFromADManager > 元素
指定是否禁用允许运行时主机为应用程序域重写配置设置的默认行为。  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<运行时 >** ](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<disableFusionUpdatesFromADManager>**  
  
## <a name="syntax"></a>语法  
  
```xml  
<disableFusionUpdatesFromADManager enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a>特性和元素  
 下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
|特性|描述|  
|---------------|-----------------|  
|enabled|必需的特性。<br /><br /> 指定是否禁用用于重写合成设置的默认功能。|  
  
## <a name="enabled-attribute"></a>enabled 特性  
  
|值|Description|  
|-----------|-----------------|  
|0|不要禁用替代合成设置的功能。 这是默认行为，从 .NET Framework 4 开始。|  
|1|禁用重写合成设置的功能。 这会恢复到 .NET Framework 早期版本的行为。|  
  
### <a name="child-elements"></a>子元素  
 无。  
  
### <a name="parent-elements"></a>父元素  
  
|元素|描述|  
|-------------|-----------------|  
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|  
|`runtime`|包含有关程序集绑定和垃圾回收的信息。|  
  
## <a name="remarks"></a>备注  
 从 .NET Framework 4 开始，默认<xref:System.AppDomainManager>行为是允许对象通过<xref:System.AppDomainSetup.ConfigurationFile%2A>使用传递到实现的<xref:System.AppDomainSetup>对象的属性或<xref:System.AppDomainSetup.SetConfigurationBytes%2A>方法来重写配置设置。在的子类中，为。 <xref:System.AppDomainManager> <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> 对于默认应用程序域，所更改的设置将覆盖由应用程序配置文件指定的设置。 对于其他应用程序域，它们会重写传递给<xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType>或<xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType>方法的配置设置。  
  
 可以传递新的配置信息，也可以传递 null （`Nothing`在 Visual Basic 中）以消除传入的配置信息。  
  
 不要将配置信息传递给<xref:System.AppDomainSetup.ConfigurationFile%2A>属性<xref:System.AppDomainSetup.SetConfigurationBytes%2A>和方法。 如果将配置信息传递到这两个文件，则会忽略<xref:System.AppDomainSetup.ConfigurationFile%2A>传递给属性的信息， <xref:System.AppDomainSetup.SetConfigurationBytes%2A>因为方法会重写应用程序配置文件中的配置信息。 如果<xref:System.AppDomainSetup.ConfigurationFile%2A>使用属性，则可以将 null （`Nothing` <xref:System.AppDomainSetup.SetConfigurationBytes%2A>在 Visual Basic 中）传递给方法，以消除对<xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType>或<xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType>方法的调用中指定的任何配置字节。  
  
 除了配置信息之外，你还<xref:System.AppDomainSetup>可以在传递给<xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType>方法的实现的对象上更改以下设置： <xref:System.AppDomainSetup.ApplicationBase%2A>、 <xref:System.AppDomainSetup.ApplicationName%2A>、 <xref:System.AppDomainSetup.CachePath%2A>、、 <xref:System.AppDomainSetup.DisallowBindingRedirects%2A> <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>、 <xref:System.AppDomainSetup.DisallowCodeDownload%2A>、 <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A> 、<xref:System.AppDomainSetup.DynamicBase%2A>、 、<xref:System.AppDomainSetup.PrivateBinPath%2A>、、和<xref:System.AppDomainSetup.ShadowCopyFiles%2A>。 <xref:System.AppDomainSetup.LoaderOptimization%2A> <xref:System.AppDomainSetup.PrivateBinPathProbe%2A> <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>  
  
 作为使用`<disableFusionUpdatesFromADManager>`元素的替代方法，你可以通过创建注册表设置或通过设置环境变量来禁用默认行为。 在注册表中，创建一个名为`COMPLUS_disableFusionUpdatesFromADManager` `HKCU\Software\Microsoft\.NETFramework`或`HKLM\Software\Microsoft\.NETFramework`的 DWORD 值，并将该值设置为1。 在命令行中，将环境变量`COMPLUS_disableFusionUpdatesFromADManager`设置为1。  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用`<disableFusionUpdatesFromADManager>`元素禁用重写合成设置的功能。  
  
```xml  
<configuration>  
   <runtime>  
      <disableFusionUpdatesFromADManager enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅

- [运行时设置架构](index.md)
- [配置文件架构](../index.md)
- [运行时如何定位程序集](../../../deployment/how-the-runtime-locates-assemblies.md)

---
title: <startup> 元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup
- http://schemas.microsoft.com/.NetConfiguration/v2.0#startup
helpviewer_keywords:
- container tags, <startup> element
- <startup> element
- startup element
ms.assetid: 536acfd8-f827-452f-838a-e14fa3b87621
ms.openlocfilehash: e936c069275bfa9f7ac81ef1c6fc6228828182a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153721"
---
# <a name="startup-element"></a>\<启动>元素

指定通用语言运行时启动信息。

[**\<配置>**](../configuration-element.md)  
&nbsp;&nbsp;**\<启动>**  

## <a name="syntax"></a>语法

```xml
<startup useLegacyV2RuntimeActivationPolicy="true|false" >
</startup>
```

## <a name="attributes-and-elements"></a>特性和元素

 下列各节描述了特性、子元素和父元素。

### <a name="attributes"></a>属性

|Attribute|说明|
|---------------|-----------------|
|`useLegacyV2RuntimeActivationPolicy`|可选特性。<br /><br /> 指定是启用 .NET 框架 2.0 运行时激活策略还是使用 .NET 框架 4 激活策略。|

## <a name="uselegacyv2runtimeactivationpolicy-attribute"></a>使用传统V2运行时激活策略属性

|值|说明|
|-----------|-----------------|
|`true`|为所选运行时启用 .NET Framework 2.0 运行时激活策略，即将旧式运行时激活技术（如[CorBindToRuntimeEx 函数](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)）绑定到从配置文件中选择的运行时，而不是在 CLR 版本 2.0 上将其封顶。 因此，如果从配置文件中选择 CLR 版本 4 或更高版本，则使用早期版本的 .NET Framework 创建的混合模式程序集将加载所选 CLR 版本。 设置此值可防止 CLR 版本 1.1 或 CLR 版本 2.0 加载到同一进程中，从而有效地禁用进程内并排功能。|
|`false`|对 .NET 框架 4 及更高版本使用默认激活策略，即允许旧式运行时激活技术将 CLR 版本 1.1 或 2.0 加载到进程中。 设置此值可防止混合模式程序集加载到 .NET 框架 4 或更高版本，除非这些程序集是使用 .NET 框架 4 或更高版本构建的。 此值为默认值。|

### <a name="child-elements"></a>子元素

|元素|说明|
|-------------|-----------------|
|[\<所需的运行时>](requiredruntime-element.md)|指定应用程序仅支持 1.0 版本的公共语言运行时。 使用运行时版本 1.1 或更高版本构建的应用程序应使用**\<支持的 Runtime>** 元素。|
|[\<支持的运行时>](supportedruntime-element.md)|指定应用程序支持的公共语言运行时版本。|

### <a name="parent-elements"></a>父元素

|元素|说明|
|-------------|-----------------|
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|

## <a name="remarks"></a>备注

 **\<支持的 Runtime>** 元素应由使用运行时版本 1.1 或更高版本构建的所有应用程序使用。 为仅支持运行时版本 1.0 而构建的应用程序必须使用**\<所需的 Runtime>** 元素。

 Microsoft Internet Explorer 中托管的应用程序的启动代码忽略**\<启动>** 元素及其子元素。

## <a name="the-uselegacyv2runtimeactivationpolicy-attribute"></a>使用传统V2运行时激活策略属性

 如果应用程序使用旧版激活路径（如[CorBindToRuntimeEx 函数](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)），并且希望这些路径激活 CLR 的版本 4 而不是早期版本，或者应用程序是使用 .NET 框架 4 构建的，但依赖于使用早期版本的 .NET Framework 构建的混合模式程序集，则此属性非常有用。 在这些情况下，将属性设置为`true`。

> [!NOTE]
> 设置属性以防止`true`CLR 版本 1.1 或 CLR 版本 2.0 加载到同一进程中，从而有效地禁用进程内并行功能（请参阅[COM 内部操作的并行执行](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))）。

## <a name="example"></a>示例

 下面的示例演示如何在配置文件中指定运行时版本。

```xml
<!-- When used with version 1.0 of the .NET Framework runtime -->
<configuration>
   <startup>
      <requiredRuntime version="v1.0.3705" safemode="true"/>
   </startup>
</configuration>
<!-- When used with version 1.1 (or later) of the runtime -->
<configuration>
   <startup>
      <supportedRuntime version="v1.1.4322"/>
      <supportedRuntime version="v1.0.3705"/>
   </startup>
</configuration>
```

## <a name="see-also"></a>另请参阅

- [启动设置架构](index.md)
- [配置文件架构](../index.md)
- [如何：将应用配置为支持 .NET 框架 4 或更高版本](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- [COM 互操作的并行执行](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8t8td04t(v=vs.100))
- [进程内并行执行](../../../deployment/in-process-side-by-side-execution.md)

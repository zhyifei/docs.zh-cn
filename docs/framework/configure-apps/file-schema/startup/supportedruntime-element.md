---
title: <supportedRuntime>配置元素 - .NET
ms.date: 04/02/2019
ms.custom: updateeachrelease
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#supportedRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/supportedRuntime
helpviewer_keywords:
- supportedRuntime element
- <supportedRuntime> element
ms.assetid: 1ae16e23-afbe-4de4-b413-bc457f37b69f
ms.openlocfilehash: e16eb098db4bce115a5f1e043829eb272c952860
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153693"
---
# <a name="supportedruntime-element"></a>\<支持的运行时>元素

指定应用程序支持哪个通用语言运行时版本，以及可选的 .NET Framework 版本。  

[\<配置>](../configuration-element.md)  
&nbsp;&nbsp;[\<启动>](startup-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<支持的运行时>**  

## <a name="syntax"></a>语法

```xml
<supportedRuntime version="runtime version" sku="sku id"/>
```

## <a name="attributes"></a>属性

|Attribute|说明|
|---------------|-----------------|
|**version**|可选特性。<br /><br /> 一个字符串值，它指定此应用程序支持的公共语言运行时 (CLR) 版本。 有关`version`属性的有效值，请参阅["运行时版本"值](#version)部分。 **注：** 通过 .NET 框架 3.5，"*运行时版本*"值采用窗体*主要*。*次要*。*生成*。 从 .NET 框架 4 开始，只需要主要版本号和次要版本号（即"v4.0"而不是"v4.0.30319"）。 建议使用较短字符串。|
|**Sku**|可选特性。<br /><br /> 一个字符串值，该值指定库存单位 (SKU)，库存单位则指定此应用程序支持的 .NET Framework 版本。<br /><br /> 从 .NET Framework 4.0 起，建议使用 `sku` 特性。  若存在该特性，则它指示应用面向的 .NET Framework 版本。<br /><br /> 有关 sku 属性的有效值，请参阅["sku id"值](#sku)部分。|

## <a name="remarks"></a>备注

如果应用程序配置文件中不存在**\<支持的 Runtime>** 元素，则使用用于生成应用程序的运行时版本。

**\<支持的 Runtime>** 元素应由使用运行时版本 1.1 或更高版本构建的所有应用程序使用。 为仅支持运行时版本 1.0 而构建的应用程序必须使用[\<所需的 Runtime>](../startup/requiredruntime-element.md)元素。

> [!NOTE]
> 如果使用[CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md)函数来指定配置文件，则必须对运行时的所有版本使用`<requiredRuntime>`该元素。 当您`<supportedRuntime>`使用[CorBindtoRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md)时，该元素将被忽略。  
  
对于支持从 .NET Framework 1.1 到 3.5 的运行时版本的应用，支持多个运行时版本时，第一个元素应指定优先级最高的版本，最后一个元素应指定优先级最低的版本。 对于支持 .NET Framework 4.0 或更高版本的应用`version`，该属性指示 CLR 版本（这是 .NET Framework 4 和更高版本`sku`所共有的），该属性指示应用所针对的单个 .NET Framework 版本。

如果配置文件中存在`sku`**\<包含该属性的受支持的 Runtime>** 元素，并且已安装的 .NET Framework 版本较低，则指定的受支持版本无法运行，则应用程序将失败，而是显示一条消息，要求安装受支持的版本。 否则，应用程序会尝试在任何已安装的版本上运行，但如果它与该版本不完全兼容，则可能会意外。 （有关 .NET 框架版本之间的兼容性差异，请参阅[.NET 框架中的应用程序兼容性](https://docs.microsoft.com/dotnet/framework/migration-guide/application-compatibility)。因此，我们建议您在应用程序配置文件中包含此元素，以便更轻松地进行错误诊断。 （可视化工作室在创建新项目时自动生成的配置文件已包含该文件。
  
> [!NOTE]
> 如果应用程序使用旧版激活路径（如[CorBindToRuntimeEx 函数](../../../unmanaged-api/hosting/corbindtoruntimeex-function.md)），并且希望这些路径激活 CLR 版本 4 而不是早期版本，或者如果应用程序使用 .NET 框架 4 构建，但依赖于使用早期版本的 .NET Framework 构建的混合模式程序集，则在受支持的运行时列表中指定 .NET Framework 4 是不够的。 此外，在配置文件中的[\<启动>元素](../startup/startup-element.md)中，必须将`useLegacyV2RuntimeActivationPolicy`属性设置为`true`。 但是，将此属性设置为`true`意味着使用 .NET Framework 的早期版本构建的所有组件都使用 .NET Framework 4 而不是它们构建的运行时运行。

我们建议你使用应用程序可在其上运行的所有 .NET Framework 版本来测试这些应用程序。

<a name="version"></a>
## <a name="runtime-version-values"></a>“运行时版本”值
该`runtime`属性指定给定应用程序所需的通用语言运行时 （CLR） 版本。 请注意，所有 .NET 框架 v4.x`v4.0`版本都指定 CLR。 下表列出了`version`属性的*运行时版本*值的有效值。

|.NET Framework 版本|`version` 特性|
|----------------------------|-------------------------|
|1.0|"v1.0.3705"|
|1.1|"v1.1.4322"|
|2.0|"v2.0.50727"|
|3.0|"v2.0.50727"|
|3.5|"v2.0.50727"|
|4.0-4.8|"v4.0"|

## <a name="sku-id-values"></a><a name="sku"></a>"sku id"值

该`sku`属性使用目标框架名字对象 （TFM） 来指示应用的目标和运行所需的 .NET 框架的版本。 下表列出了`sku`属性支持的有效值，从 .NET 框架 4 开始。

|.NET Framework 版本|`sku` 特性|
|----------------------------|---------------------|
|4.0|".NETFramework,Version=v4.0"|
|4.0，客户端配置文件|".NETFramework,Version=v4.0,Profile=Client"|
|4.0，平台更新 1|".NETFramework，版本=v4.0.1"|
|4.0，客户端配置文件，Update 1|".NETFramework，版本=v4.0.1，配置文件=客户端"|
|4.0，平台更新 2|".NETFramework，版本=v4.0.2"|
|4.0，客户端配置文件，Update 2|".NETFramework，版本=v4.0.2，配置文件=客户端"|
|4.0，平台更新 3|".NETFramework，版本=v4.0.3"|
|4.0，客户端配置文件，Update 3|".NETFramework，版本=v4.0.3，配置文件=客户端"|
|4.5|".NETFramework,Version=v4.5"|
|4.5.1|".NETFramework,Version=v4.5"|
|4.5.2|".NETFramework,Version=v4.5"|
|4.6|".NETFramework,Version=v4.5"|
|4.6.1|".NETFramework,Version=v4.5"|
|4.6.2|".NETFramework，版本=v4.6.2"|
|4.7|".NETFramework，版本=v4.7"|
|4.7.1|".NETFramework，版本=v4.7.1"|
|4.7.2|".NETFramework，版本=v4.7.2"|
|4.8|".NETFramework，版本=v4.8"|

## <a name="example"></a>示例

下面的示例演示如何在配置文件中指定支持的运行时版本。 配置文件指示应用以 .NET 框架 4.7 为目标。

```xml
<configuration>
   <startup>
      <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.7" />
   </startup>
</configuration>
```

## <a name="configuration-file"></a>配置文件

此元素可用于应用程序配置文件中。

## <a name="see-also"></a>另请参阅

- [启动设置架构](../startup/index.md)
- [配置文件架构](../index.md)
- [进程内并行执行](../../../deployment/in-process-side-by-side-execution.md)

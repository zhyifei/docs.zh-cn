---
title: '&lt;requiredRuntime&gt;元素'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requiredRuntime
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup/requiredRuntime
helpviewer_keywords:
- requiredRuntime element
- <requiredRuntime> element
- container tags, <requiredRuntime> element
ms.assetid: 9fa1639e-beb8-43be-b7a4-12f7b229c34b
ms.openlocfilehash: 66de3e30ce862cd317e80ea267bf22ce728aca82
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2019
ms.locfileid: "54222124"
---
# <a name="ltrequiredruntimegt-element"></a>&lt;requiredRuntime&gt;元素

指定应用程序仅支持 1.0 版本的公共语言运行时。 此元素已弃用，应不再使用。 [ `supportedRuntime` ](supportedruntime-element.md)元素应改为使用。

\<配置 >\<启动 > \<requiredRuntime >

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
|`version`|可选特性。<br /><br /> 一个字符串值，该值指定此应用程序支持的.NET framework 版本。 字符串值必须与.NET Framework 安装根目录下找到的目录名称匹配。 未分析的字符串值的内容。|
|`safemode`|可选特性。<br /><br /> 指定是否在运行时启动代码搜索注册表，以确定运行时版本。|

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
 仅支持 1.0 版的运行时生成的应用程序必须使用`<requiredRuntime>`元素。 构建使用 1.1 版或更高版本的运行时版本的应用程序必须使用`<supportedRuntime>`元素。

> [!NOTE]
> 如果您使用[CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md)函数以指定配置文件，则必须使用`<requiredRuntime>`所有版本的运行时的元素。 `<supportedRuntime>`使用时，将忽略元素[CorBindToRuntimeByCfg](../../../unmanaged-api/hosting/corbindtoruntimebycfg-function.md)。

 `version`属性字符串必须匹配指定版本的.NET framework 的安装文件夹名称。 此字符串不解释。 如果运行时启动代码没有找到匹配的文件夹，则不会加载运行时;启动代码显示了一条错误消息并退出。

> [!NOTE]
> Microsoft Internet Explorer 中承载的应用程序的启动代码将忽略`<requiredRuntime>`元素。

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

- [启动设置架构](index.md)
- [配置文件架构](../index.md)
- [如何：配置应用以支持.NET Framework 4 或更高版本](../../../migration-guide/how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
---
title: gc并发元素
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcConcurrent
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcConcurrent
helpviewer_keywords:
- container tags, <gcConcurrent> element
- gcConcurrent element
- <gcConcurrent> element
ms.assetid: 503f55ba-26ed-45ac-a2ea-caf994da04cd
ms.openlocfilehash: 249518ae7477d284d50f9010757db83b7752c657
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102900"
---
# <a name="gcconcurrent-element"></a>\<gc并发>元素

指定公共语言运行时是否在单独线程上运行垃圾回收。

[\<配置>](../configuration-element.md)\
&nbsp;&nbsp;[\<运行时>](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<gc 并发>

## <a name="syntax"></a>语法

```xml
<gcConcurrent
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>特性和元素

下列各节描述了特性、子元素和父元素。

### <a name="attributes"></a>特性

|特性|描述|
|---------------|-----------------|
|`enabled`|必需的特性。<br /><br />指定运行时是否并发运行服务器垃圾回收。|

#### <a name="enabled-attribute"></a>启用的属性

|值|描述|
|-----------|-----------------|
|`false`|不同时运行垃圾回收。|
|`true`|并发运行垃圾回收。 这是默认值。|

### <a name="child-elements"></a>子元素

无。

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|
|`runtime`|包含有关程序集绑定和垃圾回收的信息。|

## <a name="remarks"></a>备注

在 .NET 框架 4 之前，工作站垃圾回收支持并发垃圾回收，该回收在后台在单独的线程上执行垃圾回收。 在 .NET 框架 4 中，并发垃圾回收被后台 GC 替换，后台 GC 也在单独的线程的后台执行垃圾回收。 从 .NET 框架 4.5 开始，后台收集在服务器垃圾回收中可用。 **gcConcurrent**元素控制运行时是否执行并发或后台垃圾回收，是否可用，或者它是否在前台执行垃圾回收。

### <a name="to-disable-background-garbage-collection"></a>禁用后台垃圾回收

> [!WARNING]
> 从 .NET 框架 4 开始，并发垃圾回收将被后台垃圾回收替换。 术语*并发*和*背景*在 .NET 框架文档中可互换使用。 要禁用后台垃圾回收，请使用**gcConcurrent**元素，如本文所述。

默认情况下，运行时使用并发或后台垃圾回收，回收针对延迟进行了优化。 如果应用程序涉及大量用户交互，则通过让并发垃圾回收保持启用状态，可最大限度缩短应用程序执行垃圾回收时的暂停时间。 如果将`enabled`**gcConcurrent**元素的属性设置为`false`，运行时将使用非并发垃圾回收，该回收针对吞吐量进行了优化。

以下配置文件禁用后台垃圾回收：

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="false"/>
   </runtime>
</configuration>
```

如果计算机配置文件中有**gcConcurrent设置，** 它将为所有 .NET Framework 应用程序定义默认值。 计算机配置文件设置将重写应用程序配置文件设置。

有关并发和后台垃圾回收的详细信息，请参阅[后台垃圾回收](../../../../standard/garbage-collection/background-gc.md)。

## <a name="example"></a>示例

以下示例支持后台垃圾回收：

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>另请参阅

- [运行时设置架构](index.md)
- [配置文件架构](../index.md)
- [垃圾回收的基础](../../../../standard/garbage-collection/fundamentals.md)

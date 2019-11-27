---
title: <GCCpuGroup> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
ms.openlocfilehash: ae9c96c9d49cf3f6be94da3f77b91423cab12e0b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430479"
---
# <a name="gccpugroup-element"></a>\<GCCpuGroup > 元素

指定垃圾回收是否支持多个 CPU 组。

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<运行时 >** ](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<GCCpuGroup >**

## <a name="syntax"></a>语法

```xml
<GCCpuGroup
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>属性和元素

下列各节描述了特性、子元素和父元素。

### <a name="attributes"></a>Attributes

|属性|说明|
|---------------|-----------------|
|`enabled`|必需的特性。<br /><br /> 指定垃圾回收是否支持多个 CPU 组。|

## <a name="enabled-attribute"></a>enabled 特性

|值|说明|
|-----------|-----------------|
|`false`|垃圾回收不支持多个 CPU 组。 这是默认设置。|
|`true`|如果启用了服务器垃圾回收，则垃圾回收支持多个 CPU 组。|

### <a name="child-elements"></a>子元素

无。

### <a name="parent-elements"></a>父元素

|元素|说明|
|-------------|-----------------|
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|
|`runtime`|包含有关程序集绑定和垃圾回收的信息。|

## <a name="remarks"></a>备注

当计算机具有多个 CPU 组并且启用了服务器垃圾回收功能时（请参阅[\<r >](gcserver-element.md)元素），启用此元素可跨所有 CPU 组扩展垃圾回收，并在创建和平衡堆时考虑所有内核。

> [!NOTE]
> 此元素仅适用于垃圾回收线程。 若要使运行时能够在所有 CPU 组之间分配用户线程，还必须启用[Thread_UseAllCpuGroups >](thread-useallcpugroups-element.md)元素的\<。

## <a name="example"></a>示例

下面的示例演示如何为多个 CPU 组启用垃圾回收。

```xml
<configuration>
   <runtime>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>另请参阅

- [运行时设置架构](index.md)
- [配置文件架构](../index.md)
- [禁用并发垃圾回收](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [工作站和服务器垃圾回收](../../../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection)

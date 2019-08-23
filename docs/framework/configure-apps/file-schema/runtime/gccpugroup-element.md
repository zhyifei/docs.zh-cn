---
title: <GCCpuGroup> 元素
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ee56b23b6d5fca6d0527d509c9b6a6fc6dd82336
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920784"
---
# <a name="gccpugroup-element"></a>\<GCCpuGroup > 元素

指定垃圾回收是否支持多个 CPU 组。

\<配置 > \
\<运行时 > \
\<GCCpuGroup>

## <a name="syntax"></a>语法

```xml
<GCCpuGroup
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>特性和元素

下列各节描述了特性、子元素和父元素。

### <a name="attributes"></a>特性

|特性|描述|
|---------------|-----------------|
|`enabled`|必需的特性。<br /><br /> 指定垃圾回收是否支持多个 CPU 组。|

## <a name="enabled-attribute"></a>enabled 特性

|值|描述|
|-----------|-----------------|
|`false`|垃圾回收不支持多个 CPU 组。 这是默认设置。|
|`true`|如果启用了服务器垃圾回收, 则垃圾回收支持多个 CPU 组。|

### <a name="child-elements"></a>子元素

无。

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|
|`runtime`|包含有关程序集绑定和垃圾回收的信息。|

## <a name="remarks"></a>备注

如果计算机具有多个 CPU 组并且启用了服务器垃圾回收 (请参阅[ \<r >](gcserver-element.md)元素), 则启用此元素会在所有 CPU 组之间扩展垃圾回收, 并在创建和平衡堆。

> [!NOTE]
> 此元素仅适用于垃圾回收线程。 若要使运行时能够在所有 CPU 组之间分配用户线程, 还必须启用[ \<Thread_UseAllCpuGroups >](thread-useallcpugroups-element.md)元素。

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

## <a name="see-also"></a>请参阅

- [运行时设置架构](index.md)
- [配置文件架构](../index.md)
- [禁用并发垃圾回收](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [工作站和服务器垃圾回收](../../../../standard/garbage-collection/fundamentals.md#workstation_and_server_garbage_collection)

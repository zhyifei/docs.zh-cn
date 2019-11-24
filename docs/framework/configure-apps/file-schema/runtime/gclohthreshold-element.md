---
title: GCLOHThreshold element
ms.date: 11/20/2019
helpviewer_keywords:
- GCLOHThreshold element
- <GCLOHThreshold> element
ms.openlocfilehash: d72dc9d27984f60dfb6296217263ce8b176093c6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74451322"
---
# <a name="gclohthreshold-element"></a>GCLOHThreshold element

Specifies the threshold size, in bytes, that causes the garbage collector to put objects on the large object heap (LOH).

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;[\<runtime>](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCLOHThreshold>

## <a name="syntax"></a>语法

```xml
<GCLOHThreshold
   enabled="nnnn"/>
```

## <a name="attributes"></a>特性

|特性|描述|
|---------------|-----------------|
|`enabled`|必需的特性。<br /><br />Specifies the threshold size that causes objects to go on the large object heap.|

### <a name="enabled-attribute"></a>enabled attribute

|“值”|描述|
|-----------|-----------------|
|`nnnn`|The threshold size, in bytes, that causes objects to go on the large object heap.|

## <a name="child-elements"></a>子元素

无。

## <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|
|`runtime`|包含有关程序集绑定和垃圾回收的信息。|

## <a name="remarks"></a>备注

This setting was introduced in .NET Framework 4.8.

## <a name="see-also"></a>请参阅

- [Run-time settings schema](index.md)
- [配置文件架构](../index.md)
- [垃圾回收的基本知识](../../../../standard/garbage-collection/fundamentals.md)
- [NET Core run-time config options for GC](../../../../core/run-time-config/garbage-collector.md)

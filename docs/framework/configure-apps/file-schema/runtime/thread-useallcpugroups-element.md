---
title: <Thread_UseAllCpuGroups> 元素
ms.date: 03/30/2017
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e9ee6bdb7094ea2bc9e283e331c0f6ad9b68e4f9
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663428"
---
# <a name="thread_useallcpugroups-element"></a>\<Thread_UseAllCpuGroups > 元素

指定运行时是否跨所有 CPU 组分发托管的线程。

\<配置 > \
\<运行时 > \
\<Thread_UseAllCpuGroups>

## <a name="syntax"></a>语法

```xml
<Thread_UseAllCpuGroups
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>特性和元素

下列各节描述了特性、子元素和父元素。

### <a name="attributes"></a>特性

|特性|描述|
|---------------|-----------------|
|`enabled`|必需的特性。<br /><br /> 指定运行时是否跨所有 CPU 组分发托管的线程。|

## <a name="enabled-attribute"></a>enabled 特性

|值|描述|
|-----------|-----------------|
|`false`|运行时不会跨多个 CPU 组分发托管线程。 这是默认设置。|
|`true`|如果计算机具有多个 cpu 组并且启用了[ \<GCCpuGroup >](gccpugroup-element.md)元素, 则运行时将跨多个 cpu 组分发托管线程。|

### <a name="child-elements"></a>子元素

无。

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|
|`runtime`|包含有关程序集绑定和垃圾回收的信息。|

## <a name="remarks"></a>备注

如果计算机具有多个 CPU 组, 则启用此元素会使运行时将托管线程分散到所有 CPU 组。 若要使用此功能, 还必须启用[ \<GCCpuGroup >](gccpugroup-element.md)元素, 该元素将垃圾回收扩展到所有 CPU 组, 并在创建和平衡堆时考虑所有核心。 启用 GCCpuGroup [ >元素需要启用r>元素。\<](gccpugroup-element.md) [ \<](gcserver-element.md) 如果未启用这些元素, 则`<Thread_UseAllCpuGroups>`启用元素不起作用。

## <a name="example"></a>示例

下面的示例演示如何启用对多个 CPU 组的支持。

```xml
<configuration>
   <runtime>
      <Thread_UseAllCpuGroups enabled="true"/>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>请参阅

- [运行时设置架构](index.md)
- [配置文件架构](../index.md)
- [\<GCCpuGroup > 元素](gccpugroup-element.md)

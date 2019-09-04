---
title: <TimeSpan_LegacyFormatMode> 元素
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- <TimeSpan_LegacyFormatMode> element
- TimeSpan_LegacyFormatMode element
ms.assetid: 865e7207-d050-4442-b574-57ea29d5e2d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 64bf667c5c9bc20db14f08f18fa6f4f84fa12a24
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252254"
---
# <a name="timespan_legacyformatmode-element"></a>\<TimeSpan_LegacyFormatMode > 元素

确定运行时是否在格式设置操作<xref:System.TimeSpan?displayProperty=nameWithType>中保留值。

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<运行时 >** ](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<TimeSpan_LegacyFormatMode >**  

## <a name="syntax"></a>语法

```xml
<TimeSpan_LegacyFormatMode
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>特性和元素

下列各节描述了特性、子元素和父元素。

### <a name="attributes"></a>特性

|特性|描述|
|---------------|-----------------|
|`enabled`|必需的特性。<br /><br /> 指定运行时是否对<xref:System.TimeSpan?displayProperty=nameWithType>值使用旧格式设置行为。|

## <a name="enabled-attribute"></a>enabled 特性

|值|描述|
|-----------|-----------------|
|`false`|运行时不会还原旧的格式设置行为。|
|`true`|运行时将还原旧的格式设置行为。|

### <a name="child-elements"></a>子元素

无。

### <a name="parent-elements"></a>父元素

|元素|描述|
|-------------|-----------------|
|`configuration`|公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。|
|`runtime`|包含有关运行时初始化选项的信息。|

## <a name="remarks"></a>备注

从 .NET Framework 4 开始， <xref:System.TimeSpan?displayProperty=nameWithType>结构<xref:System.IFormattable>实现接口，并支持带有标准和自定义格式字符串的格式设置操作。 如果分析方法遇到不支持的格式说明符或格式字符串，则将引发<xref:System.FormatException>。

在 .NET Framework 的以前版本中， <xref:System.TimeSpan>结构未实现<xref:System.IFormattable> ，并且不支持格式字符串。 但是，很多开发人员都<xref:System.TimeSpan>认为确实支持一组格式字符串，并在[复合格式设置操作](../../../../standard/base-types/composite-formatting.md)中将它们用于<xref:System.String.Format%2A?displayProperty=nameWithType>方法（如）。 通常，如果某个类型实现<xref:System.IFormattable>并支持格式字符串，则使用不受支持的格式字符串的格式设置<xref:System.FormatException>方法的调用通常会引发。 但是，因为<xref:System.TimeSpan>未实现<xref:System.IFormattable>，所以运行时将忽略格式<xref:System.TimeSpan.ToString?displayProperty=nameWithType>字符串，而改为调用方法。 这意味着，尽管格式字符串对格式设置操作没有影响，但它们的<xref:System.FormatException>存在不会导致。

对于旧式代码传递复合格式设置方法和无效格式字符串的情况，并且无法重新编译该代码，可以使用`<TimeSpan_LegacyFormatMode>`元素来还原旧<xref:System.TimeSpan>行为。 将此元素的`enabled`特性设置为`true`时，复合格式设置方法将<xref:System.TimeSpan.ToString?displayProperty=nameWithType>导致调用而<xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>不是，并且<xref:System.FormatException>不会引发。

## <a name="example"></a>示例

下面的示例实例化<xref:System.TimeSpan>一个对象，并使用不受支持<xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType>的标准格式字符串尝试使用方法对其进行格式设置。

[!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
[!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]

在 .NET Framework 3.5 或更早版本上运行此示例时，将显示以下输出：

```
12:30:45
```

如果在 .NET Framework 4 或更高版本上运行此示例，则这与输出明显不同：

```
Invalid Format
```

但是，如果将下面的配置文件添加到示例的目录中，然后在 .NET Framework 4 或更高版本上运行此示例，则输出将与示例在 .NET Framework 3.5 上运行时所生成的输出相同。

```xml
<?xml version ="1.0"?>
<configuration>
   <runtime>
      <TimeSpan_LegacyFormatMode enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>请参阅

- [运行时设置架构](index.md)
- [配置文件架构](../index.md)

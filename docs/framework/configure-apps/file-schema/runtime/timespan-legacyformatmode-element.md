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
ms.openlocfilehash: c835e1bcef7bbfdc990c8db177eafed4ec6bb30c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73115210"
---
# <a name="timespan_legacyformatmode-element"></a>\<TimeSpan_LegacyFormatMode > 元素

确定运行时是否在格式设置操作中保留 <xref:System.TimeSpan?displayProperty=nameWithType> 值的旧行为。

[ **\<configuration>** ](../configuration-element.md)\
&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) \
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
|`enabled`|必需的特性。<br /><br /> 指定运行时是否对 <xref:System.TimeSpan?displayProperty=nameWithType> 值使用旧格式设置行为。|

## <a name="enabled-attribute"></a>enabled 特性

|“值”|描述|
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

从 .NET Framework 4 开始，<xref:System.TimeSpan?displayProperty=nameWithType> 结构实现了 <xref:System.IFormattable> 接口，并支持带有标准和自定义格式字符串的格式设置操作。 如果分析方法遇到不支持的格式说明符或格式字符串，则会引发 <xref:System.FormatException>。

在以前版本的 .NET Framework 中，<xref:System.TimeSpan> 结构未实现 <xref:System.IFormattable>，并且不支持格式字符串。 但是，许多开发人员都误认为 <xref:System.TimeSpan> 支持一组格式字符串，并在[复合格式设置操作](../../../../standard/base-types/composite-formatting.md)中将其用于 <xref:System.String.Format%2A?displayProperty=nameWithType>等方法。 通常情况下，如果某个类型实现 <xref:System.IFormattable> 并支持格式字符串，则具有不受支持的格式字符串的格式设置方法的调用通常会引发 <xref:System.FormatException>。 但是，因为 <xref:System.TimeSpan> 未实现 <xref:System.IFormattable>，所以运行时将忽略格式字符串，而改为调用 <xref:System.TimeSpan.ToString?displayProperty=nameWithType> 方法。 这意味着，尽管格式字符串对格式设置操作没有影响，但它们的存在不会导致 <xref:System.FormatException>。

对于旧式代码传递复合格式设置方法和无效格式字符串的情况，如果不能重新编译该代码，则可以使用 `<TimeSpan_LegacyFormatMode>` 元素来还原旧 <xref:System.TimeSpan> 行为。 将此元素的 `enabled` 特性设置为 `true`时，复合格式设置方法会导致对 <xref:System.TimeSpan.ToString?displayProperty=nameWithType> 而不是 <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>的调用，并且不会引发 <xref:System.FormatException>。

## <a name="example"></a>示例

下面的示例实例化一个 <xref:System.TimeSpan> 对象，并使用不受支持的标准格式字符串尝试使用 <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> 方法对其进行格式设置。

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

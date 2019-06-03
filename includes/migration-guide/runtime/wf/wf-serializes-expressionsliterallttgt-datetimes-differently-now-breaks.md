---
ms.openlocfilehash: 335647f899c79eff22e313fa40b2e2a73e7cfff0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "66379619"
---
### <a name="wf-serializes-expressionsliteralt-datetimes-differently-now-breaks-custom-xaml-parsers"></a>WF 现在采用不同方式序列化 Expressions.Literal\<T> DateTimes（中断自定义 XAML 分析器）

|   |   |
|---|---|
|详细信息|关联的 <xref:System.Windows.Markup.ValueSerializer> 对象将一个 <xref:System.DateTime?displayProperty=name> 或 <xref:System.DateTimeOffset?displayProperty=name> 对象（其 Second 和 <xref:System.DateTime.Millisecond?displayProperty=name> 组件非零且（针对 <xref:System.DateTime?displayProperty=name> 值）且其 <xref:System.DateTime.Kind> 属性不是 Unspecified）转换为属性元素语法而不是字符串。 此更改允许 <xref:System.DateTime?displayProperty=name> 和 <xref:System.DateTimeOffset?displayProperty=name> 值往返。 假定输入 XAML 是采用特性语法的自定义 XAML 分析器将无法正常运行。|
|建议|此更改允许 <xref:System.DateTime?displayProperty=name> 和 <xref:System.DateTimeOffset?displayProperty=name> 值往返。 假定输入 XAML 是采用特性语法的自定义 XAML 分析器将无法正常运行。|
|范围|边缘|
|版本|4.5|
|类型|运行时|

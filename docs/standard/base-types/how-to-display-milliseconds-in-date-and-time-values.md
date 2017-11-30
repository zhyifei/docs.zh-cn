---
title: "如何：显示日期和时间值中的毫秒"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DateTime.ToString method
- displaying date and time data
- time [.NET Framework], milliseconds
- dates [.NET Framework], milliseconds
- milliseconds [.NET Framework]
ms.assetid: ae1a0610-90b9-4877-8eb6-4e30bc5e00cf
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 260d202eb0a218a6657bc719e36da6f39138e54e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-milliseconds-in-date-and-time-values"></a>如何：显示日期和时间值中的毫秒
默认日期和时间格式设置方法，如<xref:System.DateTime.ToString?displayProperty=nameWithType>，包括小时、 分钟和秒的时间值，但排除它的毫秒部分。 本主题说明如何在格式化日期和时间字符串中包含日期和时间的毫秒部分。  
  
### <a name="to-display-the-millisecond-component-of-a-datetime-value"></a>显示的 DateTime 值的毫秒部分  
  
1.  如果要使用日期的字符串表示形式，请使用静态 <xref:System.DateTime> 或 <xref:System.DateTimeOffset> 方法将其转换为 <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> 或 <xref:System.DateTimeOffset.Parse%28System.String%29?displayProperty=nameWithType> 值。  
  
2.  若要提取的字符串表示形式时间的毫秒组成部分，请调用日期和时间值的<xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType>或<xref:System.DateTimeOffset.ToString%2A>方法，并传入`fff`或`FFF`单独使用或与其他自定义格式的自定义格式模式说明符作为`format`参数。  
  
## <a name="example"></a>示例  
 该示例显示的毫秒数部分<xref:System.DateTime>和<xref:System.DateTimeOffset>到控制台，单独与在较长的日期和时间字符串中提供的值。  
  
 [!code-csharp[Formatting.HowTo.Millisecond#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#1)]
 [!code-vb[Formatting.HowTo.Millisecond#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#1)]  
  
 `fff` 格式模式包含毫秒值中的任何尾随零。 `FFF` 格式模式禁止显示它们。 下面的示例阐释了差异。  
  
 [!code-csharp[Formatting.HowTo.Millisecond#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#2)]
 [!code-vb[Formatting.HowTo.Millisecond#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#2)]  
  
 与定义包含日期和时间的毫秒部分的完整自定义格式说明符有关的一个问题在于，它定义可能与应用程序当前区域性中的时间元素排列不对应的硬编码格式。 更好的选择是要检索的某个日期和时间定义由当前区域性的显示模式<xref:System.Globalization.DateTimeFormatInfo>对象，并修改它以包含毫秒。 该示例也阐释了这种方法。 它检索当前区域性的完整的日期和时间模式从<xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A?displayProperty=nameWithType>属性，然后将自定义模式`.ffff`其秒钟模式后面。 请注意，该示例使用正则表达式在单个方法调用中执行此操作。  
  
 还可以使用自定义格式说明符来显示毫秒之外的秒的小数部分。 例如，`f` 或 `F` 自定义格式说明符显示十分之几秒，`ff` 或 `FF` 自定义格式说明符显示百分之几秒，`ffff` 或 `FFFF` 自定义格式说明符显示万分之几秒。 毫秒的小数部分在返回的字符串中会进行截断而不是舍入。 下面的示例中使用了这些格式说明符。  
  
 [!code-csharp[Formatting.HowTo.Millisecond#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#3)]
 [!code-vb[Formatting.HowTo.Millisecond#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#3)]  
  
> [!NOTE]
>  可以显示秒的非常小的小数单位，如万分之几秒或十万分之几秒。 但是，这些值可能没有意义。 日期和时间值的精度取决于系统时钟的分辨率。 在 Windows NT 3.5 和更高版本，和[!INCLUDE[windowsver](../../../includes/windowsver-md.md)]操作系统上，时钟的分辨率为大约 10-15 毫秒。  
  
## <a name="compiling-the-code"></a>编译代码  
 在命令行上使用 csc.exe 或 vb.exe 代码编译。 若要编译中的代码[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]，将其放入控制台应用程序项目模板。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Globalization.DateTimeFormatInfo>  
 [Custom Date and Time Format Strings](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)

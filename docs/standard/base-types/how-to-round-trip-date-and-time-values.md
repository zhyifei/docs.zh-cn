---
title: "如何：往返日期和时间值"
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
- round-trip date and time values
- dates [.NET Framework], round-trip values
- time zones [.NET Framework], round-trip date and time values
- time [.NET Framework], round-trip values
- formatting strings [.NET Framework], round-trip values
ms.assetid: b609b277-edc6-4c74-b03e-ea73324ecbdb
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 515a29e279cfa8fc100e0612fc19df7abc6a3b36
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-round-trip-date-and-time-values"></a>如何：往返日期和时间值
在许多应用程序中，日期和时间值旨在明确标识单个时间点。 本主题说明如何保存和还原<xref:System.DateTime>值，<xref:System.DateTimeOffset>值，以及使用时间的日期和时间值分区信息，以使已还原的值标识的已保存的值在同一时间。  
  
### <a name="to-round-trip-a-datetime-value"></a>往返 DateTime 值  
  
1.  将转换<xref:System.DateTime>为通过调用其字符串表示形式的值<xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType>方法使用"o"格式说明符。  
  
2.  保存的字符串表示形式<xref:System.DateTime>值到文件，或将其传递跨进程、 应用程序域或计算机边界。  
  
3.  检索表示的字符串<xref:System.DateTime>值。  
  
4.  调用<xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType>方法，并传入<xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType>的值作为`styles`参数。  
  
 下面的示例演示如何保存/还原<xref:System.DateTime>值。  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#1)]
 [!code-vb[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#1)]  
  
 当往返<xref:System.DateTime>值，此方法成功保留所有本地和通用时间的时间。 例如，如果本地<xref:System.DateTime>值保存在美国的系统上太平洋标准时区的系统会，并在位于美国中部标准时区的系统上还原，则还原的日期和时间会比原始时间晚两个小时，这反映了两个时区之间的时差。 但是，此方法对于未指定时间不一定准确。 所有<xref:System.DateTime>值其<xref:System.DateTime.Kind%2A>属性是<xref:System.DateTimeKind.Unspecified>看做就好像它们是本地时间。 如果这不是这种情况，<xref:System.DateTime>将不会成功标识正确的点的时间。 针对此限制的解决方法是将日期和时间值与其时区紧密耦合，以便进行保存和还原操作。  
  
### <a name="to-round-trip-a-datetimeoffset-value"></a>往返 DateTimeOffset 值  
  
1.  将转换<xref:System.DateTimeOffset>为通过调用其字符串表示形式的值<xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType>方法使用"o"格式说明符。  
  
2.  保存的字符串表示形式<xref:System.DateTimeOffset>值到文件，或将其传递跨进程、 应用程序域或计算机边界。  
  
3.  检索表示的字符串<xref:System.DateTimeOffset>值。  
  
4.  调用<xref:System.DateTimeOffset.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType>方法，并传入<xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType>的值作为`styles`参数。  
  
 下面的示例演示如何保存/还原<xref:System.DateTimeOffset>值。  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#2)]
 [!code-vb[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#2)]  
  
 此方法始终明确地标识<xref:System.DateTimeOffset>作为时间中的单个点的值。 值然后可转换为协调世界时 (UTC) 通过调用<xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=nameWithType>方法，或者它可以转换为特定时区中的时间通过调用<xref:System.DateTimeOffset.ToOffset%2A?displayProperty=nameWithType>或<xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType>方法。 此方法的主要限制是该日期和时间算法，对执行时<xref:System.DateTimeOffset>值，该值表示的时间以特定时区，可能不会产生准确的结果，对应于该时区。 这是因为当<xref:System.DateTimeOffset>实例化值时，它从其时区解除关联。 因此，执行日期和时间计算时，无法再应用该时区的调整规则。 可以通过定义包含日期和时间值以及其随附时区的自定义类型，来解决此问题。  
  
### <a name="to-round-trip-a-date-and-time-value-with-its-time-zone"></a>往返日期和时间值与其时区  
  
1.  定义一个类或具有两个字段的结构。 第一个字段是<xref:System.DateTime>或<xref:System.DateTimeOffset>对象和第二个都<xref:System.TimeZoneInfo>对象。 下面的示例是这种类型的简单版本。  
  
     [!code-csharp[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#3)]
     [!code-vb[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#3)]  
  
2.  将与类标记<xref:System.SerializableAttribute>属性。  
  
3.  序列化对象使用<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>方法。  
  
4.  对象使用还原<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A>方法。  
  
5.  强制转换 （在 C# 中) 或者 （在 Visual Basic 中) 反序列化将对象转换为适当类型的对象。  
  
 下面的示例演示如何保存/还原对象存储日期和时间和时区信息。  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#4)]
 [!code-vb[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#4)]  
  
 此方法应始终明确地反映正确的二者之前和之后保存并还原，提供的组合的日期和时间和时区对象的实现不允许日期值变得与不同步的时间点时区值。  
  
## <a name="compiling-the-code"></a>编译代码  
 这些示例需要：  
  
-   使用 C# 要导入以下命名空间的`using`语句或[!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]`Imports`语句：  
  
    -   <xref:System>（仅限 C#)。  
  
    -   <xref:System.Globalization?displayProperty=nameWithType>。  
  
    -   <xref:System.IO?displayProperty=nameWithType>。  
  
    -   <xref:System.Runtime.Serialization?displayProperty=nameWithType>。  
  
    -   <xref:System.Runtime.Serialization.Formatters.Binary?displayProperty=nameWithType>。  
  
-   对 System.Core.dll 的引用。  
  
-   每个代码示例，除`DateInTimeZone`类，应包括在类或 Visual Basic 模块，包装在方法中，并从调用`Main`方法。  
  
## <a name="see-also"></a>另请参阅  
 [执行格式设置操作](../../../docs/standard/base-types/performing-formatting-operations.md)  
 [在 DateTime、DateTimeOffset、TimeSpan 和 TimeZoneInfo 之间进行选择](../../../docs/standard/datetime/choosing-between-datetime.md)  
 [Standard Date and Time Format Strings](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)

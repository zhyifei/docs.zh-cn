---
title: "dateTimeInvalidLocalFormat MDA | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "dates [.NET Framework], formatting"
  - "invalid date time local format"
  - "invalid local formats"
  - "MDAs (managed debugging assistants), invalid local formats"
  - "managed debugging assistants (MDAs), invalid local formats"
  - "dateTimeInvalidLocalFormat MDA"
  - "date formatting"
  - "time formatting"
  - "UTC formatting"
ms.assetid: c4a942bb-2651-4b65-8718-809f892a0659
caps.latest.revision: 8
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# dateTimeInvalidLocalFormat MDA
当使用只应用于本地 <xref:System.DateTime> 实例的格式格式化被存储为协调通用时间 \(UTC\) 的 <xref:System.DateTime> 实例时，将激活 `dateTimeInvalidLocalFormat` MDA。  未指定的或默认 <xref:System.DateTime> 实例不会激活此 MDA。  
  
## 症状  
 应用程序使用本地格式手动序列化 UTC <xref:System.DateTime> 实例：  
  
```  
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("yyyy-MM-dd'T'HH:mm:ss.fffffffzzz"));  
```  
  
### 原因  
 <xref:System.DateTime.ToString%2A?displayProperty=fullName> 方法的“z”格式包括本地时区偏移量，例如“\+10:00”表示悉尼时间。  因此，仅当 <xref:System.DateTime> 值是本地时间时，它才会产生有意义的结果。  如果该值是 UTC 时间，则 <xref:System.DateTime.ToString%2A?displayProperty=fullName> 包括本地时区偏移量，但是它不显示或调整时区说明符。  
  
### 解决方法  
 UTC <xref:System.DateTime> 实例应该以能够指示它们是 UTC 的方式进行格式化。  UTC 时间的建议格式是使用一个“Z”表示 UTC 时间：  
  
```  
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("yyyy-MM-dd'T'HH:mm:ss.fffffffZ"));  
```  
  
 还有一种利用 <xref:System.DateTime.Kind%2A> 属性序列化 <xref:System.DateTime> 的“o”格式，不管实例是本地时间、UTC 时间还是未指定的时间，它都能正确序列化：  
  
```  
DateTime myDateTime = DateTime.UtcNow;  
Serialize(myDateTime.ToString("o"));  
```  
  
## 对运行时的影响  
 此 MDA 不影响运行时。  
  
## Output  
 不存在作为此 MDA 激活的结果的特殊输出。但是，可以使用调用堆栈确定激活此 MDA 的 <xref:System.DateTime.ToString%2A> 调用的位置。  
  
## 配置  
  
```  
<mdaConfig>  
  <assistants>  
    <dateTimeInvalidLocalFormat />  
  </assistants>  
</mdaConfig>  
```  
  
## 示例  
 请考虑一个按以下方式使用 <xref:System.Xml.XmlConvert> 或 <xref:System.Data.DataSet> 类间接序列化 UTC <xref:System.DateTime> 值的应用程序。  
  
```  
DateTime myDateTime = DateTime.UtcNow;  
String serialized = XMLConvert.ToString(myDateTime);  
```  
  
 <xref:System.Xml.XmlConvert> 和 <xref:System.Data.DataSet> 序列化默认使用本地格式进行序列化。  序列化其他种类的 <xref:System.DateTime> 值（例如 UTC）需要其他选项。  
  
 这个特定的示例将 `XmlDateTimeSerializationMode.RoundtripKind` 传递给 `XmlConvert` 上的 `ToString` 调用。  这样将把数据序列化为 UTC 时间。  
  
 如果使用 <xref:System.Data.DataSet>，则将 <xref:System.Data.DataColumn> 对象上的 <xref:System.Data.DataColumn.DateTimeMode%2A> 属性设置为 <xref:System.Data.DataSetDateTime>。  
  
```  
DateTime myDateTime = DateTime.UtcNow;  
String serialized = XmlConvert.ToString(myDateTime,   
    XmlDateTimeSerializationMode.RoundtripKind);  
```  
  
## 请参阅  
 <xref:System.Globalization.DateTimeFormatInfo>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
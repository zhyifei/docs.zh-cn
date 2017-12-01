---
title: "将字符串转换为 .NET Framework 数据类型"
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
ms.assetid: 65455ef3-9120-412c-819b-d0f59f88ac09
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ce594234e601cd8feb4723bbc383db9e3ed40522
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="converting-strings-to-net-framework-data-types"></a>将字符串转换为 .NET Framework 数据类型
如果你想要将字符串转换为.NET Framework 数据类型，使用**XmlConvert**适合应用程序要求的方法。 有关中可用的所有转换方法的列表**XmlConvert**类，请参阅<xref:System.Xml.XmlConvert>。  
  
 返回的字符串**ToString**方法是在传递的数据的字符串版本。 此外，有几种转换使用的.NET Framework 类型**XmlConvert**类但它们不使用中的方法**System.Convert**类。 **XmlConvert**类遵循 XML 架构 (XSD) 数据类型规范和数据类型， **XmlConvert**可以将映射到。  
  
 下表列出了 .NET Framework 数据类型和使用 XML 架构 (XSD) 数据类型映射返回的字符串类型。 无法使用处理这些.NET Framework 类型**System.Convert**。  
  
|.NET Framework 类型|返回的字符串|  
|-------------------------|---------------------|  
|Boolean|“true”、“false”|  
|Single.PositiveInfinity|“INF”|  
|Single.NegativeInfinity|“-INF”|  
|Double.PositiveInfinity|“INF”|  
|Double.NegativeInfinity|“-INF”|  
|DateTime|格式为“yyyy-MM-ddTHH:mm:sszzzzzz”及其子集。|  
|Timespan|格式是 PnYnMnTnHnMnS，例如 `P2Y10M15DT10H30M20S` 表示长 2 年 10 个月 15 天 10 小时 30 分钟 20 秒的持续时间。|  
  
> [!NOTE]
>  如果将任何.NET Framework 类型转换为字符串表中列出**ToString**方法，则返回的字符串不是基类型，但 XML 架构 (XSD) 字符串类型。  
  
 **DateTime**和**Timespan**值类型不同之处在于**DateTime**时间，表示某个时刻，而**TimeSpan**表示一个时间间隔。 **DateTime**和**Timespan**格式指定 XML 架构 (XSD) 数据类型规范中。 例如:   
  
```vb  
Dim writer As New XmlTextWriter("myfile.xml", Nothing)  
Dim [date] As New DateTime(2001, 8, 4)  
writer.WriteElementString("Date", XmlConvert.ToString([date]))  
```  
  
```csharp  
XmlTextWriter writer = new XmlTextWriter("myfile.xml", null);  
DateTime date = new DateTime (2001, 08, 04);  
writer.WriteElementString("Date", XmlConvert.ToString(date));  
```  
  
 **输出**  
  
 `<Date>2001-08-04T00:00:00</Date>`。  
  
 下面的代码将整数转换为字符串：  
  
```vb  
Dim writer As New XmlTextWriter("myfile.xml", Nothing)  
Dim value As Int32 = 200  
writer.WriteElementString("Number", XmlConvert.ToString(value))  
```  
  
```csharp  
XmlTextWriter writer = new XmlTextWriter("myfile.xml", null);  
Int32 value = 200;  
writer.WriteElementString("Number", XmlConvert.ToString(value));  
```  
  
 **输出**  
  
 `<Number>200</Number>`  
  
 但是，如果要转换的字符串**布尔**，**单个**，或**Double**，返回的.NET Framework 类型不是返回时使用的类型相同**System.Convert**类。  
  
## <a name="string-to-boolean"></a>将字符串转换为 Boolean  
 下表显示哪些时生成的类型为给定的输入字符串，将字符串转换**布尔**使用**都**方法。  
  
|有效的字符串输入参数|.NET Framework 输出类型|  
|----------------------------------|--------------------------------|  
|“true”|Boolean.True|  
|"1"|Boolean.True|  
|“false”|Boolean.False|  
|“0”|Boolean.False|  
  
 例如，给定以下 XML：  
  
 **输入**  
  
```xml  
<Boolean>true</Boolean>  
<Boolean>1</Boolean>   
```  
  
 同时可以通过以下代码，理解和**bvalue**是**System.Boolean.True**:  
  
```vb  
Dim bvalue As Boolean = _  
   XmlConvert.ToBoolean(reader.ReadElementString())  
Console.WriteLine(bvalue)  
```  
  
```csharp  
Boolean bvalue = XmlConvert.ToBoolean(reader.ReadElementString());  
Console.WriteLine(bvalue);  
```  
  
## <a name="string-to-single"></a>将字符串转换为 Single  
 下表显示哪些时生成的类型为给定的输入字符串，将字符串转换**单个**使用**ToSingle**方法。  
  
|有效的字符串输入参数|.NET Framework 输出类型|  
|----------------------------------|--------------------------------|  
|“INF”|Single.PositiveInfinity|  
|“-INF”|Single.NegativeInfinity|  
  
## <a name="string-to-double"></a>将字符串转换为 Double  
 下表显示哪些时生成的类型为给定的输入字符串，将字符串转换**单个**使用**ToDouble**方法。  
  
|有效的字符串输入参数|.NET Framework 输出类型|  
|----------------------------------|--------------------------------|  
|“INF”|Double.PositiveInfinity|  
|“-INF”|Double.NegativeInfinity|  
  
 下面的代码写出 `<Infinity>INF</Infinity>`：  
  
```vb  
Dim value As Double = Double.PositiveInfinity  
writer.WriteElementString("Infinity", XmlConvert.ToString(value))  
```  
  
```csharp  
Double value = Double.PositiveInfinity;  
writer.WriteElementString("Infinity", XmlConvert.ToString(value));  
```  
  
## <a name="see-also"></a>另请参阅  
 [XML 数据类型的转换](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)  
 [将.NET Framework 类型转换为字符串](../../../../docs/standard/data/xml/converting-dotnet-types-to-strings.md)

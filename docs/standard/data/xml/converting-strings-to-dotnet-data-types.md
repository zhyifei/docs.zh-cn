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
# <a name="converting-strings-to-net-framework-data-types"></a><span data-ttu-id="bab0c-102">将字符串转换为 .NET Framework 数据类型</span><span class="sxs-lookup"><span data-stu-id="bab0c-102">Converting Strings to .NET Framework Data Types</span></span>
<span data-ttu-id="bab0c-103">如果你想要将字符串转换为.NET Framework 数据类型，使用**XmlConvert**适合应用程序要求的方法。</span><span class="sxs-lookup"><span data-stu-id="bab0c-103">If you want to convert a string to a .NET Framework data type, use the **XmlConvert** method that fits the application requirements.</span></span> <span data-ttu-id="bab0c-104">有关中可用的所有转换方法的列表**XmlConvert**类，请参阅<xref:System.Xml.XmlConvert>。</span><span class="sxs-lookup"><span data-stu-id="bab0c-104">For a list of all conversion methods available in the **XmlConvert** class, see <xref:System.Xml.XmlConvert>.</span></span>  
  
 <span data-ttu-id="bab0c-105">返回的字符串**ToString**方法是在传递的数据的字符串版本。</span><span class="sxs-lookup"><span data-stu-id="bab0c-105">The string returned from the **ToString** method is a string version of the data that is passed in.</span></span> <span data-ttu-id="bab0c-106">此外，有几种转换使用的.NET Framework 类型**XmlConvert**类但它们不使用中的方法**System.Convert**类。</span><span class="sxs-lookup"><span data-stu-id="bab0c-106">Additionally, there are several .NET Framework types that convert using the **XmlConvert** class yet they do not use the methods in the **System.Convert** class.</span></span> <span data-ttu-id="bab0c-107">**XmlConvert**类遵循 XML 架构 (XSD) 数据类型规范和数据类型， **XmlConvert**可以将映射到。</span><span class="sxs-lookup"><span data-stu-id="bab0c-107">The **XmlConvert** class follows the XML Schema (XSD) data type specification and has a data type that the **XmlConvert** can map to.</span></span>  
  
 <span data-ttu-id="bab0c-108">下表列出了 .NET Framework 数据类型和使用 XML 架构 (XSD) 数据类型映射返回的字符串类型。</span><span class="sxs-lookup"><span data-stu-id="bab0c-108">The following table lists .NET Framework data types and the string types that are returned using XML Schema (XSD) data type mapping.</span></span> <span data-ttu-id="bab0c-109">无法使用处理这些.NET Framework 类型**System.Convert**。</span><span class="sxs-lookup"><span data-stu-id="bab0c-109">These .NET Framework types cannot be processed using **System.Convert**.</span></span>  
  
|<span data-ttu-id="bab0c-110">.NET Framework 类型</span><span class="sxs-lookup"><span data-stu-id="bab0c-110">.NET Framework type</span></span>|<span data-ttu-id="bab0c-111">返回的字符串</span><span class="sxs-lookup"><span data-stu-id="bab0c-111">String returned</span></span>|  
|-------------------------|---------------------|  
|<span data-ttu-id="bab0c-112">Boolean</span><span class="sxs-lookup"><span data-stu-id="bab0c-112">Boolean</span></span>|<span data-ttu-id="bab0c-113">“true”、“false”</span><span class="sxs-lookup"><span data-stu-id="bab0c-113">"true", "false"</span></span>|  
|<span data-ttu-id="bab0c-114">Single.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="bab0c-114">Single.PositiveInfinity</span></span>|<span data-ttu-id="bab0c-115">“INF”</span><span class="sxs-lookup"><span data-stu-id="bab0c-115">"INF"</span></span>|  
|<span data-ttu-id="bab0c-116">Single.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="bab0c-116">Single.NegativeInfinity</span></span>|<span data-ttu-id="bab0c-117">“-INF”</span><span class="sxs-lookup"><span data-stu-id="bab0c-117">"-INF"</span></span>|  
|<span data-ttu-id="bab0c-118">Double.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="bab0c-118">Double.PositiveInfinity</span></span>|<span data-ttu-id="bab0c-119">“INF”</span><span class="sxs-lookup"><span data-stu-id="bab0c-119">"INF"</span></span>|  
|<span data-ttu-id="bab0c-120">Double.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="bab0c-120">Double.NegativeInfinity</span></span>|<span data-ttu-id="bab0c-121">“-INF”</span><span class="sxs-lookup"><span data-stu-id="bab0c-121">"-INF"</span></span>|  
|<span data-ttu-id="bab0c-122">DateTime</span><span class="sxs-lookup"><span data-stu-id="bab0c-122">DateTime</span></span>|<span data-ttu-id="bab0c-123">格式为“yyyy-MM-ddTHH:mm:sszzzzzz”及其子集。</span><span class="sxs-lookup"><span data-stu-id="bab0c-123">Format is "yyyy-MM-ddTHH:mm:sszzzzzz" and its subsets.</span></span>|  
|<span data-ttu-id="bab0c-124">Timespan</span><span class="sxs-lookup"><span data-stu-id="bab0c-124">Timespan</span></span>|<span data-ttu-id="bab0c-125">格式是 PnYnMnTnHnMnS，例如 `P2Y10M15DT10H30M20S` 表示长 2 年 10 个月 15 天 10 小时 30 分钟 20 秒的持续时间。</span><span class="sxs-lookup"><span data-stu-id="bab0c-125">Format is PnYnMnTnHnMnS that is, `P2Y10M15DT10H30M20S` is a duration of 2 years, 10 months, 15 days, 10 hours, 30 minutes, and 20 seconds.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="bab0c-126">如果将任何.NET Framework 类型转换为字符串表中列出**ToString**方法，则返回的字符串不是基类型，但 XML 架构 (XSD) 字符串类型。</span><span class="sxs-lookup"><span data-stu-id="bab0c-126">If converting any of the .NET Framework types listed in the table to a string using the **ToString** method, the returned string is not the base type, but the XML Schema (XSD) string type.</span></span>  
  
 <span data-ttu-id="bab0c-127">**DateTime**和**Timespan**值类型不同之处在于**DateTime**时间，表示某个时刻，而**TimeSpan**表示一个时间间隔。</span><span class="sxs-lookup"><span data-stu-id="bab0c-127">The **DateTime** and **Timespan** value type differs in that a **DateTime** represents an instant in time, whereas a **TimeSpan** represents a time interval.</span></span> <span data-ttu-id="bab0c-128">**DateTime**和**Timespan**格式指定 XML 架构 (XSD) 数据类型规范中。</span><span class="sxs-lookup"><span data-stu-id="bab0c-128">The **DateTime** and **Timespan** formats are specified in the XML Schema (XSD) data types specification.</span></span> <span data-ttu-id="bab0c-129">例如: </span><span class="sxs-lookup"><span data-stu-id="bab0c-129">For example:</span></span>  
  
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
  
 <span data-ttu-id="bab0c-130">**输出**</span><span class="sxs-lookup"><span data-stu-id="bab0c-130">**Output**</span></span>  
  
 <span data-ttu-id="bab0c-131">`<Date>2001-08-04T00:00:00</Date>`。</span><span class="sxs-lookup"><span data-stu-id="bab0c-131">`<Date>2001-08-04T00:00:00</Date>`.</span></span>  
  
 <span data-ttu-id="bab0c-132">下面的代码将整数转换为字符串：</span><span class="sxs-lookup"><span data-stu-id="bab0c-132">The following code converts an integer to a string:</span></span>  
  
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
  
 <span data-ttu-id="bab0c-133">**输出**</span><span class="sxs-lookup"><span data-stu-id="bab0c-133">**Output**</span></span>  
  
 `<Number>200</Number>`  
  
 <span data-ttu-id="bab0c-134">但是，如果要转换的字符串**布尔**，**单个**，或**Double**，返回的.NET Framework 类型不是返回时使用的类型相同**System.Convert**类。</span><span class="sxs-lookup"><span data-stu-id="bab0c-134">However, if you are converting a string to **Boolean**, **Single**, or **Double**, the .NET Framework type that is returned is not the same as the type returned when using the **System.Convert** class.</span></span>  
  
## <a name="string-to-boolean"></a><span data-ttu-id="bab0c-135">将字符串转换为 Boolean</span><span class="sxs-lookup"><span data-stu-id="bab0c-135">String to Boolean</span></span>  
 <span data-ttu-id="bab0c-136">下表显示哪些时生成的类型为给定的输入字符串，将字符串转换**布尔**使用**都**方法。</span><span class="sxs-lookup"><span data-stu-id="bab0c-136">The following table shows what type is generated for the given input strings, when converting a string to **Boolean** using the **ToBoolean** method.</span></span>  
  
|<span data-ttu-id="bab0c-137">有效的字符串输入参数</span><span class="sxs-lookup"><span data-stu-id="bab0c-137">Valid string input parameter</span></span>|<span data-ttu-id="bab0c-138">.NET Framework 输出类型</span><span class="sxs-lookup"><span data-stu-id="bab0c-138">.NET Framework output type</span></span>|  
|----------------------------------|--------------------------------|  
|<span data-ttu-id="bab0c-139">“true”</span><span class="sxs-lookup"><span data-stu-id="bab0c-139">"true"</span></span>|<span data-ttu-id="bab0c-140">Boolean.True</span><span class="sxs-lookup"><span data-stu-id="bab0c-140">Boolean.True</span></span>|  
|<span data-ttu-id="bab0c-141">"1"</span><span class="sxs-lookup"><span data-stu-id="bab0c-141">"1"</span></span>|<span data-ttu-id="bab0c-142">Boolean.True</span><span class="sxs-lookup"><span data-stu-id="bab0c-142">Boolean.True</span></span>|  
|<span data-ttu-id="bab0c-143">“false”</span><span class="sxs-lookup"><span data-stu-id="bab0c-143">"false"</span></span>|<span data-ttu-id="bab0c-144">Boolean.False</span><span class="sxs-lookup"><span data-stu-id="bab0c-144">Boolean.False</span></span>|  
|<span data-ttu-id="bab0c-145">“0”</span><span class="sxs-lookup"><span data-stu-id="bab0c-145">"0"</span></span>|<span data-ttu-id="bab0c-146">Boolean.False</span><span class="sxs-lookup"><span data-stu-id="bab0c-146">Boolean.False</span></span>|  
  
 <span data-ttu-id="bab0c-147">例如，给定以下 XML：</span><span class="sxs-lookup"><span data-stu-id="bab0c-147">For example, given the following XML:</span></span>  
  
 <span data-ttu-id="bab0c-148">**输入**</span><span class="sxs-lookup"><span data-stu-id="bab0c-148">**Input**</span></span>  
  
```xml  
<Boolean>true</Boolean>  
<Boolean>1</Boolean>   
```  
  
 <span data-ttu-id="bab0c-149">同时可以通过以下代码，理解和**bvalue**是**System.Boolean.True**:</span><span class="sxs-lookup"><span data-stu-id="bab0c-149">Both can be understood by the following code, and **bvalue** is **System.Boolean.True**:</span></span>  
  
```vb  
Dim bvalue As Boolean = _  
   XmlConvert.ToBoolean(reader.ReadElementString())  
Console.WriteLine(bvalue)  
```  
  
```csharp  
Boolean bvalue = XmlConvert.ToBoolean(reader.ReadElementString());  
Console.WriteLine(bvalue);  
```  
  
## <a name="string-to-single"></a><span data-ttu-id="bab0c-150">将字符串转换为 Single</span><span class="sxs-lookup"><span data-stu-id="bab0c-150">String to Single</span></span>  
 <span data-ttu-id="bab0c-151">下表显示哪些时生成的类型为给定的输入字符串，将字符串转换**单个**使用**ToSingle**方法。</span><span class="sxs-lookup"><span data-stu-id="bab0c-151">The following table shows what type is generated for the given input strings, when converting a string to a **Single** using the **ToSingle** method.</span></span>  
  
|<span data-ttu-id="bab0c-152">有效的字符串输入参数</span><span class="sxs-lookup"><span data-stu-id="bab0c-152">Valid string input parameter</span></span>|<span data-ttu-id="bab0c-153">.NET Framework 输出类型</span><span class="sxs-lookup"><span data-stu-id="bab0c-153">.NET Framework output type</span></span>|  
|----------------------------------|--------------------------------|  
|<span data-ttu-id="bab0c-154">“INF”</span><span class="sxs-lookup"><span data-stu-id="bab0c-154">"INF"</span></span>|<span data-ttu-id="bab0c-155">Single.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="bab0c-155">Single.PositiveInfinity</span></span>|  
|<span data-ttu-id="bab0c-156">“-INF”</span><span class="sxs-lookup"><span data-stu-id="bab0c-156">"-INF"</span></span>|<span data-ttu-id="bab0c-157">Single.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="bab0c-157">Single.NegativeInfinity</span></span>|  
  
## <a name="string-to-double"></a><span data-ttu-id="bab0c-158">将字符串转换为 Double</span><span class="sxs-lookup"><span data-stu-id="bab0c-158">String to Double</span></span>  
 <span data-ttu-id="bab0c-159">下表显示哪些时生成的类型为给定的输入字符串，将字符串转换**单个**使用**ToDouble**方法。</span><span class="sxs-lookup"><span data-stu-id="bab0c-159">The following table shows what type is generated for the given input strings, when converting a string to a **Single** using the **ToDouble** method.</span></span>  
  
|<span data-ttu-id="bab0c-160">有效的字符串输入参数</span><span class="sxs-lookup"><span data-stu-id="bab0c-160">Valid string input parameter</span></span>|<span data-ttu-id="bab0c-161">.NET Framework 输出类型</span><span class="sxs-lookup"><span data-stu-id="bab0c-161">.NET Framework output type</span></span>|  
|----------------------------------|--------------------------------|  
|<span data-ttu-id="bab0c-162">“INF”</span><span class="sxs-lookup"><span data-stu-id="bab0c-162">"INF"</span></span>|<span data-ttu-id="bab0c-163">Double.PositiveInfinity</span><span class="sxs-lookup"><span data-stu-id="bab0c-163">Double.PositiveInfinity</span></span>|  
|<span data-ttu-id="bab0c-164">“-INF”</span><span class="sxs-lookup"><span data-stu-id="bab0c-164">"-INF"</span></span>|<span data-ttu-id="bab0c-165">Double.NegativeInfinity</span><span class="sxs-lookup"><span data-stu-id="bab0c-165">Double.NegativeInfinity</span></span>|  
  
 <span data-ttu-id="bab0c-166">下面的代码写出 `<Infinity>INF</Infinity>`：</span><span class="sxs-lookup"><span data-stu-id="bab0c-166">The following code writes `<Infinity>INF</Infinity>`:</span></span>  
  
```vb  
Dim value As Double = Double.PositiveInfinity  
writer.WriteElementString("Infinity", XmlConvert.ToString(value))  
```  
  
```csharp  
Double value = Double.PositiveInfinity;  
writer.WriteElementString("Infinity", XmlConvert.ToString(value));  
```  
  
## <a name="see-also"></a><span data-ttu-id="bab0c-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bab0c-167">See Also</span></span>  
 [<span data-ttu-id="bab0c-168">XML 数据类型的转换</span><span class="sxs-lookup"><span data-stu-id="bab0c-168">Conversion of XML Data Types</span></span>](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)  
 [<span data-ttu-id="bab0c-169">将.NET Framework 类型转换为字符串</span><span class="sxs-lookup"><span data-stu-id="bab0c-169">Converting .NET Framework Types to Strings</span></span>](../../../../docs/standard/data/xml/converting-dotnet-types-to-strings.md)

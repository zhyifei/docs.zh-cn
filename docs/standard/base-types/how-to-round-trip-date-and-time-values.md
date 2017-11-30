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
# <a name="how-to-round-trip-date-and-time-values"></a><span data-ttu-id="e21c8-102">如何：往返日期和时间值</span><span class="sxs-lookup"><span data-stu-id="e21c8-102">How to: Round-trip Date and Time Values</span></span>
<span data-ttu-id="e21c8-103">在许多应用程序中，日期和时间值旨在明确标识单个时间点。</span><span class="sxs-lookup"><span data-stu-id="e21c8-103">In many applications, a date and time value is intended to unambiguously identify a single point in time.</span></span> <span data-ttu-id="e21c8-104">本主题说明如何保存和还原<xref:System.DateTime>值，<xref:System.DateTimeOffset>值，以及使用时间的日期和时间值分区信息，以使已还原的值标识的已保存的值在同一时间。</span><span class="sxs-lookup"><span data-stu-id="e21c8-104">This topic shows how to save and restore a <xref:System.DateTime> value, a <xref:System.DateTimeOffset> value, and a date and time value with time zone information so that the restored value identifies the same time as the saved value.</span></span>  
  
### <a name="to-round-trip-a-datetime-value"></a><span data-ttu-id="e21c8-105">往返 DateTime 值</span><span class="sxs-lookup"><span data-stu-id="e21c8-105">To round-trip a DateTime value</span></span>  
  
1.  <span data-ttu-id="e21c8-106">将转换<xref:System.DateTime>为通过调用其字符串表示形式的值<xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType>方法使用"o"格式说明符。</span><span class="sxs-lookup"><span data-stu-id="e21c8-106">Convert the <xref:System.DateTime> value to its string representation by calling the <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> method with the "o" format specifier.</span></span>  
  
2.  <span data-ttu-id="e21c8-107">保存的字符串表示形式<xref:System.DateTime>值到文件，或将其传递跨进程、 应用程序域或计算机边界。</span><span class="sxs-lookup"><span data-stu-id="e21c8-107">Save the string representation of the <xref:System.DateTime> value to a file, or pass it across a process, application domain, or machine boundary.</span></span>  
  
3.  <span data-ttu-id="e21c8-108">检索表示的字符串<xref:System.DateTime>值。</span><span class="sxs-lookup"><span data-stu-id="e21c8-108">Retrieve the string that represents the <xref:System.DateTime> value.</span></span>  
  
4.  <span data-ttu-id="e21c8-109">调用<xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType>方法，并传入<xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType>的值作为`styles`参数。</span><span class="sxs-lookup"><span data-stu-id="e21c8-109">Call the <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> method, and pass <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> as the value of the `styles` parameter.</span></span>  
  
 <span data-ttu-id="e21c8-110">下面的示例演示如何保存/还原<xref:System.DateTime>值。</span><span class="sxs-lookup"><span data-stu-id="e21c8-110">The following example illustrates how to round-trip a <xref:System.DateTime> value.</span></span>  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#1)]
 [!code-vb[Formatting.HowTo.RoundTrip#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#1)]  
  
 <span data-ttu-id="e21c8-111">当往返<xref:System.DateTime>值，此方法成功保留所有本地和通用时间的时间。</span><span class="sxs-lookup"><span data-stu-id="e21c8-111">When round-tripping a <xref:System.DateTime> value, this technique successfully preserves the time for all local and universal times.</span></span> <span data-ttu-id="e21c8-112">例如，如果本地<xref:System.DateTime>值保存在美国的系统上太平洋标准时区的系统会，并在位于美国中部标准时区的系统上还原，则还原的日期和时间会比原始时间晚两个小时，这反映了两个时区之间的时差。</span><span class="sxs-lookup"><span data-stu-id="e21c8-112">For example, if a local <xref:System.DateTime> value is saved on a system in the U.S. Pacific Standard Time zone and is restored on a system in the U.S. Central Standard Time zone, the restored date and time will be two hours later than the original time, which reflects the time difference between the two time zones.</span></span> <span data-ttu-id="e21c8-113">但是，此方法对于未指定时间不一定准确。</span><span class="sxs-lookup"><span data-stu-id="e21c8-113">However, this technique is not necessarily accurate for unspecified times.</span></span> <span data-ttu-id="e21c8-114">所有<xref:System.DateTime>值其<xref:System.DateTime.Kind%2A>属性是<xref:System.DateTimeKind.Unspecified>看做就好像它们是本地时间。</span><span class="sxs-lookup"><span data-stu-id="e21c8-114">All <xref:System.DateTime> values whose <xref:System.DateTime.Kind%2A> property is <xref:System.DateTimeKind.Unspecified> are treated as if they are local times.</span></span> <span data-ttu-id="e21c8-115">如果这不是这种情况，<xref:System.DateTime>将不会成功标识正确的点的时间。</span><span class="sxs-lookup"><span data-stu-id="e21c8-115">If this is not the case, the <xref:System.DateTime> will not successfully identify the correct point in time.</span></span> <span data-ttu-id="e21c8-116">针对此限制的解决方法是将日期和时间值与其时区紧密耦合，以便进行保存和还原操作。</span><span class="sxs-lookup"><span data-stu-id="e21c8-116">The workaround for this limitation is to tightly couple a date and time value with its time zone for the save and restore operation.</span></span>  
  
### <a name="to-round-trip-a-datetimeoffset-value"></a><span data-ttu-id="e21c8-117">往返 DateTimeOffset 值</span><span class="sxs-lookup"><span data-stu-id="e21c8-117">To round-trip a DateTimeOffset value</span></span>  
  
1.  <span data-ttu-id="e21c8-118">将转换<xref:System.DateTimeOffset>为通过调用其字符串表示形式的值<xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType>方法使用"o"格式说明符。</span><span class="sxs-lookup"><span data-stu-id="e21c8-118">Convert the <xref:System.DateTimeOffset> value to its string representation by calling the <xref:System.DateTimeOffset.ToString%28System.String%29?displayProperty=nameWithType> method with the "o" format specifier.</span></span>  
  
2.  <span data-ttu-id="e21c8-119">保存的字符串表示形式<xref:System.DateTimeOffset>值到文件，或将其传递跨进程、 应用程序域或计算机边界。</span><span class="sxs-lookup"><span data-stu-id="e21c8-119">Save the string representation of the <xref:System.DateTimeOffset> value to a file, or pass it across a process, application domain, or machine boundary.</span></span>  
  
3.  <span data-ttu-id="e21c8-120">检索表示的字符串<xref:System.DateTimeOffset>值。</span><span class="sxs-lookup"><span data-stu-id="e21c8-120">Retrieve the string that represents the <xref:System.DateTimeOffset> value.</span></span>  
  
4.  <span data-ttu-id="e21c8-121">调用<xref:System.DateTimeOffset.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType>方法，并传入<xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType>的值作为`styles`参数。</span><span class="sxs-lookup"><span data-stu-id="e21c8-121">Call the <xref:System.DateTimeOffset.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType> method, and pass <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> as the value of the `styles` parameter.</span></span>  
  
 <span data-ttu-id="e21c8-122">下面的示例演示如何保存/还原<xref:System.DateTimeOffset>值。</span><span class="sxs-lookup"><span data-stu-id="e21c8-122">The following example illustrates how to round-trip a <xref:System.DateTimeOffset> value.</span></span>  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#2)]
 [!code-vb[Formatting.HowTo.RoundTrip#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#2)]  
  
 <span data-ttu-id="e21c8-123">此方法始终明确地标识<xref:System.DateTimeOffset>作为时间中的单个点的值。</span><span class="sxs-lookup"><span data-stu-id="e21c8-123">This technique always unambiguously identifies a <xref:System.DateTimeOffset> value as a single point in time.</span></span> <span data-ttu-id="e21c8-124">值然后可转换为协调世界时 (UTC) 通过调用<xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=nameWithType>方法，或者它可以转换为特定时区中的时间通过调用<xref:System.DateTimeOffset.ToOffset%2A?displayProperty=nameWithType>或<xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="e21c8-124">The value can then be converted to Coordinated Universal Time (UTC) by calling the <xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=nameWithType> method, or it can be converted to the time in a particular time zone by calling the <xref:System.DateTimeOffset.ToOffset%2A?displayProperty=nameWithType> or <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="e21c8-125">此方法的主要限制是该日期和时间算法，对执行时<xref:System.DateTimeOffset>值，该值表示的时间以特定时区，可能不会产生准确的结果，对应于该时区。</span><span class="sxs-lookup"><span data-stu-id="e21c8-125">The major limitation of this technique is that date and time arithmetic, when performed on a <xref:System.DateTimeOffset> value that represents the time in a particular time zone, may not produce accurate results for that time zone.</span></span> <span data-ttu-id="e21c8-126">这是因为当<xref:System.DateTimeOffset>实例化值时，它从其时区解除关联。</span><span class="sxs-lookup"><span data-stu-id="e21c8-126">This is because when a <xref:System.DateTimeOffset> value is instantiated, it is disassociated from its time zone.</span></span> <span data-ttu-id="e21c8-127">因此，执行日期和时间计算时，无法再应用该时区的调整规则。</span><span class="sxs-lookup"><span data-stu-id="e21c8-127">Therefore, that time zone's adjustment rules can no longer be applied when you perform date and time calculations.</span></span> <span data-ttu-id="e21c8-128">可以通过定义包含日期和时间值以及其随附时区的自定义类型，来解决此问题。</span><span class="sxs-lookup"><span data-stu-id="e21c8-128">You can work around this problem by defining a custom type that includes both a date and time value and its accompanying time zone.</span></span>  
  
### <a name="to-round-trip-a-date-and-time-value-with-its-time-zone"></a><span data-ttu-id="e21c8-129">往返日期和时间值与其时区</span><span class="sxs-lookup"><span data-stu-id="e21c8-129">To round-trip a date and time value with its time zone</span></span>  
  
1.  <span data-ttu-id="e21c8-130">定义一个类或具有两个字段的结构。</span><span class="sxs-lookup"><span data-stu-id="e21c8-130">Define a class or a structure with two fields.</span></span> <span data-ttu-id="e21c8-131">第一个字段是<xref:System.DateTime>或<xref:System.DateTimeOffset>对象和第二个都<xref:System.TimeZoneInfo>对象。</span><span class="sxs-lookup"><span data-stu-id="e21c8-131">The first field is either a <xref:System.DateTime> or a <xref:System.DateTimeOffset> object, and the second is a <xref:System.TimeZoneInfo> object.</span></span> <span data-ttu-id="e21c8-132">下面的示例是这种类型的简单版本。</span><span class="sxs-lookup"><span data-stu-id="e21c8-132">The following example is a simple version of such a type.</span></span>  
  
     [!code-csharp[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#3)]
     [!code-vb[Formatting.HowTo.RoundTrip#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#3)]  
  
2.  <span data-ttu-id="e21c8-133">将与类标记<xref:System.SerializableAttribute>属性。</span><span class="sxs-lookup"><span data-stu-id="e21c8-133">Mark the class with the <xref:System.SerializableAttribute> attribute.</span></span>  
  
3.  <span data-ttu-id="e21c8-134">序列化对象使用<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="e21c8-134">Serialize the object using the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType> method.</span></span>  
  
4.  <span data-ttu-id="e21c8-135">对象使用还原<xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="e21c8-135">Restore the object using the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A> method.</span></span>  
  
5.  <span data-ttu-id="e21c8-136">强制转换 （在 C# 中) 或者 （在 Visual Basic 中) 反序列化将对象转换为适当类型的对象。</span><span class="sxs-lookup"><span data-stu-id="e21c8-136">Cast (in C#) or convert (in Visual Basic) the deserialized object to an object of the appropriate type.</span></span>  
  
 <span data-ttu-id="e21c8-137">下面的示例演示如何保存/还原对象存储日期和时间和时区信息。</span><span class="sxs-lookup"><span data-stu-id="e21c8-137">The following example illustrates how to round-trip an object that stores both date and time and time zone information.</span></span>  
  
 [!code-csharp[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/cs/RoundTrip.cs#4)]
 [!code-vb[Formatting.HowTo.RoundTrip#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.RoundTrip/vb/RoundTrip.vb#4)]  
  
 <span data-ttu-id="e21c8-138">此方法应始终明确地反映正确的二者之前和之后保存并还原，提供的组合的日期和时间和时区对象的实现不允许日期值变得与不同步的时间点时区值。</span><span class="sxs-lookup"><span data-stu-id="e21c8-138">This technique should always unambiguously reflect the correct point of time both before and after it is saved and restored, provided that the implementation of the combined date and time and time zone object does not allow the date value to become out of sync with the time zone value.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e21c8-139">编译代码</span><span class="sxs-lookup"><span data-stu-id="e21c8-139">Compiling the Code</span></span>  
 <span data-ttu-id="e21c8-140">这些示例需要：</span><span class="sxs-lookup"><span data-stu-id="e21c8-140">These examples require:</span></span>  
  
-   <span data-ttu-id="e21c8-141">使用 C# 要导入以下命名空间的`using`语句或[!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]`Imports`语句：</span><span class="sxs-lookup"><span data-stu-id="e21c8-141">That the following namespaces be imported with C# `using` statements or [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] `Imports` statements:</span></span>  
  
    -   <span data-ttu-id="e21c8-142"><xref:System>（仅限 C#)。</span><span class="sxs-lookup"><span data-stu-id="e21c8-142"><xref:System> (C# only).</span></span>  
  
    -   <span data-ttu-id="e21c8-143"><xref:System.Globalization?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="e21c8-143"><xref:System.Globalization?displayProperty=nameWithType>.</span></span>  
  
    -   <span data-ttu-id="e21c8-144"><xref:System.IO?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="e21c8-144"><xref:System.IO?displayProperty=nameWithType>.</span></span>  
  
    -   <span data-ttu-id="e21c8-145"><xref:System.Runtime.Serialization?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="e21c8-145"><xref:System.Runtime.Serialization?displayProperty=nameWithType>.</span></span>  
  
    -   <span data-ttu-id="e21c8-146"><xref:System.Runtime.Serialization.Formatters.Binary?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="e21c8-146"><xref:System.Runtime.Serialization.Formatters.Binary?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="e21c8-147">对 System.Core.dll 的引用。</span><span class="sxs-lookup"><span data-stu-id="e21c8-147">A reference to System.Core.dll.</span></span>  
  
-   <span data-ttu-id="e21c8-148">每个代码示例，除`DateInTimeZone`类，应包括在类或 Visual Basic 模块，包装在方法中，并从调用`Main`方法。</span><span class="sxs-lookup"><span data-stu-id="e21c8-148">Each code example, other than the `DateInTimeZone` class, should be included in a class or Visual Basic module, wrapped in methods, and called from the `Main` method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e21c8-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e21c8-149">See Also</span></span>  
 [<span data-ttu-id="e21c8-150">执行格式设置操作</span><span class="sxs-lookup"><span data-stu-id="e21c8-150">Performing Formatting Operations</span></span>](../../../docs/standard/base-types/performing-formatting-operations.md)  
 [<span data-ttu-id="e21c8-151">在 DateTime、DateTimeOffset、TimeSpan 和 TimeZoneInfo 之间进行选择</span><span class="sxs-lookup"><span data-stu-id="e21c8-151">Choosing Between DateTime, DateTimeOffset, TimeSpan, and TimeZoneInfo</span></span>](../../../docs/standard/datetime/choosing-between-datetime.md)  
 [<span data-ttu-id="e21c8-152">Standard Date and Time Format Strings</span><span class="sxs-lookup"><span data-stu-id="e21c8-152">Standard Date and Time Format Strings</span></span>](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)

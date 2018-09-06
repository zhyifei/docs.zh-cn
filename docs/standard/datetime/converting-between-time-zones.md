---
title: 在各时区之间转换时间
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- times [.NET Framework], converting
- time zones [.NET Framework], conversions
- UTC times, converting
- converting times
- local time conversions
ms.assetid: a51e1a3b-c983-4320-b31a-1f9fa3cf824a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 64b971e71019359cebc1493a410e748a1fd7b7cb
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43734976"
---
# <a name="converting-times-between-time-zones"></a><span data-ttu-id="2e958-102">在各时区之间转换时间</span><span class="sxs-lookup"><span data-stu-id="2e958-102">Converting times between time zones</span></span>

<span data-ttu-id="2e958-103">对任何使用日期和时间的应用程序而言，处理各时区之间的差异变得愈发重要。</span><span class="sxs-lookup"><span data-stu-id="2e958-103">It is becoming increasingly important for any application that works with dates and times to handle differences between time zones.</span></span> <span data-ttu-id="2e958-104">应用程序不再假定所有时间可以都表示的本地时间指的是时间可从<xref:System.DateTime>结构。</span><span class="sxs-lookup"><span data-stu-id="2e958-104">An application can no longer assume that all times can be expressed in the local time, which is the time available from the <xref:System.DateTime> structure.</span></span> <span data-ttu-id="2e958-105">例如，显示美国东部当前时间的网页对东亚客户而言缺乏可信度。</span><span class="sxs-lookup"><span data-stu-id="2e958-105">For example, a Web page that displays the current time in the eastern part of the United States will lack credibility to a customer in eastern Asia.</span></span> <span data-ttu-id="2e958-106">本主题说明如何将时间从一个时区转换到另一个，以及如何将转换<xref:System.DateTimeOffset>具有有限的时区感知功能的值。</span><span class="sxs-lookup"><span data-stu-id="2e958-106">This topic explains how to convert times from one time zone to another, as well as how to convert <xref:System.DateTimeOffset> values that have limited time zone awareness.</span></span>

## <a name="converting-to-coordinated-universal-time"></a><span data-ttu-id="2e958-107">转换为协调世界时</span><span class="sxs-lookup"><span data-stu-id="2e958-107">Converting to Coordinated Universal Time</span></span>

<span data-ttu-id="2e958-108">协调世界时 (UTC) 是一项高精度的原子时标准。</span><span class="sxs-lookup"><span data-stu-id="2e958-108">Coordinated Universal Time (UTC) is a high-precision, atomic time standard.</span></span> <span data-ttu-id="2e958-109">世界的时区表示为相对于 UTC 的正/负偏移量。</span><span class="sxs-lookup"><span data-stu-id="2e958-109">The world’s time zones are expressed as positive or negative offsets from UTC.</span></span> <span data-ttu-id="2e958-110">因此，UTC 提供一种无时区或中间时区的时间。</span><span class="sxs-lookup"><span data-stu-id="2e958-110">Thus, UTC provides a kind of time-zone free or time-zone neutral time.</span></span> <span data-ttu-id="2e958-111">如果日期和时间在计算机之间的可移植性非常重要，则建议使用 UTC 时间。</span><span class="sxs-lookup"><span data-stu-id="2e958-111">The use of UTC time is recommended when a date and time's portability across computers is important.</span></span> <span data-ttu-id="2e958-112">(有关详细信息和使用日期和时间的其他最佳做法，请参阅[编码在.NET Framework 中使用 DateTime 的最佳实践](https://msdn.microsoft.com/library/ms973825.aspx)。)通过将各个时区转换为 UTC，可以简化时间的比较。</span><span class="sxs-lookup"><span data-stu-id="2e958-112">(For details and other best practices using dates and times, see [Coding best practices using DateTime in the .NET Framework](https://msdn.microsoft.com/library/ms973825.aspx).) Converting individual time zones to UTC makes time comparisons easy.</span></span>

> [!NOTE]
> <span data-ttu-id="2e958-113">此外可以序列化<xref:System.DateTimeOffset>结构，明确时间表示的单一点。</span><span class="sxs-lookup"><span data-stu-id="2e958-113">You can also serialize a <xref:System.DateTimeOffset> structure to unambiguously represent a single point in time.</span></span> <span data-ttu-id="2e958-114">因为<xref:System.DateTimeOffset>对象存储以及其相对于 UTC 的偏移量的日期和时间值，它们始终为 UTC 表示的特定点的关系中的时间。</span><span class="sxs-lookup"><span data-stu-id="2e958-114">Because <xref:System.DateTimeOffset> objects store a date and time value along with its offset from UTC, they always represent a particular point in time in relationship to UTC.</span></span>

<span data-ttu-id="2e958-115">将时间转换为 UTC 的最简单方法是调用`static`(`Shared`在 Visual Basic 中)<xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="2e958-115">The easiest way to convert a time to UTC is to call the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="2e958-116">该方法所执行的具体转换取决于的值`dateTime`参数的<xref:System.DateTime.Kind%2A>属性，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="2e958-116">The exact conversion performed by the method depends on the value of the `dateTime` parameter's <xref:System.DateTime.Kind%2A> property, as the following table shows.</span></span>

| `DateTime.Kind`            | <span data-ttu-id="2e958-117">转换</span><span class="sxs-lookup"><span data-stu-id="2e958-117">Conversion</span></span>                                                                     |
| -------------------------- | ------------------------------------------------------------------------------ |
| `DateTimeKind.Local`       | <span data-ttu-id="2e958-118">将本地时间转换为 UTC。</span><span class="sxs-lookup"><span data-stu-id="2e958-118">Converts local time to UTC.</span></span>                                                    |
| `DateTimeKind.Unspecified` | <span data-ttu-id="2e958-119">假定 `dateTime` 参数为本地时间并将本地时间转换为 UTC。</span><span class="sxs-lookup"><span data-stu-id="2e958-119">Assumes the `dateTime` parameter is local time and converts local time to UTC.</span></span> |
| `DateTimeKind.Utc`         | <span data-ttu-id="2e958-120">返回未更改的 `dateTime` 参数。</span><span class="sxs-lookup"><span data-stu-id="2e958-120">Returns the `dateTime` parameter unchanged.</span></span>                                    |

<span data-ttu-id="2e958-121">以下代码可将当前本地时间转换为 UTC，并将结果显示在控制台上。</span><span class="sxs-lookup"><span data-stu-id="2e958-121">The following code converts the current local time to UTC and displays the result to the console.</span></span>

[!code-csharp[System.TimeZone2.Concepts#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#6)]
[!code-vb[System.TimeZone2.Concepts#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#6)]

> [!NOTE]
> <span data-ttu-id="2e958-122"><xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType>方法不一定会生成相同的结果<xref:System.TimeZone.ToUniversalTime%2A?displayProperty=nameWithType>和<xref:System.DateTime.ToUniversalTime%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="2e958-122">The <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType> method does not necessarily produce results that are identical to the <xref:System.TimeZone.ToUniversalTime%2A?displayProperty=nameWithType> and <xref:System.DateTime.ToUniversalTime%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="2e958-123">如果主机系统的本地时区包含多个调整规则，<xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType>合适的规则适用于特定日期和时间。</span><span class="sxs-lookup"><span data-stu-id="2e958-123">If the host system's local time zone includes multiple adjustment rules, <xref:System.TimeZoneInfo.ConvertTimeToUtc%28System.DateTime%29?displayProperty=nameWithType> applies the appropriate rule to a particular date and time.</span></span> <span data-ttu-id="2e958-124">其他两种方法始终应用最新调整规则。</span><span class="sxs-lookup"><span data-stu-id="2e958-124">The other two methods always apply the latest adjustment rule.</span></span>

<span data-ttu-id="2e958-125">如果日期和时间值不表示本地时间或 UTC，<xref:System.DateTime.ToUniversalTime%2A>方法可能返回错误的结果。</span><span class="sxs-lookup"><span data-stu-id="2e958-125">If the date and time value does not represent either the local time or UTC, the <xref:System.DateTime.ToUniversalTime%2A> method will likely return an erroneous result.</span></span> <span data-ttu-id="2e958-126">但是，可以使用<xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType>方法将从指定的时区转换的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="2e958-126">However, you can use the <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType> method to convert the date and time from a specified time zone.</span></span> <span data-ttu-id="2e958-127">(有关详细信息中检索<xref:System.TimeZoneInfo>对象，表示目标时区，请参阅[查找本地系统上定义的时区](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)。)下面的代码使用<xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType>方法将东部标准时间转换为 UTC。</span><span class="sxs-lookup"><span data-stu-id="2e958-127">(For details on retrieving a <xref:System.TimeZoneInfo> object that represents the destination time zone, see [Finding the time zones defined on a local system](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md).) The following code uses the <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A?displayProperty=nameWithType> method to convert Eastern Standard Time to UTC.</span></span>

[!code-csharp[System.TimeZone2.Concepts#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#7)]
[!code-vb[System.TimeZone2.Concepts#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#7)]

<span data-ttu-id="2e958-128">请注意，此方法将引发<xref:System.ArgumentException>如果<xref:System.DateTime>对象的<xref:System.DateTime.Kind%2A>属性与时区不匹配。</span><span class="sxs-lookup"><span data-stu-id="2e958-128">Note that this method throws an <xref:System.ArgumentException> if the <xref:System.DateTime> object's <xref:System.DateTime.Kind%2A> property and the time zone are mismatched.</span></span> <span data-ttu-id="2e958-129">如果出现不匹配<xref:System.DateTime.Kind%2A>属性是<xref:System.DateTimeKind.Local?displayProperty=nameWithType>但<xref:System.TimeZoneInfo>对象不表示本地时区，或者如果<xref:System.DateTime.Kind%2A>属性是<xref:System.DateTimeKind.Utc?displayProperty=nameWithType>但<xref:System.TimeZoneInfo>对象不等于<xref:System.TimeZoneInfo.Utc?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="2e958-129">A mismatch occurs if the <xref:System.DateTime.Kind%2A> property is <xref:System.DateTimeKind.Local?displayProperty=nameWithType> but the <xref:System.TimeZoneInfo> object does not represent the local time zone, or if the <xref:System.DateTime.Kind%2A> property is <xref:System.DateTimeKind.Utc?displayProperty=nameWithType> but the <xref:System.TimeZoneInfo> object does not equal <xref:System.TimeZoneInfo.Utc?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="2e958-130">所有这些方法采用<xref:System.DateTime>作为参数和返回值<xref:System.DateTime>值。</span><span class="sxs-lookup"><span data-stu-id="2e958-130">All of these methods take <xref:System.DateTime> values as parameters and return a <xref:System.DateTime> value.</span></span> <span data-ttu-id="2e958-131">有关<xref:System.DateTimeOffset>值，<xref:System.DateTimeOffset>结构具有<xref:System.DateTimeOffset.ToUniversalTime%2A>实例转换为 UTC 日期和时间的当前实例的方法。</span><span class="sxs-lookup"><span data-stu-id="2e958-131">For <xref:System.DateTimeOffset> values, the <xref:System.DateTimeOffset> structure has a <xref:System.DateTimeOffset.ToUniversalTime%2A> instance method that converts the date and time of the current instance to UTC.</span></span> <span data-ttu-id="2e958-132">下面的示例调用<xref:System.DateTimeOffset.ToUniversalTime%2A>方法，将本地时间和几个其他时间转换为协调世界时 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="2e958-132">The following example calls the <xref:System.DateTimeOffset.ToUniversalTime%2A> method to convert a local time and several other times to Coordinated Universal Time (UTC).</span></span>

[!code-csharp[System.DateTimeOffset.Methods#16](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/cs/Methods.cs#16)]
[!code-vb[System.DateTimeOffset.Methods#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Methods/vb/Methods.vb#16)]

## <a name="converting-utc-to-a-designated-time-zone"></a><span data-ttu-id="2e958-133">将 UTC 转换为指定的时区</span><span class="sxs-lookup"><span data-stu-id="2e958-133">Converting UTC to a designated time zone</span></span>

<span data-ttu-id="2e958-134">若要将 UTC 转换为本地时间，请参阅后面的"转换 UTC 转换为本地时间"部分。</span><span class="sxs-lookup"><span data-stu-id="2e958-134">To convert UTC to local time, see the "Converting UTC to Local Time" section that follows.</span></span> <span data-ttu-id="2e958-135">若要将 UTC 转换为指定的任何时区的时间，请调用<xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="2e958-135">To convert UTC to the time in any time zone that you designate, call the <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A> method.</span></span> <span data-ttu-id="2e958-136">该方法采用两个参数：</span><span class="sxs-lookup"><span data-stu-id="2e958-136">The method takes two parameters:</span></span>

* <span data-ttu-id="2e958-137">要转换的 UTC。</span><span class="sxs-lookup"><span data-stu-id="2e958-137">The UTC to convert.</span></span> <span data-ttu-id="2e958-138">这必须是<xref:System.DateTime>值，其<xref:System.DateTime.Kind%2A>属性设置为`Unspecified`或`Utc`。</span><span class="sxs-lookup"><span data-stu-id="2e958-138">This must be a <xref:System.DateTime> value whose <xref:System.DateTime.Kind%2A> property is set to `Unspecified` or `Utc`.</span></span>

* <span data-ttu-id="2e958-139">UTC 要转换的目标时区。</span><span class="sxs-lookup"><span data-stu-id="2e958-139">The time zone to convert the UTC to.</span></span>

<span data-ttu-id="2e958-140">以下代码可将 UTC 转换为中部标准时间。</span><span class="sxs-lookup"><span data-stu-id="2e958-140">The following code converts UTC to Central Standard Time.</span></span>

[!code-csharp[System.TimeZone2.Concepts#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#8)]
[!code-vb[System.TimeZone2.Concepts#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#8)]

## <a name="converting-utc-to-local-time"></a><span data-ttu-id="2e958-141">将 UTC 转换为本地时间</span><span class="sxs-lookup"><span data-stu-id="2e958-141">Converting UTC to local time</span></span>

<span data-ttu-id="2e958-142">若要将 UTC 转换为本地时间，请调用<xref:System.DateTime.ToLocalTime%2A>方法的<xref:System.DateTime>对象要转换其时间。</span><span class="sxs-lookup"><span data-stu-id="2e958-142">To convert UTC to local time, call the <xref:System.DateTime.ToLocalTime%2A> method of the <xref:System.DateTime> object whose time you want to convert.</span></span> <span data-ttu-id="2e958-143">该方法的具体行为取决于对象的值<xref:System.DateTime.Kind%2A>属性，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="2e958-143">The exact behavior of the method depends on the value of the object’s <xref:System.DateTime.Kind%2A> property, as the following table shows.</span></span>

| `DateTime.Kind`            | <span data-ttu-id="2e958-144">转换</span><span class="sxs-lookup"><span data-stu-id="2e958-144">Conversion</span></span>                                                                               |
| -------------------------- | ---------------------------------------------------------------------------------------- |
| `DateTimeKind.Local`       | <span data-ttu-id="2e958-145">返回<xref:System.DateTime>值保持不变。</span><span class="sxs-lookup"><span data-stu-id="2e958-145">Returns the <xref:System.DateTime> value unchanged.</span></span>                                      |
| `DateTimeKind.Unspecified` | <span data-ttu-id="2e958-146">假定<xref:System.DateTime>值为 UTC，并将 UTC 转换为本地时间。</span><span class="sxs-lookup"><span data-stu-id="2e958-146">Assumes that the <xref:System.DateTime> value is UTC and converts the UTC to local time.</span></span> |
| `DateTimeKind.Utc`         | <span data-ttu-id="2e958-147">将转换<xref:System.DateTime>为本地时间的值。</span><span class="sxs-lookup"><span data-stu-id="2e958-147">Converts the <xref:System.DateTime> value to local time.</span></span>                                 |

> [!NOTE]
> <span data-ttu-id="2e958-148"><xref:System.TimeZone.ToLocalTime%2A?displayProperty=nameWithType>方法的行为完全相同`DateTime.ToLocalTime`方法。</span><span class="sxs-lookup"><span data-stu-id="2e958-148">The <xref:System.TimeZone.ToLocalTime%2A?displayProperty=nameWithType> method behaves identically to the `DateTime.ToLocalTime` method.</span></span> <span data-ttu-id="2e958-149">它采用单个参数，这是要转换的日期和时间值。</span><span class="sxs-lookup"><span data-stu-id="2e958-149">It takes a single parameter, which is the date and time value to convert.</span></span>

<span data-ttu-id="2e958-150">您还可以将任何指定时区中的时间通过转换为本地时间`static`(`Shared`在 Visual Basic 中)<xref:System.TimeZoneInfo.ConvertTime%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="2e958-150">You can also convert the time in any designated time zone to local time by using the `static` (`Shared` in Visual Basic) <xref:System.TimeZoneInfo.ConvertTime%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="2e958-151">下一节中讨论此技术。</span><span class="sxs-lookup"><span data-stu-id="2e958-151">This technique is discussed in the next section.</span></span>

## <a name="converting-between-any-two-time-zones"></a><span data-ttu-id="2e958-152">在任意两个时区之间转换</span><span class="sxs-lookup"><span data-stu-id="2e958-152">Converting between any two time zones</span></span>

<span data-ttu-id="2e958-153">可以通过使用以下两个任意两个时区之间转换`static`(`Shared`在 Visual Basic 中) 的方法<xref:System.TimeZoneInfo>类：</span><span class="sxs-lookup"><span data-stu-id="2e958-153">You can convert between any two time zones by using either of the following two `static` (`Shared` in Visual Basic) methods of the <xref:System.TimeZoneInfo> class:</span></span>

* <xref:System.TimeZoneInfo.ConvertTime%2A>

  <span data-ttu-id="2e958-154">此方法的参数是要转换的日期和时间值`TimeZoneInfo`对象，表示日期和时间值的时区和`TimeZoneInfo`对象，表示要转换到的日期和时间值的时区。</span><span class="sxs-lookup"><span data-stu-id="2e958-154">This method's parameters are the date and time value to convert, a `TimeZoneInfo` object that represents the time zone of the date and time value, and a `TimeZoneInfo` object that represents the time zone to convert the date and time value to.</span></span>

* <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A>

  <span data-ttu-id="2e958-155">此方法的参数是日期和要转换的时间值、 日期和时间值的时区的标识符和时区的标识符将日期和时间值转换为。</span><span class="sxs-lookup"><span data-stu-id="2e958-155">This method's parameters are the date and time value to convert, the identifier of the date and time value's time zone, and the identifier of the time zone to convert the date and time value to.</span></span>

<span data-ttu-id="2e958-156">这两种方法需要<xref:System.DateTime.Kind%2A>要转换的日期和时间值的属性和<xref:System.TimeZoneInfo>表示其时区的对象或时区标识符彼此对应。</span><span class="sxs-lookup"><span data-stu-id="2e958-156">Both methods require that the <xref:System.DateTime.Kind%2A> property of the date and time value to convert and the <xref:System.TimeZoneInfo> object or time zone identifier that represents its time zone correspond to one another.</span></span> <span data-ttu-id="2e958-157">否则会引发 <xref:System.ArgumentException>。</span><span class="sxs-lookup"><span data-stu-id="2e958-157">Otherwise, an <xref:System.ArgumentException> is thrown.</span></span> <span data-ttu-id="2e958-158">例如，如果`Kind`属性的日期和时间值是`DateTimeKind.Local`，如果引发异常`TimeZoneInfo`作为参数传递给方法的对象是否不等于`TimeZoneInfo.Local`。</span><span class="sxs-lookup"><span data-stu-id="2e958-158">For example, if the `Kind` property of the date and time value is `DateTimeKind.Local`, an exception is thrown if the `TimeZoneInfo` object passed as a parameter to the method is not equal to `TimeZoneInfo.Local`.</span></span> <span data-ttu-id="2e958-159">作为参数传递给方法的标识符是否不相等，也会引发异常`TimeZoneInfo.Local.Id`。</span><span class="sxs-lookup"><span data-stu-id="2e958-159">An exception is also thrown if the identifier passed as a parameter to the method is not equal to `TimeZoneInfo.Local.Id`.</span></span>

<span data-ttu-id="2e958-160">下面的示例使用<xref:System.TimeZoneInfo.ConvertTime%2A>方法将夏威夷标准时间转换为本地时间。</span><span class="sxs-lookup"><span data-stu-id="2e958-160">The following example uses the <xref:System.TimeZoneInfo.ConvertTime%2A> method to convert from Hawaiian Standard Time to local time.</span></span>

[!code-csharp[System.TimeZone2.Concepts#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#9)]
[!code-vb[System.TimeZone2.Concepts#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#9)]

## <a name="converting-datetimeoffset-values"></a><span data-ttu-id="2e958-161">转换 DateTimeOffset 值</span><span class="sxs-lookup"><span data-stu-id="2e958-161">Converting DateTimeOffset values</span></span>

<span data-ttu-id="2e958-162">所表示的日期和时间值<xref:System.DateTimeOffset>对象不是完全时区感知能力，因为该对象解除关联从其所在的时区时实例化。</span><span class="sxs-lookup"><span data-stu-id="2e958-162">Date and time values represented by <xref:System.DateTimeOffset> objects are not fully time-zone aware because the object is disassociated from its time zone at the time it is instantiated.</span></span> <span data-ttu-id="2e958-163">但是，大多数情况下，应用程序仅需根据两种相对于 UTC 的偏移量，而不是特定时区的时间来转换日期和时间。</span><span class="sxs-lookup"><span data-stu-id="2e958-163">However, in many cases an application simply needs to convert a date and time based on two different offsets from UTC rather than on the time in particular time zones.</span></span> <span data-ttu-id="2e958-164">若要执行此转换，可以调用当前实例的<xref:System.DateTimeOffset.ToOffset%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="2e958-164">To perform this conversion, you can call the current instance's <xref:System.DateTimeOffset.ToOffset%2A> method.</span></span> <span data-ttu-id="2e958-165">方法的单个参数是新的日期和时间的方法是返回的值的偏移量。</span><span class="sxs-lookup"><span data-stu-id="2e958-165">The method's single parameter is the offset of the new date and time value that the method is to return.</span></span>

<span data-ttu-id="2e958-166">例如，如果用户所请求网页的日期和时间已知，并且已被序列化为 MM/dd/yyyy hh:mm:ss zzzz 格式的字符串，以下 `ReturnTimeOnServer` 方法会将此日期和时间值转换为 Web 服务器上的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="2e958-166">For example, if the date and time of a user request for a Web page is known and is serialized as a string in the format MM/dd/yyyy hh:mm:ss zzzz, the following `ReturnTimeOnServer` method converts this date and time value to the date and time on the Web server.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/TimeConversions.cs#1)]
[!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions.vb#1)] 

<span data-ttu-id="2e958-167">如果向该方法传递字符串“9/1/2007 5:32:07 -05:00”（表示比 UTC 早五个小时的时区中的日期和时间），则对处于美国太平洋标准时区中的服务器，太平洋标准时区运行。</span><span class="sxs-lookup"><span data-stu-id="2e958-167">If the method is passed the string "9/1/2007 5:32:07 -05:00", which represents the date and time in a time zone five hours earlier than UTC, it returns 9/1/2007 3:32:07 AM -07:00 for a server located in the U.S. Pacific Standard Time zone.</span></span>

<span data-ttu-id="2e958-168"><xref:System.TimeZoneInfo>类还包括一个重载<xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType>执行时区转换方法<xref:System.DateTimeOffset.ToOffset(System.TimeSpan)>值。</span><span class="sxs-lookup"><span data-stu-id="2e958-168">The <xref:System.TimeZoneInfo> class also includes an overload of the <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> method that performs time zone conversions with <xref:System.DateTimeOffset.ToOffset(System.TimeSpan)> values.</span></span> <span data-ttu-id="2e958-169">方法的参数是<xref:System.DateTimeOffset>值和时区的时间是要转换的引用。</span><span class="sxs-lookup"><span data-stu-id="2e958-169">The method's parameters are a <xref:System.DateTimeOffset> value and a reference to the time zone to which the time is to be converted.</span></span> <span data-ttu-id="2e958-170">方法调用返回<xref:System.DateTimeOffset>值。</span><span class="sxs-lookup"><span data-stu-id="2e958-170">The method call returns a <xref:System.DateTimeOffset> value.</span></span> <span data-ttu-id="2e958-171">例如，`ReturnTimeOnServer`方法在前面的示例重写，如下所示调用<xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29>方法。</span><span class="sxs-lookup"><span data-stu-id="2e958-171">For example, the `ReturnTimeOnServer` method in the previous example could be rewritten as follows to call the <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29> method.</span></span>

[!code-csharp[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/cs/timeconversions2.cs#2)]
[!code-vb[System.DateTimeOffset.Conceptual.OffsetConversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.OffsetConversions/vb/TimeConversions2.vb#2)]

## <a name="see-also"></a><span data-ttu-id="2e958-172">请参阅</span><span class="sxs-lookup"><span data-stu-id="2e958-172">See also</span></span>

<span data-ttu-id="2e958-173"><xref:System.TimeZoneInfo>
[日期、 时间和时区](../../../docs/standard/datetime/index.md)
[查找本地系统上定义的时区](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)</span><span class="sxs-lookup"><span data-stu-id="2e958-173"><xref:System.TimeZoneInfo>
[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[Finding the time zones defined on a local system](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)</span></span>

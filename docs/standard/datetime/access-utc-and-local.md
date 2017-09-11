---
title: "如何：访问预定义 UTC 和本地时区对象"
description: "如何访问预定义 UTC 和本地时区对象"
keywords: ".NET、.NET Core"
author: stevehoag
ms.author: shoag
ms.date: 08/11/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 13454d47-d957-421b-9ecd-940058b8835e
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: fcc48e40cdad25c6142dbc3a86513b816378fa4b
ms.contentlocale: zh-cn
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a><span data-ttu-id="3c77c-104">如何：访问预定义 UTC 和本地时区对象</span><span class="sxs-lookup"><span data-stu-id="3c77c-104">How to: access the predefined UTC and local time zone objects</span></span>

<span data-ttu-id="3c77c-105">[System.TimeZoneInfo](xref:System.TimeZoneInfo) 类提供 `Utc` 和 `Local` 两种属性，允许代码访问预定义时区对象。</span><span class="sxs-lookup"><span data-stu-id="3c77c-105">The [System.TimeZoneInfo](xref:System.TimeZoneInfo) class provides two properties, `Utc` and `Local`, that give your code access to predefined time zone objects.</span></span> <span data-ttu-id="3c77c-106">本主题介绍如何访问这些属性返回的 `TimeZoneInfo` 对象。</span><span class="sxs-lookup"><span data-stu-id="3c77c-106">This topic discusses how to access the `TimeZoneInfo` objects returned by those properties.</span></span>

## <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a><span data-ttu-id="3c77c-107">访问协调世界时 (UTC) TimeZoneInfo 对象</span><span class="sxs-lookup"><span data-stu-id="3c77c-107">To access the Coordinated Universal Time (UTC) TimeZoneInfo object</span></span>

1. <span data-ttu-id="3c77c-108">使用 **static**（在 Visual Basic 中使用 **Shared**）[TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) 属性访问协调世界时。</span><span class="sxs-lookup"><span data-stu-id="3c77c-108">Use the **static** (**Shared** in Visual Basic) [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) property to access Coordinated Universal Time.</span></span>

2. <span data-ttu-id="3c77c-109">不要将该属性返回的 [TimeZoneInfo](xref:System.TimeZoneInfo) 对象分配给对象变量，而是继续通过 [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) 属性访问协调世界时。</span><span class="sxs-lookup"><span data-stu-id="3c77c-109">Rather than assigning the [TimeZoneInfo](xref:System.TimeZoneInfo) object returned by the property to an object variable, continue to access Coordinated Universal Time through the [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) property.</span></span>


## <a name="to-access-the-local-time-zone"></a><span data-ttu-id="3c77c-110">访问本地时区</span><span class="sxs-lookup"><span data-stu-id="3c77c-110">To access the local time zone</span></span>

1. <span data-ttu-id="3c77c-111">使用 **static**（在 Visual Basic 中使用 **Shared**）[TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) 属性访问本地系统时区。</span><span class="sxs-lookup"><span data-stu-id="3c77c-111">Use the **static** (**Shared** in Visual Basic) [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) property to access the local system time zone.</span></span>

2. <span data-ttu-id="3c77c-112">不要将该属性返回的 [TimeZoneInfo](xref:System.TimeZoneInfo) 对象分配给对象变量，而是继续通过 [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) 属性访问本地时区。</span><span class="sxs-lookup"><span data-stu-id="3c77c-112">Rather than assigning the [TimeZoneInfo](xref:System.TimeZoneInfo) object returned by the property to an object variable, continue to access the local time zone through the [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) property.</span></span>

## <a name="example"></a><span data-ttu-id="3c77c-113">示例</span><span class="sxs-lookup"><span data-stu-id="3c77c-113">Example</span></span>

<span data-ttu-id="3c77c-114">以下代码使用 [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) 和 [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) 属性来转换美国和加拿大东部标准时区的时间，并将时区名称显示到控制台。</span><span class="sxs-lookup"><span data-stu-id="3c77c-114">The following code uses the [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) and [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) properties to convert a time from the U.S. and Canadian Eastern Standard time zone, as well as to display the time zone name to the console.</span></span>

```csharp
// Create Eastern Standard Time value and TimeZoneInfo object      
DateTime estTime = new DateTime(2007, 1, 1, 00, 00, 00);
string timeZoneName = "Eastern Standard Time";
try
{
   TimeZoneInfo est = TimeZoneInfo.FindSystemTimeZoneById(timeZoneName);

   // Convert EST to local time
   DateTime localTime = TimeZoneInfo.ConvertTime(estTime, est, TimeZoneInfo.Local);
   Console.WriteLine("At {0} {1}, the local time is {2} {3}.", 
           estTime, 
           est, 
           localTime, 
           TimeZoneInfo.Local.IsDaylightSavingTime(localTime) ?
                     TimeZoneInfo.Local.DaylightName : 
                     TimeZoneInfo.Local.StandardName);

   // Convert EST to UTC
   DateTime utcTime = TimeZoneInfo.ConvertTime(estTime, est, TimeZoneInfo.Utc);
   Console.WriteLine("At {0} {1}, the time is {2} {3}.", 
           estTime, 
           est, 
           utcTime, 
           TimeZoneInfo.Utc.StandardName);
}
catch (TimeZoneNotFoundException)
{
   Console.WriteLine("The {0} zone cannot be found in the registry.", 
                     timeZoneName);
}
catch (InvalidTimeZoneException)
{
   Console.WriteLine("The registry contains invalid data for the {0} zone.", 
                     timeZoneName);
}
```

```vb
' Create Eastern Standard Time value and TimeZoneInfo object      
Dim estTime As Date = #01/01/2007 00:00:00#
Dim timeZoneName As String = "Eastern Standard Time"
Try
   Dim est As TimeZoneInfo = TimeZoneInfo.FindSystemTimeZoneById(timeZoneName)

   ' Convert EST to local time
   Dim localTime As Date = TimeZoneInfo.ConvertTime(estTime, est, TimeZoneInfo.Local)
   Console.WriteLine("At {0} {1}, the local time is {2} {3}.", _
           estTime, _
           est, _
           localTime, _
           IIf(TimeZoneInfo.Local.IsDaylightSavingTime(localTime), _
               TimeZoneInfo.Local.DaylightName, _
               TimeZoneInfo.Local.StandardName))

   ' Convert EST to UTC
   Dim utcTime As Date = TimeZoneInfo.ConvertTime(estTime, est, TimeZoneInfo.Utc)
   Console.WriteLine("At {0} {1}, the time is {2} {3}.", _
           estTime, _
           est, _
           utcTime, _
           TimeZoneInfo.Utc.StandardName)
Catch e As TimeZoneNotFoundException
   Console.WriteLine("The {0} zone cannot be found in the registry.", _
                     timeZoneName)
Catch e As InvalidTimeZoneException
   Console.WriteLine("The registry contains invalid data for the {0} zone.", _
                     timeZoneName)
End Try
```

<span data-ttu-id="3c77c-115">应始终通过 [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) 属性来访问本地时区，而不是将本地时区分配给 [TimeZoneInfo](xref:System.TimeZoneInfo) 对象变量。</span><span class="sxs-lookup"><span data-stu-id="3c77c-115">You should always access the local time zone through the [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) property rather than assigning the local time zone to a [TimeZoneInfo](xref:System.TimeZoneInfo) object variable.</span></span> <span data-ttu-id="3c77c-116">同样，应始终通过 [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) 属性来访问协调世界时，而不是将 UTC 时区分配给 [TimeZoneInfo](xref:System.TimeZoneInfo) 对象变量。</span><span class="sxs-lookup"><span data-stu-id="3c77c-116">Similarly, you should always access Coordinated Universal Time through the [TimeZoneInfo.Utc](xref:System.TimeZoneInfo.Utc) property rather than assigning the UTC zone to a [TimeZoneInfo](xref:System.TimeZoneInfo) object variable.</span></span> <span data-ttu-id="3c77c-117">这可防止 [TimeZoneInfo](xref:System.TimeZoneInfo) 对象变量因外部方法而失效。</span><span class="sxs-lookup"><span data-stu-id="3c77c-117">This prevents the [TimeZoneInfo](xref:System.TimeZoneInfo) object variable from being invalidated by an external method.</span></span>


## <a name="see-also"></a><span data-ttu-id="3c77c-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3c77c-118">See Also</span></span>

[<span data-ttu-id="3c77c-119">日期、时间和时区</span><span class="sxs-lookup"><span data-stu-id="3c77c-119">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="3c77c-120">查找本地系统上定义的时区</span><span class="sxs-lookup"><span data-stu-id="3c77c-120">Finding the time zones defined on a local system</span></span>](finding-the-time-zones-on-local-system.md)


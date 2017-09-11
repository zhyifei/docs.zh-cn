---
title: "如何：让用户解决不明确时间"
description: "如何让用户解决不明确时间"
keywords: ".NET、.NET Core"
author: stevehoag
ms.author: shoag
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: d6858a5c-02ab-4367-9e08-fa22c051c38d
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: ede8d021a4f524cf37f7ad00b6aed89d1b1729f8
ms.contentlocale: zh-cn
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-let-users-resolve-ambiguous-times"></a><span data-ttu-id="0efb3-104">如何：让用户解决不明确时间</span><span class="sxs-lookup"><span data-stu-id="0efb3-104">How to: let users resolve ambiguous times</span></span>

<span data-ttu-id="0efb3-105">不明确时间是指映射到多个协调世界时 (UTC) 的时间。</span><span class="sxs-lookup"><span data-stu-id="0efb3-105">An ambiguous time is a time that maps to more than one Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="0efb3-106">在向后调整时钟时间时，例如从时区的夏令时调整到标准时间这段转换期间，便会出现不明确时间。</span><span class="sxs-lookup"><span data-stu-id="0efb3-106">It occurs when the clock time is adjusted back in time, such as during the transition from a time zone's daylight saving time to its standard time.</span></span> <span data-ttu-id="0efb3-107">在处理不明确时间时，可执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="0efb3-107">When handling an ambiguous time, you can do one of the following:</span></span>

* <span data-ttu-id="0efb3-108">如果不明确时间是用户输入的数据项，则可以让用户自行解决。</span><span class="sxs-lookup"><span data-stu-id="0efb3-108">If the ambiguous time is an item of data entered by the user, you can leave it to the user to resolve the ambiguity.</span></span>

* <span data-ttu-id="0efb3-109">假设一下时间如何映射到 UTC。</span><span class="sxs-lookup"><span data-stu-id="0efb3-109">Make an assumption about how the time maps to UTC.</span></span> <span data-ttu-id="0efb3-110">例如，可以假定不明确时间始终以时区的标准时间表示。</span><span class="sxs-lookup"><span data-stu-id="0efb3-110">For example, you can assume that an ambiguous time is always expressed in the time zone's standard time.</span></span>

<span data-ttu-id="0efb3-111">本文介绍如何让用户解决不明确时间。</span><span class="sxs-lookup"><span data-stu-id="0efb3-111">This article shows how to let a user resolve an ambiguous time.</span></span>

## <a name="to-let-a-user-resolve-an-ambiguous-time"></a><span data-ttu-id="0efb3-112">让用户解决不明确时间</span><span class="sxs-lookup"><span data-stu-id="0efb3-112">To let a user resolve an ambiguous time</span></span>

1. <span data-ttu-id="0efb3-113">获取用户输入的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="0efb3-113">Get the date and time input by the user.</span></span>

2. <span data-ttu-id="0efb3-114">调用 [IsAmbiguousTime(DateTime)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTime)) 或 [IsAmbiguousTime(DateTimeOffset)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTimeOffset)) 方法，确定时间是否不明确。</span><span class="sxs-lookup"><span data-stu-id="0efb3-114">Call the [IsAmbiguousTime(DateTime)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTime)) or [IsAmbiguousTime(DateTimeOffset)](xref:System.TimeZoneInfo.IsAmbiguousTime(System.DateTimeOffset)) method to determine whether the time is ambiguous.</span></span>

3. <span data-ttu-id="0efb3-115">让用户选择所需时差。</span><span class="sxs-lookup"><span data-stu-id="0efb3-115">Let the user select the desired offset.</span></span>

4. <span data-ttu-id="0efb3-116">用本地时间减去用户所选时差，得出 UTC 日期和时间。</span><span class="sxs-lookup"><span data-stu-id="0efb3-116">Get the UTC date and time by subtracting the offset selected by the user from the local time.</span></span>

5. <span data-ttu-id="0efb3-117">调用 `static`（Visual Basic 中的 `Shared`）[SpecifyKind](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)) 方法，将 UTC 日期和时间值的 [Kind](xref:System.DateTime.Kind) 属性设置为 [DateTimeKind.Utc](xref:System.DateTimeKind.Utc)。</span><span class="sxs-lookup"><span data-stu-id="0efb3-117">Call the `static` (`Shared` in Visual Basic ) [SpecifyKind](xref:System.DateTime.SpecifyKind(System.DateTime,System.DateTimeKind)) method to set the UTC date and time value's [Kind](xref:System.DateTime.Kind) property to [DateTimeKind.Utc](xref:System.DateTimeKind.Utc).</span></span>

## <a name="example"></a><span data-ttu-id="0efb3-118">示例</span><span class="sxs-lookup"><span data-stu-id="0efb3-118">Example</span></span>

<span data-ttu-id="0efb3-119">以下示例将提示用户输入日期和时间，如果时间不明确，会让用户选择不明确时间映射到的 UTC 时间。</span><span class="sxs-lookup"><span data-stu-id="0efb3-119">The following example prompts the user to enter a date and time and, if it is ambiguous, lets the user select the UTC time that the ambiguous time maps to.</span></span> <span data-ttu-id="0efb3-120">该示例使用 [DateTime](xref:System.DateTime) 对象；如果需要，可替换为 [DateTimeOffset](xref:System.DateTimeOffset) 对象。</span><span class="sxs-lookup"><span data-stu-id="0efb3-120">The example uses a [DateTime](xref:System.DateTime) object; you can substitute a [DateTimeOffset](xref:System.DateTimeOffset) object if desired.</span></span>

```csharp
private void GetUserDateInput()
{
   // Get date and time from user
   DateTime inputDate = GetUserDateTime();
   DateTime utcDate;

   // Exit if date has no significant value
   if (inputDate == DateTime.MinValue) return;

   if (TimeZoneInfo.Local.IsAmbiguousTime(inputDate))
   {
      Console.WriteLine("The date you've entered is ambiguous.");
      Console.WriteLine("Please select the correct offset from Universal Coordinated Time:");
      TimeSpan[] offsets = TimeZoneInfo.Local.GetAmbiguousTimeOffsets(inputDate);
      for (int ctr = 0; ctr < offsets.Length; ctr++)
      {
         Console.WriteLine("{0}.) {1} hours, {2} minutes", ctr, offsets[ctr].Hours, offsets[ctr].Minutes);
      }
      Console.Write("> ");
      int selection = Convert.ToInt32(Console.ReadLine());

      // Convert local time to UTC, and set Kind property to DateTimeKind.Utc
      utcDate = DateTime.SpecifyKind(inputDate - offsets[selection], DateTimeKind.Utc);

      Console.WriteLine("{0} local time corresponds to {1} {2}.", inputDate, utcDate, utcDate.Kind.ToString());
   }
   else
   {
      utcDate = inputDate.ToUniversalTime();
      Console.WriteLine("{0} local time corresponds to {1} {2}.", inputDate, utcDate, utcDate.Kind.ToString());    
   }
}

private DateTime GetUserDateTime() 
{
   bool exitFlag = false;             // flag to exit loop if date is valid
   string dateString;  
   DateTime inputDate = DateTime.MinValue;

   Console.Write("Enter a local date and time: ");
   while (! exitFlag)
   {
      dateString = Console.ReadLine();
      if (dateString.ToUpper() == "E")
         exitFlag = true;

      if (DateTime.TryParse(dateString, out inputDate))
         exitFlag = true;
      else
         Console.Write("Enter a valid date and time, or enter 'e' to exit: ");
   }

   return inputDate;        
}
```

```vb
Private Sub GetUserDateInput()
   ' Get date and time from user
   Dim inputDate As Date = GetUserDateTime()
   Dim utcDate As Date

   ' Exit if date has no significant value
   If inputDate = Date.MinValue Then Exit Sub

   If TimeZoneInfo.Local.IsAmbiguousTime(inputDate) Then
      Console.WriteLine("The date you've entered is ambiguous.")
      Console.WriteLine("Please select the correct offset from Universal Coordinated Time:")
      Dim offsets() As TimeSpan = TimeZoneInfo.Local.GetAmbiguousTimeOffsets(inputDate)
      For ctr As Integer = 0 to offsets.Length - 1
         Dim zoneDescription As String
         If offsets(ctr).Equals(TimeZoneInfo.Local.BaseUtcOffset) Then 
            zoneDescription = TimeZoneInfo.Local.StandardName
         Else
            zoneDescription = TimeZoneInfo.Local.DaylightName
         End If
         Console.WriteLine("{0}.) {1} hours, {2} minutes ({3})", _
                           ctr, offsets(ctr).Hours, offsets(ctr).Minutes, zoneDescription)
      Next         
      Console.Write("> ")
      Dim selection As Integer = CInt(Console.ReadLine())

      ' Convert local time to UTC, and set Kind property to DateTimeKind.Utc
      utcDate = Date.SpecifyKind(inputDate - offsets(selection), DateTimeKind.Utc)

      Console.WriteLine("{0} local time corresponds to {1} {2}.", inputDate, utcDate, utcDate.Kind.ToString())
   Else
      utcDate = inputDate.ToUniversalTime()
      Console.WriteLine("{0} local time corresponds to {1} {2}.", inputDate, utcDate, utcDate.Kind.ToString())    
   End If
End Sub

Private Function GetUserDateTime() As Date
   Dim exitFlag As Boolean = False            ' flag to exit loop if date is valid
   Dim dateString As String 
   Dim inputDate As Date = Date.MinValue

   Console.Write("Enter a local date and time: ")
   Do While Not exitFlag
      dateString = Console.ReadLine()
      If dateString.ToUpper = "E" Then exitFlag = True
      If Date.TryParse(dateString, inputDate) Then
         exitFlag = true
      Else   
         Console.Write("Enter a valid date and time, or enter 'e' to exit: ")
      End If
   Loop

   Return inputDate        
End Function
```

<span data-ttu-id="0efb3-121">该示例代码的核心使用一组 [TimeSpan](xref:System.TimeSpan) 对象，来指示不明确时间与 UTC 之间可能的时差。</span><span class="sxs-lookup"><span data-stu-id="0efb3-121">The core of the example code uses an array of [TimeSpan](xref:System.TimeSpan) objects to indicate possible offsets of the ambiguous time from UTC.</span></span> <span data-ttu-id="0efb3-122">但是，这些时差值对用户可能没有什么意义。</span><span class="sxs-lookup"><span data-stu-id="0efb3-122">However, these offsets are unlikely to be meaningful to the user.</span></span> <span data-ttu-id="0efb3-123">为了阐明时差的含义，该代码还会指示时差是表示本地时区的标准时间还是其夏令时。</span><span class="sxs-lookup"><span data-stu-id="0efb3-123">To clarify the meaning of the offsets, the code also notes whether an offset represents the local time zone's standard time or its daylight saving time.</span></span> <span data-ttu-id="0efb3-124">该代码通过将时差与 [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset) 属性的值相比较，确定哪个是标准时间，哪个是夏令时。</span><span class="sxs-lookup"><span data-stu-id="0efb3-124">The code determines which time is standard and which time is daylight by comparing the offset with the value of the [BaseUtcOffset](xref:System.TimeZoneInfo.BaseUtcOffset) property.</span></span> <span data-ttu-id="0efb3-125">此属性指示 UTC 与时区的标准时间之差。</span><span class="sxs-lookup"><span data-stu-id="0efb3-125">This property indicates the difference between the UTC and the time zone's standard time.</span></span>

<span data-ttu-id="0efb3-126">在本示例中，均通过 [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) 属性引用本地时区；绝不会将本地时区分配给对象变量。</span><span class="sxs-lookup"><span data-stu-id="0efb3-126">In this example, all references to the local time zone are made through the [TimeZoneInfo.Local](xref:System.TimeZoneInfo.Local) property; the local time zone is never assigned to an object variable.</span></span> <span data-ttu-id="0efb3-127">这是建议做法，因为另一个调用可以清除缓存数据并使本地时区分配到的任何对象无效。</span><span class="sxs-lookup"><span data-stu-id="0efb3-127">This is a recommended practice because another call could clear the cached data and invalidate any objects that the local time zone is assigned to.</span></span>

## <a name="see-also"></a><span data-ttu-id="0efb3-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0efb3-128">See Also</span></span>

[<span data-ttu-id="0efb3-129">日期、时间和时区</span><span class="sxs-lookup"><span data-stu-id="0efb3-129">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="0efb3-130">如何：解决不明确时间</span><span class="sxs-lookup"><span data-stu-id="0efb3-130">How to: resolve ambiguous times</span></span>](resolve-ambiguous-times.md)



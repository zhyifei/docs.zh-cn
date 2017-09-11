---
title: "如何：枚举计算机上存在的时区"
description: "如何枚举计算机上存在的时区"
keywords: ".NET、.NET Core"
author: stevehoag
ms.author: shoag
ms.date: 08/15/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: c5ae4a6c-1790-4355-b5b1-879aaf956129
ms.translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: f30ba2a483ff7e5867417969946c2774175d5e3d
ms.contentlocale: zh-cn
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-enumerate-time-zones-present-on-a-computer"></a><span data-ttu-id="a3431-104">如何：枚举计算机上存在的时区</span><span class="sxs-lookup"><span data-stu-id="a3431-104">How to: enumerate time zones present on a computer</span></span>

<span data-ttu-id="a3431-105">若要成功使用指定的时区，需要该时区的相关信息可供系统使用。</span><span class="sxs-lookup"><span data-stu-id="a3431-105">Successfully working with a designated time zone requires that information about that time zone be available to the system.</span></span> <span data-ttu-id="a3431-106">例如，Windows 操作系统将此信息存储在注册表中。</span><span class="sxs-lookup"><span data-stu-id="a3431-106">For example, the Windows operating system stores this information in the registry.</span></span> <span data-ttu-id="a3431-107">但是，尽管世界上存在的时区总数非常大，但注册表包含的信息只是其中的一个子集。</span><span class="sxs-lookup"><span data-stu-id="a3431-107">However, although the total number of time zones that exist throughout the world is large, the registry contains information about only a subset of them.</span></span> <span data-ttu-id="a3431-108">此外，注册表本身是一个动态结构，其内容可能发生有意或无意的更改。</span><span class="sxs-lookup"><span data-stu-id="a3431-108">In addition, the registry itself is a dynamic structure whose contents are subject to both deliberate and accidental change.</span></span> <span data-ttu-id="a3431-109">因此，应用程序无法保证系统上始终存在已定义且可用的特定时区。</span><span class="sxs-lookup"><span data-stu-id="a3431-109">As a result, an application cannot always assume that a particular time zone is defined and available on a system.</span></span> <span data-ttu-id="a3431-110">对于使用时区信息应用程序的许多应用程序来说，第一步是确定所需时区在本地系统上是否可用，或者向用户提供可供选择的时区列表。</span><span class="sxs-lookup"><span data-stu-id="a3431-110">The first step for many applications that use time zone information applications is to determine whether required time zones are available on the local system, or to give the user a list of time zones from which to select.</span></span> <span data-ttu-id="a3431-111">这要求应用程序枚举本地系统上定义的时区。</span><span class="sxs-lookup"><span data-stu-id="a3431-111">This requires that an application enumerate the time zones defined on a local system.</span></span> 

## <a name="to-enumerate-the-time-zones-present-on-the-local-system"></a><span data-ttu-id="a3431-112">枚举本地系统上存在的时区</span><span class="sxs-lookup"><span data-stu-id="a3431-112">To enumerate the time zones present on the local system</span></span>

1. <span data-ttu-id="a3431-113">请调用 [TimeZoneInfo.GetSystemTimeZones](xref:System.TimeZoneInfo.GetSystemTimeZones) 方法。</span><span class="sxs-lookup"><span data-stu-id="a3431-113">Call the [TimeZoneInfo.GetSystemTimeZones](xref:System.TimeZoneInfo.GetSystemTimeZones) method.</span></span> <span data-ttu-id="a3431-114">该方法会返回 [TimeZoneInfo](xref:System.TimeZoneInfo) 对象的泛型 [ReadOnlyCollection&lt;T&gt;](xref:System.Collections.ObjectModel.ReadOnlyCollection%601) 集合。</span><span class="sxs-lookup"><span data-stu-id="a3431-114">The method returns a generic [ReadOnlyCollection&lt;T&gt;](xref:System.Collections.ObjectModel.ReadOnlyCollection%601) collection of [TimeZoneInfo](xref:System.TimeZoneInfo) objects.</span></span> <span data-ttu-id="a3431-115">集合中的项按其 [DisplayName](xref:System.TimeZoneInfo.DisplayName) 属性排序。</span><span class="sxs-lookup"><span data-stu-id="a3431-115">The entries in the collection are sorted by their [DisplayName](xref:System.TimeZoneInfo.DisplayName) property.</span></span> <span data-ttu-id="a3431-116">例如: </span><span class="sxs-lookup"><span data-stu-id="a3431-116">For example:</span></span>

    ```csharp
    ReadOnlyCollection<TimeZoneInfo> tzCollection;
    tzCollection = TimeZoneInfo.GetSystemTimeZones();
    ```

    ```vb
    Dim tzCollection As ReadOnlyCollection(Of TimeZoneInfo) = TimeZoneInfo.GetSystemTimeZones
    ```

2. <span data-ttu-id="a3431-117">使用 `foreach` 循环（C# 中）或 `For Each…Next` 循环（Visual Basic 中）枚举集合中的各个 [TimeZoneInfo](xref:System.TimeZoneInfo) 对象，并对每个对象执行任何必要的处理。</span><span class="sxs-lookup"><span data-stu-id="a3431-117">Enumerate the individual [TimeZoneInfo](xref:System.TimeZoneInfo) objects in the collection by using a `foreach` loop (in C#) or a `For Each…Next` loop (in Visual Basic), and perform any necessary processing on each object.</span></span> <span data-ttu-id="a3431-118">例如，以下代码枚举步骤 1 中所返回 [TimeZoneInfo](xref:System.TimeZoneInfo) 对象的 [ReadOnlyCollection&lt;T&gt;](xref:System.Collections.ObjectModel.ReadOnlyCollection%601) 集合，并在控制台上列出每个时区的显示名称。</span><span class="sxs-lookup"><span data-stu-id="a3431-118">For example, the following code enumerates the [ReadOnlyCollection&lt;T&gt;](xref:System.Collections.ObjectModel.ReadOnlyCollection%601) collection of [TimeZoneInfo](xref:System.TimeZoneInfo) objects returned in step 1 and lists the display name of each time zone on the console.</span></span>

    ```csharp
    foreach (TimeZoneInfo timeZone in tzCollection)
    Console.WriteLine("   {0}: {1}", timeZone.Id, timeZone.DisplayName);
    ```

    ```vb
    For Each timeZone As TimeZoneInfo In tzCollection
        Console.WriteLine("   {0}: {1}", timeZone.Id, timeZone.DisplayName)
    Next
    ```

## <a name="see-also"></a><span data-ttu-id="a3431-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a3431-119">See Also</span></span>

[<span data-ttu-id="a3431-120">日期、时间和时区</span><span class="sxs-lookup"><span data-stu-id="a3431-120">Dates, times, and time zones</span></span>](index.md)

[<span data-ttu-id="a3431-121">查找本地系统上定义的时区</span><span class="sxs-lookup"><span data-stu-id="a3431-121">Finding the time zones defined on a local system</span></span>](finding-the-time-zones-on-local-system.md)



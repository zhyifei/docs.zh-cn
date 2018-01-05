---
title: "如何： 枚举计算机上存在的时区"
ms.custom: 
ms.date: 04/10/2017
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
- time zones [.NET Framework], enumerating
- enumerating time zones [.NET Framework]
ms.assetid: bb7a42ab-6bd9-4c5c-b734-5546d51f8669
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 2318a42040388adfe327f9d0075754daa1aa22a6
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-enumerate-time-zones-present-on-a-computer"></a><span data-ttu-id="fefed-102">如何： 枚举计算机上存在的时区</span><span class="sxs-lookup"><span data-stu-id="fefed-102">How to: Enumerate time zones present on a computer</span></span>

<span data-ttu-id="fefed-103">若要成功使用指定的时区，需要该时区的相关信息可供系统使用。</span><span class="sxs-lookup"><span data-stu-id="fefed-103">Successfully working with a designated time zone requires that information about that time zone be available to the system.</span></span> <span data-ttu-id="fefed-104">Windows XP 和 Windows Vista 操作系统在系统注册表中存储此信息。</span><span class="sxs-lookup"><span data-stu-id="fefed-104">The Windows XP and Windows Vista operating systems store this information in the registry.</span></span> <span data-ttu-id="fefed-105">但是，尽管世界上存在的时区总数非常大，但注册表包含的信息只是其中的一个子集。</span><span class="sxs-lookup"><span data-stu-id="fefed-105">However, although the total number of time zones that exist throughout the world is large, the registry contains information about only a subset of them.</span></span> <span data-ttu-id="fefed-106">此外，注册表本身是一个动态结构，其内容可能发生有意或无意的更改。</span><span class="sxs-lookup"><span data-stu-id="fefed-106">In addition, the registry itself is a dynamic structure whose contents are subject to both deliberate and accidental change.</span></span> <span data-ttu-id="fefed-107">因此，应用程序无法保证系统上始终存在已定义且可用的特定时区。</span><span class="sxs-lookup"><span data-stu-id="fefed-107">As a result, an application cannot always assume that a particular time zone is defined and available on a system.</span></span> <span data-ttu-id="fefed-108">对于使用时区信息应用程序的许多应用程序来说，第一步是确定所需时区在本地系统上是否可用，或者向用户提供可供选择的时区列表。</span><span class="sxs-lookup"><span data-stu-id="fefed-108">The first step for many applications that use time zone information applications is to determine whether required time zones are available on the local system, or to give the user a list of time zones from which to select.</span></span> <span data-ttu-id="fefed-109">这要求应用程序枚举本地系统上定义的时区。</span><span class="sxs-lookup"><span data-stu-id="fefed-109">This requires that an application enumerate the time zones defined on a local system.</span></span>

> [!NOTE]
> <span data-ttu-id="fefed-110">如果应用程序依赖于本地系统可能未定义特定时区的存在状态，则应用程序可以通过序列化和反序列化有关时区信息确保其存在。</span><span class="sxs-lookup"><span data-stu-id="fefed-110">If an application relies on the presence of a particular time zone that may not be defined on a local system, the application can ensure its presence by serializing and deserializing information about the time zone.</span></span> <span data-ttu-id="fefed-111">时区然后可以添加到列表控件，以便应用程序用户可以选择它。</span><span class="sxs-lookup"><span data-stu-id="fefed-111">The time zone can then be added to a list control so that the application user can select it.</span></span> <span data-ttu-id="fefed-112">有关详细信息，请参阅[如何： 保存时区添加到嵌入的资源](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)和[如何： 从嵌入的资源还原时区](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)。</span><span class="sxs-lookup"><span data-stu-id="fefed-112">For details, see [How to: Save Time Zones to an Embedded Resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) and [How to: Restore time zones from an embedded resource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).</span></span>

### <a name="to-enumerate-the-time-zones-present-on-the-local-system"></a><span data-ttu-id="fefed-113">枚举本地系统上存在的时区</span><span class="sxs-lookup"><span data-stu-id="fefed-113">To enumerate the time zones present on the local system</span></span>

1. <span data-ttu-id="fefed-114">调用 <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="fefed-114">Call the <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="fefed-115">该方法返回泛型<xref:System.Collections.ObjectModel.ReadOnlyCollection%601>集合<xref:System.TimeZoneInfo>对象。</span><span class="sxs-lookup"><span data-stu-id="fefed-115">The method returns a generic <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> collection of <xref:System.TimeZoneInfo> objects.</span></span> <span data-ttu-id="fefed-116">集合中的项将按其<xref:System.TimeZoneInfo.DisplayName%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="fefed-116">The entries in the collection are sorted by their <xref:System.TimeZoneInfo.DisplayName%2A> property.</span></span> <span data-ttu-id="fefed-117">例如:</span><span class="sxs-lookup"><span data-stu-id="fefed-117">For example:</span></span>

   [!code-csharp[System.TimeZone2.Concepts#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#1)]
   [!code-vb[System.TimeZone2.Concepts#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#1)]

2. <span data-ttu-id="fefed-118">枚举个人<xref:System.TimeZoneInfo>通过使用集合中的对象`foreach`循环 （在 C# 中) 或`For Each`...`Next`</span><span class="sxs-lookup"><span data-stu-id="fefed-118">Enumerate the individual <xref:System.TimeZoneInfo> objects in the collection by using a `foreach` loop (in C#) or a `For Each`…`Next`</span></span> <span data-ttu-id="fefed-119">循环 （在 Visual Basic 中)，并对每个对象执行任何必要的处理。</span><span class="sxs-lookup"><span data-stu-id="fefed-119">loop (in Visual Basic), and perform any necessary processing on each object.</span></span> <span data-ttu-id="fefed-120">例如，下面的代码枚举<xref:System.Collections.ObjectModel.ReadOnlyCollection%601>集合<xref:System.TimeZoneInfo>对象步骤 1 中返回，并列出在控制台上每个时区的显示名称。</span><span class="sxs-lookup"><span data-stu-id="fefed-120">For example, the following code enumerates the <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> collection of <xref:System.TimeZoneInfo> objects returned in step 1 and lists the display name of each time zone on the console.</span></span>

   [!code-csharp[System.TimeZone2.Concepts#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#12)]
   [!code-vb[System.TimeZone2.Concepts#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#12)]

### <a name="to-present-the-user-with-a-list-of-time-zones-present-on-the-local-system"></a><span data-ttu-id="fefed-121">若要向用户提供的本地系统上存在的时间区域的列表</span><span class="sxs-lookup"><span data-stu-id="fefed-121">To present the user with a list of time zones present on the local system</span></span>

1. <span data-ttu-id="fefed-122">调用 <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="fefed-122">Call the <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="fefed-123">该方法返回泛型<xref:System.Collections.ObjectModel.ReadOnlyCollection%601>集合<xref:System.TimeZoneInfo>对象。</span><span class="sxs-lookup"><span data-stu-id="fefed-123">The method returns a generic <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> collection of <xref:System.TimeZoneInfo> objects.</span></span>

2. <span data-ttu-id="fefed-124">分配到第 1 步中返回的集合`DataSource`属性的 Windows 窗体或 ASP.NET 列表控件。</span><span class="sxs-lookup"><span data-stu-id="fefed-124">Assign the collection returned in step 1 to the `DataSource` property of a Windows forms or ASP.NET list control.</span></span>

3. <span data-ttu-id="fefed-125">检索<xref:System.TimeZoneInfo>用户选定的对象。</span><span class="sxs-lookup"><span data-stu-id="fefed-125">Retrieve the <xref:System.TimeZoneInfo> object that the user has selected.</span></span>

<span data-ttu-id="fefed-126">该示例说明了为 Windows 应用程序。</span><span class="sxs-lookup"><span data-stu-id="fefed-126">The example provides an illustration for a Windows application.</span></span>

## <a name="example"></a><span data-ttu-id="fefed-127">示例</span><span class="sxs-lookup"><span data-stu-id="fefed-127">Example</span></span>

<span data-ttu-id="fefed-128">该示例启动的 Windows 应用程序显示在列表框中的系统上定义的时区。</span><span class="sxs-lookup"><span data-stu-id="fefed-128">The example starts a Windows application that displays the time zones defined on a system in a list box.</span></span> <span data-ttu-id="fefed-129">该示例然后显示一个对话框，其中包含值<xref:System.TimeZoneInfo.DisplayName%2A>由用户选择的时区对象的属性。</span><span class="sxs-lookup"><span data-stu-id="fefed-129">The example then displays a dialog box that contains the value of the <xref:System.TimeZoneInfo.DisplayName%2A> property of the time zone object selected by the user.</span></span>

[!code-csharp[System.TimeZone2.Concepts#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#2)]
[!code-vb[System.TimeZone2.Concepts#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#2)]

<span data-ttu-id="fefed-130">大多数 list 控件 (如<xref:System.Windows.Forms.ListBox?displayProperty=nameWithType>或<xref:System.Web.UI.WebControls.BulletedList?displayProperty=nameWithType>控件) 可以分配到的对象变量的集合其`DataSource`属性，条件是该集合实现<xref:System.Collections.IEnumerable>接口。</span><span class="sxs-lookup"><span data-stu-id="fefed-130">Most list controls (such as the <xref:System.Windows.Forms.ListBox?displayProperty=nameWithType> or <xref:System.Web.UI.WebControls.BulletedList?displayProperty=nameWithType> control) allow you to assign a collection of object variables to their `DataSource` property as long as that collection implements the <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="fefed-131">(泛型<xref:System.Collections.ObjectModel.ReadOnlyCollection%601>类如此。)若要显示集合中的单个对象，该控件调用该对象的`ToString`方法以提取用于表示对象的字符串。</span><span class="sxs-lookup"><span data-stu-id="fefed-131">(The generic <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> class does this.) To display an individual object in the collection, the control calls that object's `ToString` method to extract the string that is used to represent the object.</span></span> <span data-ttu-id="fefed-132">情况下<xref:System.TimeZoneInfo>对象，`ToString`方法返回<xref:System.TimeZoneInfo>对象的显示名称 (的值其<xref:System.TimeZoneInfo.DisplayName%2A>属性)。</span><span class="sxs-lookup"><span data-stu-id="fefed-132">In the case of <xref:System.TimeZoneInfo> objects, the `ToString` method returns the <xref:System.TimeZoneInfo> object's display name (the value of its <xref:System.TimeZoneInfo.DisplayName%2A> property).</span></span>

> [!NOTE]
> <span data-ttu-id="fefed-133">原因是，列表控件调用对象的`ToString`方法，你可以分配的集合<xref:System.TimeZoneInfo>的对象添加到该控件，使该控件显示每个对象，有意义的名称和检索<xref:System.TimeZoneInfo>用户选定的对象。</span><span class="sxs-lookup"><span data-stu-id="fefed-133">Because list controls call an object's `ToString` method, you can assign a collection of <xref:System.TimeZoneInfo> objects to the control, have the control display a meaningful name for each object, and retrieve the <xref:System.TimeZoneInfo> object that the user has selected.</span></span> <span data-ttu-id="fefed-134">这消除了需要提取每个对象在集合中的字符串，将字符串分配给某个集合，将依次分配到控件的`DataSource`属性，检索用户选择，该字符串，然后使用此字符串中提取对象它描述。</span><span class="sxs-lookup"><span data-stu-id="fefed-134">This eliminates the need to extract a string for each object in the collection, assign the string to a collection that is in turn assigned to the control's `DataSource` property, retrieve the string the user has selected, and then use this string to extract the object that it describes.</span></span> 

## <a name="compiling-the-code"></a><span data-ttu-id="fefed-135">编译代码</span><span class="sxs-lookup"><span data-stu-id="fefed-135">Compiling the code</span></span>

<span data-ttu-id="fefed-136">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="fefed-136">This example requires:</span></span>

* <span data-ttu-id="fefed-137">对 System.Core.dll 的引用无法添加到项目。</span><span class="sxs-lookup"><span data-stu-id="fefed-137">That a reference to System.Core.dll be added to the project.</span></span>

* <span data-ttu-id="fefed-138">将导入以下命名空间：</span><span class="sxs-lookup"><span data-stu-id="fefed-138">That the following namespaces be imported:</span></span>

  <span data-ttu-id="fefed-139"><xref:System>（在 C# 代码中）</span><span class="sxs-lookup"><span data-stu-id="fefed-139"><xref:System> (in C# code)</span></span>

  <xref:System.Collections.ObjectModel>

## <a name="see-also"></a><span data-ttu-id="fefed-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="fefed-140">See also</span></span>

<span data-ttu-id="fefed-141">[日期、 时间和时区](../../../docs/standard/datetime/index.md)
[如何： 将时区保存到嵌入的资源](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
[如何： 从嵌入的资源还原时区](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)</span><span class="sxs-lookup"><span data-stu-id="fefed-141">[Dates, times, and time zones](../../../docs/standard/datetime/index.md)
[How to: Save time zones to an embedded resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
[How to: Restore time zones from an embedded resource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)</span></span>

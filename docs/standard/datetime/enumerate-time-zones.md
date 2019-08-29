---
title: 如何：枚举计算机上的时区
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], enumerating
- enumerating time zones [.NET Framework]
ms.assetid: bb7a42ab-6bd9-4c5c-b734-5546d51f8669
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: afc3b57659dd6719f72cefba8a6d2f1abe08c0d0
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106656"
---
# <a name="how-to-enumerate-time-zones-present-on-a-computer"></a><span data-ttu-id="a3e3f-102">如何：枚举计算机上的时区</span><span class="sxs-lookup"><span data-stu-id="a3e3f-102">How to: Enumerate time zones present on a computer</span></span>

<span data-ttu-id="a3e3f-103">若要成功使用指定的时区，需要该时区的相关信息可供系统使用。</span><span class="sxs-lookup"><span data-stu-id="a3e3f-103">Successfully working with a designated time zone requires that information about that time zone be available to the system.</span></span> <span data-ttu-id="a3e3f-104">Windows XP 和 Windows Vista 操作系统将此信息存储在注册表中。</span><span class="sxs-lookup"><span data-stu-id="a3e3f-104">The Windows XP and Windows Vista operating systems store this information in the registry.</span></span> <span data-ttu-id="a3e3f-105">但是，尽管世界上存在的时区总数非常大，但注册表包含的信息只是其中的一个子集。</span><span class="sxs-lookup"><span data-stu-id="a3e3f-105">However, although the total number of time zones that exist throughout the world is large, the registry contains information about only a subset of them.</span></span> <span data-ttu-id="a3e3f-106">此外，注册表本身是一个动态结构，其内容可能发生有意或无意的更改。</span><span class="sxs-lookup"><span data-stu-id="a3e3f-106">In addition, the registry itself is a dynamic structure whose contents are subject to both deliberate and accidental change.</span></span> <span data-ttu-id="a3e3f-107">因此，应用程序无法保证系统上始终存在已定义且可用的特定时区。</span><span class="sxs-lookup"><span data-stu-id="a3e3f-107">As a result, an application cannot always assume that a particular time zone is defined and available on a system.</span></span> <span data-ttu-id="a3e3f-108">对于使用时区信息应用程序的许多应用程序来说，第一步是确定所需时区在本地系统上是否可用，或者向用户提供可供选择的时区列表。</span><span class="sxs-lookup"><span data-stu-id="a3e3f-108">The first step for many applications that use time zone information applications is to determine whether required time zones are available on the local system, or to give the user a list of time zones from which to select.</span></span> <span data-ttu-id="a3e3f-109">这要求应用程序枚举本地系统上定义的时区。</span><span class="sxs-lookup"><span data-stu-id="a3e3f-109">This requires that an application enumerate the time zones defined on a local system.</span></span>

> [!NOTE]
> <span data-ttu-id="a3e3f-110">如果应用程序依赖于可能未在本地系统上定义的特定时区, 则该应用程序可以通过序列化和反序列化有关时区的信息来确保其存在。</span><span class="sxs-lookup"><span data-stu-id="a3e3f-110">If an application relies on the presence of a particular time zone that may not be defined on a local system, the application can ensure its presence by serializing and deserializing information about the time zone.</span></span> <span data-ttu-id="a3e3f-111">然后, 可以将时区添加到列表控件, 使应用程序用户可以选择它。</span><span class="sxs-lookup"><span data-stu-id="a3e3f-111">The time zone can then be added to a list control so that the application user can select it.</span></span> <span data-ttu-id="a3e3f-112">有关详细信息，请参阅[如何：将时区保存到嵌入的资源](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) , [以及如何:从嵌入的资源](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)还原时区。</span><span class="sxs-lookup"><span data-stu-id="a3e3f-112">For details, see [How to: Save Time Zones to an Embedded Resource](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) and [How to: Restore time zones from an embedded resource](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md).</span></span>

### <a name="to-enumerate-the-time-zones-present-on-the-local-system"></a><span data-ttu-id="a3e3f-113">枚举本地系统上存在的时区</span><span class="sxs-lookup"><span data-stu-id="a3e3f-113">To enumerate the time zones present on the local system</span></span>

1. <span data-ttu-id="a3e3f-114">调用 <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="a3e3f-114">Call the <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="a3e3f-115">方法返回<xref:System.TimeZoneInfo>对象的泛型<xref:System.Collections.ObjectModel.ReadOnlyCollection%601>集合。</span><span class="sxs-lookup"><span data-stu-id="a3e3f-115">The method returns a generic <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> collection of <xref:System.TimeZoneInfo> objects.</span></span> <span data-ttu-id="a3e3f-116">集合中的项按其<xref:System.TimeZoneInfo.DisplayName%2A>属性进行排序。</span><span class="sxs-lookup"><span data-stu-id="a3e3f-116">The entries in the collection are sorted by their <xref:System.TimeZoneInfo.DisplayName%2A> property.</span></span> <span data-ttu-id="a3e3f-117">例如:</span><span class="sxs-lookup"><span data-stu-id="a3e3f-117">For example:</span></span>

   [!code-csharp[System.TimeZone2.Concepts#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#1)]
   [!code-vb[System.TimeZone2.Concepts#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#1)]

2. <span data-ttu-id="a3e3f-118">使用循环 (在中<xref:System.TimeZoneInfo> C#) 或...,枚举集合中的各个对象`For Each` `foreach``Next`</span><span class="sxs-lookup"><span data-stu-id="a3e3f-118">Enumerate the individual <xref:System.TimeZoneInfo> objects in the collection by using a `foreach` loop (in C#) or a `For Each`…`Next`</span></span> <span data-ttu-id="a3e3f-119">循环 (在 Visual Basic 中), 并对每个对象执行任何必要的处理。</span><span class="sxs-lookup"><span data-stu-id="a3e3f-119">loop (in Visual Basic), and perform any necessary processing on each object.</span></span> <span data-ttu-id="a3e3f-120">例如, 以下代码枚举<xref:System.Collections.ObjectModel.ReadOnlyCollection%601>步骤1中返回的<xref:System.TimeZoneInfo>对象的集合, 并在控制台上列出每个时区的显示名称。</span><span class="sxs-lookup"><span data-stu-id="a3e3f-120">For example, the following code enumerates the <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> collection of <xref:System.TimeZoneInfo> objects returned in step 1 and lists the display name of each time zone on the console.</span></span>

   [!code-csharp[System.TimeZone2.Concepts#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#12)]
   [!code-vb[System.TimeZone2.Concepts#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#12)]

### <a name="to-present-the-user-with-a-list-of-time-zones-present-on-the-local-system"></a><span data-ttu-id="a3e3f-121">向用户提供本地系统上存在的时区列表</span><span class="sxs-lookup"><span data-stu-id="a3e3f-121">To present the user with a list of time zones present on the local system</span></span>

1. <span data-ttu-id="a3e3f-122">调用 <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="a3e3f-122">Call the <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="a3e3f-123">方法返回<xref:System.TimeZoneInfo>对象的泛型<xref:System.Collections.ObjectModel.ReadOnlyCollection%601>集合。</span><span class="sxs-lookup"><span data-stu-id="a3e3f-123">The method returns a generic <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> collection of <xref:System.TimeZoneInfo> objects.</span></span>

2. <span data-ttu-id="a3e3f-124">将步骤1中返回的集合分配给`DataSource` Windows 窗体或 ASP.NET 列表控件的属性。</span><span class="sxs-lookup"><span data-stu-id="a3e3f-124">Assign the collection returned in step 1 to the `DataSource` property of a Windows forms or ASP.NET list control.</span></span>

3. <span data-ttu-id="a3e3f-125">检索用户已选择的对象。<xref:System.TimeZoneInfo></span><span class="sxs-lookup"><span data-stu-id="a3e3f-125">Retrieve the <xref:System.TimeZoneInfo> object that the user has selected.</span></span>

<span data-ttu-id="a3e3f-126">该示例为 Windows 应用程序提供了一个图例。</span><span class="sxs-lookup"><span data-stu-id="a3e3f-126">The example provides an illustration for a Windows application.</span></span>

## <a name="example"></a><span data-ttu-id="a3e3f-127">示例</span><span class="sxs-lookup"><span data-stu-id="a3e3f-127">Example</span></span>

<span data-ttu-id="a3e3f-128">该示例启动一个 Windows 应用程序, 该应用程序在列表框中显示在系统上定义的时区。</span><span class="sxs-lookup"><span data-stu-id="a3e3f-128">The example starts a Windows application that displays the time zones defined on a system in a list box.</span></span> <span data-ttu-id="a3e3f-129">然后, 该示例显示一个对话框, 其中包含用户选定的<xref:System.TimeZoneInfo.DisplayName%2A>时区对象的属性值。</span><span class="sxs-lookup"><span data-stu-id="a3e3f-129">The example then displays a dialog box that contains the value of the <xref:System.TimeZoneInfo.DisplayName%2A> property of the time zone object selected by the user.</span></span>

[!code-csharp[System.TimeZone2.Concepts#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#2)]
[!code-vb[System.TimeZone2.Concepts#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#2)]

<span data-ttu-id="a3e3f-130">大多数列表控件 ( <xref:System.Windows.Forms.ListBox?displayProperty=nameWithType>例如或<xref:System.Web.UI.WebControls.BulletedList?displayProperty=nameWithType>控件) 允许您将对象变量的集合分配给其`DataSource`属性, 只要该集合实现了<xref:System.Collections.IEnumerable>接口。</span><span class="sxs-lookup"><span data-stu-id="a3e3f-130">Most list controls (such as the <xref:System.Windows.Forms.ListBox?displayProperty=nameWithType> or <xref:System.Web.UI.WebControls.BulletedList?displayProperty=nameWithType> control) allow you to assign a collection of object variables to their `DataSource` property as long as that collection implements the <xref:System.Collections.IEnumerable> interface.</span></span> <span data-ttu-id="a3e3f-131">(泛型<xref:System.Collections.ObjectModel.ReadOnlyCollection%601>类实现此功能。)若要在集合中显示单个对象, 控件将调用该对象的`ToString`方法来提取用于表示对象的字符串。</span><span class="sxs-lookup"><span data-stu-id="a3e3f-131">(The generic <xref:System.Collections.ObjectModel.ReadOnlyCollection%601> class does this.) To display an individual object in the collection, the control calls that object's `ToString` method to extract the string that is used to represent the object.</span></span> <span data-ttu-id="a3e3f-132">对于<xref:System.TimeZoneInfo>对象<xref:System.TimeZoneInfo> , 方法返回对象的显示名称 (其<xref:System.TimeZoneInfo.DisplayName%2A>属性的值)。 `ToString`</span><span class="sxs-lookup"><span data-stu-id="a3e3f-132">In the case of <xref:System.TimeZoneInfo> objects, the `ToString` method returns the <xref:System.TimeZoneInfo> object's display name (the value of its <xref:System.TimeZoneInfo.DisplayName%2A> property).</span></span>

> [!NOTE]
> <span data-ttu-id="a3e3f-133">由于列表控件调用对象的`ToString`方法, 因此你可以将<xref:System.TimeZoneInfo>对象的集合分配给控件, 使控件为每个<xref:System.TimeZoneInfo>对象显示有意义的名称, 并检索用户已选择的对象。</span><span class="sxs-lookup"><span data-stu-id="a3e3f-133">Because list controls call an object's `ToString` method, you can assign a collection of <xref:System.TimeZoneInfo> objects to the control, have the control display a meaningful name for each object, and retrieve the <xref:System.TimeZoneInfo> object that the user has selected.</span></span> <span data-ttu-id="a3e3f-134">这样就无需为集合中的每个对象提取字符串, 而是将该字符串分配给一个集合, 该集合将变为分配给`DataSource`控件的属性, 检索用户已选择的字符串, 然后使用此字符串提取对象说明。</span><span class="sxs-lookup"><span data-stu-id="a3e3f-134">This eliminates the need to extract a string for each object in the collection, assign the string to a collection that is in turn assigned to the control's `DataSource` property, retrieve the string the user has selected, and then use this string to extract the object that it describes.</span></span> 

## <a name="compiling-the-code"></a><span data-ttu-id="a3e3f-135">编译代码</span><span class="sxs-lookup"><span data-stu-id="a3e3f-135">Compiling the code</span></span>

<span data-ttu-id="a3e3f-136">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="a3e3f-136">This example requires:</span></span>

- <span data-ttu-id="a3e3f-137">导入以下命名空间:</span><span class="sxs-lookup"><span data-stu-id="a3e3f-137">That the following namespaces be imported:</span></span>

  <span data-ttu-id="a3e3f-138"><xref:System>(在C#代码中)</span><span class="sxs-lookup"><span data-stu-id="a3e3f-138"><xref:System> (in C# code)</span></span>

  <xref:System.Collections.ObjectModel>

## <a name="see-also"></a><span data-ttu-id="a3e3f-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="a3e3f-139">See also</span></span>

- [<span data-ttu-id="a3e3f-140">日期、时间和时区</span><span class="sxs-lookup"><span data-stu-id="a3e3f-140">Dates, times, and time zones</span></span>](../../../docs/standard/datetime/index.md)
- [<span data-ttu-id="a3e3f-141">如何：将时区保存到嵌入的资源</span><span class="sxs-lookup"><span data-stu-id="a3e3f-141">How to: Save time zones to an embedded resource</span></span>](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
- [<span data-ttu-id="a3e3f-142">如何：从嵌入的资源还原时区</span><span class="sxs-lookup"><span data-stu-id="a3e3f-142">How to: Restore time zones from an embedded resource</span></span>](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)

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
# <a name="how-to-enumerate-time-zones-present-on-a-computer"></a>如何：枚举计算机上的时区

若要成功使用指定的时区，需要该时区的相关信息可供系统使用。 Windows XP 和 Windows Vista 操作系统将此信息存储在注册表中。 但是，尽管世界上存在的时区总数非常大，但注册表包含的信息只是其中的一个子集。 此外，注册表本身是一个动态结构，其内容可能发生有意或无意的更改。 因此，应用程序无法保证系统上始终存在已定义且可用的特定时区。 对于使用时区信息应用程序的许多应用程序来说，第一步是确定所需时区在本地系统上是否可用，或者向用户提供可供选择的时区列表。 这要求应用程序枚举本地系统上定义的时区。

> [!NOTE]
> 如果应用程序依赖于可能未在本地系统上定义的特定时区, 则该应用程序可以通过序列化和反序列化有关时区的信息来确保其存在。 然后, 可以将时区添加到列表控件, 使应用程序用户可以选择它。 有关详细信息，请参阅[如何：将时区保存到嵌入的资源](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) , [以及如何:从嵌入的资源](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)还原时区。

### <a name="to-enumerate-the-time-zones-present-on-the-local-system"></a>枚举本地系统上存在的时区

1. 调用 <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> 方法。 方法返回<xref:System.TimeZoneInfo>对象的泛型<xref:System.Collections.ObjectModel.ReadOnlyCollection%601>集合。 集合中的项按其<xref:System.TimeZoneInfo.DisplayName%2A>属性进行排序。 例如:

   [!code-csharp[System.TimeZone2.Concepts#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#1)]
   [!code-vb[System.TimeZone2.Concepts#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#1)]

2. 使用循环 (在中<xref:System.TimeZoneInfo> C#) 或...,枚举集合中的各个对象`For Each` `foreach``Next` 循环 (在 Visual Basic 中), 并对每个对象执行任何必要的处理。 例如, 以下代码枚举<xref:System.Collections.ObjectModel.ReadOnlyCollection%601>步骤1中返回的<xref:System.TimeZoneInfo>对象的集合, 并在控制台上列出每个时区的显示名称。

   [!code-csharp[System.TimeZone2.Concepts#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#12)]
   [!code-vb[System.TimeZone2.Concepts#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#12)]

### <a name="to-present-the-user-with-a-list-of-time-zones-present-on-the-local-system"></a>向用户提供本地系统上存在的时区列表

1. 调用 <xref:System.TimeZoneInfo.GetSystemTimeZones%2A?displayProperty=nameWithType> 方法。 方法返回<xref:System.TimeZoneInfo>对象的泛型<xref:System.Collections.ObjectModel.ReadOnlyCollection%601>集合。

2. 将步骤1中返回的集合分配给`DataSource` Windows 窗体或 ASP.NET 列表控件的属性。

3. 检索用户已选择的对象。<xref:System.TimeZoneInfo>

该示例为 Windows 应用程序提供了一个图例。

## <a name="example"></a>示例

该示例启动一个 Windows 应用程序, 该应用程序在列表框中显示在系统上定义的时区。 然后, 该示例显示一个对话框, 其中包含用户选定的<xref:System.TimeZoneInfo.DisplayName%2A>时区对象的属性值。

[!code-csharp[System.TimeZone2.Concepts#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#2)]
[!code-vb[System.TimeZone2.Concepts#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#2)]

大多数列表控件 ( <xref:System.Windows.Forms.ListBox?displayProperty=nameWithType>例如或<xref:System.Web.UI.WebControls.BulletedList?displayProperty=nameWithType>控件) 允许您将对象变量的集合分配给其`DataSource`属性, 只要该集合实现了<xref:System.Collections.IEnumerable>接口。 (泛型<xref:System.Collections.ObjectModel.ReadOnlyCollection%601>类实现此功能。)若要在集合中显示单个对象, 控件将调用该对象的`ToString`方法来提取用于表示对象的字符串。 对于<xref:System.TimeZoneInfo>对象<xref:System.TimeZoneInfo> , 方法返回对象的显示名称 (其<xref:System.TimeZoneInfo.DisplayName%2A>属性的值)。 `ToString`

> [!NOTE]
> 由于列表控件调用对象的`ToString`方法, 因此你可以将<xref:System.TimeZoneInfo>对象的集合分配给控件, 使控件为每个<xref:System.TimeZoneInfo>对象显示有意义的名称, 并检索用户已选择的对象。 这样就无需为集合中的每个对象提取字符串, 而是将该字符串分配给一个集合, 该集合将变为分配给`DataSource`控件的属性, 检索用户已选择的字符串, 然后使用此字符串提取对象说明。 

## <a name="compiling-the-code"></a>编译代码

此示例需要：

- 导入以下命名空间:

  <xref:System>(在C#代码中)

  <xref:System.Collections.ObjectModel>

## <a name="see-also"></a>请参阅

- [日期、时间和时区](../../../docs/standard/datetime/index.md)
- [如何：将时区保存到嵌入的资源](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
- [如何：从嵌入的资源还原时区](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)

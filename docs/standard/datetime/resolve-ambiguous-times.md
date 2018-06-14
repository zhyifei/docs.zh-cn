---
title: 如何： 解决不明确的时间
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], ambiguous time
- ambiguous time [.NET Framework]
ms.assetid: 2cf5fb25-492c-4875-9245-98cac8348e97
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a92081a164d15e5150c582b37c6c688cd15e619e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571194"
---
# <a name="how-to-resolve-ambiguous-times"></a>如何： 解决不明确的时间

不明确时间是指映射到多个协调世界时 (UTC) 的时间。 在向后调整时钟时间时，例如从时区的夏令时调整到标准时间这段转换期间，便会出现不明确时间。 在处理不明确时间时，可执行以下任一操作：

* 假设一下时间如何映射到 UTC。 例如，可以假定不明确时间始终以时区的标准时间表示。

* 如果不明确时间是用户输入的数据项，则可以让用户自行解决。

本主题说明如何解决由不明确的时间，前提是它表示时区的标准时间。

### <a name="to-map-an-ambiguous-time-to-a-time-zones-standard-time"></a>将不明确时间映射到时区的标准时间

1. 调用<xref:System.TimeZoneInfo.IsAmbiguousTime%2A>方法来确定时间是否不明确。

2. 如果所不明确的时间，减去的时间<xref:System.TimeSpan>对象返回的时区的<xref:System.TimeZoneInfo.BaseUtcOffset%2A>属性。

3. 调用`static`(`Shared`在 Visual Basic.NET)<xref:System.DateTime.SpecifyKind%2A>方法以设置的 UTC 日期和时间值的<xref:System.DateTime.Kind%2A>属性<xref:System.DateTimeKind.Utc?displayProperty=nameWithType>。

## <a name="example"></a>示例

下面的示例演示如何将明确的时间转换为 UTC，前提是它表示本地时区的标准时间。

[!code-csharp[System.TimeZone2.Concepts#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#10)]
[!code-vb[System.TimeZone2.Concepts#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#10)]

此示例由一个名为方法组成`ResolveAmbiguousTime`，它确定是否<xref:System.DateTime>传递给它的值是不明确。 如果值是不明确的该方法返回<xref:System.DateTime>值，该值表示相应的 UTC 时间。 该方法减去的本地时区的值来处理此转换<xref:System.TimeZoneInfo.BaseUtcOffset%2A>属性从本地时间。

通常，由不明确的时间调用<xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A>方法来检索其中的数组<xref:System.TimeSpan>对象，其中包含不明确的时间可能的 UTC 偏移量。 但是，本示例建立在一个大胆假设之上，即不明确时间始终映射到时区的标准时间。 <xref:System.TimeZoneInfo.BaseUtcOffset%2A>属性返回 UTC 和时区的标准时间之间的偏移量。

在此示例中，对本地时区的所有引用都都通过<xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType>属性; 区域永远不会分配给对象变量的本地时间。 这是建议的做法，因为调用<xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType>方法失效的本地时区分配给任何对象。

## <a name="compiling-the-code"></a>编译代码

此示例需要：

* 对 System.Core.dll 的引用无法添加到项目。

* <xref:System>命名空间导入`using`语句 （C# 代码中需要）。

## <a name="see-also"></a>请参阅

[日期、 时间和时区](../../../docs/standard/datetime/index.md)
[How to： 让用户解决不明确的时间](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)

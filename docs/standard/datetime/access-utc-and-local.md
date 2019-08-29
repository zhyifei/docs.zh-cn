---
title: 如何：访问预定义 UTC 和本地时区对象
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], local
- predefined time zones
- UTC times, predefined
- local time zone access
- time zones [.NET Framework], retrieving
- time zones [.NET Framework], UTC
ms.assetid: 961fb70b-83f0-4dab-a042-cb5fcd817cf5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8aa19118ce0837b9ce0eb523f3e086fcbcecb9e8
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2019
ms.locfileid: "70106555"
---
# <a name="how-to-access-the-predefined-utc-and-local-time-zone-objects"></a>如何：访问预定义 UTC 和本地时区对象

类提供了两个属性<xref:System.TimeZoneInfo.Utc%2A> : <xref:System.TimeZoneInfo.Local%2A>和, 可让你的代码访问预定义的时区对象。 <xref:System.TimeZoneInfo> 本主题介绍如何访问这些属性返回的 <xref:System.TimeZoneInfo> 对象。

### <a name="to-access-the-coordinated-universal-time-utc-timezoneinfo-object"></a>访问协调世界时 (UTC) TimeZoneInfo 对象

1. `static`使用 (`Shared`在 Visual Basic) <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType>属性访问协调世界时。

2. 不是将属性<xref:System.TimeZoneInfo>返回的对象分配给对象变量, 而是继续<xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType>通过属性访问协调世界时。

### <a name="to-access-the-local-time-zone"></a>访问本地时区

1. `static`使用 (`Shared`在 Visual Basic) <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType>属性访问本地系统时区。

2. 不是将属性<xref:System.TimeZoneInfo>返回的对象分配给对象变量, 而是继续<xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType>通过属性访问本地时区。

## <a name="example"></a>示例

下面的代码使用 <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> 和 <xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType> 属性转换美国和加拿大东部标准时区的时间，并将时区名称显示到控制台。

[!code-csharp[System.TimeZone2.Concepts#13](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#13)]
[!code-vb[System.TimeZone2.Concepts#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#13)]

应始终通过<xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType>属性访问本地时区, 而不是将本地时区分配<xref:System.TimeZoneInfo>给对象变量。 同样, 应始终通过<xref:System.TimeZoneInfo.Utc%2A?displayProperty=nameWithType>属性访问协调世界时, 而不是将 UTC 时区分配<xref:System.TimeZoneInfo>给对象变量。 这可防止<xref:System.TimeZoneInfo>对象变量被调用<xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=nameWithType>方法无效。

## <a name="compiling-the-code"></a>编译代码

此示例需要：

- 该命名空间将`using`与语句一起导入 (在C#代码中是必需的)。 <xref:System>

## <a name="see-also"></a>请参阅

- [日期、时间和时区](../../../docs/standard/datetime/index.md)
- [查找本地系统上定义的时区](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)
- [如何：实例化 TimeZoneInfo 对象](../../../docs/standard/datetime/instantiate-time-zone-info.md)

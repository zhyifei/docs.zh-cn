---
title: "日期、时间和时区 | Microsoft Docs"
ms.custom: ""
ms.date: "04/10/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "日期和时间数据 [.NET Framework]"
  - "时间 [.NET Framework], 时区"
  - "时区对象 [.NET Framework]"
  - "时区 [.NET Framework]"
  - "时间 [.NET Framework], 时区"
ms.assetid: 295c16e0-641b-4771-94b3-39c1ffa98c13
caps.latest.revision: 22
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 22
---
# 日期、时间和时区
除了基本的 <xref:System.DateTime> 结构外，[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 还提供了下列类来支持对时区的处理：  
  
-   <xref:System.TimeZone>  
  
     使用此类可以处理系统的本地时区和协调世界时 \(UTC\) 区域。<xref:System.TimeZone> 类的大部分功能已由 <xref:System.TimeZoneInfo> 类取代。  
  
-   <xref:System.TimeZoneInfo>  
  
     使用此类可以处理系统上预定义的任何时区、创建新时区，以及轻松地将日期和时间从一个时区转换到另一个时区。  在新开发过程中，请使用 <xref:System.TimeZoneInfo> 类代替 <xref:System.TimeZone> 类。  
  
-   <xref:System.DateTimeOffset>  
  
     使用此结构可以处理 UTC 偏移量（即差值）已知的日期和时间。  <xref:System.DateTimeOffset> 结构将日期和时间值与该时间的 UTC 偏移量组合在一起。  由于它与 UTC 存在这种关系，因此单个日期和时间值可以明确地标识单个时间点。  这就使得 <xref:System.DateTimeOffset> 值比 <xref:System.DateTime> 值在不同计算机之间具有更好的可迁移性。  
  
 本节文档提供处理时区以及创建时区识别应用程序（可将日期和时间从一个时区转换到另一个时区）时所需的信息。  
  
## 本节内容  
 [时区概述](../../../docs/standard/datetime/time-zone-overview.md)  
 讨论创建时区识别应用程序中涉及的术语、概念和问题。  
  
 [在 DateTime、DateTimeOffset、TimeSpan 和 TimeZoneInfo 之间进行选择](../../../docs/standard/datetime/choosing-between-datetime.md)  
 讨论在处理日期和时间数据时应于何时使用 <xref:System.DateTime>、<xref:System.DateTimeOffset> 和 <xref:System.TimeZoneInfo> 类型。  
  
 [查找在本地系统上定义的时区](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)  
 描述如何枚举本地系统上的时区。  
  
 [如何：枚举计算机上存在的时区](../../../docs/standard/datetime/enumerate-time-zones.md)  
 提供枚举计算机注册表中定义的时区的示例，以及允许用户从列表中选择预定义时区的示例。  
  
 [如何：访问预定义的 UTC 和本地时区对象](../../../docs/standard/datetime/access-utc-and-local.md)  
 描述如何访问协调世界时和本地时区。  
  
 [如何：实例化 TimeZoneInfo 对象](../../../docs/standard/datetime/instantiate-time-zone-info.md)  
 描述如何实例化本地系统注册表中的 <xref:System.TimeZoneInfo> 对象。  
  
 [实例化 DateTimeOffset 对象](../../../docs/standard/datetime/instantiating-a-datetimeoffset-object.md)  
 讨论如何实例化 <xref:System.DateTimeOffset> 对象以及如何将 <xref:System.DateTime> 值转换为 <xref:System.DateTimeOffset> 值。  
  
 [如何：创建不带调整规则的时区](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)  
 描述如何创建不支持与夏令时来回转换的自定义时区。  
  
 [如何：创建带有调整规则的时区](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)  
 描述如何创建支持与夏令时进行一种或多种转换的自定义时区。  
  
 [保存和还原时区](../../../docs/standard/datetime/saving-and-restoring-time-zones.md)  
 描述对序列化和反序列化时区数据的 <xref:System.TimeZoneInfo> 支持，并阐释可以使用这些功能的某些方案。  
  
 [如何：将时区保存到嵌入的资源中](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)  
 描述如何创建自定义时区并将其信息保存在资源文件中。  
  
 [如何：从嵌入的资源还原时区](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)  
 描述如何实例化已保存到嵌入的资源文件中的自定义时区。  
  
 [使用日期和时间执行算术运算](../../../docs/standard/datetime/performing-arithmetic-operations.md)  
 讨论对 <xref:System.DateTime> 和 <xref:System.DateTimeOffset> 值执行加、减和比较运算时涉及的问题。  
  
 [如何：在日期和时间算法中使用时区](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)  
 讨论如何执行反映时区调整规则的日期和时间运算。  
  
 [在 DateTime 与 DateTimeOffset 之间进行转换](../../../docs/standard/datetime/converting-between-datetime-and-offset.md)  
 描述如何在 <xref:System.DateTime> 和 <xref:System.DateTimeOffset> 值之间进行转换。  
  
 [在不同时区之间转换时间](../../../docs/standard/datetime/converting-between-time-zones.md)  
 描述如何将时间从一个时区转换到另一个时区。  
  
 [如何：解决不明确的时间](../../../docs/standard/datetime/resolve-ambiguous-times.md)  
 描述如何通过将不明确的时间映射到时区的标准时间来解析它。  
  
 [如何：让用户解决不明确的时间](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)  
 描述如何让用户确定不明确的本地时间与协调世界时之间的映射。  
  
## 参考  
 <xref:System.TimeZoneInfo?displayProperty=fullName>
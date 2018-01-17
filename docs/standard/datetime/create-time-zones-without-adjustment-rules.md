---
title: "如何： 创建不带调整规则的时区"
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
- time zones [.NET Framework], adjustment rule
- time zones [.NET Framework], creating
- adjustment rule [.NET Framework]
ms.assetid: a6af8647-7893-4f29-95a9-d94c65a6e8dd
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 14c5e02ce5af03d063260af19e9dd1a970a93ab6
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-create-time-zones-without-adjustment-rules"></a>如何： 创建不带调整规则的时区

应用程序所需的精确的时区信息可能不存在特定的系统上有几个原因：

* 永远不会在本地系统注册表中定义该时区。

* 已修改或从注册表中删除有关时区数据。

* 时区存在，但不是具有特定的历史时期时区调整的准确信息。

在这些情况下，你可以调用<xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>方法用来定义应用程序所需的时区。 此方法的重载可用于创建使用或不带调整规则的时区。 如果时区支持夏令制，则可以定义与任一固定或浮动的调整规则的调整。 (有关这些术语的定义，请参阅中的"时区术语"一节[时区概述](../../../docs/standard/datetime/time-zone-overview.md)。)

> [!IMPORTANT]
> 通过调用创建的自定义时区<xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>方法不会添加到注册表。 相反，它们可以仅通过返回的对象引用<xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>方法调用。

本主题演示如何创建不带调整规则的时区。 若要创建支持夏时制调整规则的时区，请参阅[如何： 创建带有调整规则的时区](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)。

### <a name="to-create-a-time-zone-without-adjustment-rules"></a>若要创建不带调整规则的时区

1. 定义时区的显示名称。

   显示名称应遵循标准格式时区偏移量从协调世界时 (UTC) 括在括号中后, 跟一个字符串，标识一个或多个城市中时区，或一个或多个 cou 时区ntries 或时区中的区域。

2. 定义时区的标准时间的名称。 通常情况下，此字符串还用作时区的标识符。

3. 如果你想要使用比时区的标准名称的不同标识符，定义的时区标识符。

4. 实例化<xref:System.TimeSpan>对象，用于定义相对于 UTC 的时区偏移量。 时间晚于 UTC 的时区具有负的偏移量。 时间早于 UTC 的时区有负的偏移量。

5. 调用<xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%29?displayProperty=nameWithType>方法可实例化新的时区。

## <a name="example"></a>示例

下面的示例定义莫南极洲，没有调整规则的自定义时区。

[!code-csharp[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#1)]
[!code-vb[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#1)]

分配给字符串<xref:System.TimeZoneInfo.DisplayName%2A>属性应遵循标准格式，相对于 UTC 的时区偏移量跟时区的友好说明。

## <a name="compiling-the-code"></a>编译代码

此示例需要：

* 对 System.Core.dll 的引用无法添加到项目。

* 将导入以下命名空间：

  [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
  [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]

## <a name="see-also"></a>请参阅

[日期、 时间和时区](../../../docs/standard/datetime/index.md)
[时区概述](../../../docs/standard/datetime/time-zone-overview.md)
[如何： 创建带有调整规则的时区](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)

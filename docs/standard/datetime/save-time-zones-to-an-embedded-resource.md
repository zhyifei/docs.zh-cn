---
title: 如何： 将时区保存到嵌入的资源
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], saving
- time zone objects [.NET Framework], serializing
- time zone objects [.NET Framework], saving
ms.assetid: 3c96d83a-a057-4496-abb0-8f4b12712558
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4dd7e6db78b76d737cb4646c2fad79d96fb60aee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-save-time-zones-to-an-embedded-resource"></a>如何： 将时区保存到嵌入的资源

时区感知的应用程序通常需要特定时区的状态。 但是，因为单个可用性<xref:System.TimeZoneInfo>对象依赖于本地系统注册表中存储信息，即使通常可用的时区可能不存在。 此外，有关自定义时区信息使用的实例化<xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>方法不会存储与注册表中的其他时区信息。 若要确保这些时区提供了在需要时，你可以通过序列化，将其保存，并在以后还原它们进行反序列化它们。

通常情况下，序列化<xref:System.TimeZoneInfo>对象出现于时区识别应用程序。 具体取决于用来保存序列化数据存储区<xref:System.TimeZoneInfo>对象，作为 （例如，当数据存储在注册表的应用程序密钥时），安装程序或安装例程的一部分或作为运行实用程序例程的一部分，时区数据可能会进行序列化之前 （例如，当序列化的数据存储在一个.NET XML 资源 (.resx) 文件） 编译最终应用程序。

除了进行编译的应用程序资源文件，多个其他数据存储可以用于时区信息。 其中包括：

* 注册表中。 请注意应用程序应使用其自己的应用程序项的子项来存储自定义时区数据，而不是无需使用 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Time 区域的子项。

* 配置文件。

* 其他系统文件。

### <a name="to-save-a-time-zone-by-serializing-it-to-a-resx-file"></a>若要通过序列化到.resx 文件中保存时区

1. 检索现有的时区，或者创建新的时区。

   若要检索现有的时区，请参阅[如何： 访问预定义的 UTC 和当地时间区域对象](../../../docs/standard/datetime/access-utc-and-local.md)和[如何： 实例化 TimeZoneInfo 对象](../../../docs/standard/datetime/instantiate-time-zone-info.md)。

   若要创建新的时区，调用的重载之一<xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>方法。 有关详细信息，请参阅[如何： 创建不带调整规则的时区](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)和[如何： 创建带有调整规则的时区](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)。

2. 调用<xref:System.TimeZoneInfo.ToSerializedString%2A>方法来创建包含时区的数据的字符串。

3. 实例化<xref:System.IO.StreamWriter>对象提供的名称和 （可选） 的.resx 文件的路径<xref:System.IO.StreamWriter>类构造函数。

4. 实例化<xref:System.Resources.ResXResourceWriter>通过传递的对象<xref:System.IO.StreamWriter>对象传递给<xref:System.Resources.ResXResourceWriter>类构造函数。

5. 序列化到的字符串传递传递时区<xref:System.Resources.ResXResourceWriter.AddResource%2A?displayProperty=nameWithType>方法。

6. 调用 <xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType> 方法。

7. 调用 <xref:System.Resources.ResXResourceWriter.Close%2A?displayProperty=nameWithType> 方法。

8. 关闭<xref:System.IO.StreamWriter>对象通过调用其<xref:System.IO.StreamWriter.Close%2A>方法。

9. 将生成的.resx 文件添加到应用程序的 Visual Studio 项目。

10. 使用**属性**窗口在 Visual Studio 中，请确保.resx 文件**生成操作**属性设置为**嵌入的资源**。

## <a name="example"></a>示例

下面的示例序列化<xref:System.TimeZoneInfo>表示中部标准时间的对象和一个<xref:System.TimeZoneInfo>到名为 SerializedTimeZones.resx 的.NET XML 资源文件中表示的 Palmer 工作站、 南极洲时间的对象。 在注册表中; 通常定义中部标准时间Palmer 工作站、 南极洲是自定义时区。

[!code-csharp[TimeZone2.Serialization#1](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#1)]
[!code-vb[TimeZone2.Serialization#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#1)]

此示例将序列化为<xref:System.TimeZoneInfo>对象，以便它们可在资源文件在编译时。

因为<xref:System.Resources.ResXResourceWriter.Generate%2A?displayProperty=nameWithType>方法将完整的标头信息添加到.NET XML 资源文件，所以不能用来将资源添加到现有文件。 通过检查 SerializedTimeZones.resx 文件，该示例处理这，并且，如果存在，而不存储它的所有资源两个都序列泛型时区<xref:System.Collections.Generic.Dictionary%602>对象。 现有文件被删除，并且现有资源添加到新的 SerializedTimeZones.resx 文件。 序列化的时区数据也添加到此文件中。

密钥 (或**名称**) 的资源的字段不应包含嵌入的空格。 <xref:System.String.Replace%28System.String%2CSystem.String%29>方法调用之前分配给资源文件，它们所在的时区标识符中移除所有嵌入的空格。

## <a name="compiling-the-code"></a>编译代码

此示例需要：

* 对 System.Windows.Forms.dll 和 System.Core.dll 的引用无法添加到项目。

* 将导入以下命名空间：

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a>请参阅

[日期、 时间和时区](../../../docs/standard/datetime/index.md)
[时区概述](../../../docs/standard/datetime/time-zone-overview.md)
[如何： 从嵌入的资源还原时区](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)

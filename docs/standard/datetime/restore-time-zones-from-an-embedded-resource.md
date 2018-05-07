---
title: 如何： 从嵌入的资源还原时区
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], deserializing
- time zones [.NET Framework], restoring
ms.assetid: 6b7b4de9-da07-47e3-8f4c-823f81798ee7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 31dd785c419d9a8e11eb23deabd2dfa71c4d6e9c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-restore-time-zones-from-an-embedded-resource"></a>如何： 从嵌入的资源还原时区

本主题介绍如何还原已保存的资源文件中的时区。 有关信息和有关保存时区的说明，请参阅[如何： 将时区保存到嵌入的资源](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)。

### <a name="to-deserialize-a-timezoneinfo-object-from-an-embedded-resource"></a>若要反序列化中嵌入的资源的 TimeZoneInfo 对象

1. 如果要检索时区不是自定义的时区，尝试通过使用下面实例<xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>方法。

2. 实例化<xref:System.Resources.ResourceManager>通过将传递对包含资源文件的程序集的引用以及嵌入式的资源文件的完全限定的名称的对象。

   如果无法确定嵌入式的资源文件的完全限定的名称，使用[Ildasm.exe （IL 反汇编程序）](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)来检查程序集的清单。 `.mresource`条目标识的资源。 在示例中，该资源的完全限定的名称是`SerializeTimeZoneData.SerializedTimeZones`。

   如果包含时区实例化代码相同的程序集中嵌入资源文件，则可以通过调用来检索对它的引用`static`(`Shared`在 Visual Basic 中)<xref:System.Reflection.Assembly.GetExecutingAssembly%2A>方法。

3. 如果调用<xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>方法失败，或如果要实例化自定义的时区，检索一个字符串，通过调用包含序列化的时区<xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType>方法。

4. 通过调用时区数据反序列化<xref:System.TimeZoneInfo.FromSerializedString%2A>方法。

## <a name="example"></a>示例

下面的示例进行反序列化<xref:System.TimeZoneInfo>嵌入.NET XML 资源文件中存储的对象。

[!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
[!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]

此代码演示异常处理来确保<xref:System.TimeZoneInfo>应用程序所需的对象是否存在。 它首先尝试实例化<xref:System.TimeZoneInfo>对象通过检索从注册表使用<xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>方法。 如果时区不能实例化，此代码将检索它从嵌入的资源文件。

因为自定义时区的数据 (通过使用实例化时区<xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>方法) 不存储在注册表中，代码不调用<xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A>来实例化 Palmer，南极洲时区。 相反，它立即查找到嵌入的资源文件，以检索一个字符串，包含时区的数据，然后才能调用<xref:System.TimeZoneInfo.FromSerializedString%2A>方法。

## <a name="compiling-the-code"></a>编译代码

此示例需要：

* 对 System.Windows.Forms.dll 和 System.Core.dll 的引用无法添加到项目。

* 将导入以下命名空间：

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a>请参阅

[日期、 时间和时区](../../../docs/standard/datetime/index.md)
[时区概述](../../../docs/standard/datetime/time-zone-overview.md)
[如何： 将时区保存到嵌入的资源](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)

---
title: 如何确定.NET 标准对象是否可序列化
description: 演示如何确定在运行时是否可以序列化.NET Standard 的类型。
ms.date: 10/20/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 196e99ab1f1a0baae53c6a1dc295b135e36fbfe0
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2018
ms.locfileid: "45675608"
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a>如何确定.NET 标准对象是否可序列化

.NET Standard 是标准的定义的类型和特定于该版本符合的.NET 实现必须存在的成员的规范。 但是，.NET Standard 未定义是否可序列化类型。 在.NET Standard 库中定义的类型不会标记有<xref:System.SerializableAttribute>属性。 相反，特定的.NET 实现，如.NET Framework 和.NET Core 是可用来确定特定类型是否为可序列化。  

如果你面向的.NET Standard 开发了一个库，你的库可供任何支持.NET Standard 的.NET 实现。 这意味着，您无法事先知道特定类型是否是可序列化;仅可以确定是否可序列化在运行时使用它。

您可以确定某个对象是否可序列化在运行时检索的值来<xref:System.Type.IsSerializable>属性的<xref:System.Type>对象，表示该对象的类型。 下面的示例提供了一种实现。 它定义`IsSerializable(Object)`扩展方法，该值指示是否有任何<xref:System.Object>实例可序列化。

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

然后可以将任何对象传递给该方法以确定它是否可以进行序列化和上当前的.NET 实现中，将如以下示例所示的反序列化：

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

## <a name="see-also"></a>请参阅

- [二进制序列化](binary-serialization.md)
- <xref:System.SerializableAttribute?displayProperty=nameWithType>
- <xref:System.Type.IsSerializable?displayProperty=nameWithType>

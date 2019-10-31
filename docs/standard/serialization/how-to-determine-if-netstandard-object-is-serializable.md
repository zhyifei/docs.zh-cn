---
title: 如何确定 .NET Standard 对象是否可以序列化
description: 演示如何在运行时确定是否可以序列化 .NET Standard 类型。
ms.date: 10/20/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
ms.openlocfilehash: 87bf863b158fe3b2c03c7a6d23462bc2aabf9966
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73106622"
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a>如何确定 .NET Standard 对象是否可以序列化

.NET Standard 是一种规范，用于定义符合该标准版本的特定 .NET 实现上必须存在的类型和成员。 但 .NET Standard 不会定义某个类型是否可序列化。 .NET Standard 库中定义的类型未标记 <xref:System.SerializableAttribute> 特性。 具体的 .NET 实现（如 .NET Framework 和 .NET Core）可随意确定特定类型是否可序列化。 

如果你已开发了面向 .NET Standard 的库，则支持 .NET Standard 的任何 .NET 实现都可以使用你的库。 这意味着你不会提前知道特定类型是否可序列化;只能在运行时确定它是否可序列化。

可以通过检索表示对象类型的 <xref:System.Type> 对象的 <xref:System.Type.IsSerializable> 属性的值，来确定对象在运行时是否可以序列化。 下面的示例提供了一个实现。 它定义了一个 `IsSerializable(Object)` 扩展方法，用于指示是否可以序列化任何 <xref:System.Object> 实例。

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

然后，可以将任何对象传递给方法，以确定是否可以在当前 .NET 实现上对其进行序列化和反序列化，如下例所示：

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

## <a name="see-also"></a>请参阅

- [二进制序列化](binary-serialization.md)
- <xref:System.SerializableAttribute?displayProperty=nameWithType>
- <xref:System.Type.IsSerializable?displayProperty=nameWithType>

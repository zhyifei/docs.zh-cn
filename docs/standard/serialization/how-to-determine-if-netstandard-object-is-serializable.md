---
title: 如何确定 .NET Standard 对象是否可以序列化
description: 演示如何确定在运行时是否可以序列化.NET Standard 的类型。
ms.date: 10/20/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
ms.openlocfilehash: 4037dee36aeb619eb2757016904fd877158e57cf
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159892"
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a>如何确定 .NET Standard 对象是否可以序列化

.NET Standard 是标准的定义的类型和特定于该版本符合的.NET 实现必须存在的成员的规范。 但是，.NET Standard 未定义是否可序列化类型。 .NET Standard 库中定义的类型未标记 <xref:System.SerializableAttribute> 特性。 相反，特定的.NET 实现，如.NET Framework 和.NET Core 是可用来确定特定类型是否为可序列化。

如果你面向的.NET Standard 开发了一个库，你的库可供任何支持.NET Standard 的.NET 实现。 这意味着你不会提前知道特定类型是否可序列化;只能在运行时确定它是否可序列化。

可以通过检索表示对象类型的 <xref:System.Type> 对象的 <xref:System.Type.IsSerializable> 属性的值，来确定对象在运行时是否可以序列化。 下面的示例提供了一个实现。 它定义了一个 `IsSerializable(Object)` 扩展方法，用于指示是否可以序列化任何 <xref:System.Object> 实例。

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

然后，可以将任何对象传递给方法，以确定是否可以在当前 .NET 实现上对其进行序列化和反序列化，如下例所示：

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

## <a name="see-also"></a>另请参阅

- [二进制序列化](binary-serialization.md)
- <xref:System.SerializableAttribute?displayProperty=nameWithType>
- <xref:System.Type.IsSerializable?displayProperty=nameWithType>

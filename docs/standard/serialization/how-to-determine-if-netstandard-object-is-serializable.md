---
title: "如何： 确定是否可序列化的标准.NET 对象"
description: "演示如何确定在运行时是否可以序列化.NET 标准的类型。"
ms.custom: 
ms.date: 10/20/2017
ms.prod: .net
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 7c44e350ad4e561f03bf6c598172058a0a9ca41e
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a>如何： 确定是否可序列化的标准.NET 对象

.NET 标准是标准的定义的类型和特定于该版本符合的.NET 实现必须存在的成员的规范。 但是，.NET 标准未定义是否可序列化类型。 在.NET 标准库中定义的类型不会标记有<xref:System.SerializableAttribute>属性。 相反，特定的.NET 实现，如.NET Framework 和.NET 核心是可用来确定特定类型是否为可序列化。 

如果你面向的.NET 标准开发了一个库，你的库可供任何支持.NET 标准的.NET 实现。 这意味着，您无法事先知道特定类型是否是可序列化;你可以仅确定它是否是可序列化在运行时。

你可以确定对象是否可序列化在运行时检索的值的<xref:System.Type.IsSerializable>属性<xref:System.Type>对象，表示该对象的类型。 下面的示例提供一个实现。 它定义`IsSerializable(Object)`扩展方法，该值指示是否有任何<xref:System.Object>可以序列化实例。

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

然后可以将任何对象传递给该方法以确定是否可序列化和它上当前的.NET 实现中，将如以下示例所示的反序列化：

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

# <a name="see-also"></a>请参阅

[二进制序列化](binary-serialization.md)   
<xref:System.SerializableAttribute?displayProperty=fullName>    
<xref:System.Type.IsSerializable?displayProperty=nameWithType>   

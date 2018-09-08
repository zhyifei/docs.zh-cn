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
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44207663"
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a><span data-ttu-id="89607-103">如何确定.NET 标准对象是否可序列化</span><span class="sxs-lookup"><span data-stu-id="89607-103">How to determine if a .NET Standard object is serializable</span></span>

<span data-ttu-id="89607-104">.NET Standard 是标准的定义的类型和特定于该版本符合的.NET 实现必须存在的成员的规范。</span><span class="sxs-lookup"><span data-stu-id="89607-104">The .NET Standard is a specification that defines the types and members that must be present on specific .NET implementations that conform to that version of the standard.</span></span> <span data-ttu-id="89607-105">但是，.NET Standard 未定义是否可序列化类型。</span><span class="sxs-lookup"><span data-stu-id="89607-105">However, the .NET Standard does not define whether a type is serializable.</span></span> <span data-ttu-id="89607-106">在.NET Standard 库中定义的类型不会标记有<xref:System.SerializableAttribute>属性。</span><span class="sxs-lookup"><span data-stu-id="89607-106">The types defined in the .NET Standard Library are not marked with the <xref:System.SerializableAttribute> attribute.</span></span> <span data-ttu-id="89607-107">相反，特定的.NET 实现，如.NET Framework 和.NET Core 是可用来确定特定类型是否为可序列化。 </span><span class="sxs-lookup"><span data-stu-id="89607-107">Instead, specific .NET implementations, such as the .NET Framework and .NET Core, are free to determine whether a particular type is serializable.</span></span> 

<span data-ttu-id="89607-108">如果你面向的.NET Standard 开发了一个库，你的库可供任何支持.NET Standard 的.NET 实现。</span><span class="sxs-lookup"><span data-stu-id="89607-108">If you've developed a library that targets the .NET Standard, your library can be consumed by any .NET implementation that supports the .NET Standard.</span></span> <span data-ttu-id="89607-109">这意味着，您无法事先知道特定类型是否是可序列化;仅可以确定是否可序列化在运行时使用它。</span><span class="sxs-lookup"><span data-stu-id="89607-109">This means that you cannot know in advance whether a particular type is serializable; you can only determine whether it is serializable at run time.</span></span>

<span data-ttu-id="89607-110">您可以确定某个对象是否可序列化在运行时检索的值来<xref:System.Type.IsSerializable>属性的<xref:System.Type>对象，表示该对象的类型。</span><span class="sxs-lookup"><span data-stu-id="89607-110">You can determine whether an object is serializable at runtime by retrieving the value of the <xref:System.Type.IsSerializable> property of a <xref:System.Type> object that represents that object's type.</span></span> <span data-ttu-id="89607-111">下面的示例提供了一种实现。</span><span class="sxs-lookup"><span data-stu-id="89607-111">The following example provides one implementation.</span></span> <span data-ttu-id="89607-112">它定义`IsSerializable(Object)`扩展方法，该值指示是否有任何<xref:System.Object>实例可序列化。</span><span class="sxs-lookup"><span data-stu-id="89607-112">It defines an `IsSerializable(Object)` extension method that indicates whether any <xref:System.Object> instance can be serialized.</span></span>

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

<span data-ttu-id="89607-113">然后可以将任何对象传递给该方法以确定它是否可以进行序列化和上当前的.NET 实现中，将如以下示例所示的反序列化：</span><span class="sxs-lookup"><span data-stu-id="89607-113">You can then pass any object to the method to determine whether it can be serialized and deserialized on the current .NET implementation, as the following example shows:</span></span>

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

## <a name="see-also"></a><span data-ttu-id="89607-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="89607-114">See also</span></span>

- [<span data-ttu-id="89607-115">二进制序列化</span><span class="sxs-lookup"><span data-stu-id="89607-115">Binary serialization</span></span>](binary-serialization.md)
- <xref:System.SerializableAttribute?displayProperty=nameWithType>
- <xref:System.Type.IsSerializable?displayProperty=nameWithType>

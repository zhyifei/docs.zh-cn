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
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a><span data-ttu-id="32385-103">如何确定 .NET Standard 对象是否可以序列化</span><span class="sxs-lookup"><span data-stu-id="32385-103">How to determine if a .NET Standard object is serializable</span></span>

<span data-ttu-id="32385-104">.NET Standard 是标准的定义的类型和特定于该版本符合的.NET 实现必须存在的成员的规范。</span><span class="sxs-lookup"><span data-stu-id="32385-104">The .NET Standard is a specification that defines the types and members that must be present on specific .NET implementations that conform to that version of the standard.</span></span> <span data-ttu-id="32385-105">但是，.NET Standard 未定义是否可序列化类型。</span><span class="sxs-lookup"><span data-stu-id="32385-105">However, the .NET Standard does not define whether a type is serializable.</span></span> <span data-ttu-id="32385-106">.NET Standard 库中定义的类型未标记 <xref:System.SerializableAttribute> 特性。</span><span class="sxs-lookup"><span data-stu-id="32385-106">The types defined in the .NET Standard Library are not marked with the <xref:System.SerializableAttribute> attribute.</span></span> <span data-ttu-id="32385-107">相反，特定的.NET 实现，如.NET Framework 和.NET Core 是可用来确定特定类型是否为可序列化。</span><span class="sxs-lookup"><span data-stu-id="32385-107">Instead, specific .NET implementations, such as the .NET Framework and .NET Core, are free to determine whether a particular type is serializable.</span></span>

<span data-ttu-id="32385-108">如果你面向的.NET Standard 开发了一个库，你的库可供任何支持.NET Standard 的.NET 实现。</span><span class="sxs-lookup"><span data-stu-id="32385-108">If you've developed a library that targets the .NET Standard, your library can be consumed by any .NET implementation that supports the .NET Standard.</span></span> <span data-ttu-id="32385-109">这意味着你不会提前知道特定类型是否可序列化;只能在运行时确定它是否可序列化。</span><span class="sxs-lookup"><span data-stu-id="32385-109">This means that you cannot know in advance whether a particular type is serializable; you can only determine whether it is serializable at run time.</span></span>

<span data-ttu-id="32385-110">可以通过检索表示对象类型的 <xref:System.Type> 对象的 <xref:System.Type.IsSerializable> 属性的值，来确定对象在运行时是否可以序列化。</span><span class="sxs-lookup"><span data-stu-id="32385-110">You can determine whether an object is serializable at runtime by retrieving the value of the <xref:System.Type.IsSerializable> property of a <xref:System.Type> object that represents that object's type.</span></span> <span data-ttu-id="32385-111">下面的示例提供了一个实现。</span><span class="sxs-lookup"><span data-stu-id="32385-111">The following example provides one implementation.</span></span> <span data-ttu-id="32385-112">它定义了一个 `IsSerializable(Object)` 扩展方法，用于指示是否可以序列化任何 <xref:System.Object> 实例。</span><span class="sxs-lookup"><span data-stu-id="32385-112">It defines an `IsSerializable(Object)` extension method that indicates whether any <xref:System.Object> instance can be serialized.</span></span>

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

<span data-ttu-id="32385-113">然后，可以将任何对象传递给方法，以确定是否可以在当前 .NET 实现上对其进行序列化和反序列化，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="32385-113">You can then pass any object to the method to determine whether it can be serialized and deserialized on the current .NET implementation, as the following example shows:</span></span>

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

## <a name="see-also"></a><span data-ttu-id="32385-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="32385-114">See also</span></span>

- [<span data-ttu-id="32385-115">二进制序列化</span><span class="sxs-lookup"><span data-stu-id="32385-115">Binary serialization</span></span>](binary-serialization.md)
- <xref:System.SerializableAttribute?displayProperty=nameWithType>
- <xref:System.Type.IsSerializable?displayProperty=nameWithType>

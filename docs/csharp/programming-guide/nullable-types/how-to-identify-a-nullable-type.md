---
title: 如何：标识可以为 null 的类型（C# 编程指南）
description: 了解如何确定类型是否是可以为 null 的类型或实例是否是可以为 null 的类型
ms.date: 08/06/2018
helpviewer_keywords:
- nullable types [C#], identifying
ms.assetid: d4b67ee2-66e8-40c1-ae9d-545d32c71387
ms.openlocfilehash: bb7ab2b8c13c2b8b4b6cd60e7959a391cd7e75c1
ms.sourcegitcommit: bd4fa78f5a46133efdead1bc692a9aa2811d7868
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "42754951"
---
# <a name="how-to-identify-a-nullable-type-c-programming-guide"></a><span data-ttu-id="f43d4-103">如何：确定可以为 null 的类型（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="f43d4-103">How to: Identify a nullable type (C# Programming Guide)</span></span>

<span data-ttu-id="f43d4-104">以下示例显示如何确定 <xref:System.Type?displayProperty=nameWithType> 实例是否表示可以为 null 的类型：</span><span class="sxs-lookup"><span data-stu-id="f43d4-104">The following example shows how to determine whether a <xref:System.Type?displayProperty=nameWithType> instance represents a nullable type:</span></span>

[!code-csharp-interactive[whether Type is nullable](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#1)]

<span data-ttu-id="f43d4-105">如示例所示，使用 [typeof](../../language-reference/keywords/typeof.md) 运算符来创建 <xref:System.Type?displayProperty=nameWithType> 对象。</span><span class="sxs-lookup"><span data-stu-id="f43d4-105">As the example shows, you use the [typeof](../../language-reference/keywords/typeof.md) operator to create a <xref:System.Type?displayProperty=nameWithType> object.</span></span>  
  
<span data-ttu-id="f43d4-106">如果要确定实例是否是可以为 null 的类型，请不要使用 <xref:System.Object.GetType%2A?displayProperty=nameWithType> 方法获取要通过前面的代码测试的 <xref:System.Type> 实例。</span><span class="sxs-lookup"><span data-stu-id="f43d4-106">If you want to determine whether an instance is of a nullable type, don't use the <xref:System.Object.GetType%2A?displayProperty=nameWithType> method to get a <xref:System.Type> instance to be tested with the preceding code.</span></span> <span data-ttu-id="f43d4-107">如果对可以为 null 的类型的实例调用 <xref:System.Object.GetType%2A?displayProperty=nameWithType> 方法，该实例将[装箱](using-nullable-types.md#boxing-and-unboxing)到 <xref:System.Object>。</span><span class="sxs-lookup"><span data-stu-id="f43d4-107">When you call the <xref:System.Object.GetType%2A?displayProperty=nameWithType> method on an instance of a nullable type, the instance is [boxed](using-nullable-types.md#boxing-and-unboxing) to <xref:System.Object>.</span></span> <span data-ttu-id="f43d4-108">由于对可以为 null 的类型的非 NULL 实例的装箱等效于对基础类型的值的装箱，因此 <xref:System.Object.GetType%2A> 返回表示可以为 null 的类型的基础类型的 <xref:System.Type> 对象：</span><span class="sxs-lookup"><span data-stu-id="f43d4-108">As boxing of a non-null instance of a nullable type is equivalent to boxing of a value of the underlying type, <xref:System.Object.GetType%2A> returns a <xref:System.Type> object that represents the underlying type of a nullable type:</span></span>

[!code-csharp-interactive[GetType example](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#2)]

<span data-ttu-id="f43d4-109">请勿使用 [is](../../language-reference/keywords/is.md) 运算符来确定实例是否是可以为 null 的类型。</span><span class="sxs-lookup"><span data-stu-id="f43d4-109">Don't use the [is](../../language-reference/keywords/is.md) operator to determine whether an instance is of a nullable type.</span></span> <span data-ttu-id="f43d4-110">如以下示例所示，无法使用 `is` 运算符区分可以为 null 的类型的实例类型和其基础类型：</span><span class="sxs-lookup"><span data-stu-id="f43d4-110">As the following example shows, you cannot distinguish types of instances of a nullable type and its underlying type with using the `is` operator:</span></span>

[!code-csharp-interactive[is operator example](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#3)]

<span data-ttu-id="f43d4-111">可使用以下示例中提供的代码来确定实例是否是可以为 null 的类型：</span><span class="sxs-lookup"><span data-stu-id="f43d4-111">You can use the code presented in the following example to determine whether an instance is of a nullable type:</span></span>

[!code-csharp-interactive[whether an instance is of a nullable type](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#4)]
  
## <a name="see-also"></a><span data-ttu-id="f43d4-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="f43d4-112">See also</span></span>

[<span data-ttu-id="f43d4-113">可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="f43d4-113">Nullable types</span></span>](index.md)  
[<span data-ttu-id="f43d4-114">使用可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="f43d4-114">Using nullable types</span></span>](using-nullable-types.md)  
<xref:System.Nullable.GetUnderlyingType%2A>  

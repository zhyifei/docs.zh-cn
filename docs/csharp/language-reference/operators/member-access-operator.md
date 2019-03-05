---
title: . 运算符 - C# 参考
ms.custom: seodec18
ms.date: 02/25/2019
f1_keywords:
- ._CSharpKeyword
helpviewer_keywords:
- member access operator (.) [C#]
- . operator [C#]
- dot operator (.) [C#]
ms.assetid: a1f54b52-b686-4ae5-a48e-a2a9ebd0eb7b
ms.openlocfilehash: 2661676d53deb874c5e5a90b4443b301730e09df
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "56836456"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="bd6f5-103">.</span><span class="sxs-lookup"><span data-stu-id="bd6f5-103">.</span></span> <span data-ttu-id="bd6f5-104">运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="bd6f5-104">operator (C# Reference)</span></span>

<span data-ttu-id="bd6f5-105">点 `.` 通常用于成员访问。</span><span class="sxs-lookup"><span data-stu-id="bd6f5-105">The dot, `.`, is typically used for member access.</span></span>

<span data-ttu-id="bd6f5-106">可以使用 `.` 标记来访问命名空间或类型的成员，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="bd6f5-106">You use the `.` token to access a member of a namespace or a type, as the following examples demonstrate:</span></span>

- <span data-ttu-id="bd6f5-107">使用 `.` 访问命名空间内的嵌套命名空间，如以下 [`using` directive](../keywords/using-directive.md) 的示例所示：</span><span class="sxs-lookup"><span data-stu-id="bd6f5-107">Use `.` to access a nested namespace within a namespace, as the following example of a [`using` directive](../keywords/using-directive.md) shows:</span></span>

  [!code-csharp[nested namespaces](~/samples/snippets/csharp/language-reference/operators/MemberAccessExamples.cs#NestedNamespace)]

- <span data-ttu-id="bd6f5-108">使用 `.` 构成限定名称以访问命名空间中的类型，如下面的代码所示：</span><span class="sxs-lookup"><span data-stu-id="bd6f5-108">Use `.` to form a *qualified name* to access a type within a namespace, as the following code shows:</span></span>

  [!code-csharp[qualified name](~/samples/snippets/csharp/language-reference/operators/MemberAccessExamples.cs#QualifiedName)]

  <span data-ttu-id="bd6f5-109">使用 [`using` directive](../keywords/using-directive.md) 可以选择使用限定名称。</span><span class="sxs-lookup"><span data-stu-id="bd6f5-109">Use the [`using` directive](../keywords/using-directive.md) to make the use of qualified names optional.</span></span>

- <span data-ttu-id="bd6f5-110">使用 `.` 访问[类型成员](../../programming-guide/classes-and-structs/index.md#members)（静态和非静态），如下面的代码所示：</span><span class="sxs-lookup"><span data-stu-id="bd6f5-110">Use `.` to access [type members](../../programming-guide/classes-and-structs/index.md#members), static and non-static, as the following code shows:</span></span>

  [!code-csharp-interactive[type members](~/samples/snippets/csharp/language-reference/operators/MemberAccessExamples.cs#TypeMemberAccess)]

<span data-ttu-id="bd6f5-111">还可以使用 `.` 调用[扩展方法](../../programming-guide/classes-and-structs/extension-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="bd6f5-111">You can also use `.` to invoke an [extension method](../../programming-guide/classes-and-structs/extension-methods.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="bd6f5-112">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="bd6f5-112">Operator overloadability</span></span>

<span data-ttu-id="bd6f5-113">不能重载 `.` 运算符。</span><span class="sxs-lookup"><span data-stu-id="bd6f5-113">The operator `.` cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="bd6f5-114">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="bd6f5-114">C# language specification</span></span>

<span data-ttu-id="bd6f5-115">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的[成员访问](~/_csharplang/spec/expressions.md#member-access)部分。</span><span class="sxs-lookup"><span data-stu-id="bd6f5-115">For more information, see the [Member access](~/_csharplang/spec/expressions.md#member-access) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bd6f5-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd6f5-116">See also</span></span>

- [<span data-ttu-id="bd6f5-117">C# 参考</span><span class="sxs-lookup"><span data-stu-id="bd6f5-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="bd6f5-118">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="bd6f5-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="bd6f5-119">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="bd6f5-119">C# Operators</span></span>](index.md)
- <span data-ttu-id="bd6f5-120">[?. 和 ?[] 运算符](null-conditional-operators.md)</span><span class="sxs-lookup"><span data-stu-id="bd6f5-120">[?. and ?[] operators](null-conditional-operators.md)</span></span>
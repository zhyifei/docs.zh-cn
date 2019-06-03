---
title: sizeof - C# 参考
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
ms.openlocfilehash: a00c4f96e62f7fd7d7c352aece097acd5b600ae2
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422396"
---
# <a name="sizeof-c-reference"></a><span data-ttu-id="e385c-102">sizeof（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="e385c-102">sizeof (C# Reference)</span></span>

<span data-ttu-id="e385c-103">用于获取非托管类型的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="e385c-103">Used to obtain the size in bytes for an unmanaged type.</span></span>

<span data-ttu-id="e385c-104">非托管类型包括：</span><span class="sxs-lookup"><span data-stu-id="e385c-104">Unmanaged types include:</span></span>

- <span data-ttu-id="e385c-105">下表列出了简单类型：</span><span class="sxs-lookup"><span data-stu-id="e385c-105">The simple types that are listed in the following table:</span></span>

   |<span data-ttu-id="e385c-106">表达式</span><span class="sxs-lookup"><span data-stu-id="e385c-106">Expression</span></span>|<span data-ttu-id="e385c-107">常量值</span><span class="sxs-lookup"><span data-stu-id="e385c-107">Constant value</span></span>|
   |----------------|--------------------|
   |`sizeof(sbyte)`|<span data-ttu-id="e385c-108">1</span><span class="sxs-lookup"><span data-stu-id="e385c-108">1</span></span>|
   |`sizeof(byte)`|<span data-ttu-id="e385c-109">1</span><span class="sxs-lookup"><span data-stu-id="e385c-109">1</span></span>|
   |`sizeof(short)`|<span data-ttu-id="e385c-110">2</span><span class="sxs-lookup"><span data-stu-id="e385c-110">2</span></span>|
   |`sizeof(ushort)`|<span data-ttu-id="e385c-111">2</span><span class="sxs-lookup"><span data-stu-id="e385c-111">2</span></span>|
   |`sizeof(int)`|<span data-ttu-id="e385c-112">4</span><span class="sxs-lookup"><span data-stu-id="e385c-112">4</span></span>|
   |`sizeof(uint)`|<span data-ttu-id="e385c-113">4</span><span class="sxs-lookup"><span data-stu-id="e385c-113">4</span></span>|
   |`sizeof(long)`|<span data-ttu-id="e385c-114">8</span><span class="sxs-lookup"><span data-stu-id="e385c-114">8</span></span>|
   |`sizeof(ulong)`|<span data-ttu-id="e385c-115">8</span><span class="sxs-lookup"><span data-stu-id="e385c-115">8</span></span>|
   |`sizeof(char)`|<span data-ttu-id="e385c-116">2 (Unicode)</span><span class="sxs-lookup"><span data-stu-id="e385c-116">2 (Unicode)</span></span>|
   |`sizeof(float)`|<span data-ttu-id="e385c-117">4</span><span class="sxs-lookup"><span data-stu-id="e385c-117">4</span></span>|
   |`sizeof(double)`|<span data-ttu-id="e385c-118">8</span><span class="sxs-lookup"><span data-stu-id="e385c-118">8</span></span>|
   |`sizeof(decimal)`|<span data-ttu-id="e385c-119">16</span><span class="sxs-lookup"><span data-stu-id="e385c-119">16</span></span>|
   |`sizeof(bool)`|<span data-ttu-id="e385c-120">1</span><span class="sxs-lookup"><span data-stu-id="e385c-120">1</span></span>|

- <span data-ttu-id="e385c-121">枚举类型。</span><span class="sxs-lookup"><span data-stu-id="e385c-121">Enum types.</span></span>

- <span data-ttu-id="e385c-122">指针类型。</span><span class="sxs-lookup"><span data-stu-id="e385c-122">Pointer types.</span></span>

- <span data-ttu-id="e385c-123">用户定义的结构，不包含任何实例字段或作为引用类型或构造类型的自动实现的实例属性。</span><span class="sxs-lookup"><span data-stu-id="e385c-123">User-defined structs that do not contain any instance fields or auto-implemented instance properties that are reference types or constructed types.</span></span>

<span data-ttu-id="e385c-124">下面的示例演示如何检索 `int` 的大小：</span><span class="sxs-lookup"><span data-stu-id="e385c-124">The following example shows how to retrieve the size of an `int`:</span></span>

```csharp
// Constant value 4:
int intSize = sizeof(int);
```

## <a name="remarks"></a><span data-ttu-id="e385c-125">备注</span><span class="sxs-lookup"><span data-stu-id="e385c-125">Remarks</span></span>

<span data-ttu-id="e385c-126">从 C# 2.0 版开始，将 `sizeof` 应用于简单类型或枚举类型不再需要在[不安全](unsafe.md)上下文中编译代码。</span><span class="sxs-lookup"><span data-stu-id="e385c-126">Starting with version 2.0 of C#, applying `sizeof` to simple or enum types no longer requires that code be compiled in an [unsafe](unsafe.md) context.</span></span>

<span data-ttu-id="e385c-127">不能重载 `sizeof` 运算符。</span><span class="sxs-lookup"><span data-stu-id="e385c-127">The `sizeof` operator cannot be overloaded.</span></span> <span data-ttu-id="e385c-128">`sizeof` 运算符的返回值是 `int` 类型。</span><span class="sxs-lookup"><span data-stu-id="e385c-128">The values returned by the `sizeof` operator are of type `int`.</span></span> <span data-ttu-id="e385c-129">上表列出了一些常量值，这些值对应于以某些简单类型为操作数的 `sizeof` 表达式。</span><span class="sxs-lookup"><span data-stu-id="e385c-129">The previous table shows the constant values that are substituted for `sizeof` expressions that have certain simple types as operands.</span></span>

<span data-ttu-id="e385c-130">对于所有其他类型（包括结构），`sizeof` 运算符只能在不安全代码块中使用。</span><span class="sxs-lookup"><span data-stu-id="e385c-130">For all other types, including structs, the `sizeof` operator can be used only in unsafe code blocks.</span></span> <span data-ttu-id="e385c-131">虽然可以使用 <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> 方法，但此方法返回的值并不总是与 `sizeof` 返回的值相同。</span><span class="sxs-lookup"><span data-stu-id="e385c-131">Although you can use the <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> method, the value returned by this method is not always the same as the value returned by `sizeof`.</span></span> <span data-ttu-id="e385c-132"><xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> 在封送类型后返回大小，而 `sizeof` 返回公共语言运行时分配的大小（包括所有填充）。</span><span class="sxs-lookup"><span data-stu-id="e385c-132"><xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> returns the size after the type has been marshaled, whereas `sizeof` returns the size as it has been allocated by the common language runtime, including any padding.</span></span>

## <a name="example"></a><span data-ttu-id="e385c-133">示例</span><span class="sxs-lookup"><span data-stu-id="e385c-133">Example</span></span>

[!code-csharp[csrefKeywordsOperator#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#11)]

## <a name="c-language-specification"></a><span data-ttu-id="e385c-134">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="e385c-134">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="e385c-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="e385c-135">See also</span></span>

- [<span data-ttu-id="e385c-136">C# 参考</span><span class="sxs-lookup"><span data-stu-id="e385c-136">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e385c-137">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="e385c-137">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e385c-138">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="e385c-138">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="e385c-139">enum</span><span class="sxs-lookup"><span data-stu-id="e385c-139">enum</span></span>](enum.md)
- [<span data-ttu-id="e385c-140">不安全代码和指针</span><span class="sxs-lookup"><span data-stu-id="e385c-140">Unsafe Code and Pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)
- [<span data-ttu-id="e385c-141">结构</span><span class="sxs-lookup"><span data-stu-id="e385c-141">Structs</span></span>](../../programming-guide/classes-and-structs/structs.md)
- [<span data-ttu-id="e385c-142">常量</span><span class="sxs-lookup"><span data-stu-id="e385c-142">Constants</span></span>](../../programming-guide/classes-and-structs/constants.md)

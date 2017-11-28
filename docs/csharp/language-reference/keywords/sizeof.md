---
title: "sizeof（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
helpviewer_keywords: sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
caps.latest.revision: "20"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0148ae8381804ca9286315251582c8ab40778369
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="sizeof-c-reference"></a><span data-ttu-id="a2fb1-102">sizeof（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="a2fb1-102">sizeof (C# Reference)</span></span>
<span data-ttu-id="a2fb1-103">用于获取非托管类型的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="a2fb1-103">Used to obtain the size in bytes for an unmanaged type.</span></span> <span data-ttu-id="a2fb1-104">非托管类型包括下表列出的内置类型以及以下类型：</span><span class="sxs-lookup"><span data-stu-id="a2fb1-104">Unmanaged types include the built-in types that are listed in the table that follows, and also the following:</span></span>  
  
-   <span data-ttu-id="a2fb1-105">枚举类型</span><span class="sxs-lookup"><span data-stu-id="a2fb1-105">Enum types</span></span>  
  
-   <span data-ttu-id="a2fb1-106">指针类型</span><span class="sxs-lookup"><span data-stu-id="a2fb1-106">Pointer types</span></span>  
  
-   <span data-ttu-id="a2fb1-107">用户定义的结构，不包含任何属于引用类型的字段或属性</span><span class="sxs-lookup"><span data-stu-id="a2fb1-107">User-defined structs that do not contain any fields or properties that are reference types</span></span>  
  
 <span data-ttu-id="a2fb1-108">下面的示例演示如何检索 `int` 的大小：</span><span class="sxs-lookup"><span data-stu-id="a2fb1-108">The following example shows how to retrieve the size of an `int`:</span></span>  
  
```csharp  
// Constant value 4:  
int intSize = sizeof(int);   
```  
  
## <a name="remarks"></a><span data-ttu-id="a2fb1-109">备注</span><span class="sxs-lookup"><span data-stu-id="a2fb1-109">Remarks</span></span>  
 <span data-ttu-id="a2fb1-110">从 C# 2.0 版开始，将 `sizeof` 应用于内置类型不再要求使用 [unsafe](../../../csharp/language-reference/keywords/unsafe.md) 模式。</span><span class="sxs-lookup"><span data-stu-id="a2fb1-110">Starting with version 2.0 of C#, applying `sizeof` to built-in types no longer requires that [unsafe](../../../csharp/language-reference/keywords/unsafe.md) mode be used.</span></span>  
  
 <span data-ttu-id="a2fb1-111">不能重载 `sizeof` 运算符。</span><span class="sxs-lookup"><span data-stu-id="a2fb1-111">The `sizeof` operator cannot be overloaded.</span></span> <span data-ttu-id="a2fb1-112">`sizeof` 运算符的返回值是 `int` 类型。</span><span class="sxs-lookup"><span data-stu-id="a2fb1-112">The values returned by the `sizeof` operator are of type `int`.</span></span> <span data-ttu-id="a2fb1-113">下表列出了一些常量值，这些值对应于以某些内置类型为操作数的 `sizeof` 表达式。</span><span class="sxs-lookup"><span data-stu-id="a2fb1-113">The following table shows the constant values that are substituted for `sizeof` expressions that have certain built-in types as operands.</span></span>  
  
|<span data-ttu-id="a2fb1-114">Expression</span><span class="sxs-lookup"><span data-stu-id="a2fb1-114">Expression</span></span>|<span data-ttu-id="a2fb1-115">常量值</span><span class="sxs-lookup"><span data-stu-id="a2fb1-115">Constant value</span></span>|  
|----------------|--------------------|  
|`sizeof(sbyte)`|<span data-ttu-id="a2fb1-116">1</span><span class="sxs-lookup"><span data-stu-id="a2fb1-116">1</span></span>|  
|`sizeof(byte)`|<span data-ttu-id="a2fb1-117">1</span><span class="sxs-lookup"><span data-stu-id="a2fb1-117">1</span></span>|  
|`sizeof(short)`|<span data-ttu-id="a2fb1-118">2</span><span class="sxs-lookup"><span data-stu-id="a2fb1-118">2</span></span>|  
|`sizeof(ushort)`|<span data-ttu-id="a2fb1-119">2</span><span class="sxs-lookup"><span data-stu-id="a2fb1-119">2</span></span>|  
|`sizeof(int)`|<span data-ttu-id="a2fb1-120">4</span><span class="sxs-lookup"><span data-stu-id="a2fb1-120">4</span></span>|  
|`sizeof(uint)`|<span data-ttu-id="a2fb1-121">4</span><span class="sxs-lookup"><span data-stu-id="a2fb1-121">4</span></span>|  
|`sizeof(long)`|<span data-ttu-id="a2fb1-122">8</span><span class="sxs-lookup"><span data-stu-id="a2fb1-122">8</span></span>|  
|`sizeof(ulong)`|<span data-ttu-id="a2fb1-123">8</span><span class="sxs-lookup"><span data-stu-id="a2fb1-123">8</span></span>|  
|`sizeof(char)`|<span data-ttu-id="a2fb1-124">2 (Unicode)</span><span class="sxs-lookup"><span data-stu-id="a2fb1-124">2 (Unicode)</span></span>|  
|`sizeof(float)`|<span data-ttu-id="a2fb1-125">4</span><span class="sxs-lookup"><span data-stu-id="a2fb1-125">4</span></span>|  
|`sizeof(double)`|<span data-ttu-id="a2fb1-126">8</span><span class="sxs-lookup"><span data-stu-id="a2fb1-126">8</span></span>|  
|`sizeof(decimal)`|<span data-ttu-id="a2fb1-127">16</span><span class="sxs-lookup"><span data-stu-id="a2fb1-127">16</span></span>|  
|`sizeof(bool)`|<span data-ttu-id="a2fb1-128">1</span><span class="sxs-lookup"><span data-stu-id="a2fb1-128">1</span></span>|  
  
 <span data-ttu-id="a2fb1-129">对于所有其他类型（包括结构），`sizeof` 运算符只能在不安全代码块中使用。</span><span class="sxs-lookup"><span data-stu-id="a2fb1-129">For all other types, including structs, the `sizeof` operator can be used only in unsafe code blocks.</span></span> <span data-ttu-id="a2fb1-130">虽然可以使用 <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> 方法，但此方法返回的值并不总是与 `sizeof` 返回的值相同。</span><span class="sxs-lookup"><span data-stu-id="a2fb1-130">Although you can use the <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> method, the value returned by this method is not always the same as the value returned by `sizeof`.</span></span> <span data-ttu-id="a2fb1-131"><xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> 在封送类型后返回大小，而 `sizeof` 返回公共语言运行时分配的大小（包括所有填充）。</span><span class="sxs-lookup"><span data-stu-id="a2fb1-131"><xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> returns the size after the type has been marshaled, whereas `sizeof` returns the size as it has been allocated by the common language runtime, including any padding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2fb1-132">示例</span><span class="sxs-lookup"><span data-stu-id="a2fb1-132">Example</span></span>  
 [!code-csharp[csrefKeywordsOperator#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/sizeof_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="a2fb1-133">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="a2fb1-133">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a2fb1-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a2fb1-134">See Also</span></span>  
 [<span data-ttu-id="a2fb1-135">C# 参考</span><span class="sxs-lookup"><span data-stu-id="a2fb1-135">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="a2fb1-136">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="a2fb1-136">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="a2fb1-137">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="a2fb1-137">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="a2fb1-138">运算符关键字</span><span class="sxs-lookup"><span data-stu-id="a2fb1-138">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [<span data-ttu-id="a2fb1-139">enum</span><span class="sxs-lookup"><span data-stu-id="a2fb1-139">enum</span></span>](../../../csharp/language-reference/keywords/enum.md)  
 [<span data-ttu-id="a2fb1-140">不安全代码和指针</span><span class="sxs-lookup"><span data-stu-id="a2fb1-140">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [<span data-ttu-id="a2fb1-141">结构</span><span class="sxs-lookup"><span data-stu-id="a2fb1-141">Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/structs.md)  
 [<span data-ttu-id="a2fb1-142">常量</span><span class="sxs-lookup"><span data-stu-id="a2fb1-142">Constants</span></span>](../../../csharp/programming-guide/classes-and-structs/constants.md)

---
title: "sizeof（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
dev_langs:
- CSharp
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 15d11071c369fad398d40cfef301e462c006d5e4
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="sizeof-c-reference"></a><span data-ttu-id="bb09f-102">sizeof（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="bb09f-102">sizeof (C# Reference)</span></span>
<span data-ttu-id="bb09f-103">用于获取非托管类型的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="bb09f-103">Used to obtain the size in bytes for an unmanaged type.</span></span> <span data-ttu-id="bb09f-104">非托管类型包括下表列出的内置类型以及以下类型：</span><span class="sxs-lookup"><span data-stu-id="bb09f-104">Unmanaged types include the built-in types that are listed in the table that follows, and also the following:</span></span>  
  
-   <span data-ttu-id="bb09f-105">枚举类型</span><span class="sxs-lookup"><span data-stu-id="bb09f-105">Enum types</span></span>  
  
-   <span data-ttu-id="bb09f-106">指针类型</span><span class="sxs-lookup"><span data-stu-id="bb09f-106">Pointer types</span></span>  
  
-   <span data-ttu-id="bb09f-107">用户定义的结构，不包含任何属于引用类型的字段或属性</span><span class="sxs-lookup"><span data-stu-id="bb09f-107">User-defined structs that do not contain any fields or properties that are reference types</span></span>  
  
 <span data-ttu-id="bb09f-108">下面的示例演示如何检索 `int` 的大小：</span><span class="sxs-lookup"><span data-stu-id="bb09f-108">The following example shows how to retrieve the size of an `int`:</span></span>  
  
```csharp  
// Constant value 4:  
int intSize = sizeof(int);   
```  
  
## <a name="remarks"></a><span data-ttu-id="bb09f-109">备注</span><span class="sxs-lookup"><span data-stu-id="bb09f-109">Remarks</span></span>  
 <span data-ttu-id="bb09f-110">从 C# 2.0 版开始，将 `sizeof` 应用于内置类型不再要求使用 [unsafe](../../../csharp/language-reference/keywords/unsafe.md) 模式。</span><span class="sxs-lookup"><span data-stu-id="bb09f-110">Starting with version 2.0 of C#, applying `sizeof` to built-in types no longer requires that [unsafe](../../../csharp/language-reference/keywords/unsafe.md) mode be used.</span></span>  
  
 <span data-ttu-id="bb09f-111">不能重载 `sizeof` 运算符。</span><span class="sxs-lookup"><span data-stu-id="bb09f-111">The `sizeof` operator cannot be overloaded.</span></span> <span data-ttu-id="bb09f-112">`sizeof` 运算符的返回值是 `int` 类型。</span><span class="sxs-lookup"><span data-stu-id="bb09f-112">The values returned by the `sizeof` operator are of type `int`.</span></span> <span data-ttu-id="bb09f-113">下表列出了一些常量值，这些值对应于以某些内置类型为操作数的 `sizeof` 表达式。</span><span class="sxs-lookup"><span data-stu-id="bb09f-113">The following table shows the constant values that are substituted for `sizeof` expressions that have certain built-in types as operands.</span></span>  
  
|<span data-ttu-id="bb09f-114">Expression</span><span class="sxs-lookup"><span data-stu-id="bb09f-114">Expression</span></span>|<span data-ttu-id="bb09f-115">常量值</span><span class="sxs-lookup"><span data-stu-id="bb09f-115">Constant value</span></span>|  
|----------------|--------------------|  
|`sizeof(sbyte)`|<span data-ttu-id="bb09f-116">1</span><span class="sxs-lookup"><span data-stu-id="bb09f-116">1</span></span>|  
|`sizeof(byte)`|<span data-ttu-id="bb09f-117">1</span><span class="sxs-lookup"><span data-stu-id="bb09f-117">1</span></span>|  
|`sizeof(short)`|<span data-ttu-id="bb09f-118">2</span><span class="sxs-lookup"><span data-stu-id="bb09f-118">2</span></span>|  
|`sizeof(ushort)`|<span data-ttu-id="bb09f-119">2</span><span class="sxs-lookup"><span data-stu-id="bb09f-119">2</span></span>|  
|`sizeof(int)`|<span data-ttu-id="bb09f-120">4</span><span class="sxs-lookup"><span data-stu-id="bb09f-120">4</span></span>|  
|`sizeof(uint)`|<span data-ttu-id="bb09f-121">4</span><span class="sxs-lookup"><span data-stu-id="bb09f-121">4</span></span>|  
|`sizeof(long)`|<span data-ttu-id="bb09f-122">8</span><span class="sxs-lookup"><span data-stu-id="bb09f-122">8</span></span>|  
|`sizeof(ulong)`|<span data-ttu-id="bb09f-123">8</span><span class="sxs-lookup"><span data-stu-id="bb09f-123">8</span></span>|  
|`sizeof(char)`|<span data-ttu-id="bb09f-124">2 (Unicode)</span><span class="sxs-lookup"><span data-stu-id="bb09f-124">2 (Unicode)</span></span>|  
|`sizeof(float)`|<span data-ttu-id="bb09f-125">4</span><span class="sxs-lookup"><span data-stu-id="bb09f-125">4</span></span>|  
|`sizeof(double)`|<span data-ttu-id="bb09f-126">8</span><span class="sxs-lookup"><span data-stu-id="bb09f-126">8</span></span>|  
|`sizeof(decimal)`|<span data-ttu-id="bb09f-127">16</span><span class="sxs-lookup"><span data-stu-id="bb09f-127">16</span></span>|  
|`sizeof(bool)`|<span data-ttu-id="bb09f-128">1</span><span class="sxs-lookup"><span data-stu-id="bb09f-128">1</span></span>|  
  
 <span data-ttu-id="bb09f-129">对于所有其他类型（包括结构），`sizeof` 运算符只能在不安全代码块中使用。</span><span class="sxs-lookup"><span data-stu-id="bb09f-129">For all other types, including structs, the `sizeof` operator can be used only in unsafe code blocks.</span></span> <span data-ttu-id="bb09f-130">虽然可以使用 <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=fullName> 方法，但此方法返回的值并不总是与 `sizeof` 返回的值相同。</span><span class="sxs-lookup"><span data-stu-id="bb09f-130">Although you can use the <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=fullName> method, the value returned by this method is not always the same as the value returned by `sizeof`.</span></span> <span data-ttu-id="bb09f-131"><xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=fullName> 在封送类型后返回大小，而 `sizeof` 返回公共语言运行时分配的大小（包括所有填充）。</span><span class="sxs-lookup"><span data-stu-id="bb09f-131"><xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=fullName> returns the size after the type has been marshaled, whereas `sizeof` returns the size as it has been allocated by the common language runtime, including any padding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb09f-132">示例</span><span class="sxs-lookup"><span data-stu-id="bb09f-132">Example</span></span>  
 <span data-ttu-id="bb09f-133">[!code-cs[csrefKeywordsOperator#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/sizeof_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="bb09f-133">[!code-cs[csrefKeywordsOperator#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/sizeof_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="bb09f-134">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="bb09f-134">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bb09f-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="bb09f-135">See Also</span></span>  
 <span data-ttu-id="bb09f-136">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="bb09f-136">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="bb09f-137">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="bb09f-137">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="bb09f-138">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="bb09f-138">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="bb09f-139">[运算符关键字](../../../csharp/language-reference/keywords/operator-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="bb09f-139">[Operator Keywords](../../../csharp/language-reference/keywords/operator-keywords.md) </span></span>  
 <span data-ttu-id="bb09f-140">[enum](../../../csharp/language-reference/keywords/enum.md) </span><span class="sxs-lookup"><span data-stu-id="bb09f-140">[enum](../../../csharp/language-reference/keywords/enum.md) </span></span>  
 <span data-ttu-id="bb09f-141">[不安全代码和指针](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span><span class="sxs-lookup"><span data-stu-id="bb09f-141">[Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span></span>  
 <span data-ttu-id="bb09f-142">[结构](../../../csharp/programming-guide/classes-and-structs/structs.md) </span><span class="sxs-lookup"><span data-stu-id="bb09f-142">[Structs](../../../csharp/programming-guide/classes-and-structs/structs.md) </span></span>  
 [<span data-ttu-id="bb09f-143">常量</span><span class="sxs-lookup"><span data-stu-id="bb09f-143">Constants</span></span>](../../../csharp/programming-guide/classes-and-structs/constants.md)


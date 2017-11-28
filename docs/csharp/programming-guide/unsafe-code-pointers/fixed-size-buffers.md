---
title: "固定大小的缓冲区（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- fixed size buffers [C#]
- unsafe buffers [C#]
- unsafe code [C#], fixed size buffers
ms.assetid: 6220d454-947c-4977-ac9d-9308c6ed5051
caps.latest.revision: "31"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3f99c2c6d477fca988fcca77de5ca5c2f8addd4d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="fixed-size-buffers-c-programming-guide"></a><span data-ttu-id="be42a-102">固定大小的缓冲区（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="be42a-102">Fixed Size Buffers (C# Programming Guide)</span></span>
<span data-ttu-id="be42a-103">在 C# 中，可以使用 [fixed](../../../csharp/language-reference/keywords/fixed-statement.md) 语句来创建在数据结构中具有固定大小的数组的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="be42a-103">In C#, you can use the [fixed](../../../csharp/language-reference/keywords/fixed-statement.md) statement to create a buffer with a fixed size array in a data structure.</span></span> <span data-ttu-id="be42a-104">当使用现有代码（例如使用其他语言编写的代码、预先存在的 DLL 或 COM 项目）时，这非常有用。</span><span class="sxs-lookup"><span data-stu-id="be42a-104">This is useful when you are working with existing code, such as code written in other languages, pre-existing DLLs or COM projects.</span></span> <span data-ttu-id="be42a-105">固定的数组可以采用允许用于常规结构成员的任何属性或修饰符。</span><span class="sxs-lookup"><span data-stu-id="be42a-105">The fixed array can take any attributes or modifiers that are allowed for regular struct members.</span></span> <span data-ttu-id="be42a-106">唯一的限制是数组类型必须为 `bool`、`byte`、`char`、`short`、`int`, `long`、`sbyte`、`ushort`、`uint`、`ulong`、`float` 或 `double`。</span><span class="sxs-lookup"><span data-stu-id="be42a-106">The only restriction is that the array type must be `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float`, or `double`.</span></span>  
  
```  
private fixed char name[30];  
```  
  
## <a name="remarks"></a><span data-ttu-id="be42a-107">备注</span><span class="sxs-lookup"><span data-stu-id="be42a-107">Remarks</span></span>  
 <span data-ttu-id="be42a-108">在早期版本的 C# 中，声明 C++ 样式固定大小的结构是很困难的，因为包含数组的 C# 结构不包含数组元素。</span><span class="sxs-lookup"><span data-stu-id="be42a-108">In early versions of C#, declaring a C++ style fixed-size structure was difficult because a C# struct that contains an array does not contain the array elements.</span></span> <span data-ttu-id="be42a-109">而该结构包含对元素的引用。</span><span class="sxs-lookup"><span data-stu-id="be42a-109">Instead, the struct contains a reference to the elements.</span></span>  
  
 <span data-ttu-id="be42a-110">C# 2.0 增加了在[结构](../../../csharp/language-reference/keywords/struct.md)中嵌入固定大小的数组的功能（当在[不安全的](../../../csharp/language-reference/keywords/unsafe.md)代码块中使用该数组时）。</span><span class="sxs-lookup"><span data-stu-id="be42a-110">C# 2.0 added the ability to embed an array of fixed size in a [struct](../../../csharp/language-reference/keywords/struct.md) when it is used in an [unsafe](../../../csharp/language-reference/keywords/unsafe.md) code block.</span></span>  
  
 <span data-ttu-id="be42a-111">例如，在 C# 2.0 之前，以下 `struct` 的大小为 8 个字节。</span><span class="sxs-lookup"><span data-stu-id="be42a-111">For example, before C# 2.0, the following `struct` would be 8 bytes in size.</span></span> <span data-ttu-id="be42a-112">`pathName` 数组是对堆分配数组的引用：</span><span class="sxs-lookup"><span data-stu-id="be42a-112">The `pathName` array is a reference to the heap-allocated array:</span></span>  
  
 [!code-csharp[csProgGuidePointers#19](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/fixed-size-buffers_1.cs)]  
  
 <span data-ttu-id="be42a-113">从 C# 2.0 开始，`struct` 可以包含嵌入的数组。</span><span class="sxs-lookup"><span data-stu-id="be42a-113">Beginning with C# 2.0, a `struct` can contain an embedded array.</span></span> <span data-ttu-id="be42a-114">在下面的示例中，`fixedBuffer` 数组具有固定的大小。</span><span class="sxs-lookup"><span data-stu-id="be42a-114">In the following example, the `fixedBuffer` array has a fixed size.</span></span> <span data-ttu-id="be42a-115">若要访问数组的元素，请使用 `fixed` 语句，以建立指向第一个元素的指针。</span><span class="sxs-lookup"><span data-stu-id="be42a-115">To access the elements of the array, you use a `fixed` statement to establish a pointer to the first element.</span></span> <span data-ttu-id="be42a-116">`fixed` 语句将 `fixedBuffer` 的实例锁定到内存中的特定位置。</span><span class="sxs-lookup"><span data-stu-id="be42a-116">The `fixed` statement pins an instance of `fixedBuffer` to a specific location in memory.</span></span>  
  
 [!code-csharp[csProgGuidePointers#20](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/fixed-size-buffers_2.cs)]  
  
 <span data-ttu-id="be42a-117">包含 128 个元素的 `char` 数组的大小为 256 个字节。</span><span class="sxs-lookup"><span data-stu-id="be42a-117">The size of the 128 element `char` array is 256 bytes.</span></span> <span data-ttu-id="be42a-118">固定大小的 [char](../../../csharp/language-reference/keywords/char.md) 缓冲区每个字符始终占用两个字节，而不考虑编码。</span><span class="sxs-lookup"><span data-stu-id="be42a-118">Fixed size [char](../../../csharp/language-reference/keywords/char.md) buffers always take two bytes per character, regardless of the encoding.</span></span> <span data-ttu-id="be42a-119">甚至在将 char 缓冲区封送到 API 方法或具有 `CharSet = CharSet.Auto` 或 `CharSet = CharSet.Ansi` 的结构时，这也为 true。</span><span class="sxs-lookup"><span data-stu-id="be42a-119">This is true even when char buffers are marshaled to API methods or structs with `CharSet = CharSet.Auto` or `CharSet = CharSet.Ansi`.</span></span> <span data-ttu-id="be42a-120">有关更多信息，请参见<xref:System.Runtime.InteropServices.CharSet>。</span><span class="sxs-lookup"><span data-stu-id="be42a-120">For more information, see <xref:System.Runtime.InteropServices.CharSet>.</span></span>  
  
 <span data-ttu-id="be42a-121">另一常见的固定大小的数组是 [bool](../../../csharp/language-reference/keywords/bool.md) 数组。</span><span class="sxs-lookup"><span data-stu-id="be42a-121">Another common fixed-size array is the [bool](../../../csharp/language-reference/keywords/bool.md) array.</span></span> <span data-ttu-id="be42a-122">`bool` 数组中的元素大小始终为一个字节。</span><span class="sxs-lookup"><span data-stu-id="be42a-122">The elements in a `bool` array are always one byte in size.</span></span> <span data-ttu-id="be42a-123">`bool` 数组不适用于创建位数组或缓冲区。</span><span class="sxs-lookup"><span data-stu-id="be42a-123">`bool` arrays are not appropriate for creating bit arrays or buffers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="be42a-124">除了通过使用 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md) 创建的内存外，C# 编译器和公共语言运行时 (CLR) 不执行任何安全缓冲区溢出检查。</span><span class="sxs-lookup"><span data-stu-id="be42a-124">Except for memory created by using [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md), the C# compiler and the common language runtime (CLR) do not perform any security buffer overrun checks.</span></span> <span data-ttu-id="be42a-125">与所有不安全代码一样，请谨慎使用。</span><span class="sxs-lookup"><span data-stu-id="be42a-125">As with all unsafe code, use caution.</span></span>  
  
 <span data-ttu-id="be42a-126">不安全的缓冲区与常规数组的区别体现在以下方面：</span><span class="sxs-lookup"><span data-stu-id="be42a-126">Unsafe buffers differ from regular arrays in the following ways:</span></span>  
  
-   <span data-ttu-id="be42a-127">只能在不安全的上下文中使用不安全的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="be42a-127">You can only use unsafe buffers in an unsafe context.</span></span>  
  
-   <span data-ttu-id="be42a-128">不安全的缓冲区始终是矢量或一维数组。</span><span class="sxs-lookup"><span data-stu-id="be42a-128">Unsafe buffers are always vectors, or one-dimensional arrays.</span></span>  
  
-   <span data-ttu-id="be42a-129">数组的声明应包括计数，如 `char id[8]`。</span><span class="sxs-lookup"><span data-stu-id="be42a-129">The declaration of the array should include a count, such as `char id[8]`.</span></span> <span data-ttu-id="be42a-130">不能改用 `char id[]`。</span><span class="sxs-lookup"><span data-stu-id="be42a-130">You cannot use `char id[]` instead.</span></span>  
  
-   <span data-ttu-id="be42a-131">在不安全的上下文中，不安全的缓冲区只能是结构的实例字段。</span><span class="sxs-lookup"><span data-stu-id="be42a-131">Unsafe buffers can only be instance fields of structs in an unsafe context.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be42a-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="be42a-132">See Also</span></span>  
 [<span data-ttu-id="be42a-133">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="be42a-133">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="be42a-134">不安全代码和指针</span><span class="sxs-lookup"><span data-stu-id="be42a-134">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [<span data-ttu-id="be42a-135">fixed 语句</span><span class="sxs-lookup"><span data-stu-id="be42a-135">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="be42a-136">互操作性</span><span class="sxs-lookup"><span data-stu-id="be42a-136">Interoperability</span></span>](../../../csharp/programming-guide/interop/index.md)

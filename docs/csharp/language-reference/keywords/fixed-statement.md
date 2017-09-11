---
title: "fixed 语句（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- fixed_CSharpKeyword
- fixed
dev_langs:
- CSharp
helpviewer_keywords:
- fixed keyword [C#]
ms.assetid: 7ea6db08-ad49-4a7a-b934-d8c4acad1c3a
caps.latest.revision: 24
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
ms.openlocfilehash: 4e1f810f6e6cfaef3a65c7391f074b414ef18b5a
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="fixed-statement-c-reference"></a><span data-ttu-id="2d42d-102">fixed 语句（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="2d42d-102">fixed Statement (C# Reference)</span></span>
<span data-ttu-id="2d42d-103">`fixed` 语句可防止垃圾回收器重新定位可移动的变量。</span><span class="sxs-lookup"><span data-stu-id="2d42d-103">The `fixed` statement prevents the garbage collector from relocating a movable variable.</span></span> <span data-ttu-id="2d42d-104">`fixed` 语句仅允许存在于[不安全的](../../../csharp/language-reference/keywords/unsafe.md)上下文中。</span><span class="sxs-lookup"><span data-stu-id="2d42d-104">The `fixed` statement is only permitted in an [unsafe](../../../csharp/language-reference/keywords/unsafe.md) context.</span></span> <span data-ttu-id="2d42d-105">`Fixed` 还可用于创建[固定大小的缓冲区](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)。</span><span class="sxs-lookup"><span data-stu-id="2d42d-105">`Fixed` can also be used to create [fixed size buffers](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span></span>  
  
 <span data-ttu-id="2d42d-106">`fixed` 语句将为托管变量设置一个指针，并在该语句的执行过程中“单边锁定”该变量。</span><span class="sxs-lookup"><span data-stu-id="2d42d-106">The `fixed` statement sets a pointer to a managed variable and "pins" that variable during the execution of the statement.</span></span> <span data-ttu-id="2d42d-107">如果没有 `fixed`，指向可移动的托管变量的指针将几乎没有什么用处，因为垃圾回收可能会不可预见地重新定位变量。</span><span class="sxs-lookup"><span data-stu-id="2d42d-107">Without `fixed`, pointers to movable managed variables would be of little use since garbage collection could relocate the variables unpredictably.</span></span> <span data-ttu-id="2d42d-108">C# 编译器只允许将指针分配给 `fixed` 语句中的托管变量。</span><span class="sxs-lookup"><span data-stu-id="2d42d-108">The C# compiler only lets you assign a pointer to a managed variable in a `fixed` statement.</span></span>  
  
 <span data-ttu-id="2d42d-109">[!code-cs[csrefKeywordsFixedLock#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="2d42d-109">[!code-cs[csrefKeywordsFixedLock#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_1.cs)]</span></span>  
  
 <span data-ttu-id="2d42d-110">可以通过使用一个数组、字符串、固定大小的缓冲区或变量的地址来初始化指针。</span><span class="sxs-lookup"><span data-stu-id="2d42d-110">You can initialize a pointer by using an array, a string, a fixed-size buffer, or the address of a variable.</span></span> <span data-ttu-id="2d42d-111">下面的示例说明了变量地址、数组和字符串的使用。</span><span class="sxs-lookup"><span data-stu-id="2d42d-111">The following example illustrates the use of variable addresses, arrays, and strings.</span></span> <span data-ttu-id="2d42d-112">有关固定大小的缓冲区的详细信息，请参阅[固定大小的缓冲区](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)。</span><span class="sxs-lookup"><span data-stu-id="2d42d-112">For more information about fixed-size buffers, see [Fixed Size Buffers](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span></span>  
  
 <span data-ttu-id="2d42d-113">[!code-cs[csrefKeywordsFixedLock#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="2d42d-113">[!code-cs[csrefKeywordsFixedLock#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_2.cs)]</span></span>  
  
 <span data-ttu-id="2d42d-114">可以初始化多个指针，只要它们的类型相同。</span><span class="sxs-lookup"><span data-stu-id="2d42d-114">You can initialize multiple pointers, as long as they are all of the same type.</span></span>  
  
```csharp
fixed (byte* ps = srcarray, pd = dstarray) {...}  
```
  
 <span data-ttu-id="2d42d-115">若要初始化不同类型的指针，只需嵌套 `fixed` 语句，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="2d42d-115">To initialize pointers of different types, simply nest `fixed` statements, as shown in the following example.</span></span>  
  
 <span data-ttu-id="2d42d-116">[!code-cs[csrefKeywordsFixedLock#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="2d42d-116">[!code-cs[csrefKeywordsFixedLock#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_3.cs)]</span></span>  
  
 <span data-ttu-id="2d42d-117">执行该语句中的代码之后，任何固定的变量都将被解锁并受垃圾回收的约束。</span><span class="sxs-lookup"><span data-stu-id="2d42d-117">After the code in the statement is executed, any pinned variables are unpinned and subject to garbage collection.</span></span> <span data-ttu-id="2d42d-118">因此，请勿指向 `fixed` 语句之外的那些变量。</span><span class="sxs-lookup"><span data-stu-id="2d42d-118">Therefore, do not point to those variables outside the `fixed` statement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2d42d-119">不能修改在固定语句中初始化的指针。</span><span class="sxs-lookup"><span data-stu-id="2d42d-119">Pointers initialized in fixed statements cannot be modified.</span></span>  
  
 <span data-ttu-id="2d42d-120">在不安全模式中，可以在堆栈上分配内存，在这种情况下，内存不受垃圾回收的约束，因此不需要固定。</span><span class="sxs-lookup"><span data-stu-id="2d42d-120">In unsafe mode, you can allocate memory on the stack, where it is not subject to garbage collection and therefore does not need to be pinned.</span></span> <span data-ttu-id="2d42d-121">有关详细信息，请参阅 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)。</span><span class="sxs-lookup"><span data-stu-id="2d42d-121">For more information, see [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d42d-122">示例</span><span class="sxs-lookup"><span data-stu-id="2d42d-122">Example</span></span>  
 <span data-ttu-id="2d42d-123">[!code-cs[csrefKeywordsFixedLock#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="2d42d-123">[!code-cs[csrefKeywordsFixedLock#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_4.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="2d42d-124">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="2d42d-124">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2d42d-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="2d42d-125">See Also</span></span>  
 <span data-ttu-id="2d42d-126">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="2d42d-126">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="2d42d-127">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="2d42d-127">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="2d42d-128">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="2d42d-128">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="2d42d-129">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="2d42d-129">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 [<span data-ttu-id="2d42d-130">固定大小的缓冲区</span><span class="sxs-lookup"><span data-stu-id="2d42d-130">Fixed Size Buffers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)


---
title: "* 运算符（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '*_CSharpKeyword'
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
caps.latest.revision: "14"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 64c32def0935f4347f9aaccc2865b9cd33dd8a70
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="222b0-102">* 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="222b0-102">* Operator (C# Reference)</span></span>
<span data-ttu-id="222b0-103">乘法运算符 (`*`)，用于计算其操作数的乘积。</span><span class="sxs-lookup"><span data-stu-id="222b0-103">The multiplication operator (`*`), which computes the product of its operands.</span></span>  <span data-ttu-id="222b0-104">此外，取消引用运算符，用于读取和写入指针。</span><span class="sxs-lookup"><span data-stu-id="222b0-104">Also, the dereference operator, which allows reading and writing to a pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="222b0-105">备注</span><span class="sxs-lookup"><span data-stu-id="222b0-105">Remarks</span></span>  
 <span data-ttu-id="222b0-106">所有数值类型都具有预定义的乘法运算符。</span><span class="sxs-lookup"><span data-stu-id="222b0-106">All numeric types have predefined multiplication operators.</span></span>  
  
 <span data-ttu-id="222b0-107">`*` 运算符还用于声明指针类型和取消引用指针。</span><span class="sxs-lookup"><span data-stu-id="222b0-107">The `*` operator is also used to declare pointer types and to dereference pointers.</span></span> <span data-ttu-id="222b0-108">此运算符仅可用于不安全的上下文，通过使用 [unsafe](../../../csharp/language-reference/keywords/unsafe.md) 关键字表示，且需要 [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) 编译器选项。</span><span class="sxs-lookup"><span data-stu-id="222b0-108">This operator can only be used in unsafe contexts, denoted by the use of the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword, and requiring the [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>  <span data-ttu-id="222b0-109">取消引用运算符也称为间接寻址运算符。</span><span class="sxs-lookup"><span data-stu-id="222b0-109">The dereference operator is also known as the indirection operator.</span></span>  
  
 <span data-ttu-id="222b0-110">用户定义的类型可以重载二元 `*` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="222b0-110">User-defined types can overload the binary `*` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="222b0-111">重载二元运算符时，也会隐式重载相应的赋值运算符（若有）。</span><span class="sxs-lookup"><span data-stu-id="222b0-111">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="222b0-112">示例</span><span class="sxs-lookup"><span data-stu-id="222b0-112">Example</span></span>  
 [!code-csharp[csRefOperators#50](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="222b0-113">示例</span><span class="sxs-lookup"><span data-stu-id="222b0-113">Example</span></span>  
 [!code-csharp[csRefOperators#51](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="222b0-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="222b0-114">See Also</span></span>  
 [<span data-ttu-id="222b0-115">C# 参考</span><span class="sxs-lookup"><span data-stu-id="222b0-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="222b0-116">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="222b0-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="222b0-117">不安全代码和指针</span><span class="sxs-lookup"><span data-stu-id="222b0-117">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [<span data-ttu-id="222b0-118">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="222b0-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

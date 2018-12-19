---
title: '* 运算符 - C# 参考'
ms.custom: seodec18
ms.date: 04/04/2018
f1_keywords:
- '*_CSharpKeyword'
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
ms.openlocfilehash: 24ac4a99c48f1e8204b821bfbf5f7fbc0a2b2f1d
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237345"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="b3b94-102">\* 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="b3b94-102">\* Operator (C# Reference)</span></span>
<span data-ttu-id="b3b94-103">乘法运算符 (`*`) 计算操作数的乘积。</span><span class="sxs-lookup"><span data-stu-id="b3b94-103">The multiplication operator (`*`) computes the product of its operands.</span></span> <span data-ttu-id="b3b94-104">所有数值类型都具有预定义的乘法运算符。</span><span class="sxs-lookup"><span data-stu-id="b3b94-104">All numeric types have predefined multiplication operators.</span></span>  

<span data-ttu-id="b3b94-105">`*` 还用作取消引用运算符，用于对指针执行读取和写入操作。</span><span class="sxs-lookup"><span data-stu-id="b3b94-105">`*` also serves as the dereference operator, which allows reading and writing to a pointer.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="b3b94-106">备注</span><span class="sxs-lookup"><span data-stu-id="b3b94-106">Remarks</span></span>  
 <span data-ttu-id="b3b94-107">`*` 运算符还用于声明指针类型和取消引用指针。</span><span class="sxs-lookup"><span data-stu-id="b3b94-107">The `*` operator is also used to declare pointer types and to dereference pointers.</span></span> <span data-ttu-id="b3b94-108">此运算符仅可用于不安全的上下文，通过使用 [unsafe](../../../csharp/language-reference/keywords/unsafe.md) 关键字表示，且需要 [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) 编译器选项。</span><span class="sxs-lookup"><span data-stu-id="b3b94-108">This operator can only be used in unsafe contexts, denoted by the use of the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword, and requiring the [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>  <span data-ttu-id="b3b94-109">取消引用运算符也称为间接寻址运算符。</span><span class="sxs-lookup"><span data-stu-id="b3b94-109">The dereference operator is also known as the indirection operator.</span></span>  
  
 <span data-ttu-id="b3b94-110">用户定义的类型可以重载二元 `*` 运算符（请参阅[运算符](../../../csharp/language-reference/keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="b3b94-110">User-defined types can overload the binary `*` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="b3b94-111">重载二元运算符时，也会隐式重载相应的赋值运算符（若有）。</span><span class="sxs-lookup"><span data-stu-id="b3b94-111">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3b94-112">示例</span><span class="sxs-lookup"><span data-stu-id="b3b94-112">Example</span></span>  
 [!code-csharp-interactive[csRefOperators#50](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="b3b94-113">示例</span><span class="sxs-lookup"><span data-stu-id="b3b94-113">Example</span></span>  
 [!code-csharp[csRefOperators#51](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="b3b94-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="b3b94-114">See Also</span></span>

- [<span data-ttu-id="b3b94-115">C# 参考</span><span class="sxs-lookup"><span data-stu-id="b3b94-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="b3b94-116">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="b3b94-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="b3b94-117">不安全代码和指针</span><span class="sxs-lookup"><span data-stu-id="b3b94-117">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
- [<span data-ttu-id="b3b94-118">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="b3b94-118">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

---
title: = 运算符（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: 9cd1af400a9afdb7942a49dee7e7f7bb78387f2d
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2018
ms.locfileid: "43477927"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="479f5-102">= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="479f5-102">= Operator (C# Reference)</span></span>
<span data-ttu-id="479f5-103">赋值运算符 (`=`) 在由左操作数表示的存储位置、属性或索引器中存储右操作数的值，并将该值作为结果返回。</span><span class="sxs-lookup"><span data-stu-id="479f5-103">The assignment operator (`=`) stores the value of its right-hand operand in the storage location, property, or indexer denoted by its left-hand operand and returns the value as its result.</span></span> <span data-ttu-id="479f5-104">操作数类型必须相同（或右操作数必须可隐式转换为左操作数的类型）。</span><span class="sxs-lookup"><span data-stu-id="479f5-104">The operands must be of the same type (or the right-hand operand must be implicitly convertible to the type of the left-hand operand).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="479f5-105">备注</span><span class="sxs-lookup"><span data-stu-id="479f5-105">Remarks</span></span>  
 <span data-ttu-id="479f5-106">赋值运算符无法重载。</span><span class="sxs-lookup"><span data-stu-id="479f5-106">The assignment operator cannot be overloaded.</span></span> <span data-ttu-id="479f5-107">但是，可定义类型的隐式转换运算符，这样可将赋值运算符用于这些类型。</span><span class="sxs-lookup"><span data-stu-id="479f5-107">However, you can define implicit conversion operators for a type, which enable you to use the assignment operator with those types.</span></span> <span data-ttu-id="479f5-108">有关详细信息，请参阅[使用转换运算符](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)。</span><span class="sxs-lookup"><span data-stu-id="479f5-108">For more information, see [Using Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="479f5-109">示例</span><span class="sxs-lookup"><span data-stu-id="479f5-109">Example</span></span>  
 [!code-csharp[csRefOperators#49](../../../csharp/language-reference/operators/codesnippet/CSharp/assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="479f5-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="479f5-110">See Also</span></span>

- [<span data-ttu-id="479f5-111">C# 参考</span><span class="sxs-lookup"><span data-stu-id="479f5-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="479f5-112">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="479f5-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="479f5-113">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="479f5-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

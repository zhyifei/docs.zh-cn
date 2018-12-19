---
title: 如何：在结构间实现用户定义的转换 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- user-defined conversions [C#]
ms.assetid: 97839aef-8fbc-40d5-9769-6b569bc2710b
ms.openlocfilehash: 85345203982679c0ab8dc9a6ae899312204c3230
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53241569"
---
# <a name="how-to-implement-user-defined-conversions-between-structs-c-programming-guide"></a><span data-ttu-id="69d0d-102">如何：在结构间实现用户定义的转换（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="69d0d-102">How to: Implement User-Defined Conversions Between Structs (C# Programming Guide)</span></span>
<span data-ttu-id="69d0d-103">本示例定义 `RomanNumeral` 和 `BinaryNumeral` 两个结构，并演示二者之间的转换。</span><span class="sxs-lookup"><span data-stu-id="69d0d-103">This example defines two structs, `RomanNumeral` and `BinaryNumeral`, and demonstrates conversions between them.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69d0d-104">示例</span><span class="sxs-lookup"><span data-stu-id="69d0d-104">Example</span></span>  
 [!code-csharp[csProgGuideStatements#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_1.cs)]  
  
## <a name="robust-programming"></a><span data-ttu-id="69d0d-105">可靠编程</span><span class="sxs-lookup"><span data-stu-id="69d0d-105">Robust Programming</span></span>  
  
-   <span data-ttu-id="69d0d-106">在上述示例中，语句：</span><span class="sxs-lookup"><span data-stu-id="69d0d-106">In the previous example, the statement:</span></span>  
  
     [!code-csharp[csProgGuideStatements#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_2.cs)]  
  
     <span data-ttu-id="69d0d-107">执行从 `RomanNumeral` 到 `BinaryNumeral` 的转换。</span><span class="sxs-lookup"><span data-stu-id="69d0d-107">performs a conversion from a `RomanNumeral` to a `BinaryNumeral`.</span></span> <span data-ttu-id="69d0d-108">因为没有从 `RomanNumeral` 到 `BinaryNumeral` 的直接转换，所以使用强制转换将 `RomanNumeral` 转换为 `int`，并使用另一个强制转换将 `int` 转换为 `BinaryNumeral`。</span><span class="sxs-lookup"><span data-stu-id="69d0d-108">Because there is no direct conversion from `RomanNumeral` to `BinaryNumeral`, a cast is used to convert from a `RomanNumeral` to an `int`, and another cast to convert from an `int` to a `BinaryNumeral`.</span></span>  
  
-   <span data-ttu-id="69d0d-109">另外，语句</span><span class="sxs-lookup"><span data-stu-id="69d0d-109">Also the statement</span></span>  
  
     [!code-csharp[csProgGuideStatements#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_3.cs)]  
  
     <span data-ttu-id="69d0d-110">执行从 `BinaryNumeral` 到 `RomanNumeral` 的转换。</span><span class="sxs-lookup"><span data-stu-id="69d0d-110">performs a conversion from a `BinaryNumeral` to a `RomanNumeral`.</span></span> <span data-ttu-id="69d0d-111">由于 `RomanNumeral` 定义了从 `BinaryNumeral` 的隐式转换，所以不需要强制转换。</span><span class="sxs-lookup"><span data-stu-id="69d0d-111">Because `RomanNumeral` defines an implicit conversion from `BinaryNumeral`, no cast is required.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69d0d-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="69d0d-112">See Also</span></span>

- [<span data-ttu-id="69d0d-113">C# 参考</span><span class="sxs-lookup"><span data-stu-id="69d0d-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="69d0d-114">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="69d0d-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="69d0d-115">转换运算符</span><span class="sxs-lookup"><span data-stu-id="69d0d-115">Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)

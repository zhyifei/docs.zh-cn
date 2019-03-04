---
title: 如何：在结构间实现用户定义的转换 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- user-defined conversions [C#]
ms.assetid: 97839aef-8fbc-40d5-9769-6b569bc2710b
ms.openlocfilehash: bc792562b4849d402e03328e50dedac030520011
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/01/2019
ms.locfileid: "57201139"
---
# <a name="how-to-implement-user-defined-conversions-between-structs-c-programming-guide"></a><span data-ttu-id="1a7cd-102">如何：在结构间实现用户定义的转换（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="1a7cd-102">How to: Implement User-Defined Conversions Between Structs (C# Programming Guide)</span></span>
<span data-ttu-id="1a7cd-103">本示例定义 `RomanNumeral` 和 `BinaryNumeral` 两个结构，并演示二者之间的转换。</span><span class="sxs-lookup"><span data-stu-id="1a7cd-103">This example defines two structs, `RomanNumeral` and `BinaryNumeral`, and demonstrates conversions between them.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1a7cd-104">示例</span><span class="sxs-lookup"><span data-stu-id="1a7cd-104">Example</span></span>  
 [!code-csharp[csProgGuideStatements#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#13)]  
  
## <a name="robust-programming"></a><span data-ttu-id="1a7cd-105">可靠编程</span><span class="sxs-lookup"><span data-stu-id="1a7cd-105">Robust Programming</span></span>  
  
-   <span data-ttu-id="1a7cd-106">在上述示例中，语句：</span><span class="sxs-lookup"><span data-stu-id="1a7cd-106">In the previous example, the statement:</span></span>  
  
     [!code-csharp[csProgGuideStatements#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#14)]  
  
     <span data-ttu-id="1a7cd-107">执行从 `RomanNumeral` 到 `BinaryNumeral` 的转换。</span><span class="sxs-lookup"><span data-stu-id="1a7cd-107">performs a conversion from a `RomanNumeral` to a `BinaryNumeral`.</span></span> <span data-ttu-id="1a7cd-108">因为没有从 `RomanNumeral` 到 `BinaryNumeral` 的直接转换，所以使用强制转换将 `RomanNumeral` 转换为 `int`，并使用另一个强制转换将 `int` 转换为 `BinaryNumeral`。</span><span class="sxs-lookup"><span data-stu-id="1a7cd-108">Because there is no direct conversion from `RomanNumeral` to `BinaryNumeral`, a cast is used to convert from a `RomanNumeral` to an `int`, and another cast to convert from an `int` to a `BinaryNumeral`.</span></span>  
  
-   <span data-ttu-id="1a7cd-109">另外，语句</span><span class="sxs-lookup"><span data-stu-id="1a7cd-109">Also the statement</span></span>  
  
     [!code-csharp[csProgGuideStatements#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#15)]  
  
     <span data-ttu-id="1a7cd-110">执行从 `BinaryNumeral` 到 `RomanNumeral` 的转换。</span><span class="sxs-lookup"><span data-stu-id="1a7cd-110">performs a conversion from a `BinaryNumeral` to a `RomanNumeral`.</span></span> <span data-ttu-id="1a7cd-111">由于 `RomanNumeral` 定义了从 `BinaryNumeral` 的隐式转换，所以不需要强制转换。</span><span class="sxs-lookup"><span data-stu-id="1a7cd-111">Because `RomanNumeral` defines an implicit conversion from `BinaryNumeral`, no cast is required.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a7cd-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="1a7cd-112">See also</span></span>

- [<span data-ttu-id="1a7cd-113">C# 参考</span><span class="sxs-lookup"><span data-stu-id="1a7cd-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="1a7cd-114">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="1a7cd-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="1a7cd-115">转换运算符</span><span class="sxs-lookup"><span data-stu-id="1a7cd-115">Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)

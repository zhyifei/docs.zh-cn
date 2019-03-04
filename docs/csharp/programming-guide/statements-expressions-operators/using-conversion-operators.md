---
title: 使用转换运算符 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [C#], operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
- implicit conversion operators [C#]
- explicit conversion operators [C#]
ms.assetid: caf36e89-c6c0-4b87-9f9e-85780a45c9a4
ms.openlocfilehash: 888339661ba1cb2e0b702f284d9f27b3217e74c1
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973153"
---
# <a name="using-conversion-operators-c-programming-guide"></a><span data-ttu-id="21ed6-102">使用转换运算符（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="21ed6-102">Using Conversion Operators (C# Programming Guide)</span></span>
<span data-ttu-id="21ed6-103">您可以使用 `implicit` 转换运算符或者 `explicit` 转换运算符，前者更易于使用，后者能向阅读代码的每个人清楚地指示您要转换类型。</span><span class="sxs-lookup"><span data-stu-id="21ed6-103">You can use `implicit` conversion operators, which are easier to use, or `explicit` conversion operators, which clearly indicate to anyone reading the code that you're converting a type.</span></span> <span data-ttu-id="21ed6-104">本主题演示转换运算符的两个类型。</span><span class="sxs-lookup"><span data-stu-id="21ed6-104">This topic demonstrates both types of conversion operator.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="21ed6-105">若要了解简单类型转换，请参阅[操作说明：将字符串转换为数字](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md)、[操作说明：将字节数组转换为 int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md)、[操作说明：在十六进制字符串与数值类型之间转换](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md)或 <xref:System.Convert>。</span><span class="sxs-lookup"><span data-stu-id="21ed6-105">For information about simple type conversions, see [How to: Convert a String to a Number](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md), [How to: Convert a byte Array to an int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [How to: Convert Between Hexadecimal Strings and Numeric Types](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md), or <xref:System.Convert>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21ed6-106">示例</span><span class="sxs-lookup"><span data-stu-id="21ed6-106">Example</span></span>  
 <span data-ttu-id="21ed6-107">这是显式转换运算符的示例。</span><span class="sxs-lookup"><span data-stu-id="21ed6-107">This is an example of an explicit conversion operator.</span></span> <span data-ttu-id="21ed6-108">此运算符从类型 <xref:System.Byte> 转换为名为 `Digit` 的值类型。</span><span class="sxs-lookup"><span data-stu-id="21ed6-108">This operator converts from the type <xref:System.Byte> to a value type called `Digit`.</span></span> <span data-ttu-id="21ed6-109">由于不是所有字节都可转换为数字，因此该转换是显式的，意味着必须使用转换，如 `Main` 方法所示。</span><span class="sxs-lookup"><span data-stu-id="21ed6-109">Because not all bytes can be converted to a digit, the conversion is explicit, meaning that a cast must be used, as shown in the `Main` method.</span></span>  
  
 [!code-csharp[csProgGuideStatements#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#11)]  
  
## <a name="example"></a><span data-ttu-id="21ed6-110">示例</span><span class="sxs-lookup"><span data-stu-id="21ed6-110">Example</span></span>  
 <span data-ttu-id="21ed6-111">此示例通过定义撤消前一示例所执行操作的转换运算符来演示隐式转换运算符：它将名为 `Digit` 的值类转换为整型 <xref:System.Byte> 类型。</span><span class="sxs-lookup"><span data-stu-id="21ed6-111">This example demonstrates an implicit conversion operator by defining a conversion operator that undoes what the previous example did: it converts from a value class called `Digit` to the integral <xref:System.Byte> type.</span></span> <span data-ttu-id="21ed6-112">由于任何数字都可转换为 <xref:System.Byte>，因此没必要非得让用户知道进行的转换。</span><span class="sxs-lookup"><span data-stu-id="21ed6-112">Because any digit can be converted to a <xref:System.Byte>, there's no need to force users to be explicit about the conversion.</span></span>  
  
 [!code-csharp[csProgGuideStatements#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#12)]  
  
## <a name="see-also"></a><span data-ttu-id="21ed6-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="21ed6-113">See also</span></span>

- [<span data-ttu-id="21ed6-114">C# 参考</span><span class="sxs-lookup"><span data-stu-id="21ed6-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="21ed6-115">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="21ed6-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="21ed6-116">转换运算符</span><span class="sxs-lookup"><span data-stu-id="21ed6-116">Conversion Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)
- [<span data-ttu-id="21ed6-117">is</span><span class="sxs-lookup"><span data-stu-id="21ed6-117">is</span></span>](../../../csharp/language-reference/keywords/is.md)

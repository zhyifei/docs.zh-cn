---
title: "使用转换运算符（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- conversions [C#], operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
- implicit conversion operators [C#]
- explicit conversion operators [C#]
ms.assetid: caf36e89-c6c0-4b87-9f9e-85780a45c9a4
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
ms.openlocfilehash: 2561b680da567623b8dab13e9e5294c3dd2c1012
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="using-conversion-operators-c-programming-guide"></a><span data-ttu-id="6e28f-102">使用转换运算符（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="6e28f-102">Using Conversion Operators (C# Programming Guide)</span></span>
<span data-ttu-id="6e28f-103">您可以使用 `implicit` 转换运算符或者 `explicit` 转换运算符，前者更易于使用，后者能向阅读代码的每个人清楚地指示您要转换类型。</span><span class="sxs-lookup"><span data-stu-id="6e28f-103">You can use `implicit` conversion operators, which are easier to use, or `explicit` conversion operators, which clearly indicate to anyone reading the code that you're converting a type.</span></span> <span data-ttu-id="6e28f-104">本主题演示转换运算符的两个类型。</span><span class="sxs-lookup"><span data-stu-id="6e28f-104">This topic demonstrates both types of conversion operator.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6e28f-105">有关简单类型转换的信息，请参阅[如何：将字符串转换为数字](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md)、[如何：将字节数组转换为 int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md)、[如何：在十六进制字符串与数值类型之间转换](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md)或 <xref:System.Convert>。</span><span class="sxs-lookup"><span data-stu-id="6e28f-105">For information about simple type conversions, see [How to: Convert a String to a Number](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md), [How to: Convert a byte Array to an int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [How to: Convert Between Hexadecimal Strings and Numeric Types](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md), or <xref:System.Convert>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e28f-106">示例</span><span class="sxs-lookup"><span data-stu-id="6e28f-106">Example</span></span>  
 <span data-ttu-id="6e28f-107">这是显式转换运算符的示例。</span><span class="sxs-lookup"><span data-stu-id="6e28f-107">This is an example of an explicit conversion operator.</span></span> <span data-ttu-id="6e28f-108">此运算符从类型 <xref:System.Byte> 转换为名为 `Digit` 的值类型。</span><span class="sxs-lookup"><span data-stu-id="6e28f-108">This operator converts from the type <xref:System.Byte> to a value type called `Digit`.</span></span> <span data-ttu-id="6e28f-109">由于不是所有字节都可转换为数字，因此该转换是显式的，意味着必须使用转换，如 `Main` 方法所示。</span><span class="sxs-lookup"><span data-stu-id="6e28f-109">Because not all bytes can be converted to a digit, the conversion is explicit, meaning that a cast must be used, as shown in the `Main` method.</span></span>  
  
 <span data-ttu-id="6e28f-110">[!code-cs[csProgGuideStatements#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-conversion-operators_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="6e28f-110">[!code-cs[csProgGuideStatements#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-conversion-operators_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e28f-111">示例</span><span class="sxs-lookup"><span data-stu-id="6e28f-111">Example</span></span>  
 <span data-ttu-id="6e28f-112">此示例通过定义撤消前一示例所执行操作的转换运算符来演示隐式转换运算符：它将名为 `Digit` 的值类转换为整型 <xref:System.Byte> 类型。</span><span class="sxs-lookup"><span data-stu-id="6e28f-112">This example demonstrates an implicit conversion operator by defining a conversion operator that undoes what the previous example did: it converts from a value class called `Digit` to the integral <xref:System.Byte> type.</span></span> <span data-ttu-id="6e28f-113">由于任何数字都可转换为 <xref:System.Byte>，因此没必要非得让用户知道进行的转换。</span><span class="sxs-lookup"><span data-stu-id="6e28f-113">Because any digit can be converted to a <xref:System.Byte>, there's no need to force users to be explicit about the conversion.</span></span>  
  
 <span data-ttu-id="6e28f-114">[!code-cs[csProgGuideStatements#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-conversion-operators_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="6e28f-114">[!code-cs[csProgGuideStatements#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-conversion-operators_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e28f-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e28f-115">See Also</span></span>  
 <span data-ttu-id="6e28f-116">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="6e28f-116">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="6e28f-117">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="6e28f-117">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="6e28f-118">[转换运算符](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md) </span><span class="sxs-lookup"><span data-stu-id="6e28f-118">[Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md) </span></span>  
 [<span data-ttu-id="6e28f-119">is</span><span class="sxs-lookup"><span data-stu-id="6e28f-119">is</span></span>](../../../csharp/language-reference/keywords/is.md)


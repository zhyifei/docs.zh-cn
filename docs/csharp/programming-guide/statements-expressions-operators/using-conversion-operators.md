---
title: 使用转换运算符（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [C#], operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
- implicit conversion operators [C#]
- explicit conversion operators [C#]
ms.assetid: caf36e89-c6c0-4b87-9f9e-85780a45c9a4
ms.openlocfilehash: e03fb12200bc15de9c1686edd40921201598621f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33332301"
---
# <a name="using-conversion-operators-c-programming-guide"></a>使用转换运算符（C# 编程指南）
您可以使用 `implicit` 转换运算符或者 `explicit` 转换运算符，前者更易于使用，后者能向阅读代码的每个人清楚地指示您要转换类型。 本主题演示转换运算符的两个类型。  
  
> [!NOTE]
>  有关简单类型转换的信息，请参阅[如何：将字符串转换为数字](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md)、[如何：将字节数组转换为 int](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md)、[如何：在十六进制字符串与数值类型之间转换](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md)或 <xref:System.Convert>。  
  
## <a name="example"></a>示例  
 这是显式转换运算符的示例。 此运算符从类型 <xref:System.Byte> 转换为名为 `Digit` 的值类型。 由于不是所有字节都可转换为数字，因此该转换是显式的，意味着必须使用转换，如 `Main` 方法所示。  
  
 [!code-csharp[csProgGuideStatements#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-conversion-operators_1.cs)]  
  
## <a name="example"></a>示例  
 此示例通过定义撤消前一示例所执行操作的转换运算符来演示隐式转换运算符：它将名为 `Digit` 的值类转换为整型 <xref:System.Byte> 类型。 由于任何数字都可转换为 <xref:System.Byte>，因此没必要非得让用户知道进行的转换。  
  
 [!code-csharp[csProgGuideStatements#12](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-conversion-operators_2.cs)]  
  
## <a name="see-also"></a>请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [转换运算符](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)  
 [is](../../../csharp/language-reference/keywords/is.md)

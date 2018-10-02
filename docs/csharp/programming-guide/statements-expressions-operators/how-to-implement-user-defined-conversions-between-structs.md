---
title: 如何：在结构间实现用户定义的转换（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- user-defined conversions [C#]
ms.assetid: 97839aef-8fbc-40d5-9769-6b569bc2710b
ms.openlocfilehash: cff85d60c1b59f4d1ca028f8fc02fee5728fa3d6
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2018
ms.locfileid: "46696647"
---
# <a name="how-to-implement-user-defined-conversions-between-structs-c-programming-guide"></a>如何：在结构间实现用户定义的转换（C# 编程指南）
本示例定义 `RomanNumeral` 和 `BinaryNumeral` 两个结构，并演示二者之间的转换。  
  
## <a name="example"></a>示例  
 [!code-csharp[csProgGuideStatements#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_1.cs)]  
  
## <a name="robust-programming"></a>可靠编程  
  
-   在上述示例中，语句：  
  
     [!code-csharp[csProgGuideStatements#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_2.cs)]  
  
     执行从 `RomanNumeral` 到 `BinaryNumeral` 的转换。 因为没有从 `RomanNumeral` 到 `BinaryNumeral` 的直接转换，所以使用强制转换将 `RomanNumeral` 转换为 `int`，并使用另一个强制转换将 `int` 转换为 `BinaryNumeral`。  
  
-   另外，语句  
  
     [!code-csharp[csProgGuideStatements#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-implement-user-defined-conversions-between-structs_3.cs)]  
  
     执行从 `BinaryNumeral` 到 `RomanNumeral` 的转换。 由于 `RomanNumeral` 定义了从 `BinaryNumeral` 的隐式转换，所以不需要强制转换。  
  
## <a name="see-also"></a>请参阅

- [C# 参考](../../../csharp/language-reference/index.md)  
- [C# 编程指南](../../../csharp/programming-guide/index.md)  
- [转换运算符](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)

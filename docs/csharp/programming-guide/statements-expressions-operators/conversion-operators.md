---
title: "转换运算符（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- C# language, conversion operators
- conversion operators [C#]
- operators [C#], conversion
- user-defined conversions [C#]
ms.assetid: c5ad73a3-d57b-4d2b-b4c9-24e3c2856efc
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 056971dcd648208d77573c180df28ffdd46788c5
ms.sourcegitcommit: 22a48b64a0150a60b00b4fc4d8c62cde7f1670c4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2018
---
# <a name="conversion-operators-c-programming-guide"></a>转换运算符（C# 编程指南）
C# 允许程序员在类或结构上声明转换，以便类或结构能够与其他类或结构或者基本类型进行相互转换。 以类似于运算符的方式定义转换，并根据它们所转换为的类型命名。 要转换的参数类型或转换结果的类型必须是包含类型（但不能两者同时都是）。  
  
 [!code-csharp[csProgGuideStatements#10](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/conversion-operators_1.cs)]  
  
## <a name="conversion-operators-overview"></a>转换运算符概述  
 转换运算符具有以下属性：  
  
-   声明为 `implicit` 的转换在需要时自动执行。  
  
-   声明为 `explicit` 的转换需要调用强制转换。  
  
-   所有转换都必须都声明为 `static`。  
  
## <a name="related-sections"></a>相关章节  
 更多相关信息：  
  
-   [使用转换运算符](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)  
  
-   [强制转换和类型转换](../../../csharp/programming-guide/types/casting-and-type-conversions.md)  
  
-   [如何：在结构之间实现用户定义的转换](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
  
-   [explicit](../../../csharp/language-reference/keywords/explicit.md)  
  
-   [implicit](../../../csharp/language-reference/keywords/implicit.md)  
  
-   [static](../../../csharp/language-reference/keywords/static.md)  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Convert>  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [Chained user-defined explicit conversions in C#](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)（C# 中链接在一起的用户定义的显式转换）

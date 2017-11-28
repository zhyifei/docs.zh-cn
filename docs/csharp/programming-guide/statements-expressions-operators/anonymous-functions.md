---
title: "匿名函数（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- lambda expressions [C#], as anonymus functions
- anonymous functions [C#]
- anonymous methods [C#]
ms.assetid: 6ce3f04d-0c71-4728-9127-634c7e9a8365
caps.latest.revision: "14"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 888743bb1c49df123b57b4d09e0251dbe1e049d3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="anonymous-functions-c-programming-guide"></a>匿名函数（C# 编程指南）
匿名函数是一个“内联”语句或表达式，可在需要委托类型的任何地方使用。 可以使用匿名函数来初始化命名委托，或传递命名委托（而不是命名委托类型）作为方法参数。  
  
 共有两种匿名函数，以下主题中分别讨论了这些函数：  
  
-   [Lambda 表达式](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)。  
  
-   [匿名方法](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)  
  
    > [!NOTE]
    >  Lambda 表达式可以绑定到表达式树，也可以绑定到委托。  
  
## <a name="the-evolution-of-delegates-in-c"></a>C# 中委托的发展  
 在 C# 1.0 中，通过使用在代码中其他位置定义的方法显式初始化委托来创建委托的实例。 C# 2.0 引入了匿名方法的概念，作为一种编写可在委托调用中执行的未命名内联语句块的方式。 C# 3.0 引入了 lambda 表达式，这种表达式与匿名方法的概念类似，但更具表现力并且更简练。 这两个功能统称为*匿名函数*。 通常，面向 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 3.5 及更高版本的应用程序应使用 lambda 表达式。  
  
 下面的示例演示从 C# 1.0 到 C# 3.0 委托创建过程的发展：  
  
 [!code-csharp[csProgGuideLINQ#65](../../../csharp/programming-guide/arrays/codesnippet/CSharp/anonymous-functions_1.cs)]  
  
## <a name="c-language-specification"></a>C# 语言规范  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 [语句、表达式和运算符](../../../csharp/programming-guide/statements-expressions-operators/index.md)  
 [Lambda 表达式](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)  
 [委托](../../../csharp/programming-guide/delegates/index.md)  
 [表达式树](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b)

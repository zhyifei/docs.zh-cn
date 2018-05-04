---
title: 命名空间（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
ms.openlocfilehash: 60e4c6e98ca9e71d1a095a0c7ee1df6be6d13f4b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="namespaces-c-programming-guide"></a>命名空间（C# 编程指南）
在 C# 编程中，命名空间在两个方面被大量使用。 首先，.NET Framework 使用命名空间来组织许多类，如下所示：  
  
 [!code-csharp[csProgGuide#22](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_1.cs)]  
  
 `System` 是一个命名空间，`Console` 是该命名空间中的一个类。 可以使用 `using` 关键字，如此则不必使用完整的名称，如下例所示：  
  
 [!code-csharp[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_2.cs)]  
  
 [!code-csharp[csProgGuide#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/index_3.cs)]  
  
 有关详细信息，请参阅 [using 指令](../../../csharp/language-reference/keywords/using-directive.md)。  
  
 其次，在较大的编程项目中，声明自己的命名空间可以帮助控制类和方法名称的范围。 使用 [namespace](../../../csharp/language-reference/keywords/namespace.md) 关键字可声明命名空间，如下例所示：  
  
 [!code-csharp[csProgGuideNamespaces#6](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/index_4.cs)]  
  
## <a name="namespaces-overview"></a>命名空间概述  
 命名空间具有以下属性：  
  
-   它们组织大型代码项目。  
  
-   通过使用 `.` 运算符分隔它们。  
  
-   使用 `using directive` 可免去为每个类指定名称空间的名称。  
  
-   `global` 命名空间是“根”命名空间：`global::System` 始终引用 .NET Framework 命名空间 `System`。  
  
## <a name="related-sections"></a>相关章节  
 有关命名空间的详细信息，请参阅以下主题：  
  
-   [使用命名空间](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
  
-   [如何：使用全局命名空间别名](../../../csharp/programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)  
  
-   [如何：使用 My 命名空间](../../../csharp/programming-guide/namespaces/how-to-use-the-my-namespace.md)  
  
## <a name="c-language-specification"></a>C# 语言规范  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [命名空间关键字](../../../csharp/language-reference/keywords/namespace-keywords.md)  
 [using 指令](../../../csharp/language-reference/keywords/using-directive.md)  
 [:: 运算符](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)  
 [。运算符](../../../csharp/language-reference/operators/member-access-operator.md)

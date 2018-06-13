---
title: 如何：使用全局命名空间别名（C# 编程指南）
ms.date: 07/20/2015
helpviewer_keywords:
- aliases [C#]
- namespaces [C#], global namespace qualifier
- global namespace [C#]
ms.assetid: 98a1d89b-3c5a-44f7-8400-c4a3c0ec22a9
ms.openlocfilehash: 74f51d18ddda1ae4706b78aaf713683d2e505d2e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33327237"
---
# <a name="how-to-use-the-global-namespace-alias-c-programming-guide"></a>如何：使用全局命名空间别名（C# 编程指南）
当具有同一名称的其他实体可能隐藏了成员时，访问全局[命名空间](../../../csharp/language-reference/keywords/namespace.md)中的成员的功能将十分有用。  
  
 例如，在下面的代码中，`Console` 解析为 `TestApp.Console` 而不是 <xref:System> 命名空间中的 `Console` 类型。  
  
 [!code-csharp[csProgGuide#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/how-to-use-the-global-namespace-alias_1.cs)]  
  
 [!code-csharp[csProgGuideNamespaces#1](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_2.cs)]  
  
 使用 `System.Console` 仍会导致错误，因为类 `TestApp.System` 隐藏了 `System` 命名空间：  
  
 [!code-csharp[csProgGuideNamespaces#2](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_3.cs)]  
  
 但是，可以使用 `global::System.Console` 解决此错误，如下所示：  
  
 [!code-csharp[csProgGuideNamespaces#3](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_4.cs)]  
  
 如果左标识符为 `global`，则会在全局命名空间开始搜索右标识符。 例如，以下声明引用 `TestApp` 作为全局空间的成员。  
  
 [!code-csharp[csProgGuideNamespaces#4](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_5.cs)]  
  
 显然，不建议将自己的命名空间的名称创建为 `System`，并且不可能会遇到发生此情况的代码。 但是，在大型项目中，很有可能会以一种或另一种形式发生命名空间重复。 在这些情况下，全局命名空间限定符可保证指定根命名空间。  
  
## <a name="example"></a>示例  
 在此示例中，命名空间 `System` 用于包括类 `TestClass`，因此， `global::System.Console` 必须用于引用 `System.Console` 类，该类由 `System` 命名空间隐藏。 此外，别名 `colAlias` 用于引用命名空间 `System.Collections`；因此，<xref:System.Collections.Hashtable?displayProperty=nameWithType> 实例是使用此别名而不是命名空间创建的。  
  
 [!code-csharp[csProgGuideNamespaces#5](../../../csharp/programming-guide/namespaces/codesnippet/CSharp/how-to-use-the-global-namespace-alias_6.cs)]  
  
 A 1  
B 2  
C 3   
## <a name="see-also"></a>请参阅  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [命名空间](../../../csharp/programming-guide/namespaces/index.md)  
 [。运算符](../../../csharp/language-reference/operators/member-access-operator.md)  
 [:: 运算符](../../../csharp/language-reference/operators/namespace-alias-qualifer.md)  
 [extern](../../../csharp/language-reference/keywords/extern.md)

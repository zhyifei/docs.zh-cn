---
title: 命名空间（C# 编程指南）
ms.date: 08/21/2018
helpviewer_keywords:
- C# language, namespaces
- namespaces [C#]
ms.assetid: b1c4ab46-3fad-4ffa-9deb-dd50a2d8c65a
ms.openlocfilehash: c4011092a6c605137053b544d4b9f14cce2fdb4c
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2018
ms.locfileid: "45560277"
---
# <a name="namespaces-c-programming-guide"></a>命名空间（C# 编程指南）

在 C# 编程中，命名空间在两个方面被大量使用。 首先，.NET Framework 使用命名空间来组织许多类，如下所示：  
  
[!code-csharp[csProgGuide#22](../inside-a-program/codesnippet/CSharp/index_1.cs)]  
  
`System` 是一个命名空间，`Console` 是该命名空间中的一个类。 可以使用 `using` 关键字，如此则不必使用完整的名称，如下例所示：  
  
[!code-csharp[csProgGuide#1](../inside-a-program/codesnippet/CSharp/index_2.cs)]  
  
[!code-csharp[csProgGuide#25](../inside-a-program/codesnippet/CSharp/index_3.cs)]  
  
有关详细信息，请参阅 [using 指令](../../language-reference/keywords/using-directive.md)。  
  
其次，在较大的编程项目中，声明自己的命名空间可以帮助控制类和方法名称的范围。 使用 [namespace](../../language-reference/keywords/namespace.md) 关键字可声明命名空间，如下例所示：  
  
[!code-csharp[csProgGuideNamespaces#6](codesnippet/CSharp/index_4.cs)]

命名空间的名称必须是有效的 C# [标识符名称](../inside-a-program/identifier-names.md)。

## <a name="namespaces-overview"></a>命名空间概述  

命名空间具有以下属性：  
  
- 它们组织大型代码项目。  
- 通过使用 `.` 运算符分隔它们。  
- 使用 `using directive` 可免去为每个类指定名称空间的名称。  
- `global` 命名空间是“根”命名空间：`global::System` 始终引用 .NET Framework 命名空间 `System`。  

## <a name="c-language-specification"></a>C# 语言规范

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>请参阅

- [使用命名空间](using-namespaces.md)
- [如何：使用全局命名空间别名](how-to-use-the-global-namespace-alias.md)
- [如何：使用 My 命名空间](how-to-use-the-my-namespace.md)
- [C# 编程指南](../index.md)  
- [标识符名称](../inside-a-program/identifier-names.md)
- [命名空间关键字](../../language-reference/keywords/namespace-keywords.md)  
- [using 指令](../../language-reference/keywords/using-directive.md)  
- [:: 运算符](../../language-reference/operators/namespace-alias-qualifer.md)  
- [。运算符](../../language-reference/operators/member-access-operator.md)
>>>>>>> 添加标识符命名规则

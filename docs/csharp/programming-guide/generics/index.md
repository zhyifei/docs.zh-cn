---
title: 泛型 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generics
- generics [C#]
ms.assetid: 75ea8509-a4ea-4e7a-a2b3-cf72482e9282
ms.openlocfilehash: e32eb7c60e01ca72824ffb3a1e1269cf34650f5a
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/31/2019
ms.locfileid: "66423402"
---
# <a name="generics-c-programming-guide"></a>泛型（C# 编程指南）
C# 语言和公共语言运行时 (CLR) 的 2.0 版本中添加了泛型。 泛型将类型参数的概念引入 .NET Framework，这样就可以设计具有以下特征的类和方法：在客户端代码声明并初始化这些类和方法之前，这些类和方法会延迟指定一个或多个类型。 例如，通过使用泛型类型参数 T，可以编写其他客户端代码能够使用的单个类，而不会产生运行时转换或装箱操作的成本或风险，如下所示：  
  
 [!code-csharp[csProgGuideGenerics#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#1)]  

泛型类和泛型方法兼具可重用性、类型安全性和效率，这是非泛型类和非泛型方法无法实现的。 泛型通常与集合以及作用于集合的方法一起使用。 .NET Framework 2.0 版类库提供新的命名空间 <xref:System.Collections.Generic>，其中包含几个新的基于泛型的集合类。 建议所有定目标到 .NET Framework 2.0 及更高版本的应用程序都使用新增的泛型集合类，而不是旧的非泛型集合类（如 <xref:System.Collections.ArrayList>）。 有关详细信息，请参阅 [.NET 中的泛型](../../../standard/generics/index.md)。  
  
 当然，也可以创建自定义泛型类型和泛型方法，以提供自己的通用解决方案，设计类型安全的高效模式。 以下代码示例演示了出于演示目的的简单泛型链接列表类。 （大多数情况下，应使用 .NET Framework 类库提供的 <xref:System.Collections.Generic.List%601> 类，而不是自行创建类。）在通常使用具体类型来指示列表中所存储项的类型的情况下，可使用类型参数 `T`。 其使用方法如下：  
  
- 在 `AddHead` 方法中作为方法参数的类型。  
  
- 在 `Node` 嵌套类中作为 `Data` 属性的返回类型。  
  
- 在嵌套类中作为私有成员 `data` 的类型。  
  
 请注意，T 可用于 `Node` 嵌套类。 如果使用具体类型实例化 `GenericList<T>`（例如，作为 `GenericList<int>`），则出现的所有 `T` 都将替换为 `int`。  
  
 [!code-csharp[csProgGuideGenerics#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#2)]  
  
 以下代码示例演示了客户端代码如何使用泛型 `GenericList<T>` 类来创建整数列表。 只需更改类型参数，即可轻松修改以下代码，创建字符串或任何其他自定义类型的列表：  
  
 [!code-csharp[csProgGuideGenerics#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#3)]  
  
## <a name="generics-overview"></a>泛型概述  
  
- 使用泛型类型可以最大限度地重用代码、保护类型安全性以及提高性能。  
  
- 泛型最常见的用途是创建集合类。  
  
- .NET Framework 类库在 <xref:System.Collections.Generic> 命名空间中包含几个新的泛型集合类。 应尽可能使用这些类来代替某些类，如 <xref:System.Collections> 命名空间中的 <xref:System.Collections.ArrayList>。  
  
- 可以创建自己的泛型接口、泛型类、泛型方法、泛型事件和泛型委托。  
  
- 可以对泛型类进行约束以访问特定数据类型的方法。  
  
- 在泛型数据类型中所用类型的信息可在运行时通过使用反射来获取。  
  
## <a name="related-sections"></a>相关章节  
 更多相关信息：  
  
- [泛型类型参数](../../../csharp/programming-guide/generics/generic-type-parameters.md)  
  
- [类型参数的约束](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)  
  
- [泛型类](../../../csharp/programming-guide/generics/generic-classes.md)  
  
- [泛型接口](../../../csharp/programming-guide/generics/generic-interfaces.md)  
  
- [泛型方法](../../../csharp/programming-guide/generics/generic-methods.md)  
  
- [泛型委托](../../../csharp/programming-guide/generics/generic-delegates.md)  
  
- [C++ 模板和 C# 泛型之间的区别](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)  
  
- [泛型和反射](../../../csharp/programming-guide/generics/generics-and-reflection.md)  
  
- [运行时中的泛型](../../../csharp/programming-guide/generics/generics-in-the-run-time.md)  
  
## <a name="c-language-specification"></a>C# 语言规范  
 有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/types.md#constructed-types)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Collections.Generic>
- [C# 编程指南](../../../csharp/programming-guide/index.md)
- [类型](../../../csharp/programming-guide/types/index.md)
- [\<typeparam>](../../../csharp/programming-guide/xmldoc/typeparam.md)
- [\<typeparamref>](../../../csharp/programming-guide/xmldoc/typeparamref.md)
- [.NET 中的泛型](../../../standard/generics/index.md)

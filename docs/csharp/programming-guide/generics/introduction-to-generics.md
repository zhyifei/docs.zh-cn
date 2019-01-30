---
title: 泛型介绍 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], about generics
ms.assetid: a1ad761e-42f7-41dd-a62f-452a2de26b9d
ms.openlocfilehash: ed767ca100ee0405ce918d2d842d951f09d19e7a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54646339"
---
# <a name="introduction-to-generics-c-programming-guide"></a>泛型介绍（C# 编程指南）
泛型类和泛型方法兼具可重用性、类型安全性和效率，这是非泛型类和非泛型方法无法实现的。 泛型通常与集合以及作用于集合的方法一起使用。 .NET Framework 2.0 版类库提供新的命名空间 <xref:System.Collections.Generic>，其中包含几个新的基于泛型的集合类。 建议所有定目标到 .NET Framework 2.0 及更高版本的应用程序都使用新增的泛型集合类，而不是旧的非泛型集合类（如 <xref:System.Collections.ArrayList>）。 有关详细信息，请参阅 [.NET 中的泛型](../../../standard/generics/index.md)。  
  
 当然，也可以创建自定义泛型类型和泛型方法，以提供自己的通用解决方案，设计类型安全的高效模式。 以下代码示例演示了出于演示目的的简单泛型链接列表类。 （大多数情况下，应使用 .NET Framework 类库提供的 <xref:System.Collections.Generic.List%601> 类，而不是自行创建类。）在通常使用具体类型来指示列表中所存储项的类型的情况下，可使用类型参数 `T`。 其使用方法如下：  
  
-   在 `AddHead` 方法中作为方法参数的类型。  
  
-   在 `Node` 嵌套类中作为 `Data` 属性的返回类型。  
  
-   在嵌套类中作为私有成员 `data` 的类型。  
  
 请注意，T 可用于 `Node` 嵌套类。 如果使用具体类型实例化 `GenericList<T>`（例如，作为 `GenericList<int>`），则出现的所有 `T` 都将替换为 `int`。  
  
 [!code-csharp[csProgGuideGenerics#2](../../../csharp/programming-guide/generics/codesnippet/CSharp/introduction-to-generics_1.cs)]  
  
 以下代码示例演示了客户端代码如何使用泛型 `GenericList<T>` 类来创建整数列表。 只需更改类型参数，即可轻松修改以下代码，创建字符串或任何其他自定义类型的列表：  
  
 [!code-csharp[csProgGuideGenerics#3](../../../csharp/programming-guide/generics/codesnippet/CSharp/introduction-to-generics_2.cs)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Collections.Generic>
- [C# 编程指南](../../../csharp/programming-guide/index.md)
- [泛型](../../../csharp/programming-guide/generics/index.md)

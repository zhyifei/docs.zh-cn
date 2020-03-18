---
title: 如何使用集合初始值设定项初始化字典 - C# 编程指南
ms.date: 12/20/2018
helpviewer_keywords:
- collection initializers [C#], with Dictionary
ms.assetid: 25283922-f8ee-40dc-a639-fac30804ec71
ms.openlocfilehash: 1e6e7fac9dd49ad1943ac9046bd9e4932c383257
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "75741366"
---
# <a name="how-to-initialize-a-dictionary-with-a-collection-initializer-c-programming-guide"></a>如何使用集合初始值设定项初始化字典（C# 编程指南）

<xref:System.Collections.Generic.Dictionary%602> 包含键/值对集合。 其 <xref:System.Collections.Generic.Dictionary%602.Add%2A> 方法采用两个参数，一个用于键，一个用于值。 若要初始化 <xref:System.Collections.Generic.Dictionary%602> 或其 `Add` 方法采用多个参数的任何集合，一种方法是将每组参数括在大括号中，如下面的示例中所示。 另一种方法是使用索引初始值设定项，如下面的示例所示。

## <a name="example"></a>示例

在下面的代码示例中，使用类型 <xref:System.Collections.Generic.Dictionary%602> 的实例初始化 `StudentName`。  第一个初始化使用具有两个参数的 `Add` 方法。 编译器为每对 `Add` 键和 `int` 值生成对 `StudentName` 的调用。 第二个初始化使用 `Dictionary` 类的公共读取/写入索引器方法：

[!code-csharp[InitializerExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToDictionaryInitializer.cs#HowToDictionaryInitializer)]  

请注意，在第一个声明中，集合中的每个元素有两对大括号。 最内层的大括号中的是 `StudentName` 的对象初始值设定项，最外层的大括号中的是要添加到 `students` <xref:System.Collections.Generic.Dictionary%602> 的键/值对的初始值设定项。 最后，字典的整个集合初始值设定项被括在大括号中。 在第二个初始化中，左侧赋值是键，右侧是将对象初始值设定项用于 `StudentName` 的值。

## <a name="see-also"></a>另请参阅

- [C# 编程指南](../index.md)
- [对象和集合初始值设定项](./object-and-collection-initializers.md)

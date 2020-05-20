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
# <a name="how-to-initialize-a-dictionary-with-a-collection-initializer-c-programming-guide"></a><span data-ttu-id="56ed4-102">如何使用集合初始值设定项初始化字典（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="56ed4-102">How to initialize a dictionary with a collection initializer (C# Programming Guide)</span></span>

<span data-ttu-id="56ed4-103"><xref:System.Collections.Generic.Dictionary%602> 包含键/值对集合。</span><span class="sxs-lookup"><span data-stu-id="56ed4-103">A <xref:System.Collections.Generic.Dictionary%602> contains a collection of key/value pairs.</span></span> <span data-ttu-id="56ed4-104">其 <xref:System.Collections.Generic.Dictionary%602.Add%2A> 方法采用两个参数，一个用于键，一个用于值。</span><span class="sxs-lookup"><span data-stu-id="56ed4-104">Its <xref:System.Collections.Generic.Dictionary%602.Add%2A> method takes two parameters, one for the key and one for the value.</span></span> <span data-ttu-id="56ed4-105">若要初始化 <xref:System.Collections.Generic.Dictionary%602> 或其 `Add` 方法采用多个参数的任何集合，一种方法是将每组参数括在大括号中，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="56ed4-105">One way to initialize a <xref:System.Collections.Generic.Dictionary%602>, or any collection whose `Add` method takes multiple parameters, is to enclose each set of parameters in braces as shown in the following example.</span></span> <span data-ttu-id="56ed4-106">另一种方法是使用索引初始值设定项，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="56ed4-106">Another option is to use an index initializer, also shown in the following example.</span></span>

## <a name="example"></a><span data-ttu-id="56ed4-107">示例</span><span class="sxs-lookup"><span data-stu-id="56ed4-107">Example</span></span>

<span data-ttu-id="56ed4-108">在下面的代码示例中，使用类型 `StudentName` 的实例初始化 <xref:System.Collections.Generic.Dictionary%602>。</span><span class="sxs-lookup"><span data-stu-id="56ed4-108">In the following code example, a <xref:System.Collections.Generic.Dictionary%602> is initialized with instances of type `StudentName`.</span></span>  <span data-ttu-id="56ed4-109">第一个初始化使用具有两个参数的 `Add` 方法。</span><span class="sxs-lookup"><span data-stu-id="56ed4-109">The first initialization uses the `Add` method with two arguments.</span></span> <span data-ttu-id="56ed4-110">编译器为每对 `int` 键和 `StudentName` 值生成对 `Add` 的调用。</span><span class="sxs-lookup"><span data-stu-id="56ed4-110">The compiler generates a call to `Add` for each of the pairs of `int` keys and `StudentName` values.</span></span> <span data-ttu-id="56ed4-111">第二个初始化使用 `Dictionary` 类的公共读取/写入索引器方法：</span><span class="sxs-lookup"><span data-stu-id="56ed4-111">The second uses a public read / write indexer method of the `Dictionary` class:</span></span>

[!code-csharp[InitializerExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToDictionaryInitializer.cs#HowToDictionaryInitializer)]  

<span data-ttu-id="56ed4-112">请注意，在第一个声明中，集合中的每个元素有两对大括号。</span><span class="sxs-lookup"><span data-stu-id="56ed4-112">Note the two pairs of braces in each element of the collection in the first declaration.</span></span> <span data-ttu-id="56ed4-113">最内层的大括号中的是 `StudentName` 的对象初始值设定项，最外层的大括号中的是要添加到 `students` <xref:System.Collections.Generic.Dictionary%602> 的键/值对的初始值设定项。</span><span class="sxs-lookup"><span data-stu-id="56ed4-113">The innermost braces enclose the object initializer for the `StudentName`, and the outermost braces enclose the initializer for the key/value pair that will be added to the `students` <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="56ed4-114">最后，字典的整个集合初始值设定项被括在大括号中。</span><span class="sxs-lookup"><span data-stu-id="56ed4-114">Finally, the whole collection initializer for the dictionary is enclosed in braces.</span></span> <span data-ttu-id="56ed4-115">在第二个初始化中，左侧赋值是键，右侧是将对象初始值设定项用于 `StudentName` 的值。</span><span class="sxs-lookup"><span data-stu-id="56ed4-115">In the second initialization, the left side of the assignment is the key and the right side is the value, using an object initializer for `StudentName`.</span></span>

## <a name="see-also"></a><span data-ttu-id="56ed4-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="56ed4-116">See also</span></span>

- [<span data-ttu-id="56ed4-117">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="56ed4-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="56ed4-118">对象和集合初始值设定项</span><span class="sxs-lookup"><span data-stu-id="56ed4-118">Object and Collection Initializers</span></span>](./object-and-collection-initializers.md)

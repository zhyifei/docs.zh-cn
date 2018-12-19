---
title: 如何使用集合初始值设定项初始化字典 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [C#], with Dictionary
ms.assetid: 25283922-f8ee-40dc-a639-fac30804ec71
ms.openlocfilehash: 42deee85b3a425531ddadfa96cfaff6d342d1221
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243876"
---
# <a name="how-to-initialize-a-dictionary-with-a-collection-initializer-c-programming-guide"></a><span data-ttu-id="7b86b-102">如何使用集合初始值设定项初始化字典（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="7b86b-102">How to initialize a dictionary with a collection initializer (C# Programming Guide)</span></span>

<span data-ttu-id="7b86b-103"><xref:System.Collections.Generic.Dictionary%602> 包含键/值对集合。</span><span class="sxs-lookup"><span data-stu-id="7b86b-103">A <xref:System.Collections.Generic.Dictionary%602> contains a collection of key/value pairs.</span></span> <span data-ttu-id="7b86b-104">其 <xref:System.Collections.Generic.Dictionary%602.Add*> 方法采用两个参数，一个用于键，一个用于值。</span><span class="sxs-lookup"><span data-stu-id="7b86b-104">Its <xref:System.Collections.Generic.Dictionary%602.Add*> method takes two parameters, one for the key and one for the value.</span></span> <span data-ttu-id="7b86b-105">若要初始化 <xref:System.Collections.Generic.Dictionary%602> 或其 `Add` 方法采用多个参数的任何集合，请将每组参数括在大括号中，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="7b86b-105">To initialize a <xref:System.Collections.Generic.Dictionary%602>, or any collection whose `Add` method takes multiple parameters, enclose each set of parameters in braces as shown in the following example.</span></span>

## <a name="example"></a><span data-ttu-id="7b86b-106">示例</span><span class="sxs-lookup"><span data-stu-id="7b86b-106">Example</span></span>

<span data-ttu-id="7b86b-107">在下面的代码示例中，使用类型 `StudentName` 的实例初始化 <xref:System.Collections.Generic.Dictionary%602>。</span><span class="sxs-lookup"><span data-stu-id="7b86b-107">In the following code example, a <xref:System.Collections.Generic.Dictionary%602> is initialized with instances of type `StudentName`.</span></span>  
  
[!code-csharp[csProgGuideLINQ#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-a-dictionary-with-a-collection-initializer_1.cs)]

<span data-ttu-id="7b86b-108">请注意，集合中的每个元素有两对大括号。</span><span class="sxs-lookup"><span data-stu-id="7b86b-108">Note the two pairs of braces in each element of the collection.</span></span> <span data-ttu-id="7b86b-109">最内层的大括号中的是 `StudentName` 的对象初始值设定项，最外层的大括号中的是要添加到 `students` <xref:System.Collections.Generic.Dictionary%602> 的键/值对的初始值设定项。</span><span class="sxs-lookup"><span data-stu-id="7b86b-109">The innermost braces enclose the object initializer for the `StudentName`, and the outermost braces enclose the initializer for the key/value pair that will be added to the `students` <xref:System.Collections.Generic.Dictionary%602>.</span></span> <span data-ttu-id="7b86b-110">最后，字典的整个集合初始值设定项被括在大括号中。</span><span class="sxs-lookup"><span data-stu-id="7b86b-110">Finally, the whole collection initializer for the dictionary is enclosed in braces.</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="7b86b-111">编译代码</span><span class="sxs-lookup"><span data-stu-id="7b86b-111">Compiling the code</span></span>

<span data-ttu-id="7b86b-112">若要运行此代码，请将该类复制并粘贴到已在 Visual Studio 中创建的 Visual C# 控制台应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="7b86b-112">To run this code, copy and paste the class into a Visual C# console application project that has been created in Visual Studio.</span></span> <span data-ttu-id="7b86b-113">默认情况下，此项目面向 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 3.5 版，并且具有对 System.Core.dll 的引用和一个用于 System.Linq 的 using 指令。</span><span class="sxs-lookup"><span data-stu-id="7b86b-113">By default, this project targets version 3.5 of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], and it has a reference to System.Core.dll and a using directive for System.Linq.</span></span> <span data-ttu-id="7b86b-114">如果项目中缺少其中一个或多个要求，则可以手动添加它们。</span><span class="sxs-lookup"><span data-stu-id="7b86b-114">If one or more of these requirements are missing from the project, you can add them manually.</span></span>

## <a name="see-also"></a><span data-ttu-id="7b86b-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="7b86b-115">See also</span></span>

- [<span data-ttu-id="7b86b-116">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="7b86b-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="7b86b-117">对象和集合初始值设定项</span><span class="sxs-lookup"><span data-stu-id="7b86b-117">Object and Collection Initializers</span></span>](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)

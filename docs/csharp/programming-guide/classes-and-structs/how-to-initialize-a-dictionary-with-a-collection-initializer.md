---
title: "如何：使用集合初始值设定项初始化字典（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- collection initializers [C#], with Dictionary
ms.assetid: 25283922-f8ee-40dc-a639-fac30804ec71
caps.latest.revision: 10
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 41d6a9934daaa1274901e20de58cfd480c904bfa
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-initialize-a-dictionary-with-a-collection-initializer-c-programming-guide"></a><span data-ttu-id="30f4c-102">如何：使用集合初始值设定项初始化字典（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="30f4c-102">How to: Initialize a Dictionary with a Collection Initializer (C# Programming Guide)</span></span>
<span data-ttu-id="30f4c-103"><xref:System.Collections.Generic.Dictionary`2> contains a collection of key/value pairs. Its <xref:System.Collections.Generic.Dictionary`2.Add*> 方法采用两个参数，一个用于键和另一个用于值。</span><span class="sxs-lookup"><span data-stu-id="30f4c-103">A <xref:System.Collections.Generic.Dictionary`2> contains a collection of key/value pairs. Its <xref:System.Collections.Generic.Dictionary`2.Add*> method takes two parameters, one for the key and one for the value.</span></span> <span data-ttu-id="30f4c-104">若要初始化 <xref:System.Collections.Generic.Dictionary`2>, or any collection whose ` 或 Add 方法采用多个参数的任何集合，请将每组参数括在大括号中，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="30f4c-104">To initialize a <xref:System.Collections.Generic.Dictionary`2>, or any collection whose `Add\` method takes multiple parameters, enclose each set of parameters in braces as shown in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30f4c-105">示例</span><span class="sxs-lookup"><span data-stu-id="30f4c-105">Example</span></span>  
 <span data-ttu-id="30f4c-106">在下面的代码示例中，<xref:System.Collections.Generic.Dictionary`2> is initialized with instances of type `StudentName\`</span><span class="sxs-lookup"><span data-stu-id="30f4c-106">In the following code example, a <xref:System.Collections.Generic.Dictionary`2> is initialized with instances of type `StudentName\`.</span></span>  
  
 <span data-ttu-id="30f4c-107">[!code-cs[csProgGuideLINQ#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-a-dictionary-with-a-collection-initializer_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="30f4c-107">[!code-cs[csProgGuideLINQ#34](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-a-dictionary-with-a-collection-initializer_1.cs)]</span></span>  
  
 <span data-ttu-id="30f4c-108">请注意，集合中的每个元素有两对大括号。</span><span class="sxs-lookup"><span data-stu-id="30f4c-108">Note the two pairs of braces in each element of the collection.</span></span> <span data-ttu-id="30f4c-109">最内层的大括号中的是 `StudentName` 的对象初始值设定项，最外层的大括号中的是要添加到 `students`<xref:System.Collections.Generic.Dictionary\`2> 的键/值对的初始值设定项。</span><span class="sxs-lookup"><span data-stu-id="30f4c-109">The innermost braces enclose the object initializer for the `StudentName`, and the outermost braces enclose the initializer for the key/value pair that will be added to the `students`<xref:System.Collections.Generic.Dictionary\`2>.</span></span> <span data-ttu-id="30f4c-110">最后，字典的整个集合初始值设定项被括在大括号中。</span><span class="sxs-lookup"><span data-stu-id="30f4c-110">Finally, the whole collection initializer for the dictionary is enclosed in braces.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="30f4c-111">编译代码</span><span class="sxs-lookup"><span data-stu-id="30f4c-111">Compiling the Code</span></span>  
 <span data-ttu-id="30f4c-112">若要运行此代码，请将该类复制并粘贴到已经在 [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)] 中创建的 Visual C# 控制台应用程序项目中。</span><span class="sxs-lookup"><span data-stu-id="30f4c-112">To run this code, copy and paste the class into a Visual C# console application project that has been created in [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)].</span></span> <span data-ttu-id="30f4c-113">默认情况下，此项目面向 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 3.5 版，并且具有对 System.Core.dll 的引用和一个用于 System.Linq 的 using 指令。</span><span class="sxs-lookup"><span data-stu-id="30f4c-113">By default, this project targets version 3.5 of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], and it has a reference to System.Core.dll and a using directive for System.Linq.</span></span> <span data-ttu-id="30f4c-114">如果项目中缺少其中一个或多个要求，则可以手动添加它们。</span><span class="sxs-lookup"><span data-stu-id="30f4c-114">If one or more of these requirements are missing from the project, you can add them manually.</span></span>   
  
## <a name="see-also"></a><span data-ttu-id="30f4c-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="30f4c-115">See Also</span></span>  
 <span data-ttu-id="30f4c-116">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="30f4c-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="30f4c-117">对象和集合初始值设定项</span><span class="sxs-lookup"><span data-stu-id="30f4c-117">Object and Collection Initializers</span></span>](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)


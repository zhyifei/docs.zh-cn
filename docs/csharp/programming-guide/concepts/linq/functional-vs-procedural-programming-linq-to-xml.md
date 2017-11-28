---
title: "函数编程与过程编程 (LINQ to XML) (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: fc64e39c-a487-4882-9169-da4de97917d9
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b6aa8ce45afdb68f7ff544b8c8f2f5e1e4a79533
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="functional-vs-procedural-programming-linq-to-xml-c"></a><span data-ttu-id="56a0e-102">函数编程与过程编程 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="56a0e-102">Functional vs. Procedural Programming (LINQ to XML) (C#)</span></span>
<span data-ttu-id="56a0e-103">XML 应用程序有多种类型：</span><span class="sxs-lookup"><span data-stu-id="56a0e-103">There are various types of XML applications:</span></span>  
  
-   <span data-ttu-id="56a0e-104">有些应用程序采用源 XML 文档并生成与源文档形状不同的新 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="56a0e-104">Some applications take source XML documents, and produce new XML documents that are in a different shape than the source documents.</span></span>  
  
-   <span data-ttu-id="56a0e-105">有些应用程序采用源 XML 文档并生成格式完全不同的结果文档，如 HTML 或 CSV 文本文件。</span><span class="sxs-lookup"><span data-stu-id="56a0e-105">Some applications take source XML documents, and produce result documents in an entirely different form, such as HTML or CSV text files.</span></span>  
  
-   <span data-ttu-id="56a0e-106">有些应用程序采用源 XML 文档并将记录插入数据库。</span><span class="sxs-lookup"><span data-stu-id="56a0e-106">Some applications take source XML documents, and insert records into a database.</span></span>  
  
-   <span data-ttu-id="56a0e-107">有些应用程序采用另一个源（如数据库）中的数据并从该数据创建 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="56a0e-107">Some applications take data from another source, such as a database, and create XML documents from it.</span></span>  
  
 <span data-ttu-id="56a0e-108">这些并不是所有的 XML 应用程序类型，但它们是 XML 程序员必须实现的一组有代表性的功能类型。</span><span class="sxs-lookup"><span data-stu-id="56a0e-108">These are not all of the types of XML applications, but these are a representative set of the types of functionality that an XML programmer has to implement.</span></span>  
  
 <span data-ttu-id="56a0e-109">对于所有这些类型应用程序，开发人员可以采用两种对比方法：</span><span class="sxs-lookup"><span data-stu-id="56a0e-109">With all of these types of applications, there are two contrasting approaches that a developer can take:</span></span>  
  
-   <span data-ttu-id="56a0e-110">使用声明性方法的函数构造。</span><span class="sxs-lookup"><span data-stu-id="56a0e-110">Functional construction using a declarative approach.</span></span>  
  
-   <span data-ttu-id="56a0e-111">使用过程代码的内存中 XML 树修改法。</span><span class="sxs-lookup"><span data-stu-id="56a0e-111">In-memory XML tree modification using procedural code.</span></span>  
  
 <span data-ttu-id="56a0e-112">LINQ to XML 同时支持这两种方法。</span><span class="sxs-lookup"><span data-stu-id="56a0e-112">LINQ to XML supports both approaches.</span></span>  
  
 <span data-ttu-id="56a0e-113">使用函数方法时，编写可采用源文档并生成具有所需形状的全新结果文档的转换。</span><span class="sxs-lookup"><span data-stu-id="56a0e-113">When using the functional approach, you write transformations that take the source documents and generate completely new result documents with the desired shape.</span></span>  
  
 <span data-ttu-id="56a0e-114">就地修改 XML 树时，编写可遍历内存中 XML 树节点并在其中导航以便根据需要插入、删除和修改节点的代码。</span><span class="sxs-lookup"><span data-stu-id="56a0e-114">When modifying an XML tree in place, you write code that traverses and navigates through nodes in an in-memory XML tree, inserting, deleting, and modifying nodes as necessary.</span></span>  
  
 <span data-ttu-id="56a0e-115">可以对任一方法使用 LINQ to XML。</span><span class="sxs-lookup"><span data-stu-id="56a0e-115">You can use LINQ to XML with either approach.</span></span> <span data-ttu-id="56a0e-116">使用的类相同，在某些情况下使用的方法也相同。</span><span class="sxs-lookup"><span data-stu-id="56a0e-116">You use the same classes, and in some cases the same methods.</span></span> <span data-ttu-id="56a0e-117">但这两种方法的结构和目标却大相径庭。</span><span class="sxs-lookup"><span data-stu-id="56a0e-117">However, the structure and goals of the two approaches are very different.</span></span> <span data-ttu-id="56a0e-118">例如，在不同情况下，其中一种方法通常具有更好的性能，使用更多或更少的内存。</span><span class="sxs-lookup"><span data-stu-id="56a0e-118">For example, in different situations, one or the other approach will often have better performance, and use more or less memory.</span></span> <span data-ttu-id="56a0e-119">另外，其中一种方法会更容易编写并生成更容易维护的代码。</span><span class="sxs-lookup"><span data-stu-id="56a0e-119">In addition, one or the other approach will be easier to write and yield more maintainable code.</span></span>  
  
 <span data-ttu-id="56a0e-120">若要对比查看这两种方法，请参阅[内存中 XML 树修改与函数构造 (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="56a0e-120">To see the two approaches contrasted, see [In-Memory XML Tree Modification vs. Functional Construction (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="56a0e-121">有关编写功能转换的教程，请参阅 [XML 的纯功能转换 (C#)](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="56a0e-121">For a tutorial on writing functional transformations, see [Pure Functional Transformations of XML (C#)](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56a0e-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="56a0e-122">See Also</span></span>  
 [<span data-ttu-id="56a0e-123">LINQ to XML 编程概述 (C#)</span><span class="sxs-lookup"><span data-stu-id="56a0e-123">LINQ to XML Programming Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)

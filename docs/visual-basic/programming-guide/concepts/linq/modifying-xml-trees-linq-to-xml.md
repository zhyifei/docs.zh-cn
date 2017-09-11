---
title: "修改 XML 树 (LINQ to XML) (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 4ae511a5-4fc9-4178-9c8e-761357deae3f
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9ff0f95afec6248ba7f64812be5f9906c90496d9
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017


---
# <a name="modifying-xml-trees-linq-to-xml-visual-basic"></a><span data-ttu-id="8a092-102">修改 XML 树 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8a092-102">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>
[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="8a092-103"> 是一个 XML 树在内存中的存储区。</span><span class="sxs-lookup"><span data-stu-id="8a092-103"> is an in-memory store for an XML tree.</span></span> <span data-ttu-id="8a092-104">加载或解析 XML 树从一个源之后,[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]允许您修改该树中的位置，然后序列化该树，可以将其保存到文件或将其发送到远程服务器。</span><span class="sxs-lookup"><span data-stu-id="8a092-104">After you load or parse an XML tree from a source, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] lets you modify that tree in place, and then serialize the tree, perhaps saving it to a file or sending it to a remote server.</span></span>  
  
 <span data-ttu-id="8a092-105">当您就地修改树时，可使用某些方法，如<xref:System.Xml.Linq.XContainer.Add%2A>。</xref:System.Xml.Linq.XContainer.Add%2A></span><span class="sxs-lookup"><span data-stu-id="8a092-105">When you modify a tree in place, you use certain methods, such as <xref:System.Xml.Linq.XContainer.Add%2A>.</span></span>  
  
 <span data-ttu-id="8a092-106">但是有另外一种方法，就是使用函数构造来生成具有不同形状的新树。</span><span class="sxs-lookup"><span data-stu-id="8a092-106">However, there is another approach, which is to use functional construction to generate a new tree with a different shape.</span></span> <span data-ttu-id="8a092-107">根据需要对 XML 树所做的更改类型的不同，以及根据树大小的不同，该方法可能更加强大，更易于开发。</span><span class="sxs-lookup"><span data-stu-id="8a092-107">Depending on the types of changes that you need to make to your XML tree, and depending on the size of the tree, this approach can be more robust and easier to develop.</span></span> <span data-ttu-id="8a092-108">本节第一个主题将比较这两种方法。</span><span class="sxs-lookup"><span data-stu-id="8a092-108">The first topic in this section compares these two approaches.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8a092-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="8a092-109">In This Section</span></span>  
  
|<span data-ttu-id="8a092-110">主题</span><span class="sxs-lookup"><span data-stu-id="8a092-110">Topic</span></span>|<span data-ttu-id="8a092-111">描述</span><span class="sxs-lookup"><span data-stu-id="8a092-111">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="8a092-112">内存中 XML 树修改与功能构造 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8a092-112">In-Memory XML Tree Modification vs. Functional Construction (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/in-memory-xml-tree-modification-vs-functional-construction.md)|<span data-ttu-id="8a092-113">在内存中修改 XML 树与使用函数构造的比较。</span><span class="sxs-lookup"><span data-stu-id="8a092-113">Compares modifying an XML tree in memory to functional construction.</span></span>|  
|[<span data-ttu-id="8a092-114">将元素、 特性和节点添加到 XML 树 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8a092-114">Adding Elements, Attributes, and Nodes to an XML Tree (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/adding-elements-attributes-and-nodes-to-an-xml-tree.md)|<span data-ttu-id="8a092-115">提供有关向 XML 树中添加元素、属性或节点的信息。</span><span class="sxs-lookup"><span data-stu-id="8a092-115">Provides information about adding elements, attributes, or nodes to an XML tree.</span></span>|  
|[<span data-ttu-id="8a092-116">修改 XML 树中的元素、特性和节点</span><span class="sxs-lookup"><span data-stu-id="8a092-116">Modifying Elements, Attributes, and Nodes in an XML Tree</span></span>](../../../../visual-basic/programming-guide/concepts/linq/modifying-elements-attributes-and-nodes-in-an-xml-tree.md)|<span data-ttu-id="8a092-117">提供有关修改现有元素、属性或节点的信息。</span><span class="sxs-lookup"><span data-stu-id="8a092-117">Provides information about modifying existing elements, attributes, or nodes.</span></span>|  
|[<span data-ttu-id="8a092-118">从 XML 树 (Visual Basic 中) 中移除元素、 特性和节点</span><span class="sxs-lookup"><span data-stu-id="8a092-118">Removing Elements, Attributes, and Nodes from an XML Tree (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/removing-elements-attributes-and-nodes-from-an-xml-tree.md)|<span data-ttu-id="8a092-119">提供有关从 XML 树中移除元素、属性或节点的信息。</span><span class="sxs-lookup"><span data-stu-id="8a092-119">Provides information about removing elements, attributes, or nodes from the XML tree.</span></span>|  
|[<span data-ttu-id="8a092-120">维护名称/值对 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8a092-120">Maintaining Name/Value Pairs (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/maintaining-name-value-pairs.md)|<span data-ttu-id="8a092-121">描述如何维护最好保存为名称/值对的应用程序信息，例如配置信息或全局设置。</span><span class="sxs-lookup"><span data-stu-id="8a092-121">Describes how to maintain application information that is best kept as name/value pairs, such as configuration information or global settings.</span></span>|  
|[<span data-ttu-id="8a092-122">如何︰ 更改整个 XML 树 (Visual Basic 中) Namespace</span><span class="sxs-lookup"><span data-stu-id="8a092-122">How to: Change the Namespace for an Entire XML Tree (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-change-the-namespace-for-an-entire-xml-tree.md)|<span data-ttu-id="8a092-123">演示如何将 XML 树从一个命名空间移动到另一个命名空间。</span><span class="sxs-lookup"><span data-stu-id="8a092-123">Shows how to move an XML tree from one namespace into another.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8a092-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8a092-124">See Also</span></span>  
 [<span data-ttu-id="8a092-125">编程指南 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8a092-125">Programming Guide (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)

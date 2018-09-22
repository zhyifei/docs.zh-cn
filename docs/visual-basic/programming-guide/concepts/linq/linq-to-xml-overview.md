---
title: LINQ to XML 概述 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 502661e0-bc5d-438d-94c2-7efb63bb6fbd
ms.openlocfilehash: 962fddcfec04259425c1094f07adf0e3966dfab0
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2018
ms.locfileid: "46697706"
---
# <a name="linq-to-xml-overview-visual-basic"></a><span data-ttu-id="368f8-102">LINQ to XML 概述 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="368f8-102">LINQ to XML Overview (Visual Basic)</span></span>
<span data-ttu-id="368f8-103">在很多环境中，XML 已广泛采用为格式化数据的方式。</span><span class="sxs-lookup"><span data-stu-id="368f8-103">XML has been widely adopted as a way to format data in many contexts.</span></span> <span data-ttu-id="368f8-104">例如，在 Web 上，在配置文件、Microsoft Office Word 文件以及数据库中，都可以看到 XML。</span><span class="sxs-lookup"><span data-stu-id="368f8-104">For example, you can find XML on the Web, in configuration files, in Microsoft Office Word files, and in databases.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="368f8-105"> 经过了重新设计，是最新的 XML 编程方法。</span><span class="sxs-lookup"><span data-stu-id="368f8-105"> is an up-to-date, redesigned approach to programming with XML.</span></span> <span data-ttu-id="368f8-106">它提供文档对象模型 (DOM) 的内存文档修改功能，支持 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 查询表达式。</span><span class="sxs-lookup"><span data-stu-id="368f8-106">It provides the in-memory document modification capabilities of the Document Object Model (DOM), and supports [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expressions.</span></span> <span data-ttu-id="368f8-107">尽管这些查询表达式在语法上与 XPath 不同，但它们提供类似的功能。</span><span class="sxs-lookup"><span data-stu-id="368f8-107">Although these query expressions are syntactically different from XPath, they provide similar functionality.</span></span>  
  
## <a name="linq-to-xml-developers"></a><span data-ttu-id="368f8-108">LINQ to XML 开发人员</span><span class="sxs-lookup"><span data-stu-id="368f8-108">LINQ to XML Developers</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="368f8-109"> 是面向各种开发人员的。</span><span class="sxs-lookup"><span data-stu-id="368f8-109"> targets a variety of developers.</span></span> <span data-ttu-id="368f8-110">对于只想完成某项工作的普通开发人员，[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 通过提供与 SQL 相似的查询表达式，使 XML 变得更加简单。</span><span class="sxs-lookup"><span data-stu-id="368f8-110">For an average developer who just wants to get something done, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] makes XML easier by providing a query experience that is similar to SQL.</span></span> <span data-ttu-id="368f8-111">只要稍加学习，程序员就能学会以自己选择的编程语言编写简洁、功能强大的查询。</span><span class="sxs-lookup"><span data-stu-id="368f8-111">With just a bit of study, programmers can learn to write succinct and powerful queries in their programming language of choice.</span></span>  
  
 <span data-ttu-id="368f8-112">专业开发人员可以使用 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 来大幅提高他们的工作效率。</span><span class="sxs-lookup"><span data-stu-id="368f8-112">Professional developers can use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] to greatly increase their productivity.</span></span> <span data-ttu-id="368f8-113">通过使用 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]，他们可以编写出表达能力更强、更为紧凑、功能更强的代码。</span><span class="sxs-lookup"><span data-stu-id="368f8-113">With [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], they can write less code that is more expressive, more compact, and more powerful.</span></span> <span data-ttu-id="368f8-114">他们可以同时对多个数据域使用查询表达式。</span><span class="sxs-lookup"><span data-stu-id="368f8-114">They can use query expressions from multiple data domains at the same time.</span></span>  
  
## <a name="what-is-linq-to-xml"></a><span data-ttu-id="368f8-115">什么是 LINQ to XML？</span><span class="sxs-lookup"><span data-stu-id="368f8-115">What Is LINQ to XML?</span></span>  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="368f8-116"> 是一种启用了 LINQ 的内存 XML 编程接口，使用它，可以在 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 编程语言中处理 XML。</span><span class="sxs-lookup"><span data-stu-id="368f8-116"> is a LINQ-enabled, in-memory XML programming interface that enables you to work with XML from within the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] programming languages.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="368f8-117"> 将 XML 文档置于内存中，这一点很像文档对象模型 (DOM)。</span><span class="sxs-lookup"><span data-stu-id="368f8-117"> is like the Document Object Model (DOM) in that it brings the XML document into memory.</span></span> <span data-ttu-id="368f8-118">您可以查询和修改 XML 文档，修改之后，可以将其另存为文件，也可以将其序列化然后通过 Internet 发送。</span><span class="sxs-lookup"><span data-stu-id="368f8-118">You can query and modify the document, and after you modify it you can save it to a file or serialize it and send it over the Internet.</span></span> <span data-ttu-id="368f8-119">但是，[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]与 DOM 不同： 它提供了新的对象模型更轻且更易于使用，并在 Visual Basic 中采用的语言功能。</span><span class="sxs-lookup"><span data-stu-id="368f8-119">However, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] differs from DOM: It provides a new object model that is lighter weight and easier to work with, and that takes advantage of language features in Visual Basic.</span></span>  
  
 <span data-ttu-id="368f8-120">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 最重要的优势是它与 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] 的集成。</span><span class="sxs-lookup"><span data-stu-id="368f8-120">The most important advantage of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is its integration with [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)].</span></span> <span data-ttu-id="368f8-121">由于实现了这一集成，因此，可以对内存 XML 文档编写查询，以检索元素和属性的集合。</span><span class="sxs-lookup"><span data-stu-id="368f8-121">This integration enables you to write queries on the in-memory XML document to retrieve collections of elements and attributes.</span></span> <span data-ttu-id="368f8-122">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 的查询功能在功能上（尽管不是在语法上）与 XPath 和 XQuery 具有可比性。</span><span class="sxs-lookup"><span data-stu-id="368f8-122">The query capability of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is comparable in functionality (although not in syntax) to XPath and XQuery.</span></span> <span data-ttu-id="368f8-123">集成[!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]在 Visual Basic 中提供了更强类型化功能、 编译时检查和改进的调试器支持。</span><span class="sxs-lookup"><span data-stu-id="368f8-123">The integration of [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] in Visual Basic provides stronger typing, compile-time checking, and improved debugger support.</span></span>  
  
 <span data-ttu-id="368f8-124">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 的另一个优势是通过将查询结果用作 <xref:System.Xml.Linq.XElement> 和 <xref:System.Xml.Linq.XAttribute> 对象构造函数的参数，实现了一种功能强大的创建 XML 树的方法。</span><span class="sxs-lookup"><span data-stu-id="368f8-124">Another advantage of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is the ability to use query results as parameters to <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XAttribute> object constructors enables a powerful approach to creating XML trees.</span></span> <span data-ttu-id="368f8-125">此方法称为*功能构造*，可使开发人员轻松地将 XML 树从一个形状转换成另一个形状。</span><span class="sxs-lookup"><span data-stu-id="368f8-125">This approach, called *functional construction*, enables developers to easily transform XML trees from one shape to another.</span></span>  
  
 <span data-ttu-id="368f8-126">例如，你可能有一个[示例 XML 文件：典型采购订单 (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md) 中所述的典型 XML 采购订单。</span><span class="sxs-lookup"><span data-stu-id="368f8-126">For example, you might have a typical XML purchase order as described in [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span> <span data-ttu-id="368f8-127">通过使用 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]，可以运行以下查询，以获取采购单每个项元素的部件号属性值：</span><span class="sxs-lookup"><span data-stu-id="368f8-127">By using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you could run the following query to obtain the part number attribute value for every item element in the purchase order:</span></span>  
  
```vb  
Dim partNos = _  
    From item In purchaseOrder...<Item> _  
    Select item.@PartNumber  
```  
  
 <span data-ttu-id="368f8-128">另一个示例，您可能需要一个列表，列出值大于 100 美元的项，并根据部件号排序。</span><span class="sxs-lookup"><span data-stu-id="368f8-128">As another example, you might want a list, sorted by part number, of the items with a value greater than $100.</span></span> <span data-ttu-id="368f8-129">若要获取此信息，可以运行下面的查询：</span><span class="sxs-lookup"><span data-stu-id="368f8-129">To obtain this information, you could run the following query:</span></span>  
  
```vb  
Dim partNos = _  
From item In purchaseOrder...<Item> _  
Where (item.<Quantity>.Value * _  
       item.<USPrice>.Value) > 100 _  
Order By item.<PartNumber>.Value _  
Select item  
```  
  
 <span data-ttu-id="368f8-130">除了这些 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 功能以外，[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 提供了改进的 XML 编程接口。</span><span class="sxs-lookup"><span data-stu-id="368f8-130">In addition to these [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] capabilities, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] provides an improved XML programming interface.</span></span> <span data-ttu-id="368f8-131">使用 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]，您可以：</span><span class="sxs-lookup"><span data-stu-id="368f8-131">Using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can:</span></span>  
  
-   <span data-ttu-id="368f8-132">从文件或流加载 XML。</span><span class="sxs-lookup"><span data-stu-id="368f8-132">Load XML from files or streams.</span></span>  
  
-   <span data-ttu-id="368f8-133">将 XML 序列化为文件或流。</span><span class="sxs-lookup"><span data-stu-id="368f8-133">Serialize XML to files or streams.</span></span>  
  
-   <span data-ttu-id="368f8-134">使用函数构造从头开始创建 XML。</span><span class="sxs-lookup"><span data-stu-id="368f8-134">Create XML from scratch by using functional construction.</span></span>  
  
-   <span data-ttu-id="368f8-135">使用类似 XPath 的轴查询 XML。</span><span class="sxs-lookup"><span data-stu-id="368f8-135">Query XML using XPath-like axes.</span></span>  
  
-   <span data-ttu-id="368f8-136">使用 <xref:System.Xml.Linq.XContainer.Add%2A>、<xref:System.Xml.Linq.XNode.Remove%2A>、<xref:System.Xml.Linq.XNode.ReplaceWith%2A> 和 <xref:System.Xml.Linq.XElement.SetValue%2A> 等方法对内存 XML 树进行操作。</span><span class="sxs-lookup"><span data-stu-id="368f8-136">Manipulate the in-memory XML tree by using methods such as <xref:System.Xml.Linq.XContainer.Add%2A>, <xref:System.Xml.Linq.XNode.Remove%2A>, <xref:System.Xml.Linq.XNode.ReplaceWith%2A>, and <xref:System.Xml.Linq.XElement.SetValue%2A>.</span></span>  
  
-   <span data-ttu-id="368f8-137">使用 XSD 验证 XML 树。</span><span class="sxs-lookup"><span data-stu-id="368f8-137">Validate XML trees using XSD.</span></span>  
  
-   <span data-ttu-id="368f8-138">使用这些功能的组合，可将 XML 树从一种形状转换为另一种形状。</span><span class="sxs-lookup"><span data-stu-id="368f8-138">Use a combination of these features to transform XML trees from one shape into another.</span></span>  
  
## <a name="creating-xml-trees"></a><span data-ttu-id="368f8-139">创建 XML 树</span><span class="sxs-lookup"><span data-stu-id="368f8-139">Creating XML Trees</span></span>  
 <span data-ttu-id="368f8-140">使用 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 编程的一个明显优势是易于创建 XML 树。</span><span class="sxs-lookup"><span data-stu-id="368f8-140">IOne of the most significant advantages of programming with [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is that it is easy to create XML trees.</span></span> <span data-ttu-id="368f8-141">例如，若要创建一个小型 XML 树，您可以编写代码，如下所示：</span><span class="sxs-lookup"><span data-stu-id="368f8-141">For example, to create a small XML tree, you can write  code as follows:</span></span>  
  
```vb  
Dim contacts = _  
<Contacts>  
    <Contact>  
        <Name>Patrick Hines</Name>  
        <Phone Type="Home">206-555-0144</Phone>  
        <Phone Type="Work">425-555-0145</Phone>  
        <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
        </Address>  
    </Contact>  
</Contacts>  
```  
  
 <span data-ttu-id="368f8-142">Visual Basic 编译器将 XML 文本转换为[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]方法调用。</span><span class="sxs-lookup"><span data-stu-id="368f8-142">The Visual Basic compiler translates XML literals into [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] method calls.</span></span>  
  
 <span data-ttu-id="368f8-143">有关详细信息，请参阅[创建 XML 树 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)。</span><span class="sxs-lookup"><span data-stu-id="368f8-143">For more information, see [Creating XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="368f8-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="368f8-144">See also</span></span>

- <xref:System.Xml.Linq>  
- [<span data-ttu-id="368f8-145">入门 (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="368f8-145">Getting Started (LINQ to XML)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/getting-started-linq-to-xml.md)  
- [<span data-ttu-id="368f8-146">Visual Basic 中的 LINQ to XML 概述</span><span class="sxs-lookup"><span data-stu-id="368f8-146">Overview of LINQ to XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
- [<span data-ttu-id="368f8-147">XML</span><span class="sxs-lookup"><span data-stu-id="368f8-147">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)

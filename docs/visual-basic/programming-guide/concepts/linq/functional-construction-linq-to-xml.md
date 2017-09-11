---
title: "功能构造 (LINQ to XML) (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: feac4273-39ab-43ae-bab7-4059c807a785
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b88b67aca337b893f9f276c8e4a6589b6946069b
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="functional-construction-linq-to-xml-visual-basic"></a><span data-ttu-id="b5b94-102">功能构造 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b5b94-102">Functional Construction (LINQ to XML) (Visual Basic)</span></span>
[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="b5b94-103">提供了一种功能强大的方法来创建 XML 元素名*功能性构造法*。</span><span class="sxs-lookup"><span data-stu-id="b5b94-103"> provides a powerful way to create XML elements called *functional construction*.</span></span> <span data-ttu-id="b5b94-104">函数构造是指在单个语句中创建 XML 树的能力。</span><span class="sxs-lookup"><span data-stu-id="b5b94-104">Functional construction is the ability to create an XML tree in a single statement.</span></span>  
  
 <span data-ttu-id="b5b94-105">启用函数构造的 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 编程接口有几个重要功能：</span><span class="sxs-lookup"><span data-stu-id="b5b94-105">There are several key features of the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] programming interface that enable functional construction:</span></span>  
  
-   <span data-ttu-id="b5b94-106"><xref:System.Xml.Linq.XElement>构造函数采用多种类型的参数的内容。</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="b5b94-106">The <xref:System.Xml.Linq.XElement> constructor takes various types of arguments for content.</span></span> <span data-ttu-id="b5b94-107">例如，可以传递另一个<xref:System.Xml.Linq.XElement>对象，它将成为子元素。</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="b5b94-107">For example, you can pass another <xref:System.Xml.Linq.XElement> object, which becomes a child element.</span></span> <span data-ttu-id="b5b94-108">您可以将传递<xref:System.Xml.Linq.XAttribute>对象，它将成为该元素的一个属性。</xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="b5b94-108">You can pass an <xref:System.Xml.Linq.XAttribute> object, which becomes an attribute of the element.</span></span> <span data-ttu-id="b5b94-109">也可以传递任何其他类型的对象，该对象将转换为字符串并成为该元素的文本内容。</span><span class="sxs-lookup"><span data-stu-id="b5b94-109">Or you can pass any other type of object, which is converted to a string and becomes the text content of the element.</span></span>  
  
-   <span data-ttu-id="b5b94-110"><xref:System.Xml.Linq.XElement>构造函数采用`params`类型的数组<xref:System.Object>，以便可以将任意数量的对象传递给构造函数。</xref:System.Object> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="b5b94-110">The <xref:System.Xml.Linq.XElement> constructor takes a `params` array of type <xref:System.Object>, so that you can pass any number of objects to the constructor.</span></span> <span data-ttu-id="b5b94-111">这使您可以创建具有复杂内容的元素。</span><span class="sxs-lookup"><span data-stu-id="b5b94-111">This enables you to create an element that has complex content.</span></span>  
  
-   <span data-ttu-id="b5b94-112">如果对象实现<xref:System.Collections.Generic.IEnumerable%601>，枚举中对象的集合，并添加集合中的所有项。</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="b5b94-112">If an object implements <xref:System.Collections.Generic.IEnumerable%601>, the collection in the object is enumerated, and all items in the collection are added.</span></span> <span data-ttu-id="b5b94-113">如果集合包含<xref:System.Xml.Linq.XElement>或<xref:System.Xml.Linq.XAttribute>对象，则单独添加集合中的每个项。</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="b5b94-113">If the collection contains <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, each item in the collection is added separately.</span></span> <span data-ttu-id="b5b94-114">这一功能很重要，因为它允许您将 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 查询的结果传递给构造函数。</span><span class="sxs-lookup"><span data-stu-id="b5b94-114">This is important because it lets you pass the results of a [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] query to the constructor.</span></span>  
  
 <span data-ttu-id="b5b94-115">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="b5b94-115">The following is an example:</span></span>  
  
 <span data-ttu-id="b5b94-116">这些功能使您能够编写代码以创建 XML 树，以及编写使用的结果的代码使用 XML 文本[!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]查询创建 XML 树时︰</span><span class="sxs-lookup"><span data-stu-id="b5b94-116">These features enable you to write code using XML literals to create an XML tree, and also to write code that uses the results of [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] queries when you create an XML tree:</span></span>  
  
```vb  
Dim srcTree As XElement = _  
    <Root>  
        <Element>1</Element>  
        <Element>2</Element>  
        <Element>3</Element>  
        <Element>4</Element>  
        <Element>5</Element>  
    </Root>  
Dim xmlTree As XElement = _  
    <Root>  
        <Child>1</Child>  
        <Child>2</Child>  
        <%= From el In srcTree.Elements() _  
            Where CInt(el) > 2 _  
            Select el %>  
    </Root>  
Console.WriteLine(xmlTree)  
```  
  
 <span data-ttu-id="b5b94-117">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="b5b94-117">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b5b94-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b5b94-118">See Also</span></span>  
 [<span data-ttu-id="b5b94-119">创建 XML 树 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b5b94-119">Creating XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)

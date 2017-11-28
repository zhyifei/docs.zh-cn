---
title: "克隆与附加 (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 357c5efa-7b73-4f14-aa67-6bebdba4e7ea
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e58e9538c319c20f9e820ff1de1fb6f973a18bdc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="cloning-vs-attaching-c"></a><span data-ttu-id="2cdea-102">克隆与附加 (C#)</span><span class="sxs-lookup"><span data-stu-id="2cdea-102">Cloning vs. Attaching (C#)</span></span>
<span data-ttu-id="2cdea-103">在将 <xref:System.Xml.Linq.XNode>（包括 <xref:System.Xml.Linq.XElement>）或 <xref:System.Xml.Linq.XAttribute> 对象添加到新树中时，如果新内容没有父级，则直接将这些对象附加到 XML 树中。</span><span class="sxs-lookup"><span data-stu-id="2cdea-103">When adding <xref:System.Xml.Linq.XNode> (including <xref:System.Xml.Linq.XElement>) or <xref:System.Xml.Linq.XAttribute> objects to a new tree, if the new content has no parent, the objects are simply attached to the XML tree.</span></span> <span data-ttu-id="2cdea-104">如果新内容已经有父级，并且是另一 XML 树的一部分，则克隆新内容。</span><span class="sxs-lookup"><span data-stu-id="2cdea-104">If the new content already is parented, and is part of another XML tree, the new content is cloned.</span></span> <span data-ttu-id="2cdea-105">然后将新克隆的内容附加到 XML 树中。</span><span class="sxs-lookup"><span data-stu-id="2cdea-105">The newly cloned content is then attached to the XML tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2cdea-106">示例</span><span class="sxs-lookup"><span data-stu-id="2cdea-106">Example</span></span>  
 <span data-ttu-id="2cdea-107">下面的代码演示将有父级的元素添加到树中，以及将没有父级的元素添加到树中时的行为。</span><span class="sxs-lookup"><span data-stu-id="2cdea-107">The following code demonstrates the behavior when you add a parented element to a tree, and when you add an element with no parent to a tree.</span></span>  
  
```csharp  
// Create a tree with a child element.  
XElement xmlTree1 = new XElement("Root",  
    new XElement("Child1", 1)  
);  
  
// Create an element that is not parented.  
XElement child2 = new XElement("Child2", 2);  
  
// Create a tree and add Child1 and Child2 to it.  
XElement xmlTree2 = new XElement("Root",  
    xmlTree1.Element("Child1"),  
    child2  
);  
  
// Compare Child1 identity.  
Console.WriteLine("Child1 was {0}",  
    xmlTree1.Element("Child1") == xmlTree2.Element("Child1") ?  
    "attached" : "cloned");  
  
// Compare Child2 identity.  
Console.WriteLine("Child2 was {0}",  
    child2 == xmlTree2.Element("Child2") ?  
    "attached" : "cloned");  
```  
  
 <span data-ttu-id="2cdea-108">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="2cdea-108">This example produces the following output:</span></span>  
  
```  
Child1 was cloned  
Child2 was attached  
```  
  
## <a name="see-also"></a><span data-ttu-id="2cdea-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2cdea-109">See Also</span></span>  
 [<span data-ttu-id="2cdea-110">创建 XML 树 (C#)</span><span class="sxs-lookup"><span data-stu-id="2cdea-110">Creating XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md)

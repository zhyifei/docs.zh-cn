---
title: 向 XML 树添加元素、属性和节点 (C#)
ms.date: 07/20/2015
ms.assetid: db911e4f-40aa-499a-9500-a9763bb6df56
ms.openlocfilehash: 20d8d9d9c592f5f570d7c94298dcee41763c1f1f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79169570"
---
# <a name="adding-elements-attributes-and-nodes-to-an-xml-tree-c"></a><span data-ttu-id="5f4e7-102">向 XML 树添加元素、属性和节点 (C#)</span><span class="sxs-lookup"><span data-stu-id="5f4e7-102">Adding Elements, Attributes, and Nodes to an XML Tree (C#)</span></span>
<span data-ttu-id="5f4e7-103">可以向现有的 XML 树中添加内容（包括元素、属性、注释、处理指令、文本和 CDATA）。</span><span class="sxs-lookup"><span data-stu-id="5f4e7-103">You can add content (elements, attributes, comments, processing instructions, text, and CDATA) to an existing XML tree.</span></span>  
  
## <a name="methods-for-adding-content"></a><span data-ttu-id="5f4e7-104">添加内容的方法</span><span class="sxs-lookup"><span data-stu-id="5f4e7-104">Methods for Adding Content</span></span>  
 <span data-ttu-id="5f4e7-105">下面的方法将子内容添加到 <xref:System.Xml.Linq.XElement> 或 <xref:System.Xml.Linq.XDocument> 中：</span><span class="sxs-lookup"><span data-stu-id="5f4e7-105">The following methods add child content to an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XDocument>:</span></span>  
  
|<span data-ttu-id="5f4e7-106">方法</span><span class="sxs-lookup"><span data-stu-id="5f4e7-106">Method</span></span>|<span data-ttu-id="5f4e7-107">说明</span><span class="sxs-lookup"><span data-stu-id="5f4e7-107">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.Add%2A>|<span data-ttu-id="5f4e7-108">在 <xref:System.Xml.Linq.XContainer> 的子内容的末尾添加内容。</span><span class="sxs-lookup"><span data-stu-id="5f4e7-108">Adds content at the end of the child content of the <xref:System.Xml.Linq.XContainer>.</span></span>|  
|<xref:System.Xml.Linq.XContainer.AddFirst%2A>|<span data-ttu-id="5f4e7-109">在 <xref:System.Xml.Linq.XContainer> 的子内容的开头添加内容。</span><span class="sxs-lookup"><span data-stu-id="5f4e7-109">Adds content at the beginning of the child content of the <xref:System.Xml.Linq.XContainer>.</span></span>|  
  
 <span data-ttu-id="5f4e7-110">下面的方法将内容添加为 <xref:System.Xml.Linq.XNode> 的同级节点。</span><span class="sxs-lookup"><span data-stu-id="5f4e7-110">The following methods add content as sibling nodes of an <xref:System.Xml.Linq.XNode>.</span></span> <span data-ttu-id="5f4e7-111">向其中添加同级内容的最常见的节点是 <xref:System.Xml.Linq.XElement>，不过你也可以将有效的同级内容添加到其他类型的节点，例如 <xref:System.Xml.Linq.XText> 或 <xref:System.Xml.Linq.XComment>。</span><span class="sxs-lookup"><span data-stu-id="5f4e7-111">The most common node to which you add sibling content is <xref:System.Xml.Linq.XElement>, although you can add valid sibling content to other types of nodes such as <xref:System.Xml.Linq.XText> or <xref:System.Xml.Linq.XComment>.</span></span>  
  
|<span data-ttu-id="5f4e7-112">方法</span><span class="sxs-lookup"><span data-stu-id="5f4e7-112">Method</span></span>|<span data-ttu-id="5f4e7-113">说明</span><span class="sxs-lookup"><span data-stu-id="5f4e7-113">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.AddAfterSelf%2A>|<span data-ttu-id="5f4e7-114">在 <xref:System.Xml.Linq.XNode> 后面添加内容。</span><span class="sxs-lookup"><span data-stu-id="5f4e7-114">Adds content after the <xref:System.Xml.Linq.XNode>.</span></span>|  
|<xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>|<span data-ttu-id="5f4e7-115">在 <xref:System.Xml.Linq.XNode> 前面添加内容。</span><span class="sxs-lookup"><span data-stu-id="5f4e7-115">Adds content before the <xref:System.Xml.Linq.XNode>.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5f4e7-116">示例</span><span class="sxs-lookup"><span data-stu-id="5f4e7-116">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="5f4e7-117">说明</span><span class="sxs-lookup"><span data-stu-id="5f4e7-117">Description</span></span>  
 <span data-ttu-id="5f4e7-118">下面的示例创建两个 XML 树，然后修改其中一个树。</span><span class="sxs-lookup"><span data-stu-id="5f4e7-118">The following example creates two XML trees, and then modifies one of the trees.</span></span>  
  
### <a name="code"></a><span data-ttu-id="5f4e7-119">代码</span><span class="sxs-lookup"><span data-stu-id="5f4e7-119">Code</span></span>  
  
```csharp  
XElement srcTree = new XElement("Root",
    new XElement("Element1", 1),  
    new XElement("Element2", 2),  
    new XElement("Element3", 3),  
    new XElement("Element4", 4),  
    new XElement("Element5", 5)  
);  
XElement xmlTree = new XElement("Root",  
    new XElement("Child1", 1),  
    new XElement("Child2", 2),  
    new XElement("Child3", 3),  
    new XElement("Child4", 4),  
    new XElement("Child5", 5)  
);  
xmlTree.Add(new XElement("NewChild", "new content"));  
xmlTree.Add(  
    from el in srcTree.Elements()  
    where (int)el > 3  
    select el  
);  
// Even though Child9 does not exist in srcTree, the following statement will not  
// throw an exception, and nothing will be added to xmlTree.  
xmlTree.Add(srcTree.Element("Child9"));  
Console.WriteLine(xmlTree);  
```  
  
### <a name="comments"></a><span data-ttu-id="5f4e7-120">注释</span><span class="sxs-lookup"><span data-stu-id="5f4e7-120">Comments</span></span>  
 <span data-ttu-id="5f4e7-121">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="5f4e7-121">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child1>1</Child1>  
  <Child2>2</Child2>  
  <Child3>3</Child3>  
  <Child4>4</Child4>  
  <Child5>5</Child5>  
  <NewChild>new content</NewChild>  
  <Element4>4</Element4>  
  <Element5>5</Element5>  
</Root>  
```  
  
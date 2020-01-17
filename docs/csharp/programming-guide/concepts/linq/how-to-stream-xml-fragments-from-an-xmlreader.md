---
title: 如何从 XmlReader 流式处理 XML 片段 (C#)
ms.date: 07/20/2015
ms.assetid: 4a8f0e45-768a-42e2-bc5f-68bdf0e0a726
ms.openlocfilehash: f7914d33622518f983a685dd2e844a25fd3ca15f
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714657"
---
# <a name="how-to-stream-xml-fragments-from-an-xmlreader-c"></a><span data-ttu-id="2de0d-102">如何从 XmlReader 流式处理 XML 片段 (C#)</span><span class="sxs-lookup"><span data-stu-id="2de0d-102">How to stream XML fragments from an XmlReader (C#)</span></span>

<span data-ttu-id="2de0d-103">如果必须处理很大的 XML 文件，将整个 XML 树加载到内存可能不可行。</span><span class="sxs-lookup"><span data-stu-id="2de0d-103">When you have to process large XML files, it might not be feasible to load the whole XML tree into memory.</span></span> <span data-ttu-id="2de0d-104">本主题演示如何使用 <xref:System.Xml.XmlReader> 对片段进行流式处理。</span><span class="sxs-lookup"><span data-stu-id="2de0d-104">This topic shows how to stream fragments using an <xref:System.Xml.XmlReader>.</span></span>  
  
 <span data-ttu-id="2de0d-105">使用 <xref:System.Xml.XmlReader> 读取 <xref:System.Xml.Linq.XElement> 对象的一种最有效方式是编写您自己的自定义轴方法。</span><span class="sxs-lookup"><span data-stu-id="2de0d-105">One of the most effective ways to use an <xref:System.Xml.XmlReader> to read <xref:System.Xml.Linq.XElement> objects is to write your own custom axis method.</span></span> <span data-ttu-id="2de0d-106">轴方法通常会返回一个集合，比如 <xref:System.Collections.Generic.IEnumerable%601> 的 <xref:System.Xml.Linq.XElement>，如本主题中的示例所示。</span><span class="sxs-lookup"><span data-stu-id="2de0d-106">An axis method typically returns a collection such as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, as shown in the example in this topic.</span></span> <span data-ttu-id="2de0d-107">在自定义轴方法中，在通过调用 <xref:System.Xml.Linq.XNode.ReadFrom%2A> 方法创建 XML 片段后，可以使用 `yield return` 返回该集合。</span><span class="sxs-lookup"><span data-stu-id="2de0d-107">In the custom axis method, after you create the XML fragment by calling the <xref:System.Xml.Linq.XNode.ReadFrom%2A> method, return the collection using `yield return`.</span></span> <span data-ttu-id="2de0d-108">这可为您的自定义轴方法提供延迟执行语义。</span><span class="sxs-lookup"><span data-stu-id="2de0d-108">This provides deferred execution semantics to your custom axis method.</span></span>  
  
 <span data-ttu-id="2de0d-109">在从 <xref:System.Xml.XmlReader> 对象创建 XML 树时，<xref:System.Xml.XmlReader> 必须位于元素上。</span><span class="sxs-lookup"><span data-stu-id="2de0d-109">When you create an XML tree from an <xref:System.Xml.XmlReader> object, the <xref:System.Xml.XmlReader> must be positioned on an element.</span></span> <span data-ttu-id="2de0d-110"><xref:System.Xml.Linq.XNode.ReadFrom%2A> 方法在读取该元素的结束标记之前不会返回。</span><span class="sxs-lookup"><span data-stu-id="2de0d-110">The <xref:System.Xml.Linq.XNode.ReadFrom%2A> method does not return until it has read the close tag of the element.</span></span>  
  
 <span data-ttu-id="2de0d-111">如果想要创建一个部分树，可实例化 <xref:System.Xml.XmlReader>，将读取器定位在要转换为 <xref:System.Xml.Linq.XElement> 树的节点上，然后创建 <xref:System.Xml.Linq.XElement> 对象。</span><span class="sxs-lookup"><span data-stu-id="2de0d-111">If you want to create a partial tree, you can instantiate an <xref:System.Xml.XmlReader>, position the reader on the node that you want to convert to an <xref:System.Xml.Linq.XElement> tree, and then create the <xref:System.Xml.Linq.XElement> object.</span></span>  
  
<span data-ttu-id="2de0d-112">[如何通过对标头信息的访问流式处理 XML 片段 (C#)](./how-to-stream-xml-fragments-with-access-to-header-information.md) 主题包含有关如何流式处理更复杂的文档的信息和示例。</span><span class="sxs-lookup"><span data-stu-id="2de0d-112">The topic [How to stream XML fragments with access to header information (C#)](./how-to-stream-xml-fragments-with-access-to-header-information.md) contains information and an example on how to stream a more complex document.</span></span>
  
 <span data-ttu-id="2de0d-113">[如何执行大型 XML 文档的流式转换 (C#)](./how-to-perform-streaming-transform-of-large-xml-documents.md) 主题包含如何使用 LINQ to XML 在保持小内存需求量的同时转换极大 XML 文档的示例。</span><span class="sxs-lookup"><span data-stu-id="2de0d-113">The topic [How to perform streaming transform of large XML documents (C#)](./how-to-perform-streaming-transform-of-large-xml-documents.md) contains an example of using LINQ to XML to transform extremely large XML documents while maintaining a small memory footprint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2de0d-114">示例</span><span class="sxs-lookup"><span data-stu-id="2de0d-114">Example</span></span>  
 <span data-ttu-id="2de0d-115">本示例创建一个自定义轴方法。</span><span class="sxs-lookup"><span data-stu-id="2de0d-115">This example creates a custom axis method.</span></span> <span data-ttu-id="2de0d-116">可以通过使用 LINQ 查询来查询该方法。</span><span class="sxs-lookup"><span data-stu-id="2de0d-116">You can query it by using a LINQ query.</span></span> <span data-ttu-id="2de0d-117">自定义轴方法 `StreamRootChildDoc` 是一个专门设计的方法，用于读取具有重复 `Child` 元素的文档。</span><span class="sxs-lookup"><span data-stu-id="2de0d-117">The custom axis method, `StreamRootChildDoc`, is a method that is designed specifically to read a document that has a repeating `Child` element.</span></span>  
  
```csharp  
static IEnumerable<XElement> StreamRootChildDoc(StringReader stringReader)  
{  
    using (XmlReader reader = XmlReader.Create(stringReader))  
    {  
        reader.MoveToContent();  
        // Parse the file and display each of the nodes.  
        while (reader.Read())  
        {  
            switch (reader.NodeType)  
            {  
                case XmlNodeType.Element:  
                    if (reader.Name == "Child") {  
                        XElement el = XElement.ReadFrom(reader) as XElement;  
                        if (el != null)  
                            yield return el;  
                    }  
                    break;  
            }  
        }  
    }  
}  
  
static void Main(string[] args)  
{  
    string markup = @"<Root>  
      <Child Key=""01"">  
        <GrandChild>aaa</GrandChild>  
      </Child>  
      <Child Key=""02"">  
        <GrandChild>bbb</GrandChild>  
      </Child>  
      <Child Key=""03"">  
        <GrandChild>ccc</GrandChild>  
      </Child>  
    </Root>";  
  
    IEnumerable<string> grandChildData =  
        from el in StreamRootChildDoc(new StringReader(markup))  
        where (int)el.Attribute("Key") > 1  
        select (string)el.Element("GrandChild");  
  
    foreach (string str in grandChildData) {  
        Console.WriteLine(str);  
    }  
}  
```  
  
 <span data-ttu-id="2de0d-118">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="2de0d-118">This example produces the following output:</span></span>  
  
```output  
bbb  
ccc  
```  
  
 <span data-ttu-id="2de0d-119">在本示例中，源文档非常小。</span><span class="sxs-lookup"><span data-stu-id="2de0d-119">In this example, the source document is very small.</span></span> <span data-ttu-id="2de0d-120">但是即使有数百万个 `Child` 元素，本示例也仍具有很小的内存需求量。</span><span class="sxs-lookup"><span data-stu-id="2de0d-120">However, even if there were millions of `Child` elements, this example would still have a small memory footprint.</span></span>  

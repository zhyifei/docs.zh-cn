---
title: "如何：转换节点片断"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 73a6c582-b9d7-4fa7-9a05-6d931e1f3de8
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: dc3683cfe27bfed0f89cba4e0df0b0515fc6f287
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-transform-a-node-fragment"></a><span data-ttu-id="d9306-102">如何：转换节点片断</span><span class="sxs-lookup"><span data-stu-id="d9306-102">How to: Transform a Node Fragment</span></span>
<span data-ttu-id="d9306-103">在转换 <xref:System.Xml.XmlDocument> 或 <xref:System.Xml.XPath.XPathDocument> 对象中包含的数据时，XSLT 转换应用于整个文档。</span><span class="sxs-lookup"><span data-stu-id="d9306-103">When you transform data contained in an <xref:System.Xml.XmlDocument> or <xref:System.Xml.XPath.XPathDocument> object the XSLT transformations apply to a document as a whole.</span></span> <span data-ttu-id="d9306-104">换句话说，如果您传入文档根节点以外的一个节点，并不能防止转换进程访问已加载文档的所有节点。</span><span class="sxs-lookup"><span data-stu-id="d9306-104">In other words, if you pass in a node other than the document root node, this does not prevent the transformation process from accessing all nodes in the loaded document.</span></span> <span data-ttu-id="d9306-105">若要转换节点片段，必须创建一个仅包含节点片段的独立对象，并将该对象传递给 <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="d9306-105">To transform a node fragment, you must create a separate object containing just the node fragment, and pass that object to the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="d9306-106">过程</span><span class="sxs-lookup"><span data-stu-id="d9306-106">Procedures</span></span>  
  
#### <a name="to-transform-a-node-fragment"></a><span data-ttu-id="d9306-107">转换节点片断</span><span class="sxs-lookup"><span data-stu-id="d9306-107">To transform a node fragment</span></span>  
  
1.  <span data-ttu-id="d9306-108">创建一个包含源文档的对象。</span><span class="sxs-lookup"><span data-stu-id="d9306-108">Create an object containing the source document.</span></span>  
  
2.  <span data-ttu-id="d9306-109">找到要转换的节点片断。</span><span class="sxs-lookup"><span data-stu-id="d9306-109">Locate the node fragment you wish to transform.</span></span>  
  
3.  <span data-ttu-id="d9306-110">创建仅包含该节点片断的独立对象。</span><span class="sxs-lookup"><span data-stu-id="d9306-110">Create separate object with just the node fragment.</span></span>  
  
4.  <span data-ttu-id="d9306-111">将该节点片断传递给 <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="d9306-111">Pass the node fragment to the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9306-112">示例</span><span class="sxs-lookup"><span data-stu-id="d9306-112">Example</span></span>  
 <span data-ttu-id="d9306-113">以下示例转换节点片断并将结果输出到控制台。</span><span class="sxs-lookup"><span data-stu-id="d9306-113">The following example transforms a node fragment and outputs the results to the console.</span></span>  
  
 [!code-csharp[XSLT_NodeFrag#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XSLT_NodeFrag/CS/xslt_frag.cs#1)]
 [!code-vb[XSLT_NodeFrag#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XSLT_NodeFrag/VB/xslt_frag.vb#1)]  
  
### <a name="input"></a><span data-ttu-id="d9306-114">输入</span><span class="sxs-lookup"><span data-stu-id="d9306-114">Input</span></span>  
  
##### <a name="booksxml"></a><span data-ttu-id="d9306-115">books.xml</span><span class="sxs-lookup"><span data-stu-id="d9306-115">books.xml</span></span>  
 [!code-xml[XML_Core_Files#1](../../../../samples/snippets/xml/VS_Snippets_Data/XML_Core_Files/XML/books.xml#1)]  
  
##### <a name="singlexsl"></a><span data-ttu-id="d9306-116">single.xsl</span><span class="sxs-lookup"><span data-stu-id="d9306-116">single.xsl</span></span>  
 [!code-xml[XSLT_NodeFrag#2](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_NodeFrag/XML/single.xsl#2)]  
  
### <a name="output"></a><span data-ttu-id="d9306-117">输出</span><span class="sxs-lookup"><span data-stu-id="d9306-117">Output</span></span>  
 <span data-ttu-id="d9306-118">书名为 The Confidence Man。</span><span class="sxs-lookup"><span data-stu-id="d9306-118">Book title is The Confidence Man.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9306-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d9306-119">See Also</span></span>  
 [<span data-ttu-id="d9306-120">使用 XslCompiledTransform 类</span><span class="sxs-lookup"><span data-stu-id="d9306-120">Using the XslCompiledTransform Class</span></span>](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)

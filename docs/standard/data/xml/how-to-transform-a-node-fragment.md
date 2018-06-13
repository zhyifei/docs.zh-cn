---
title: 如何：转换节点片断
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 73a6c582-b9d7-4fa7-9a05-6d931e1f3de8
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4cd35e469a16dc2fdb3a7f4afd89d04f67185cd5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33568558"
---
# <a name="how-to-transform-a-node-fragment"></a><span data-ttu-id="ba29e-102">如何：转换节点片断</span><span class="sxs-lookup"><span data-stu-id="ba29e-102">How to: Transform a Node Fragment</span></span>
<span data-ttu-id="ba29e-103">在转换 <xref:System.Xml.XmlDocument> 或 <xref:System.Xml.XPath.XPathDocument> 对象中包含的数据时，XSLT 转换应用于整个文档。</span><span class="sxs-lookup"><span data-stu-id="ba29e-103">When you transform data contained in an <xref:System.Xml.XmlDocument> or <xref:System.Xml.XPath.XPathDocument> object the XSLT transformations apply to a document as a whole.</span></span> <span data-ttu-id="ba29e-104">换句话说，如果你传入文档根节点以外的一个节点，并不能防止转换进程访问已加载文档的所有节点。</span><span class="sxs-lookup"><span data-stu-id="ba29e-104">In other words, if you pass in a node other than the document root node, this does not prevent the transformation process from accessing all nodes in the loaded document.</span></span> <span data-ttu-id="ba29e-105">若要转换节点片段，必须创建一个仅包含节点片段的独立对象，并将该对象传递给 <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="ba29e-105">To transform a node fragment, you must create a separate object containing just the node fragment, and pass that object to the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="ba29e-106">过程</span><span class="sxs-lookup"><span data-stu-id="ba29e-106">Procedures</span></span>  
  
#### <a name="to-transform-a-node-fragment"></a><span data-ttu-id="ba29e-107">转换节点片断</span><span class="sxs-lookup"><span data-stu-id="ba29e-107">To transform a node fragment</span></span>  
  
1.  <span data-ttu-id="ba29e-108">创建一个包含源文档的对象。</span><span class="sxs-lookup"><span data-stu-id="ba29e-108">Create an object containing the source document.</span></span>  
  
2.  <span data-ttu-id="ba29e-109">找到要转换的节点片断。</span><span class="sxs-lookup"><span data-stu-id="ba29e-109">Locate the node fragment you wish to transform.</span></span>  
  
3.  <span data-ttu-id="ba29e-110">创建仅包含该节点片断的独立对象。</span><span class="sxs-lookup"><span data-stu-id="ba29e-110">Create separate object with just the node fragment.</span></span>  
  
4.  <span data-ttu-id="ba29e-111">将该节点片断传递给 <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="ba29e-111">Pass the node fragment to the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba29e-112">示例</span><span class="sxs-lookup"><span data-stu-id="ba29e-112">Example</span></span>  
 <span data-ttu-id="ba29e-113">以下示例转换节点片断并将结果输出到控制台。</span><span class="sxs-lookup"><span data-stu-id="ba29e-113">The following example transforms a node fragment and outputs the results to the console.</span></span>  
  
 [!code-csharp[XSLT_NodeFrag#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XSLT_NodeFrag/CS/xslt_frag.cs#1)]
 [!code-vb[XSLT_NodeFrag#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XSLT_NodeFrag/VB/xslt_frag.vb#1)]  
  
### <a name="input"></a><span data-ttu-id="ba29e-114">输入</span><span class="sxs-lookup"><span data-stu-id="ba29e-114">Input</span></span>  
  
##### <a name="booksxml"></a><span data-ttu-id="ba29e-115">books.xml</span><span class="sxs-lookup"><span data-stu-id="ba29e-115">books.xml</span></span>  
 [!code-xml[XML_Core_Files#1](../../../../samples/snippets/xml/VS_Snippets_Data/XML_Core_Files/XML/books.xml#1)]  
  
##### <a name="singlexsl"></a><span data-ttu-id="ba29e-116">single.xsl</span><span class="sxs-lookup"><span data-stu-id="ba29e-116">single.xsl</span></span>  
 [!code-xml[XSLT_NodeFrag#2](../../../../samples/snippets/xml/VS_Snippets_Data/XSLT_NodeFrag/XML/single.xsl#2)]  
  
### <a name="output"></a><span data-ttu-id="ba29e-117">输出</span><span class="sxs-lookup"><span data-stu-id="ba29e-117">Output</span></span>  
 <span data-ttu-id="ba29e-118">书名为 The Confidence Man。</span><span class="sxs-lookup"><span data-stu-id="ba29e-118">Book title is The Confidence Man.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba29e-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="ba29e-119">See Also</span></span>  
 [<span data-ttu-id="ba29e-120">使用 XslCompiledTransform 类</span><span class="sxs-lookup"><span data-stu-id="ba29e-120">Using the XslCompiledTransform Class</span></span>](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)

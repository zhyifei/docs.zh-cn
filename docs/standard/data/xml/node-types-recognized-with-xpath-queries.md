---
title: XPath 查询识别的节点类型
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 1d33e22d-18e5-43f8-a466-2e3d0a8dd094
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 005c5f4981a7ab1889678e391a6df6e0b7b43f71
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33569374"
---
# <a name="node-types-recognized-with-xpath-queries"></a><span data-ttu-id="6e5d1-102">XPath 查询识别的节点类型</span><span class="sxs-lookup"><span data-stu-id="6e5d1-102">Node Types Recognized with XPath Queries</span></span>
<span data-ttu-id="6e5d1-103">XPath 查询识别的节点类型与文档对象模型 (DOM) 中的节点类型不同。</span><span class="sxs-lookup"><span data-stu-id="6e5d1-103">The types of nodes recognized in an XPath query are not the same node types found in the Document Object Model (DOM).</span></span>  
  
## <a name="w3c-xpath-node-types"></a><span data-ttu-id="6e5d1-104">W3C XPath 节点类型</span><span class="sxs-lookup"><span data-stu-id="6e5d1-104">W3C XPath Node Types</span></span>  
 <span data-ttu-id="6e5d1-105">XPath 查询识别的节点类型与文档对象模型 (DOM) 中的节点类型不同。</span><span class="sxs-lookup"><span data-stu-id="6e5d1-105">The types of nodes recognized in an XPath query are not the types of nodes found in the Document Object Model (DOM).</span></span> <span data-ttu-id="6e5d1-106">以下是通过 <xref:System.Xml.XPath.XPathNodeType> 枚举表示的 XPath 节点类型。</span><span class="sxs-lookup"><span data-stu-id="6e5d1-106">The following are the XPath node types represented by the <xref:System.Xml.XPath.XPathNodeType> enumeration.</span></span>  
  
-   <xref:System.Xml.XPath.XPathNodeType.All>  
  
-   <xref:System.Xml.XPath.XPathNodeType.Attribute>  
  
-   <xref:System.Xml.XPath.XPathNodeType.Comment>  
  
-   <xref:System.Xml.XPath.XPathNodeType.Element>  
  
-   <xref:System.Xml.XPath.XPathNodeType.Namespace>  
  
-   <xref:System.Xml.XPath.XPathNodeType.ProcessingInstruction>  
  
-   <xref:System.Xml.XPath.XPathNodeType.Root>  
  
-   <xref:System.Xml.XPath.XPathNodeType.SignificantWhitespace>  
  
-   <xref:System.Xml.XPath.XPathNodeType.Text>  
  
-   <xref:System.Xml.XPath.XPathNodeType.Whitespace>  
  
 <span data-ttu-id="6e5d1-107">这些节点类型基于 XPath 数据模型，其中的节点从 XML 信息集派生。</span><span class="sxs-lookup"><span data-stu-id="6e5d1-107">These node types are based on the XPath data model, where the nodes are derived from the XML Information Set.</span></span> <span data-ttu-id="6e5d1-108"><xref:System.Xml.XPath.XPathNodeType.SignificantWhitespace> 和 <xref:System.Xml.XPath.XPathNodeType.Whitespace> 节点类型是 Microsoft .NET Framework 对 XPath 数据模型中所述的基本节点类型的扩展。</span><span class="sxs-lookup"><span data-stu-id="6e5d1-108">The <xref:System.Xml.XPath.XPathNodeType.SignificantWhitespace> and <xref:System.Xml.XPath.XPathNodeType.Whitespace> node types are Microsoft .NET Framework extensions to the base node types described in the XPath data model.</span></span>  
  
 <span data-ttu-id="6e5d1-109">属性节点类型在 XPath 数据模型中的用法与在 DOM 中的用法不同。</span><span class="sxs-lookup"><span data-stu-id="6e5d1-109">The attribute node type is used differently in the XPath data model than it is in the DOM.</span></span> <span data-ttu-id="6e5d1-110">在 XPath 数据模型中，元素具有相关的属性节点集，且元素是每个属性节点的父级。</span><span class="sxs-lookup"><span data-stu-id="6e5d1-110">In the XPath data model, the element node has a set of attribute nodes related to it and the element node is the parent of each attribute node.</span></span> <span data-ttu-id="6e5d1-111">但在 DOM 中，元素节点是所有者，而不是父级。</span><span class="sxs-lookup"><span data-stu-id="6e5d1-111">However, in the DOM, the element node is the owner and not the parent.</span></span> <span data-ttu-id="6e5d1-112">在这两种模型中，属性和命名空间节点都不被视为元素节点的子节点。</span><span class="sxs-lookup"><span data-stu-id="6e5d1-112">In both models, attribute and namespace nodes are not considered child nodes of the element node.</span></span>  
  
 <span data-ttu-id="6e5d1-113">命名空间节点类型是 XPath 数据模型的补充，并且不是可识别的 DOM 节点类型。</span><span class="sxs-lookup"><span data-stu-id="6e5d1-113">The namespace node type is an addition to the XPath data model and is not a recognized DOM node type.</span></span>  
  
 <span data-ttu-id="6e5d1-114">若要详细了解如何浏览元素、属性和命名空间节点，请参阅[使用 XPathNavigator 的节点集定位](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md)和[使用 XPathNavigator 的属性和命名空间节点定位](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md)主题。</span><span class="sxs-lookup"><span data-stu-id="6e5d1-114">For more information about navigating element, attribute, and namespace nodes, see the [Node Set Navigation Using XPathNavigator](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md) and [Attribute and Namespace Node Navigation Using XPathNavigator](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md) topics.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e5d1-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="6e5d1-115">See Also</span></span>  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [<span data-ttu-id="6e5d1-116">使用 XPath 数据模型处理 XML 数据</span><span class="sxs-lookup"><span data-stu-id="6e5d1-116">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [<span data-ttu-id="6e5d1-117">使用 XPathNavigator 选择 XML 数据</span><span class="sxs-lookup"><span data-stu-id="6e5d1-117">Select XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/select-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="6e5d1-118">使用 XPathNavigator 计算 XPath 表达式</span><span class="sxs-lookup"><span data-stu-id="6e5d1-118">Evaluate XPath Expressions using XPathNavigator</span></span>](../../../../docs/standard/data/xml/evaluate-xpath-expressions-using-xpathnavigator.md)  
 [<span data-ttu-id="6e5d1-119">使用 XPathNavigator 匹配节点</span><span class="sxs-lookup"><span data-stu-id="6e5d1-119">Matching Nodes using XPathNavigator</span></span>](../../../../docs/standard/data/xml/matching-nodes-using-xpathnavigator.md)  
 [<span data-ttu-id="6e5d1-120">XPath 查询和命名空间</span><span class="sxs-lookup"><span data-stu-id="6e5d1-120">XPath Queries and Namespaces</span></span>](../../../../docs/standard/data/xml/xpath-queries-and-namespaces.md)  
 [<span data-ttu-id="6e5d1-121">已编译的 XPath 表达式</span><span class="sxs-lookup"><span data-stu-id="6e5d1-121">Compiled XPath Expressions</span></span>](../../../../docs/standard/data/xml/compiled-xpath-expressions.md)

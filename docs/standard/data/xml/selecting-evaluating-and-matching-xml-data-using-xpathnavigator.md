---
title: "使用 XPathNavigator 选择、计算和匹配 XML 数据"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 46e059f8-4dc8-4185-9236-784be95228ed
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7a86fb36d367342ea0c5bc4968bdd5744bd0524e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="selecting-evaluating-and-matching-xml-data-using-xpathnavigator"></a><span data-ttu-id="c0bf9-102">使用 XPathNavigator 选择、计算和匹配 XML 数据</span><span class="sxs-lookup"><span data-stu-id="c0bf9-102">Selecting, Evaluating and Matching XML Data using XPathNavigator</span></span>
<span data-ttu-id="c0bf9-103"><xref:System.Xml.XPath.XPathNavigator> 类提供的方法可以使用 XPath 查询在 <xref:System.Xml.XPath.XPathDocument> 或 <xref:System.Xml.XmlDocument> 对象中选择节点，计算和检查 XPath 表达式的结果，并确定 <xref:System.Xml.XPath.XPathDocument> 或 <xref:System.Xml.XmlDocument> 对象中的节点是否与给定的 XPath 表达式匹配。</span><span class="sxs-lookup"><span data-stu-id="c0bf9-103">The <xref:System.Xml.XPath.XPathNavigator> class provides methods to select nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object using an XPath query, evaluate and examine the results of an XPath expression, and determine if a node in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object matches a given XPath expression.</span></span> <span data-ttu-id="c0bf9-104">这些和其他一些与在 <xref:System.Xml.XPath.XPathDocument> 或 <xref:System.Xml.XmlDocument> 对象中选择、计算和匹配节点有关的概念在下面的主题中介绍。</span><span class="sxs-lookup"><span data-stu-id="c0bf9-104">These and other concepts that relate to selecting, evaluating and matching nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object are described in the following topics.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c0bf9-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="c0bf9-105">In This Section</span></span>  
 [<span data-ttu-id="c0bf9-106">使用 XPathNavigator 选择 XML 数据</span><span class="sxs-lookup"><span data-stu-id="c0bf9-106">Select XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/select-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="c0bf9-107">介绍用于使用 XPath 表达式在 <xref:System.Xml.XPath.XPathNavigator> 或 <xref:System.Xml.XPath.XPathDocument> 对象中选择节点集的 <xref:System.Xml.XmlDocument> 类方法集。</span><span class="sxs-lookup"><span data-stu-id="c0bf9-107">Describes the set of <xref:System.Xml.XPath.XPathNavigator> class methods used to select a set of nodes in an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object using an XPath expression.</span></span>  
  
 [<span data-ttu-id="c0bf9-108">使用 XPathNavigator 计算 XPath 表达式</span><span class="sxs-lookup"><span data-stu-id="c0bf9-108">Evaluate XPath Expressions using XPathNavigator</span></span>](../../../../docs/standard/data/xml/evaluate-xpath-expressions-using-xpathnavigator.md)  
 <span data-ttu-id="c0bf9-109">介绍 <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> 类中用于计算 XPath 表达式的 <xref:System.Xml.XPath.XPathNavigator> 方法。</span><span class="sxs-lookup"><span data-stu-id="c0bf9-109">Describes the <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> method of the <xref:System.Xml.XPath.XPathNavigator> class used to evaluate an XPath expression.</span></span>  
  
 [<span data-ttu-id="c0bf9-110">使用 XPathNavigator 匹配节点</span><span class="sxs-lookup"><span data-stu-id="c0bf9-110">Matching Nodes using XPathNavigator</span></span>](../../../../docs/standard/data/xml/matching-nodes-using-xpathnavigator.md)  
 <span data-ttu-id="c0bf9-111">介绍 <xref:System.Xml.XPath.XPathNavigator.Matches%2A> 类中用于确定节点是否与 XPath 表达式匹配的 <xref:System.Xml.XPath.XPathNavigator> 方法。</span><span class="sxs-lookup"><span data-stu-id="c0bf9-111">Describes the <xref:System.Xml.XPath.XPathNavigator.Matches%2A> method of the <xref:System.Xml.XPath.XPathNavigator> class used to determine if a node matches an XPath expression.</span></span>  
  
 [<span data-ttu-id="c0bf9-112">XPath 查询识别的节点类型</span><span class="sxs-lookup"><span data-stu-id="c0bf9-112">Node Types Recognized with XPath Queries</span></span>](../../../../docs/standard/data/xml/node-types-recognized-with-xpath-queries.md)  
 <span data-ttu-id="c0bf9-113">介绍 XPath 查询中可以识别的节点类型。</span><span class="sxs-lookup"><span data-stu-id="c0bf9-113">Describes the types of nodes recognized in an XPath query.</span></span>  
  
 [<span data-ttu-id="c0bf9-114">XPath 查询和命名空间</span><span class="sxs-lookup"><span data-stu-id="c0bf9-114">XPath Queries and Namespaces</span></span>](../../../../docs/standard/data/xml/xpath-queries-and-namespaces.md)  
 <span data-ttu-id="c0bf9-115">介绍 XPath 查询中命名空间的用法。</span><span class="sxs-lookup"><span data-stu-id="c0bf9-115">Describes the use of namespaces in an XPath query.</span></span>  
  
 [<span data-ttu-id="c0bf9-116">已编译的 XPath 表达式</span><span class="sxs-lookup"><span data-stu-id="c0bf9-116">Compiled XPath Expressions</span></span>](../../../../docs/standard/data/xml/compiled-xpath-expressions.md)  
 <span data-ttu-id="c0bf9-117">介绍表示已编译的 XPath 查询的 <xref:System.Xml.XPath.XPathExpression> 类。</span><span class="sxs-lookup"><span data-stu-id="c0bf9-117">Describes the <xref:System.Xml.XPath.XPathExpression> class that represents a compiled XPath query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0bf9-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c0bf9-118">See Also</span></span>  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [<span data-ttu-id="c0bf9-119">使用 XPath 数据模型处理 XML 数据</span><span class="sxs-lookup"><span data-stu-id="c0bf9-119">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [<span data-ttu-id="c0bf9-120">使用 XPathDocument 和 XmlDocument 读取 XML 数据</span><span class="sxs-lookup"><span data-stu-id="c0bf9-120">Reading XML Data using XPathDocument and XmlDocument</span></span>](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md)  
 [<span data-ttu-id="c0bf9-121">使用 XPathNavigator 访问 XML 数据</span><span class="sxs-lookup"><span data-stu-id="c0bf9-121">Accessing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="c0bf9-122">使用 XPathNavigator 编辑 XML 数据</span><span class="sxs-lookup"><span data-stu-id="c0bf9-122">Editing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/editing-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="c0bf9-123">使用 XPathNavigator 验证架构</span><span class="sxs-lookup"><span data-stu-id="c0bf9-123">Schema Validation using XPathNavigator</span></span>](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md)

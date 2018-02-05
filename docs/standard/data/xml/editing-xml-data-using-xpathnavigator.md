---
title: "使用 XPathNavigator 编辑 XML 数据"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b1f91616-3115-4264-9821-c66589d11d11
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: a967ee63a5ae9e9cc3abc5250af40ea7ba836a07
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="editing-xml-data-using-xpathnavigator"></a><span data-ttu-id="fc246-102">使用 XPathNavigator 编辑 XML 数据</span><span class="sxs-lookup"><span data-stu-id="fc246-102">Editing XML Data using XPathNavigator</span></span>
<span data-ttu-id="fc246-103"><xref:System.Xml.XPath.XPathNavigator> 类提供的方法用于在 <xref:System.Xml.XmlDocument> 对象包含的 XML 文档中插入、修改和移除节点和值。</span><span class="sxs-lookup"><span data-stu-id="fc246-103">The <xref:System.Xml.XPath.XPathNavigator> class provides methods to insert, modify and remove nodes and values from an XML document contained in an <xref:System.Xml.XmlDocument> object.</span></span> <span data-ttu-id="fc246-104">为了使用其中任何方法插入、修改和移除节点和值，<xref:System.Xml.XPath.XPathNavigator> 对象必须可编辑，即其 <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> 属性必须为 true。</span><span class="sxs-lookup"><span data-stu-id="fc246-104">In order to use any of these methods to insert, modify, and remove nodes and values, the <xref:System.Xml.XPath.XPathNavigator> object must be editable, that is, its <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> property must be true.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fc246-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="fc246-105">In This Section</span></span>  
 [<span data-ttu-id="fc246-106">使用 XPathNavigator 插入 XML 数据</span><span class="sxs-lookup"><span data-stu-id="fc246-106">Insert XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/insert-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="fc246-107">描述如何使用 <xref:System.Xml.XmlDocument> 类将同级节点、子节点、属性节点和相应值插入 <xref:System.Xml.XPath.XPathNavigator> 对象。</span><span class="sxs-lookup"><span data-stu-id="fc246-107">Describes how to insert sibling, child, attribute nodes and values in to an <xref:System.Xml.XmlDocument> object using the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
 [<span data-ttu-id="fc246-108">使用 XPathNavigator 修改 XML 数据</span><span class="sxs-lookup"><span data-stu-id="fc246-108">Modify XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/modify-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="fc246-109">描述如何使用 <xref:System.Xml.XmlDocument> 类修改 <xref:System.Xml.XPath.XPathNavigator> 对象中的节点和值。</span><span class="sxs-lookup"><span data-stu-id="fc246-109">Describes how to modify nodes and values in an <xref:System.Xml.XmlDocument> object using the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
 [<span data-ttu-id="fc246-110">使用 XPathNavigator 删除 XML 数据</span><span class="sxs-lookup"><span data-stu-id="fc246-110">Remove XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/remove-xml-data-using-xpathnavigator.md)  
 <span data-ttu-id="fc246-111">描述如何使用 <xref:System.Xml.XmlDocument> 类移除 <xref:System.Xml.XPath.XPathNavigator> 对象中的节点和值。</span><span class="sxs-lookup"><span data-stu-id="fc246-111">Describes how to remove nodes and values from an <xref:System.Xml.XmlDocument> object using the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc246-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="fc246-112">See Also</span></span>  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [<span data-ttu-id="fc246-113">使用 XPath 数据模型处理 XML 数据</span><span class="sxs-lookup"><span data-stu-id="fc246-113">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [<span data-ttu-id="fc246-114">使用 XPathDocument 和 XmlDocument 读取 XML 数据</span><span class="sxs-lookup"><span data-stu-id="fc246-114">Reading XML Data using XPathDocument and XmlDocument</span></span>](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md)  
 [<span data-ttu-id="fc246-115">使用 XPathNavigator 选择、计算和匹配 XML 数据</span><span class="sxs-lookup"><span data-stu-id="fc246-115">Selecting, Evaluating and Matching XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/selecting-evaluating-and-matching-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="fc246-116">使用 XPathNavigator 访问 XML 数据</span><span class="sxs-lookup"><span data-stu-id="fc246-116">Accessing XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/accessing-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="fc246-117">使用 XPathNavigator 验证架构</span><span class="sxs-lookup"><span data-stu-id="fc246-117">Schema Validation using XPathNavigator</span></span>](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md)

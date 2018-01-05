---
title: "System.Xml 使用情况"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 956cc0ba37c06b39ed32500209e1af47d4035c84
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="systemxml-usage"></a><span data-ttu-id="73c57-102">System.Xml 使用情况</span><span class="sxs-lookup"><span data-stu-id="73c57-102">System.Xml Usage</span></span>
<span data-ttu-id="73c57-103">本部分介绍有关驻留在的几种类型的使用情况<xref:System.Xml?displayProperty=nameWithType>可以用于表示 XML 数据的命名空间。</span><span class="sxs-lookup"><span data-stu-id="73c57-103">This section talks about usage of several types residing in <xref:System.Xml?displayProperty=nameWithType> namespaces that can be used to represent XML data.</span></span>  
  
 <span data-ttu-id="73c57-104">**X 不**使用<xref:System.Xml.XmlNode>或<xref:System.Xml.XmlDocument>来表示 XML 数据。</span><span class="sxs-lookup"><span data-stu-id="73c57-104">**X DO NOT** use <xref:System.Xml.XmlNode> or <xref:System.Xml.XmlDocument> to represent XML data.</span></span> <span data-ttu-id="73c57-105">倾向于使用的实例<xref:System.Xml.XPath.IXPathNavigable>， <xref:System.Xml.XmlReader>， <xref:System.Xml.XmlWriter>，或子类型的<xref:System.Xml.Linq.XNode>相反。</span><span class="sxs-lookup"><span data-stu-id="73c57-105">Favor using instances of <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, or subtypes of <xref:System.Xml.Linq.XNode> instead.</span></span> <span data-ttu-id="73c57-106">`XmlNode`和`XmlDocument`不适用于公共 Api 中公开。</span><span class="sxs-lookup"><span data-stu-id="73c57-106">`XmlNode` and `XmlDocument` are not designed for exposing in public APIs.</span></span>  
  
 <span data-ttu-id="73c57-107">**✓ 执行**使用`XmlReader`， `IXPathNavigable`，或子类型的`XNode`为输入或输出的接受或返回 XML 的成员。</span><span class="sxs-lookup"><span data-stu-id="73c57-107">**✓ DO** use `XmlReader`, `IXPathNavigable`, or subtypes of `XNode` as input or output of members that accept or return XML.</span></span>  
  
 <span data-ttu-id="73c57-108">使用而不是这些抽象映射`XmlDocument`， `XmlNode`，或<xref:System.Xml.XPath.XPathDocument>，因为这将从内存中 XML 文档的特定实现的方法脱耦，并允许它们可以使用虚拟公开的 XML 数据源`XNode``XmlReader`，或<xref:System.Xml.XPath.XPathNavigator>。</span><span class="sxs-lookup"><span data-stu-id="73c57-108">Use these abstractions instead of `XmlDocument`, `XmlNode`, or <xref:System.Xml.XPath.XPathDocument>, because this decouples the methods from specific implementations of an in-memory XML document and allows them to work with virtual XML data sources that expose `XNode`, `XmlReader`, or <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
 <span data-ttu-id="73c57-109">**X 不**子类`XmlDocument`如果你想要创建表示基础对象模型或数据源的 XML 视图的类型。</span><span class="sxs-lookup"><span data-stu-id="73c57-109">**X DO NOT** subclass `XmlDocument` if you want to create a type representing an XML view of an underlying object model or data source.</span></span>  
  
 <span data-ttu-id="73c57-110">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="73c57-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="73c57-111">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="73c57-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73c57-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="73c57-112">See Also</span></span>  
 [<span data-ttu-id="73c57-113">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="73c57-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="73c57-114">使用准则</span><span class="sxs-lookup"><span data-stu-id="73c57-114">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)

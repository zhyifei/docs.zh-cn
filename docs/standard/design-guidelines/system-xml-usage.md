---
title: System.Xml 使用情况
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 82302f0d-a621-4c6f-b57d-999bd61f21a6
ms.openlocfilehash: c57f5451526094d58066d7d391f41795f17732de
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709031"
---
# <a name="systemxml-usage"></a><span data-ttu-id="19f0c-102">System.Xml 使用情况</span><span class="sxs-lookup"><span data-stu-id="19f0c-102">System.Xml Usage</span></span>
<span data-ttu-id="19f0c-103">本部分介绍 <xref:System.Xml?displayProperty=nameWithType> 命名空间中的可以用于表示 XML 数据的几种类型的用法。</span><span class="sxs-lookup"><span data-stu-id="19f0c-103">This section talks about usage of several types residing in <xref:System.Xml?displayProperty=nameWithType> namespaces that can be used to represent XML data.</span></span>  
  
 <span data-ttu-id="19f0c-104">**X 切忌**使用 <xref:System.Xml.XmlNode> 或 <xref:System.Xml.XmlDocument> 来表示 XML 数据。</span><span class="sxs-lookup"><span data-stu-id="19f0c-104">**X DO NOT** use <xref:System.Xml.XmlNode> or <xref:System.Xml.XmlDocument> to represent XML data.</span></span> <span data-ttu-id="19f0c-105">相反，倾向使用 <xref:System.Xml.XPath.IXPathNavigable>、<xref:System.Xml.XmlReader>、<xref:System.Xml.XmlWriter> 或 <xref:System.Xml.Linq.XNode> 的子类型。</span><span class="sxs-lookup"><span data-stu-id="19f0c-105">Favor using instances of <xref:System.Xml.XPath.IXPathNavigable>, <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, or subtypes of <xref:System.Xml.Linq.XNode> instead.</span></span> <span data-ttu-id="19f0c-106">`XmlNode` 和 `XmlDocument` 不是为在公共 API 中公开而设计的。</span><span class="sxs-lookup"><span data-stu-id="19f0c-106">`XmlNode` and `XmlDocument` are not designed for exposing in public APIs.</span></span>  
  
 <span data-ttu-id="19f0c-107">**✓ 务必**使用 `XmlReader`、`IXPathNavigable` 或 `XNode` 的子类型作为接受或返回 XML 的成员的输入或输出。</span><span class="sxs-lookup"><span data-stu-id="19f0c-107">**✓ DO** use `XmlReader`, `IXPathNavigable`, or subtypes of `XNode` as input or output of members that accept or return XML.</span></span>  
  
 <span data-ttu-id="19f0c-108">使用这些抽象的项，而不是 `XmlDocument`、`XmlNode` 或 <xref:System.Xml.XPath.XPathDocument>，因为这将方法与内存中 XML 文档的特定实现解耦，并允许它们与公开 `XNode`、`XmlReader` 或 <xref:System.Xml.XPath.XPathNavigator> 的虚拟 XML 数据源一起使用。</span><span class="sxs-lookup"><span data-stu-id="19f0c-108">Use these abstractions instead of `XmlDocument`, `XmlNode`, or <xref:System.Xml.XPath.XPathDocument>, because this decouples the methods from specific implementations of an in-memory XML document and allows them to work with virtual XML data sources that expose `XNode`, `XmlReader`, or <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
 <span data-ttu-id="19f0c-109">**X 切忌**将 `XmlDocument` 子类化，如果想要创建用来表示底层对象模型或数据源的 XML 视图的类型。</span><span class="sxs-lookup"><span data-stu-id="19f0c-109">**X DO NOT** subclass `XmlDocument` if you want to create a type representing an XML view of an underlying object model or data source.</span></span>  
  
 <span data-ttu-id="19f0c-110">*部分©2005，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="19f0c-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="19f0c-111">\*在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。</span><span class="sxs-lookup"><span data-stu-id="19f0c-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19f0c-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="19f0c-112">See also</span></span>

- [<span data-ttu-id="19f0c-113">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="19f0c-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="19f0c-114">使用准则</span><span class="sxs-lookup"><span data-stu-id="19f0c-114">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)

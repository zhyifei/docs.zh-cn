---
title: 转换中的节点集
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: ad034f0e-ff8b-4a71-9a4c-528c754263c4
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 23632a5df10c1ab2d1afa654d5438a4ebd903d5f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54603035"
---
# <a name="node-sets-in-transformations"></a><span data-ttu-id="f0489-102">转换中的节点集</span><span class="sxs-lookup"><span data-stu-id="f0489-102">Node Sets in Transformations</span></span>
<span data-ttu-id="f0489-103">节点集是从 XML 路径语言 (XPath) 表达式返回的四种基本数据类型之一。</span><span class="sxs-lookup"><span data-stu-id="f0489-103">Node sets are one of four basic data types that are returned from XML Path Language (XPath) expressions.</span></span> <span data-ttu-id="f0489-104">节点集是按文档顺序创建的无重复节点的无序集合，可将其分配给样式表中的某个变量。</span><span class="sxs-lookup"><span data-stu-id="f0489-104">A node set, which is an unordered collection of nodes without duplicates, created in document order, can be assigned to a variable in a style sheet.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0489-105"><xref:System.Xml.Xsl.XslTransform> 类在 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] 中已过期。</span><span class="sxs-lookup"><span data-stu-id="f0489-105">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span> <span data-ttu-id="f0489-106">可以使用 <xref:System.Xml.Xsl.XslCompiledTransform> 类执行可扩展样式表语言转换 (XSLT) 转换。</span><span class="sxs-lookup"><span data-stu-id="f0489-106">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="f0489-107">请参阅[使用 XslCompiledTransform 类](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)和[从 XslTransform 类迁移](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)，以获取详细信息。</span><span class="sxs-lookup"><span data-stu-id="f0489-107">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="f0489-108">节点集是从 XPath 表达式返回的四种基本数据类型之一。</span><span class="sxs-lookup"><span data-stu-id="f0489-108">Node sets are one of four basic data types that are returned from XPath expressions.</span></span> <span data-ttu-id="f0489-109">节点集是按文档顺序创建的无重复节点的无序集合，可将其分配给样式表中的某个变量。</span><span class="sxs-lookup"><span data-stu-id="f0489-109">A node set, which is an unordered collection of nodes without duplicates, created in document order, can be assigned to a variable in a style sheet.</span></span> <span data-ttu-id="f0489-110">此节点集是在转换中的 `select` 属性中使用的 XPath 表达式的结果，它与 XML 文档对象模型 (DOM) 中的节点集有相同的行为。</span><span class="sxs-lookup"><span data-stu-id="f0489-110">This node set, which is a result of an XPath expression used in a `select` attribute in a transformation, has the same behavior as a node set from the XML Document Object Model (DOM).</span></span> <span data-ttu-id="f0489-111">可以使用[使用 XPathNavigator 的节点集定位](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md)中介绍的一组方法浏览节点集，与结果树片断不同，后者使用 <xref:System.Xml.XPath.XPathNodeIterator> 进行浏览。</span><span class="sxs-lookup"><span data-stu-id="f0489-111">You can navigate a node set using a set of methods shown in [Node Set Navigation Using XPathNavigator](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md), unlike a result tree fragment or result tree fragment, which uses the <xref:System.Xml.XPath.XPathNodeIterator> for navigation.</span></span>  
  
 <span data-ttu-id="f0489-112">下面的代码示例显示了当样式表中的某个 `variable` 或 `parameter` 元素计算结果为节点集时如何循环访问节点集。</span><span class="sxs-lookup"><span data-stu-id="f0489-112">The following code sample shows how to iterate over a node set when a `variable` or `parameter` element in a style sheet evaluates to a node set.</span></span>  
  
## <a name="style-sheet"></a><span data-ttu-id="f0489-113">样式表</span><span class="sxs-lookup"><span data-stu-id="f0489-113">Style Sheet</span></span>  
  
```xml  
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform" version="1.0">  
  
    <xsl:variable name="x" select="bookstore/book/title"></xsl:variable>  
  
    <xsl:template match="/">  
        <xsl:for-each select="$x">  
            ******  
            <xsl:value-of select="."></xsl:value-of>  
            ******  
        </xsl:for-each>  
    </xsl:template>  
  
</xsl:stylesheet>  
```  
  
## <a name="input"></a><span data-ttu-id="f0489-114">输入</span><span class="sxs-lookup"><span data-stu-id="f0489-114">Input</span></span>  
  
```xml  
<bookstore>  
   <book style="autobiography">  
      <title>Seven Years in Trenton</title>  
   </book>  
  
   <book style="autobiography">  
      <title>Seven Years in Trenton2</title>  
   </book>  
  
   <book style="textbook">  
      <title>History of Trenton Vol 3</title>  
   </book>  
</bookstore>  
```  
  
## <a name="output"></a><span data-ttu-id="f0489-115">输出</span><span class="sxs-lookup"><span data-stu-id="f0489-115">Output</span></span>  
  
```  
******  
Seven Years in Trenton  
******  
  
******  
Seven Years in Trenton2  
******  
  
******  
History of Trenton Vol 3  
******  
```  
  
## <a name="see-also"></a><span data-ttu-id="f0489-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="f0489-116">See also</span></span>

- <xref:System.Xml.XPath.XPathNodeIterator>
- [<span data-ttu-id="f0489-117">XslTransform 类的 XSLT 转换</span><span class="sxs-lookup"><span data-stu-id="f0489-117">XSLT Transformations with the XslTransform Class</span></span>](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)
- [<span data-ttu-id="f0489-118">XslTransform 类实现 XSLT 处理器</span><span class="sxs-lookup"><span data-stu-id="f0489-118">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)

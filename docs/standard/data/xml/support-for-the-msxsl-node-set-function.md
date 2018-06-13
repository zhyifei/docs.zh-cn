---
title: 对 msxsl:node-set() 函数的支持
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: d0cbf517-d9f6-4097-9851-4fa62903decd
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d3eb24d76ffb07b36b837056ffa5cde0cbd37f5f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33570518"
---
# <a name="support-for-the-msxslnode-set-function"></a><span data-ttu-id="ae87d-102">对 msxsl:node-set() 函数的支持</span><span class="sxs-lookup"><span data-stu-id="ae87d-102">Support for the msxsl:node-set() Function</span></span>
<span data-ttu-id="ae87d-103">`msxsl:node-set` 函数使您能够将结果树片段转换成节点集。</span><span class="sxs-lookup"><span data-stu-id="ae87d-103">The `msxsl:node-set` function enables you to convert a result tree fragment into a node set.</span></span> <span data-ttu-id="ae87d-104">生成的节点集总是包含单个节点并且是树的根节点。</span><span class="sxs-lookup"><span data-stu-id="ae87d-104">The resulting node set always contains a single node and is the root node of the tree.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ae87d-105"><xref:System.Xml.Xsl.XslTransform> 类在 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] 中已过期。</span><span class="sxs-lookup"><span data-stu-id="ae87d-105">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span> <span data-ttu-id="ae87d-106">可以使用 <xref:System.Xml.Xsl.XslCompiledTransform> 类执行可扩展样式表语言转换 (XSLT) 转换。</span><span class="sxs-lookup"><span data-stu-id="ae87d-106">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="ae87d-107">请参阅[使用 XslCompiledTransform 类](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)和[从 XslTransform 类迁移](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)，以获取详细信息。</span><span class="sxs-lookup"><span data-stu-id="ae87d-107">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="ae87d-108">`msxsl:node-set` 函数使您能够将结果树片段转换成节点集。</span><span class="sxs-lookup"><span data-stu-id="ae87d-108">The `msxsl:node-set` function enables you to convert a result tree fragment into a node set.</span></span> <span data-ttu-id="ae87d-109">生成的节点集总是包含单个节点并且是树的根节点。</span><span class="sxs-lookup"><span data-stu-id="ae87d-109">The resulting node set always contains a single node and is the root node of the tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae87d-110">示例</span><span class="sxs-lookup"><span data-stu-id="ae87d-110">Example</span></span>  
 <span data-ttu-id="ae87d-111">在下面的示例中，`$var` 是一个变量，是样式表中的一个节点树。</span><span class="sxs-lookup"><span data-stu-id="ae87d-111">In the following example, `$var` is a variable that is a node tree in the style sheet.</span></span> <span data-ttu-id="ae87d-112">for-each 语句与 `node-set` 函数组合使用，允许用户将此节点树作为节点集循环访问。</span><span class="sxs-lookup"><span data-stu-id="ae87d-112">The for-each statement combined with the `node-set` function allows the user to iterate over this node tree as a node set.</span></span>  
  
## <a name="nodesetxsl"></a><span data-ttu-id="ae87d-113">nodeset.xsl</span><span class="sxs-lookup"><span data-stu-id="ae87d-113">nodeset.xsl</span></span>  
  
```xml  
<xsl:stylesheet xmlns:xsl="http://www.w3.org/1999/XSL/Transform"  
                xmlns:msxsl="urn:schemas-microsoft-com:xslt"  
                xmlns:user="http://www.contoso.com"  
                version="1.0">  
    <xsl:variable name="books">  
        <book author="Michael Howard">Writing Secure Code</book>  
        <book author="Michael Kay">XSLT Reference</book>  
    </xsl:variable>  
  
    <xsl:template match="/">  
        <authors>  
            <xsl:for-each select="msxsl:node-set($books)/book">   
                <author><xsl:value-of select="@author"/)</author>  
            </xsl:for-each>  
        </authors>  
    </xsl:template>  
</xsl:stylesheet>  
```  
  
## <a name="output"></a><span data-ttu-id="ae87d-114">输出</span><span class="sxs-lookup"><span data-stu-id="ae87d-114">Output</span></span>  
 <span data-ttu-id="ae87d-115">转换的输出为</span><span class="sxs-lookup"><span data-stu-id="ae87d-115">The output of the transformation is</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<authors><author>Michael Howard</author><author>Michael Kay</author></authors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ae87d-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae87d-116">See Also</span></span>  
 [<span data-ttu-id="ae87d-117">XslTransform 类实现 XSLT 处理器</span><span class="sxs-lookup"><span data-stu-id="ae87d-117">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)

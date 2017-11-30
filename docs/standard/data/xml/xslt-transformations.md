---
title: "XSLT 转换"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 202f8820-224c-494f-b61e-cd127eac6e03
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0d7fa8492487daff68fd8ebaf4159dd537d13e51
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="xslt-transformations"></a><span data-ttu-id="6ad84-102">XSLT 转换</span><span class="sxs-lookup"><span data-stu-id="6ad84-102">XSLT Transformations</span></span>
<span data-ttu-id="6ad84-103">可扩展样式表语言转换 (XSLT) 可以将源 XML 文档的内容转换为另一个格式或结构不同的文档。</span><span class="sxs-lookup"><span data-stu-id="6ad84-103">The Extensible Stylesheet Language Transformation (XSLT) lets you transform the content of a source XML document into another document that is different in format or structure.</span></span> <span data-ttu-id="6ad84-104">例如，可以使用 XSLT 将 XML 转换为在网站上使用的 HTML 或转换为只包含应用程序所需字段的文档。</span><span class="sxs-lookup"><span data-stu-id="6ad84-104">For example, you can use XSLT to transform XML into HTML for use on a Web site or to transform it into a document that contains only the fields required by an application.</span></span> <span data-ttu-id="6ad84-105">此转换过程由指定[W3C XSL 转换 (XSLT) 1.0 版建议](http://go.microsoft.com/fwlink/?LinkID=49919)。</span><span class="sxs-lookup"><span data-stu-id="6ad84-105">This transformation process is specified by the [W3C XSL Transformations (XSLT) Version 1.0 recommendation](http://go.microsoft.com/fwlink/?LinkID=49919).</span></span>  
  
 <span data-ttu-id="6ad84-106"><xref:System.Xml.Xsl.XslCompiledTransform> 类是 .NET Framework 中的 XSLT 处理器。</span><span class="sxs-lookup"><span data-stu-id="6ad84-106">The <xref:System.Xml.Xsl.XslCompiledTransform> class is the XSLT processor in the .NET Framework.</span></span> <span data-ttu-id="6ad84-107"><xref:System.Xml.Xsl.XslCompiledTransform> 类支持 W3C XSLT 1.0 建议。</span><span class="sxs-lookup"><span data-stu-id="6ad84-107">The <xref:System.Xml.Xsl.XslCompiledTransform> class supports the W3C XSLT 1.0 recommendation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6ad84-108"><xref:System.Xml.Xsl.XslTransform> 类在 .NET Framework 2.0 版中已过时。</span><span class="sxs-lookup"><span data-stu-id="6ad84-108">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in .NET Framework version 2.0.</span></span> <span data-ttu-id="6ad84-109"><xref:System.Xml.Xsl.XslCompiledTransform> 类是 XSLT 引擎的新实现。</span><span class="sxs-lookup"><span data-stu-id="6ad84-109">The <xref:System.Xml.Xsl.XslCompiledTransform> class is a new implementation of the XSLT engine.</span></span> <span data-ttu-id="6ad84-110">它包括性能改进和新的安全功能。</span><span class="sxs-lookup"><span data-stu-id="6ad84-110">It includes performance improvements and new security features.</span></span> <span data-ttu-id="6ad84-111">建议的做法是使用 <xref:System.Xml.Xsl.XslCompiledTransform> 类创建 XSLT 应用程序。</span><span class="sxs-lookup"><span data-stu-id="6ad84-111">The recommended practice is to create XSLT applications using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6ad84-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="6ad84-112">In This Section</span></span>  
 [<span data-ttu-id="6ad84-113">使用 XslCompiledTransform 类</span><span class="sxs-lookup"><span data-stu-id="6ad84-113">Using the XslCompiledTransform Class</span></span>](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)  
 <span data-ttu-id="6ad84-114">提供如何使用 <xref:System.Xml.Xsl.XslCompiledTransform> 类的信息。</span><span class="sxs-lookup"><span data-stu-id="6ad84-114">Provides information on using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
 [<span data-ttu-id="6ad84-115">从 XslTransform 类迁移</span><span class="sxs-lookup"><span data-stu-id="6ad84-115">Migrating From the XslTransform Class</span></span>](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)  
 <span data-ttu-id="6ad84-116">讨论如何从 <xref:System.Xml.Xsl.XslTransform> 类迁移代码。</span><span class="sxs-lookup"><span data-stu-id="6ad84-116">Discusses how to migrate code from the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
 [<span data-ttu-id="6ad84-117">XSLT 编译器 (xsltc.exe)</span><span class="sxs-lookup"><span data-stu-id="6ad84-117">XSLT Compiler (xsltc.exe)</span></span>](../../../../docs/standard/data/xml/xslt-compiler-xsltc-exe.md)  
 <span data-ttu-id="6ad84-118">提供有关如何使用 XSLT 编译器的信息。</span><span class="sxs-lookup"><span data-stu-id="6ad84-118">Provides information on using the XSLT compiler.</span></span>  
  
 [<span data-ttu-id="6ad84-119">XslTransform 类的 XSLT 转换</span><span class="sxs-lookup"><span data-stu-id="6ad84-119">XSLT Transformations with the XslTransform Class</span></span>](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)  
 <span data-ttu-id="6ad84-120">提供如何使用 <xref:System.Xml.Xsl.XslTransform> 类的信息。</span><span class="sxs-lookup"><span data-stu-id="6ad84-120">Provides information on using the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
 <span data-ttu-id="6ad84-121">**请注意**<xref:System.Xml.Xsl.XslTransform>类是.NET Framework 2.0 版本中已过时。</span><span class="sxs-lookup"><span data-stu-id="6ad84-121">**Note** The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the .NET Framework 2.0 release.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="6ad84-122">参考</span><span class="sxs-lookup"><span data-stu-id="6ad84-122">Reference</span></span>  
 <xref:System.Xml.Xsl.XslCompiledTransform>  
  
 <xref:System.Xml.Xsl.XsltArgumentList>  
  
 <xref:System.Xml.Xsl.XsltSettings>  
  
## <a name="related-sections"></a><span data-ttu-id="6ad84-123">相关章节</span><span class="sxs-lookup"><span data-stu-id="6ad84-123">Related Sections</span></span>  
 [<span data-ttu-id="6ad84-124">XML 文档和数据</span><span class="sxs-lookup"><span data-stu-id="6ad84-124">XML Documents and Data</span></span>](../../../../docs/standard/data/xml/index.md)

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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 63c73fc48d0beaeb3a77acc464734b11410467a0
ms.sourcegitcommit: ba765893e3efcece67d99fd6d5ce0074b050d1d9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2018
---
# <a name="xslt-transformations"></a><span data-ttu-id="b24e3-102">XSLT 转换</span><span class="sxs-lookup"><span data-stu-id="b24e3-102">XSLT Transformations</span></span>
<span data-ttu-id="b24e3-103">可扩展样式表语言转换 (XSLT) 可以将源 XML 文档的内容转换为另一个格式或结构不同的文档。</span><span class="sxs-lookup"><span data-stu-id="b24e3-103">The Extensible Stylesheet Language Transformation (XSLT) lets you transform the content of a source XML document into another document that is different in format or structure.</span></span> <span data-ttu-id="b24e3-104">例如，可以使用 XSLT 将 XML 转换为在网站上使用的 HTML 或转换为只包含应用程序所需字段的文档。</span><span class="sxs-lookup"><span data-stu-id="b24e3-104">For example, you can use XSLT to transform XML into HTML for use on a Web site or to transform it into a document that contains only the fields required by an application.</span></span> <span data-ttu-id="b24e3-105">此转换过程由 [W3C XSL 转换 (XSLT) 版本 1.0 建议](https://www.w3.org/TR/xslt-10/)规定。</span><span class="sxs-lookup"><span data-stu-id="b24e3-105">This transformation process is specified by the [W3C XSL Transformations (XSLT) Version 1.0 recommendation](https://www.w3.org/TR/xslt-10/).</span></span>  
  
 <span data-ttu-id="b24e3-106"><xref:System.Xml.Xsl.XslCompiledTransform> 类是 .NET 中的 XSLT 处理器。</span><span class="sxs-lookup"><span data-stu-id="b24e3-106">The <xref:System.Xml.Xsl.XslCompiledTransform> class is the XSLT processor in .NET.</span></span> <span data-ttu-id="b24e3-107"><xref:System.Xml.Xsl.XslCompiledTransform> 类支持 [W3C XSLT 1.0 建议](https://www.w3.org/TR/xslt-10/)。</span><span class="sxs-lookup"><span data-stu-id="b24e3-107">The <xref:System.Xml.Xsl.XslCompiledTransform> class supports the [W3C XSLT 1.0 recommendation](https://www.w3.org/TR/xslt-10/).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b24e3-108"><xref:System.Xml.Xsl.XslTransform> 类在 .NET Framework 2.0 版中已过时。</span><span class="sxs-lookup"><span data-stu-id="b24e3-108">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in .NET Framework version 2.0.</span></span> <span data-ttu-id="b24e3-109"><xref:System.Xml.Xsl.XslCompiledTransform> 类是 XSLT 引擎的新实现。</span><span class="sxs-lookup"><span data-stu-id="b24e3-109">The <xref:System.Xml.Xsl.XslCompiledTransform> class is a new implementation of the XSLT engine.</span></span> <span data-ttu-id="b24e3-110">它包括性能改进和新的安全功能。</span><span class="sxs-lookup"><span data-stu-id="b24e3-110">It includes performance improvements and new security features.</span></span> <span data-ttu-id="b24e3-111">建议的做法是使用 <xref:System.Xml.Xsl.XslCompiledTransform> 类创建 XSLT 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b24e3-111">The recommended practice is to create XSLT applications using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b24e3-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="b24e3-112">In This Section</span></span>  
 [<span data-ttu-id="b24e3-113">使用 XslCompiledTransform 类</span><span class="sxs-lookup"><span data-stu-id="b24e3-113">Using the XslCompiledTransform Class</span></span>](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)  
 <span data-ttu-id="b24e3-114">提供如何使用 <xref:System.Xml.Xsl.XslCompiledTransform> 类的信息。</span><span class="sxs-lookup"><span data-stu-id="b24e3-114">Provides information on using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
 [<span data-ttu-id="b24e3-115">从 XslTransform 类迁移</span><span class="sxs-lookup"><span data-stu-id="b24e3-115">Migrating From the XslTransform Class</span></span>](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)  
 <span data-ttu-id="b24e3-116">讨论如何从 <xref:System.Xml.Xsl.XslTransform> 类迁移代码。</span><span class="sxs-lookup"><span data-stu-id="b24e3-116">Discusses how to migrate code from the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
 [<span data-ttu-id="b24e3-117">XSLT 编译器 (xsltc.exe)</span><span class="sxs-lookup"><span data-stu-id="b24e3-117">XSLT Compiler (xsltc.exe)</span></span>](../../../../docs/standard/data/xml/xslt-compiler-xsltc-exe.md)  
 <span data-ttu-id="b24e3-118">提供有关如何使用 XSLT 编译器的信息。</span><span class="sxs-lookup"><span data-stu-id="b24e3-118">Provides information on using the XSLT compiler.</span></span>  
  
 [<span data-ttu-id="b24e3-119">XslTransform 类的 XSLT 转换</span><span class="sxs-lookup"><span data-stu-id="b24e3-119">XSLT Transformations with the XslTransform Class</span></span>](../../../../docs/standard/data/xml/xslt-transformations-with-the-xsltransform-class.md)  
 <span data-ttu-id="b24e3-120">提供如何使用 <xref:System.Xml.Xsl.XslTransform> 类的信息。</span><span class="sxs-lookup"><span data-stu-id="b24e3-120">Provides information on using the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="b24e3-121">参考</span><span class="sxs-lookup"><span data-stu-id="b24e3-121">Reference</span></span>  
 <xref:System.Xml.Xsl.XslCompiledTransform>  
 <xref:System.Xml.Xsl.XsltArgumentList>  
 <xref:System.Xml.Xsl.XsltSettings>  
  
## <a name="related-sections"></a><span data-ttu-id="b24e3-122">相关章节</span><span class="sxs-lookup"><span data-stu-id="b24e3-122">Related Sections</span></span>  
 [<span data-ttu-id="b24e3-123">XML 文档和数据</span><span class="sxs-lookup"><span data-stu-id="b24e3-123">XML Documents and Data</span></span>](../../../../docs/standard/data/xml/index.md)

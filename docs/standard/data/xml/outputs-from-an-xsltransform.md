---
title: "XslTransform 的输出"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8e149d32-4b2f-493f-9e4b-d0d93475acde
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 647f3829f4b26791c063d5646669b2fcb7ab6684
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="outputs-from-an-xsltransform"></a><span data-ttu-id="4831d-102">XslTransform 的输出</span><span class="sxs-lookup"><span data-stu-id="4831d-102">Outputs from an XslTransform</span></span>
<span data-ttu-id="4831d-103">样式表可以结合使用 `<xsl:output>` 语句和 `method` 属性来确定输出格式，下表说明了使用 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 方法写入输出并将输出格式声明为 <xref:System.IO.Stream> 或 <xref:System.IO.TextWriter> 时的输出格式。</span><span class="sxs-lookup"><span data-stu-id="4831d-103">Since style sheets can determine the output format using an `<xsl:output>` statement with the `method` attribute, the following table describes what the output format is when the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method is used to write the output, and the output format is declared as a <xref:System.IO.Stream> or <xref:System.IO.TextWriter>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4831d-104"><xref:System.Xml.Xsl.XslTransform> 类在 [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)] 中已过期。</span><span class="sxs-lookup"><span data-stu-id="4831d-104">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].</span></span> <span data-ttu-id="4831d-105">可以使用 <xref:System.Xml.Xsl.XslCompiledTransform> 类执行可扩展样式表语言转换 (XSLT) 转换。</span><span class="sxs-lookup"><span data-stu-id="4831d-105">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="4831d-106">请参阅[使用 XslCompiledTransform 类](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)和[从 XslTransform 类迁移](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)，以获取详细信息。</span><span class="sxs-lookup"><span data-stu-id="4831d-106">See [Using the XslCompiledTransform Class](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md) for more information.</span></span>  
  
 <span data-ttu-id="4831d-107">样式表可以结合使用 `<xsl:output>` 语句和 `method` 属性来确定输出格式，下表说明了使用 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 方法写入输出并将输出格式声明为 <xref:System.IO.Stream> 或 <xref:System.IO.TextWriter> 时的输出格式。</span><span class="sxs-lookup"><span data-stu-id="4831d-107">Since style sheets can determine the output format using an `<xsl:output>` statement with the `method` attribute, the following table describes what the output format is when the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method is used to write the output, and the output format is declared as a <xref:System.IO.Stream> or <xref:System.IO.TextWriter>.</span></span> <span data-ttu-id="4831d-108">下表说明了结合使用 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 方法和 `<xsl:output>` 语句来声明输出类型时的结果：</span><span class="sxs-lookup"><span data-stu-id="4831d-108">The following table describes what happens when an output type is declared by the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method in conjunction with the use of an `<xsl:output>` statement:</span></span>  
  
|<span data-ttu-id="4831d-109">\<xsl:output method = > attribute</span><span class="sxs-lookup"><span data-stu-id="4831d-109">\<xsl:output method = > attribute</span></span>|<span data-ttu-id="4831d-110">结果格式</span><span class="sxs-lookup"><span data-stu-id="4831d-110">Result format</span></span>|  
|-----------------------------------------|-------------------|  
|<span data-ttu-id="4831d-111">method="xml"</span><span class="sxs-lookup"><span data-stu-id="4831d-111">method="xml"</span></span>|<span data-ttu-id="4831d-112">XML</span><span class="sxs-lookup"><span data-stu-id="4831d-112">XML</span></span>|  
|<span data-ttu-id="4831d-113">method="html"</span><span class="sxs-lookup"><span data-stu-id="4831d-113">method="html"</span></span>|<span data-ttu-id="4831d-114">HTML</span><span class="sxs-lookup"><span data-stu-id="4831d-114">HTML</span></span>|  
|<span data-ttu-id="4831d-115">method="text"</span><span class="sxs-lookup"><span data-stu-id="4831d-115">method="text"</span></span>|<span data-ttu-id="4831d-116">Text</span><span class="sxs-lookup"><span data-stu-id="4831d-116">Text</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="4831d-117">注意：当 `<xsl:output>` 方法的输出为 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 或 <xref:System.Xml.XmlReader> 时，将忽略 <xref:System.Xml.XmlWriter> 语句。</span><span class="sxs-lookup"><span data-stu-id="4831d-117">Note: The `<xsl:output>` statement is ignored when the output of the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method is an <xref:System.Xml.XmlReader> or <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="4831d-118">如果 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 方法的输出为 <xref:System.IO.Stream> 或 <xref:System.IO.TextWriter>，将支持下列属性：</span><span class="sxs-lookup"><span data-stu-id="4831d-118">The following attributes are supported when the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method output is a <xref:System.IO.Stream> or <xref:System.IO.TextWriter>:</span></span>  
  
-   <span data-ttu-id="4831d-119">encoding\*</span><span class="sxs-lookup"><span data-stu-id="4831d-119">encoding\*</span></span>  
  
-   <span data-ttu-id="4831d-120">omit-xml-declaration</span><span class="sxs-lookup"><span data-stu-id="4831d-120">omit-xml-declaration</span></span>  
  
-   <span data-ttu-id="4831d-121">独立</span><span class="sxs-lookup"><span data-stu-id="4831d-121">standalone</span></span>  
  
-   <span data-ttu-id="4831d-122">doctype-public</span><span class="sxs-lookup"><span data-stu-id="4831d-122">doctype-public</span></span>  
  
-   <span data-ttu-id="4831d-123">doctype-system</span><span class="sxs-lookup"><span data-stu-id="4831d-123">doctype-system</span></span>  
  
-   <span data-ttu-id="4831d-124">cdata-section-elements</span><span class="sxs-lookup"><span data-stu-id="4831d-124">cdata-section-elements</span></span>  
  
-   <span data-ttu-id="4831d-125">indent</span><span class="sxs-lookup"><span data-stu-id="4831d-125">indent</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4831d-126">\*如果 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 方法将其输出发送到 <xref:System.IO.TextWriter>，将忽略 encoding 属性。</span><span class="sxs-lookup"><span data-stu-id="4831d-126">\*the encoding attribute is ignored when the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method is sending its output to a <xref:System.IO.TextWriter>.</span></span> <span data-ttu-id="4831d-127">而是改用 <xref:System.IO.TextWriter> 的 encoding 属性。</span><span class="sxs-lookup"><span data-stu-id="4831d-127">The encoding property on the <xref:System.IO.TextWriter> is used instead.</span></span>  
  
 <span data-ttu-id="4831d-128">如果 <xref:System.Xml.Xsl.XslTransform.Transform%2A> 方法的输出为 <xref:System.IO.Stream> 时，将忽略下列属性：</span><span class="sxs-lookup"><span data-stu-id="4831d-128">The following attribute is ignored when the <xref:System.Xml.Xsl.XslTransform.Transform%2A> method output is a <xref:System.IO.Stream>:</span></span>  
  
-   <span data-ttu-id="4831d-129">version：版本始终为 1.0</span><span class="sxs-lookup"><span data-stu-id="4831d-129">version: the version is always 1.0</span></span>  
  
-   <span data-ttu-id="4831d-130">media-type：媒体类型</span><span class="sxs-lookup"><span data-stu-id="4831d-130">media-type: the media-type</span></span>  
  
## <a name="escaping-special-characters"></a><span data-ttu-id="4831d-131">转义特殊字符</span><span class="sxs-lookup"><span data-stu-id="4831d-131">Escaping Special Characters</span></span>  
 <span data-ttu-id="4831d-132">`<xsl:text disable-output-escaping>` 标记用于指示特殊字符是需要转义为 XML 形式（例如使用 `<&lt>` 替代 `"<"` 符号）还是保持现在的状态。</span><span class="sxs-lookup"><span data-stu-id="4831d-132">The `<xsl:text disable-output-escaping>` tag is used to indicate whether or not special characters need to be escaped into an XML form (for example, using `<&lt>` in place of the `"<"` symbol) or left in the present condition.</span></span> <span data-ttu-id="4831d-133">如果转换为 `disable-output-escaping` 或 <xref:System.Xml.XmlReader> 对象，将忽略 <xref:System.Xml.XmlWriter> 属性，对特殊字符没有影响。</span><span class="sxs-lookup"><span data-stu-id="4831d-133">The `disable-output-escaping` attribute is ignored when transforming to an <xref:System.Xml.XmlReader> or <xref:System.Xml.XmlWriter> object and has no effect on special characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4831d-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="4831d-134">See Also</span></span>  
 [<span data-ttu-id="4831d-135">XslTransform 类实现 XSLT 处理器</span><span class="sxs-lookup"><span data-stu-id="4831d-135">XslTransform Class Implements the XSLT Processor</span></span>](../../../../docs/standard/data/xml/xsltransform-class-implements-the-xslt-processor.md)

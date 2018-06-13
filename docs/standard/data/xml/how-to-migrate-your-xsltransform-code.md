---
title: 如何：迁移 XslTransform 代码
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 910beb2f-cfb3-4e8e-9936-f7e0c5f4064a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2fcfe8b0fbbc829c1bee08b761271f4d12b6ae05
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33570987"
---
# <a name="how-to-migrate-your-xsltransform-code"></a><span data-ttu-id="6ea27-102">如何：迁移 XslTransform 代码</span><span class="sxs-lookup"><span data-stu-id="6ea27-102">How to: Migrate Your XslTransform Code</span></span>
<span data-ttu-id="6ea27-103">业已设计的新 XSLT 类与现有类非常相似。</span><span class="sxs-lookup"><span data-stu-id="6ea27-103">The new XSLT classes have been designed to be very similar to the existing classes.</span></span> <span data-ttu-id="6ea27-104"><xref:System.Xml.Xsl.XslCompiledTransform> 类替换 <xref:System.Xml.Xsl.XslTransform> 类。</span><span class="sxs-lookup"><span data-stu-id="6ea27-104">The <xref:System.Xml.Xsl.XslCompiledTransform> class replaces the <xref:System.Xml.Xsl.XslTransform> class.</span></span> <span data-ttu-id="6ea27-105">样式表使用 <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> 方法进行编译。</span><span class="sxs-lookup"><span data-stu-id="6ea27-105">Style sheets are compiled using the <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> method.</span></span> <span data-ttu-id="6ea27-106">使用 <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> 方法执行转换。</span><span class="sxs-lookup"><span data-stu-id="6ea27-106">Transforms are executed using the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span> <span data-ttu-id="6ea27-107">下面的过程演示常见 XSLT 任务，并比较使用 <xref:System.Xml.Xsl.XslTransform> 类和使用 <xref:System.Xml.Xsl.XslCompiledTransform> 类的代码。</span><span class="sxs-lookup"><span data-stu-id="6ea27-107">The following procedures show common XSLT tasks, and compare the code using the <xref:System.Xml.Xsl.XslTransform> class versus the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
### <a name="to-transform-a-file-and-output-to-a-uri"></a><span data-ttu-id="6ea27-108">转换文件和输出到 URI</span><span class="sxs-lookup"><span data-stu-id="6ea27-108">To transform a file and output to a URI</span></span>  
  
-   <span data-ttu-id="6ea27-109">使用 <xref:System.Xml.Xsl.XslTransform> 类编码。</span><span class="sxs-lookup"><span data-stu-id="6ea27-109">Code using the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#9](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#9)]
     [!code-vb[XML_Migration#9](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#9)]  
  
-   <span data-ttu-id="6ea27-110">使用 <xref:System.Xml.Xsl.XslCompiledTransform> 类编码。</span><span class="sxs-lookup"><span data-stu-id="6ea27-110">Code using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#10](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#10)]
     [!code-vb[XML_Migration#10](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#10)]  
  
### <a name="to-compile-a-style-sheet-and-use-a-resolver-with-default-credentials"></a><span data-ttu-id="6ea27-111">编译样式表和使用具有默认凭据的解析器</span><span class="sxs-lookup"><span data-stu-id="6ea27-111">To compile a style sheet and use a resolver with default credentials</span></span>  
  
-   <span data-ttu-id="6ea27-112">使用 <xref:System.Xml.Xsl.XslTransform> 类编码。</span><span class="sxs-lookup"><span data-stu-id="6ea27-112">Code using the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#11](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#11)]
     [!code-vb[XML_Migration#11](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#11)]  
  
-   <span data-ttu-id="6ea27-113">使用 <xref:System.Xml.Xsl.XslCompiledTransform> 类编码。</span><span class="sxs-lookup"><span data-stu-id="6ea27-113">Code using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#12](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#12)]
     [!code-vb[XML_Migration#12](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#12)]  
  
### <a name="to-use-an-xslt-parameter"></a><span data-ttu-id="6ea27-114">使用 XSLT 参数</span><span class="sxs-lookup"><span data-stu-id="6ea27-114">To use an XSLT parameter</span></span>  
  
-   <span data-ttu-id="6ea27-115">使用 <xref:System.Xml.Xsl.XslTransform> 类编码。</span><span class="sxs-lookup"><span data-stu-id="6ea27-115">Code using the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#13](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#13)]
     [!code-vb[XML_Migration#13](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#13)]  
  
-   <span data-ttu-id="6ea27-116">使用 <xref:System.Xml.Xsl.XslCompiledTransform> 类编码。</span><span class="sxs-lookup"><span data-stu-id="6ea27-116">Code using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#14](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#14)]
     [!code-vb[XML_Migration#14](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#14)]  
  
### <a name="to-enable-xslt-scripting"></a><span data-ttu-id="6ea27-117">启用 XSLT 脚本撰写</span><span class="sxs-lookup"><span data-stu-id="6ea27-117">To enable XSLT scripting</span></span>  
  
-   <span data-ttu-id="6ea27-118">使用 <xref:System.Xml.Xsl.XslTransform> 类编码。</span><span class="sxs-lookup"><span data-stu-id="6ea27-118">Code using the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#15](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#15)]
     [!code-vb[XML_Migration#15](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#15)]  
  
-   <span data-ttu-id="6ea27-119">使用 <xref:System.Xml.Xsl.XslCompiledTransform> 类编码。</span><span class="sxs-lookup"><span data-stu-id="6ea27-119">Code using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#16](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#16)]
     [!code-vb[XML_Migration#16](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#16)]  
  
### <a name="to-load-the-results-into-a-dom-object"></a><span data-ttu-id="6ea27-120">将结果加载到 DOM 对象</span><span class="sxs-lookup"><span data-stu-id="6ea27-120">To load the results into a DOM object</span></span>  
  
-   <span data-ttu-id="6ea27-121">使用 <xref:System.Xml.Xsl.XslTransform> 类编码。</span><span class="sxs-lookup"><span data-stu-id="6ea27-121">Code using the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#19](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#19)]
     [!code-vb[XML_Migration#19](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#19)]  
  
-   <span data-ttu-id="6ea27-122">使用 <xref:System.Xml.Xsl.XslCompiledTransform> 类编码。</span><span class="sxs-lookup"><span data-stu-id="6ea27-122">Code using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6ea27-123"><xref:System.Xml.Xsl.XslCompiledTransform> 类没有以 <xref:System.Xml.XmlReader> 对象形式返回 XSLT 转换结果的方法。</span><span class="sxs-lookup"><span data-stu-id="6ea27-123">The <xref:System.Xml.Xsl.XslCompiledTransform> class does not have a method that returns the XSLT transformation results as an <xref:System.Xml.XmlReader> object.</span></span> <span data-ttu-id="6ea27-124">不过，您可以将结果输出到 XML 文件并将该 XML 文件加载到其他对象。</span><span class="sxs-lookup"><span data-stu-id="6ea27-124">However, you can output to an XML file and load the XML file into another object.</span></span>  
  
     [!code-csharp[XML_Migration#20](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#20)]
     [!code-vb[XML_Migration#20](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#20)]  
  
### <a name="to-stream-the-results-into-another-data-store"></a><span data-ttu-id="6ea27-125">将结果流处理到其他数据存储区</span><span class="sxs-lookup"><span data-stu-id="6ea27-125">To stream the results into another data store</span></span>  
  
-   <span data-ttu-id="6ea27-126">使用 <xref:System.Xml.Xsl.XslTransform> 类编码。</span><span class="sxs-lookup"><span data-stu-id="6ea27-126">Code using the <xref:System.Xml.Xsl.XslTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#17](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#17)]
     [!code-vb[XML_Migration#17](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#17)]  
  
-   <span data-ttu-id="6ea27-127">使用 <xref:System.Xml.Xsl.XslCompiledTransform> 类编码。</span><span class="sxs-lookup"><span data-stu-id="6ea27-127">Code using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
     [!code-csharp[XML_Migration#18](../../../../samples/snippets/csharp/VS_Snippets_Data/XML_Migration/CS/migration.cs#18)]
     [!code-vb[XML_Migration#18](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XML_Migration/VB/migration.vb#18)]  
  
## <a name="see-also"></a><span data-ttu-id="6ea27-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="6ea27-128">See Also</span></span>  
 [<span data-ttu-id="6ea27-129">从 XslTransform 类迁移</span><span class="sxs-lookup"><span data-stu-id="6ea27-129">Migrating From the XslTransform Class</span></span>](../../../../docs/standard/data/xml/migrating-from-the-xsltransform-class.md)  
 [<span data-ttu-id="6ea27-130">使用 XslCompiledTransform 类</span><span class="sxs-lookup"><span data-stu-id="6ea27-130">Using the XslCompiledTransform Class</span></span>](../../../../docs/standard/data/xml/using-the-xslcompiledtransform-class.md)

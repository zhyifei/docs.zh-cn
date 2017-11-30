---
title: "XSLT 扩展对象"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a4ebdbad-087c-4cfe-acc0-17c48142f81a
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2916f7da6b990cddef9b86559a71b5206351d558
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="xslt-extension-objects"></a><span data-ttu-id="db166-102">XSLT 扩展对象</span><span class="sxs-lookup"><span data-stu-id="db166-102">XSLT Extension Objects</span></span>
<span data-ttu-id="db166-103">扩展对象用于扩展样式表的功能。</span><span class="sxs-lookup"><span data-stu-id="db166-103">Extension objects are used to extend the functionality of style sheets.</span></span> <span data-ttu-id="db166-104">扩展对象通过 <xref:System.Xml.Xsl.XsltArgumentList> 类来维护。</span><span class="sxs-lookup"><span data-stu-id="db166-104">Extension objects are maintained by the <xref:System.Xml.Xsl.XsltArgumentList> class.</span></span>  
  
 <span data-ttu-id="db166-105">与使用嵌入脚本相比，使用扩展对象具有以下优点：</span><span class="sxs-lookup"><span data-stu-id="db166-105">The following are advantages to using an extension object rather than embedded script:</span></span>  
  
-   <span data-ttu-id="db166-106">改善了类的包装和重用。</span><span class="sxs-lookup"><span data-stu-id="db166-106">Provides better encapsulation and reuse of classes.</span></span>  
  
-   <span data-ttu-id="db166-107">使样式表可以更小而且更容易维护。</span><span class="sxs-lookup"><span data-stu-id="db166-107">Allows style sheets to be smaller and more maintainable.</span></span>  
  
 <span data-ttu-id="db166-108">使用 <xref:System.Xml.Xsl.XsltArgumentList> 方法将 XSLT 扩展对象添加到 <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> 对象。</span><span class="sxs-lookup"><span data-stu-id="db166-108">XSLT extension objects are added to the <xref:System.Xml.Xsl.XsltArgumentList> object using the <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> method.</span></span> <span data-ttu-id="db166-109">此时，限定名和命名空间 URI 与扩展对象关联。</span><span class="sxs-lookup"><span data-stu-id="db166-109">A qualified name and namespace URI are associated with the extension object at that time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="db166-110">调用 <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> 方法要求具有 FullTrust 权限集。</span><span class="sxs-lookup"><span data-stu-id="db166-110">The FullTrust permission set is required to call the <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> method.</span></span> <span data-ttu-id="db166-111">有关详细信息，请参阅[代码访问安全性](http://msdn.microsoft.com/en-us/23a20143-241d-4fe5-9d9f-3933fd594c03)和[NIB： 命名权限集](http://msdn.microsoft.com/en-us/08250d67-c99d-4ab0-8d2b-b0e12019f6e3)。</span><span class="sxs-lookup"><span data-stu-id="db166-111">For more information, see [Code Access Security](http://msdn.microsoft.com/en-us/23a20143-241d-4fe5-9d9f-3933fd594c03) and [NIB: Named Permission Sets](http://msdn.microsoft.com/en-us/08250d67-c99d-4ab0-8d2b-b0e12019f6e3).</span></span>  
  
 <span data-ttu-id="db166-112">从扩展对象返回的数据类型是四种 XPath 基本数据类型之一：`number`、`string`、`Boolean` 和 `node set`。</span><span class="sxs-lookup"><span data-stu-id="db166-112">The data types returned from extension objects are one of the four basic XPath data types of `number`, `string`, `Boolean`, and `node set`.</span></span>  
  
 <span data-ttu-id="db166-113">任何使用 `params` 关键字定义的方法允许传递未指定的参数数目，<xref:System.Xml.Xsl.XslCompiledTransform> 类目前不支持。</span><span class="sxs-lookup"><span data-stu-id="db166-113">Any method that is defined with the `params` keyword, which allows an unspecified number of parameters to be passed, is not currently supported by the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="db166-114">利用通过 `params` 关键字定义的方法的 XSLT 样式表也无法正确使用。</span><span class="sxs-lookup"><span data-stu-id="db166-114">XSLT style sheets that utilize any method defined with the `params` keyword will not work correctly.</span></span> <span data-ttu-id="db166-115">有关详细信息，请参阅[params](~/docs/csharp/language-reference/keywords/params.md)。</span><span class="sxs-lookup"><span data-stu-id="db166-115">For details, see [params](~/docs/csharp/language-reference/keywords/params.md).</span></span>  
  
### <a name="to-use-an-xslt-extension-object"></a><span data-ttu-id="db166-116">使用 XSLT 扩展对象</span><span class="sxs-lookup"><span data-stu-id="db166-116">To use an XSLT extension object</span></span>  
  
1.  <span data-ttu-id="db166-117">创建 <xref:System.Xml.Xsl.XsltArgumentList> 对象并使用 <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> 方法添加扩展对象。</span><span class="sxs-lookup"><span data-stu-id="db166-117">Create an <xref:System.Xml.Xsl.XsltArgumentList> object and add the extension object using <xref:System.Xml.Xsl.XsltArgumentList.AddExtensionObject%2A> method.</span></span>  
  
2.  <span data-ttu-id="db166-118">从样式表调用扩展对象。</span><span class="sxs-lookup"><span data-stu-id="db166-118">Call the extension object from the style sheet.</span></span>  
  
3.  <span data-ttu-id="db166-119">将 <xref:System.Xml.Xsl.XsltArgumentList> 对象传递给 <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="db166-119">Pass the <xref:System.Xml.Xsl.XsltArgumentList> object to the <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db166-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db166-120">See Also</span></span>  
 [<span data-ttu-id="db166-121">XSLT 转换</span><span class="sxs-lookup"><span data-stu-id="db166-121">XSLT Transformations</span></span>](../../../../docs/standard/data/xml/xslt-transformations.md)  
 [<span data-ttu-id="db166-122">XSLT 安全注意事项</span><span class="sxs-lookup"><span data-stu-id="db166-122">XSLT Security Considerations</span></span>](../../../../docs/standard/data/xml/xslt-security-considerations.md)

---
title: "使用 LINQ to XML 处理 XML 数据"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 059d6b9d-63f7-4011-9ba8-8406f0bbae7d
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 26258489742db3de108ddf68f68074682c30fe57
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="process-xml-data-using-linq-to-xml"></a><span data-ttu-id="7773d-102">使用 LINQ to XML 处理 XML 数据</span><span class="sxs-lookup"><span data-stu-id="7773d-102">Process XML Data Using LINQ to XML</span></span>
<span data-ttu-id="7773d-103">LINQ to XML 是 .NET Framework 3.5 版中用于处理 XML 数据的新模型。</span><span class="sxs-lookup"><span data-stu-id="7773d-103">LINQ to XML is the new model in the .NET Framework version 3.5 for processing XML data.</span></span> <span data-ttu-id="7773d-104">LINQ to XML 允许开发人员对 XML 数据执行任何需要的操作：查询、修改、创建、保存，和序列化 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="7773d-104">LINQ to XML allows developers to do everything they would expect with XML data: querying, modifying, creating, saving, and serializing XML documents.</span></span> <span data-ttu-id="7773d-105">真正的优势在于查询和创建功能。</span><span class="sxs-lookup"><span data-stu-id="7773d-105">The real advantages lie in the query and creation capabilities.</span></span>  
  
 <span data-ttu-id="7773d-106">LINQ to XML 中的查询简洁而易于表示，与 XPath 或 XQuery 相比，使用的语法更类似于 SQL。</span><span class="sxs-lookup"><span data-stu-id="7773d-106">Queries in LINQ to XML are succinct and expressive, using syntax more similar to SQL than to XPath or XQuery.</span></span> <span data-ttu-id="7773d-107">由于查询结果可作为为元素或属性的集合而返回，并且可用作 XElement 对象的参数，因此可以容易地将 XML 树从一种形状转换为另一种形状。</span><span class="sxs-lookup"><span data-stu-id="7773d-107">Because query results can be returned as collections of elements or attributes and can be used as parameters for XElement objects, XML trees can be easily transformed from one shape to another.</span></span>  
  
 <span data-ttu-id="7773d-108">LINQ to XML 利用 .NET Framework 3.5 版中的语言集成查询 (LINQ) 技术。</span><span class="sxs-lookup"><span data-stu-id="7773d-108">LINQ to XML leverages the language-integrated query (LINQ) technology in the .NET Framework version 3.5.</span></span> <span data-ttu-id="7773d-109">LINQ 扩展了 C# 和 Visual Basic 的语言语法，提供可以扩展到几乎任何数据存储区的强大的查询功能。</span><span class="sxs-lookup"><span data-stu-id="7773d-109">LINQ extends the language syntax of C# and Visual Basic to provide powerful query capabilities that can be extended to potentially any data store.</span></span>  
  
 <span data-ttu-id="7773d-110">有关用法的详细介绍，请参阅 [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13)；有关 LINQ 框架概述，请参阅 [LINQ（语言集成查询）](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)。</span><span class="sxs-lookup"><span data-stu-id="7773d-110">See [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13) for a detailed discussion of its use, and see [LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d) for an overview of the LINQ framework.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7773d-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="7773d-111">See Also</span></span>  
 <xref:System.Xml.Linq>  
 <xref:System.Linq>  
 [<span data-ttu-id="7773d-112">LINQ to XML 与DOM</span><span class="sxs-lookup"><span data-stu-id="7773d-112">LINQ to XML vs. DOM</span></span>](http://msdn.microsoft.com/library/19b5ed02-feb2-455a-8897-f7f0fd76aca3)  
 [<span data-ttu-id="7773d-113">LINQ to XML 与其他 XML 技术</span><span class="sxs-lookup"><span data-stu-id="7773d-113">LINQ to XML vs. Other XML Technologies</span></span>](http://msdn.microsoft.com/library/7ba1eecf-f09a-42de-bc80-22ca5b2e42d3)

---
title: 类型的表达式&lt;类型&gt;不可查询
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36593
- vbc36593
helpviewer_keywords:
- BC36593
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
caps.latest.revision: 5
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3f2b98bf48f0b3965929f9211c2944ff97754f23
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="expression-of-type-lttypegt-is-not-queryable"></a><span data-ttu-id="7a79a-102">类型的表达式&lt;类型&gt;不可查询</span><span class="sxs-lookup"><span data-stu-id="7a79a-102">Expression of type &lt;type&gt; is not queryable</span></span>
<span data-ttu-id="7a79a-103">类型的表达式\<类型 > 不可查询。</span><span class="sxs-lookup"><span data-stu-id="7a79a-103">Expression of type \<type> is not queryable.</span></span> <span data-ttu-id="7a79a-104">请确保不缺少 LINQ 提供程序的程序集引用和/或命名空间导入。</span><span class="sxs-lookup"><span data-stu-id="7a79a-104">Make sure you are not missing an assembly reference and/or namespace import for the LINQ provider.</span></span>  
  
 <span data-ttu-id="7a79a-105">可查询类型中定义<xref:System.Linq>， <xref:System.Data.Linq>，和<xref:System.Xml.Linq>命名空间。</span><span class="sxs-lookup"><span data-stu-id="7a79a-105">Queryable types are defined in the <xref:System.Linq>, <xref:System.Data.Linq>, and <xref:System.Xml.Linq> namespaces.</span></span> <span data-ttu-id="7a79a-106">你必须导入一个或多个这些命名空间执行 LINQ 查询。</span><span class="sxs-lookup"><span data-stu-id="7a79a-106">You must import one or more of these namespaces to perform LINQ queries.</span></span>  
  
 <span data-ttu-id="7a79a-107"><xref:System.Linq>命名空间让你可对查询对象，如集合和数组通过使用 LINQ。</span><span class="sxs-lookup"><span data-stu-id="7a79a-107">The <xref:System.Linq> namespace enables you to query objects such as collections and arrays by using LINQ.</span></span>  
  
 <span data-ttu-id="7a79a-108"><xref:System.Data.Linq>命名空间使你能够通过使用 LINQ 查询 ADO.NET 数据集和 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="7a79a-108">The <xref:System.Data.Linq> namespace enables you to query ADO.NET Datasets and SQL Server databases by using LINQ.</span></span>  
  
 <span data-ttu-id="7a79a-109"><xref:System.Xml.Linq>命名空间使您能够查询 XML 使用 LINQ 和 Visual Basic 中使用 XML 功能。</span><span class="sxs-lookup"><span data-stu-id="7a79a-109">The <xref:System.Xml.Linq> namespace enables you to query XML by using LINQ and to use XML features in Visual Basic.</span></span>  
  
 <span data-ttu-id="7a79a-110">**错误 ID:** BC36593</span><span class="sxs-lookup"><span data-stu-id="7a79a-110">**Error ID:** BC36593</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7a79a-111">更正此错误</span><span class="sxs-lookup"><span data-stu-id="7a79a-111">To correct this error</span></span>  
  
1.  <span data-ttu-id="7a79a-112">添加`Import`语句<xref:System.Linq>， <xref:System.Data.Linq>，或<xref:System.Xml.Linq>到你的代码文件的命名空间。</span><span class="sxs-lookup"><span data-stu-id="7a79a-112">Add an `Import` statement for the <xref:System.Linq>, <xref:System.Data.Linq>, or <xref:System.Xml.Linq> namespace to your code file.</span></span> <span data-ttu-id="7a79a-113">你可以还使用导入命名空间为你的项目**引用**项目设计器的页面 (**我的项目**)。</span><span class="sxs-lookup"><span data-stu-id="7a79a-113">You can also import namespaces for your project by using the **References** page of the Project Designer (**My Project**).</span></span>  
  
2.  <span data-ttu-id="7a79a-114">请确保你已标识为你的查询的源是可查询的类型的类型。</span><span class="sxs-lookup"><span data-stu-id="7a79a-114">Ensure that the type that you have identified as the source of your query is a queryable type.</span></span> <span data-ttu-id="7a79a-115">即，实现一种<xref:System.Collections.Generic.IEnumerable%601>或<xref:System.Linq.IQueryable%601>。</span><span class="sxs-lookup"><span data-stu-id="7a79a-115">That is, a type that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a79a-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7a79a-116">See Also</span></span>  
 <xref:System.Linq>  
 <xref:System.Data.Linq>  
 <xref:System.Xml.Linq>  
 [<span data-ttu-id="7a79a-117">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="7a79a-117">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="7a79a-118">LINQ</span><span class="sxs-lookup"><span data-stu-id="7a79a-118">LINQ</span></span>](../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="7a79a-119">XML</span><span class="sxs-lookup"><span data-stu-id="7a79a-119">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [<span data-ttu-id="7a79a-120">引用和 Imports 语句</span><span class="sxs-lookup"><span data-stu-id="7a79a-120">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 [<span data-ttu-id="7a79a-121">Imports 语句（.NET 命名空间和类型）</span><span class="sxs-lookup"><span data-stu-id="7a79a-121">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [<span data-ttu-id="7a79a-122">项目设计器 ->“引用”页 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7a79a-122">References Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/references-page-project-designer-visual-basic)

---
title: "类型的表达式&lt;类型&gt;不可查询 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36593
- vbc36593
dev_langs:
- VB
helpviewer_keywords:
- BC36593
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
caps.latest.revision: 5
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 84563c7339ffe7415017280d74a13d6501236da5
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="expression-of-type-lttypegt-is-not-queryable"></a><span data-ttu-id="b13f8-102">类型的表达式&lt;类型&gt;不可查询</span><span class="sxs-lookup"><span data-stu-id="b13f8-102">Expression of type &lt;type&gt; is not queryable</span></span>
<span data-ttu-id="b13f8-103">类型的表达式\<类型&1;> 不可查询。</span><span class="sxs-lookup"><span data-stu-id="b13f8-103">Expression of type \<type> is not queryable.</span></span> <span data-ttu-id="b13f8-104">请确保没有缺少 LINQ 提供程序程序集引用和/或命名空间导入。</span><span class="sxs-lookup"><span data-stu-id="b13f8-104">Make sure you are not missing an assembly reference and/or namespace import for the LINQ provider.</span></span>  
  
 <span data-ttu-id="b13f8-105">在中定义的可查询类型<xref:System.Linq>， <xref:System.Data.Linq>，和<xref:System.Xml.Linq>命名空间。</xref:System.Xml.Linq> </xref:System.Data.Linq> </xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="b13f8-105">Queryable types are defined in the <xref:System.Linq>, <xref:System.Data.Linq>, and <xref:System.Xml.Linq> namespaces.</span></span> <span data-ttu-id="b13f8-106">您必须导入一个或多个这些命名空间，以执行 LINQ 查询。</span><span class="sxs-lookup"><span data-stu-id="b13f8-106">You must import one or more of these namespaces to perform LINQ queries.</span></span>  
  
 <span data-ttu-id="b13f8-107"><xref:System.Linq>命名空间能让您对查询对象，如集合和数组使用 LINQ。</xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="b13f8-107">The <xref:System.Linq> namespace enables you to query objects such as collections and arrays by using LINQ.</span></span>  
  
 <span data-ttu-id="b13f8-108"><xref:System.Data.Linq>命名空间能让您可以使用 LINQ 查询 ADO.NET 数据集和 SQL Server 数据库。</xref:System.Data.Linq></span><span class="sxs-lookup"><span data-stu-id="b13f8-108">The <xref:System.Data.Linq> namespace enables you to query ADO.NET Datasets and SQL Server databases by using LINQ.</span></span>  
  
 <span data-ttu-id="b13f8-109"><xref:System.Xml.Linq>命名空间可用于查询 XML 使用 LINQ 和 Visual Basic 中使用 XML 功能。</xref:System.Xml.Linq></span><span class="sxs-lookup"><span data-stu-id="b13f8-109">The <xref:System.Xml.Linq> namespace enables you to query XML by using LINQ and to use XML features in Visual Basic.</span></span>  
  
 <span data-ttu-id="b13f8-110">**错误 ID:** BC36593</span><span class="sxs-lookup"><span data-stu-id="b13f8-110">**Error ID:** BC36593</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b13f8-111">更正此错误</span><span class="sxs-lookup"><span data-stu-id="b13f8-111">To correct this error</span></span>  
  
1.  <span data-ttu-id="b13f8-112">添加`Import`语句<xref:System.Linq>， <xref:System.Data.Linq>，或<xref:System.Xml.Linq>到您的代码文件的命名空间。</xref:System.Xml.Linq> </xref:System.Data.Linq> </xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="b13f8-112">Add an `Import` statement for the <xref:System.Linq>, <xref:System.Data.Linq>, or <xref:System.Xml.Linq> namespace to your code file.</span></span> <span data-ttu-id="b13f8-113">您还可以导入的命名空间您的项目使用**引用**项目设计器的页面 (**我的项目**)。</span><span class="sxs-lookup"><span data-stu-id="b13f8-113">You can also import namespaces for your project by using the **References** page of the Project Designer (**My Project**).</span></span>  
  
2.  <span data-ttu-id="b13f8-114">请确保已标识为您的查询的源是可查询类型的类型。</span><span class="sxs-lookup"><span data-stu-id="b13f8-114">Ensure that the type that you have identified as the source of your query is a queryable type.</span></span> <span data-ttu-id="b13f8-115">也就是说，实现<xref:System.Collections.Generic.IEnumerable%601>或<xref:System.Linq.IQueryable%601>.</xref:System.Linq.IQueryable%601></xref:System.Collections.Generic.IEnumerable%601>的类型</span><span class="sxs-lookup"><span data-stu-id="b13f8-115">That is, a type that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b13f8-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b13f8-116">See Also</span></span>  
 <span data-ttu-id="b13f8-117"><xref:System.Linq></xref:System.Linq></span><span class="sxs-lookup"><span data-stu-id="b13f8-117"><xref:System.Linq></span></span>   
 <span data-ttu-id="b13f8-118"><xref:System.Data.Linq></xref:System.Data.Linq></span><span class="sxs-lookup"><span data-stu-id="b13f8-118"><xref:System.Data.Linq></span></span>   
 <span data-ttu-id="b13f8-119"><xref:System.Xml.Linq></span><span class="sxs-lookup"><span data-stu-id="b13f8-119"><xref:System.Xml.Linq></span></span>   
<span data-ttu-id="b13f8-120"> [在 Visual Basic 中的 LINQ 简介](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span><span class="sxs-lookup"><span data-stu-id="b13f8-120"> [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) </span></span>  
<span data-ttu-id="b13f8-121"> [LINQ](../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="b13f8-121"> [LINQ](../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="b13f8-122"> [XML](../../../visual-basic/programming-guide/language-features/xml/index.md) </span><span class="sxs-lookup"><span data-stu-id="b13f8-122"> [XML](../../../visual-basic/programming-guide/language-features/xml/index.md) </span></span>  
<span data-ttu-id="b13f8-123"> [引用和 Imports 语句](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md) </span><span class="sxs-lookup"><span data-stu-id="b13f8-123"> [References and the Imports Statement](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md) </span></span>  
<span data-ttu-id="b13f8-124"> [Imports 语句（.NET 命名空间和类型）](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) </span><span class="sxs-lookup"><span data-stu-id="b13f8-124"> [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) </span></span>  
<span data-ttu-id="b13f8-125"> [项目设计器 ->“引用”页 (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="b13f8-125"> [References Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)</span></span>

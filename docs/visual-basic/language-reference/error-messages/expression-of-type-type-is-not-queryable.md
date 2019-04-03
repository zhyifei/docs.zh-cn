---
title: 类型 <type> 的表达式不可查询
ms.date: 07/20/2015
f1_keywords:
- bc36593
- vbc36593
helpviewer_keywords:
- BC36593
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
ms.openlocfilehash: 7f74d56b47629ff76f9b935d26278ace8df4c353
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58842325"
---
# <a name="expression-of-type-type-is-not-queryable"></a><span data-ttu-id="30e00-102">类型的表达式\<类型 > 不可查询</span><span class="sxs-lookup"><span data-stu-id="30e00-102">Expression of type \<type> is not queryable</span></span>
<span data-ttu-id="30e00-103">类型的表达式\<类型 > 不可查询。</span><span class="sxs-lookup"><span data-stu-id="30e00-103">Expression of type \<type> is not queryable.</span></span> <span data-ttu-id="30e00-104">请确保不缺少程序集引用和/或命名空间导入 LINQ 提供程序。</span><span class="sxs-lookup"><span data-stu-id="30e00-104">Make sure you are not missing an assembly reference and/or namespace import for the LINQ provider.</span></span>  
  
 <span data-ttu-id="30e00-105">可查询类型中定义<xref:System.Linq>， <xref:System.Data.Linq>，和<xref:System.Xml.Linq>命名空间。</span><span class="sxs-lookup"><span data-stu-id="30e00-105">Queryable types are defined in the <xref:System.Linq>, <xref:System.Data.Linq>, and <xref:System.Xml.Linq> namespaces.</span></span> <span data-ttu-id="30e00-106">必须导入一个或多个这些命名空间执行 LINQ 查询。</span><span class="sxs-lookup"><span data-stu-id="30e00-106">You must import one or more of these namespaces to perform LINQ queries.</span></span>  
  
 <span data-ttu-id="30e00-107"><xref:System.Linq>命名空间能让您对查询对象，如集合和数组使用 LINQ。</span><span class="sxs-lookup"><span data-stu-id="30e00-107">The <xref:System.Linq> namespace enables you to query objects such as collections and arrays by using LINQ.</span></span>  
  
 <span data-ttu-id="30e00-108"><xref:System.Data.Linq>命名空间，可使用 LINQ 查询 ADO.NET 数据集和 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="30e00-108">The <xref:System.Data.Linq> namespace enables you to query ADO.NET Datasets and SQL Server databases by using LINQ.</span></span>  
  
 <span data-ttu-id="30e00-109"><xref:System.Xml.Linq>命名空间用于查询 XML 使用 LINQ 和 Visual Basic 中使用 XML 功能。</span><span class="sxs-lookup"><span data-stu-id="30e00-109">The <xref:System.Xml.Linq> namespace enables you to query XML by using LINQ and to use XML features in Visual Basic.</span></span>  
  
 <span data-ttu-id="30e00-110">**错误 ID:** BC36593</span><span class="sxs-lookup"><span data-stu-id="30e00-110">**Error ID:** BC36593</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="30e00-111">更正此错误</span><span class="sxs-lookup"><span data-stu-id="30e00-111">To correct this error</span></span>  
  
1.  <span data-ttu-id="30e00-112">添加`Import`语句<xref:System.Linq>， <xref:System.Data.Linq>，或<xref:System.Xml.Linq>到你的代码文件的命名空间。</span><span class="sxs-lookup"><span data-stu-id="30e00-112">Add an `Import` statement for the <xref:System.Linq>, <xref:System.Data.Linq>, or <xref:System.Xml.Linq> namespace to your code file.</span></span> <span data-ttu-id="30e00-113">您可以还使用导入命名空间为你的项目**引用**的项目设计器页 (**我的项目**)。</span><span class="sxs-lookup"><span data-stu-id="30e00-113">You can also import namespaces for your project by using the **References** page of the Project Designer (**My Project**).</span></span>  
  
2.  <span data-ttu-id="30e00-114">请确保已标识为您的查询的源是可查询类型的类型。</span><span class="sxs-lookup"><span data-stu-id="30e00-114">Ensure that the type that you have identified as the source of your query is a queryable type.</span></span> <span data-ttu-id="30e00-115">也就是说，实现的类型<xref:System.Collections.Generic.IEnumerable%601>或<xref:System.Linq.IQueryable%601>。</span><span class="sxs-lookup"><span data-stu-id="30e00-115">That is, a type that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30e00-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="30e00-116">See also</span></span>

- <xref:System.Linq>
- <xref:System.Data.Linq>
- <xref:System.Xml.Linq>
- [<span data-ttu-id="30e00-117">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="30e00-117">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [<span data-ttu-id="30e00-118">LINQ</span><span class="sxs-lookup"><span data-stu-id="30e00-118">LINQ</span></span>](../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="30e00-119">XML</span><span class="sxs-lookup"><span data-stu-id="30e00-119">XML</span></span>](../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="30e00-120">引用和 Imports 语句</span><span class="sxs-lookup"><span data-stu-id="30e00-120">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [<span data-ttu-id="30e00-121">Imports 语句（.NET 命名空间和类型）</span><span class="sxs-lookup"><span data-stu-id="30e00-121">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="30e00-122">项目设计器 ->“引用”页 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="30e00-122">References Page, Project Designer (Visual Basic)</span></span>](/visualstudio/ide/reference/references-page-project-designer-visual-basic)

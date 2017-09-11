---
title: "如何︰ 查询 (LINQ) (Visual Basic 中) 的字符串中的字符 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 499ebbe0-746c-4235-9dba-ce722c12b50e
caps.latest.revision: 4
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: dabd63e52707f3078c6cdc41db8c4f0e7dfbf70e
ms.contentlocale: zh-cn
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-query-for-characters-in-a-string-linq-visual-basic"></a><span data-ttu-id="b5cac-102">如何︰ 查询 (LINQ) (Visual Basic 中) 的字符串中的字符</span><span class="sxs-lookup"><span data-stu-id="b5cac-102">How to: Query for Characters in a String (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="b5cac-103">因为<xref:System.String>类实现泛型<xref:System.Collections.Generic.IEnumerable%601>接口，可以为字符序列的查询的任何字符串。</xref:System.Collections.Generic.IEnumerable%601> </xref:System.String></span><span class="sxs-lookup"><span data-stu-id="b5cac-103">Because the <xref:System.String> class implements the generic <xref:System.Collections.Generic.IEnumerable%601> interface, any string can be queried as a sequence of characters.</span></span> <span data-ttu-id="b5cac-104">但是，这不是 LINQ 的一个常见用途。</span><span class="sxs-lookup"><span data-stu-id="b5cac-104">However, this is not a common use of LINQ.</span></span> <span data-ttu-id="b5cac-105">对于复杂的模式匹配操作中，使用<xref:System.Text.RegularExpressions.Regex>类。</xref:System.Text.RegularExpressions.Regex></span><span class="sxs-lookup"><span data-stu-id="b5cac-105">For complex pattern matching operations, use the <xref:System.Text.RegularExpressions.Regex> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5cac-106">示例</span><span class="sxs-lookup"><span data-stu-id="b5cac-106">Example</span></span>  
 <span data-ttu-id="b5cac-107">下面的示例查询字符串以确定它包含的数字位数。</span><span class="sxs-lookup"><span data-stu-id="b5cac-107">The following example queries a string to determine the number of numeric digits it contains.</span></span> <span data-ttu-id="b5cac-108">请注意，该查询"重用"后它会在执行第一次。</span><span class="sxs-lookup"><span data-stu-id="b5cac-108">Note that the query is "reused" after it is executed the first time.</span></span> <span data-ttu-id="b5cac-109">这可能是因为查询本身不存储任何实际的结果。</span><span class="sxs-lookup"><span data-stu-id="b5cac-109">This is possible because the query itself does not store any actual results.</span></span>  
  
<span data-ttu-id="b5cac-110"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="b5cac-110"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span></span>  
## <a name="compiling-the-code"></a><span data-ttu-id="b5cac-111">编译代码</span><span class="sxs-lookup"><span data-stu-id="b5cac-111">Compiling the Code</span></span>  
 <span data-ttu-id="b5cac-112">创建一个面向.NET Framework 版本 3.5 或更高版本对 System.Core.dll 的引用与项目和一个`Imports`System.Linq 命名空间的语句。</span><span class="sxs-lookup"><span data-stu-id="b5cac-112">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5cac-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b5cac-113">See Also</span></span>  
 <span data-ttu-id="b5cac-114">[LINQ 和字符串 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md) </span><span class="sxs-lookup"><span data-stu-id="b5cac-114">[LINQ and Strings (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md) </span></span>  
<span data-ttu-id="b5cac-115"> [如何︰ 将 LINQ 查询与正则表达式 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-linq-queries-with-regular-expressions.md)</span><span class="sxs-lookup"><span data-stu-id="b5cac-115"> [How to: Combine LINQ Queries with Regular Expressions (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-linq-queries-with-regular-expressions.md)</span></span>

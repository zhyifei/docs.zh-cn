---
title: "LINQ 和字符串 (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: 75ddb201-d97a-4f98-8cdf-4ad51714529a
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 94e9627efb183c08bbb67a7e6e82df9132ebdef2
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="linq-and-strings-visual-basic"></a><span data-ttu-id="2516c-102">LINQ 和字符串 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2516c-102">LINQ and Strings (Visual Basic)</span></span>
<span data-ttu-id="2516c-103">可以使用 LINQ 来查询和转换字符串和字符串集合。</span><span class="sxs-lookup"><span data-stu-id="2516c-103">LINQ can be used to query and transform strings and collections of strings.</span></span> <span data-ttu-id="2516c-104">它可以处理文本文件中的半结构化数据尤其有用。</span><span class="sxs-lookup"><span data-stu-id="2516c-104">It can be especially useful with semi-structured data in text files.</span></span> <span data-ttu-id="2516c-105">LINQ 查询可以与传统的字符串函数和正则表达式组合。</span><span class="sxs-lookup"><span data-stu-id="2516c-105">LINQ queries can be combined with traditional string functions and regular expressions.</span></span> <span data-ttu-id="2516c-106">例如，您可以使用<xref:System.String.Split%2A>或<xref:System.Text.RegularExpressions.Regex.Split%2A>方法来创建一个字符串，然后可以查询或通过使用 LINQ 修改数组。</xref:System.Text.RegularExpressions.Regex.Split%2A> </xref:System.String.Split%2A></span><span class="sxs-lookup"><span data-stu-id="2516c-106">For example, you can use the <xref:System.String.Split%2A> or <xref:System.Text.RegularExpressions.Regex.Split%2A> method to create an array of strings that you can then query or modify by using LINQ.</span></span> <span data-ttu-id="2516c-107">您可以使用<xref:System.Text.RegularExpressions.Regex.IsMatch%2A>中的方法`where`LINQ 查询的子句。</xref:System.Text.RegularExpressions.Regex.IsMatch%2A></span><span class="sxs-lookup"><span data-stu-id="2516c-107">You can use the <xref:System.Text.RegularExpressions.Regex.IsMatch%2A> method in the `where` clause of a LINQ query.</span></span> <span data-ttu-id="2516c-108">您可以使用 LINQ 查询或修改<xref:System.Text.RegularExpressions.MatchCollection>返回正则表达式的结果。</xref:System.Text.RegularExpressions.MatchCollection></span><span class="sxs-lookup"><span data-stu-id="2516c-108">And you can use LINQ to query or modify the <xref:System.Text.RegularExpressions.MatchCollection> results returned by a regular expression.</span></span>  
  
 <span data-ttu-id="2516c-109">本部分中介绍的技术还可用于半结构化的文本数据转换为 XML。</span><span class="sxs-lookup"><span data-stu-id="2516c-109">You can also use the techniques described in this section to transform semi-structured text data to XML.</span></span> <span data-ttu-id="2516c-110">有关详细信息，请参阅[如何︰ 从 CSV 文件生成 XML](how-to-generate-xml-from-csv-files.md)。</span><span class="sxs-lookup"><span data-stu-id="2516c-110">For more information, see [How to: Generate XML from CSV Files](how-to-generate-xml-from-csv-files.md).</span></span>  
  
 <span data-ttu-id="2516c-111">本部分中的示例分为两类︰</span><span class="sxs-lookup"><span data-stu-id="2516c-111">The examples in this section fall into two categories:</span></span>  
  
## <a name="querying-a-block-of-text"></a><span data-ttu-id="2516c-112">查询文本的块</span><span class="sxs-lookup"><span data-stu-id="2516c-112">Querying a Block of Text</span></span>  
 <span data-ttu-id="2516c-113">您可以查询、 分析和修改通过使用拆分成较小的字符串的可查询数组的文本块<xref:System.String.Split%2A>方法或<xref:System.Text.RegularExpressions.Regex.Split%2A>方法。</xref:System.Text.RegularExpressions.Regex.Split%2A> </xref:System.String.Split%2A></span><span class="sxs-lookup"><span data-stu-id="2516c-113">You can query, analyze, and modify text blocks by splitting them into a queryable array of smaller strings by using the <xref:System.String.Split%2A> method or the <xref:System.Text.RegularExpressions.Regex.Split%2A> method.</span></span> <span data-ttu-id="2516c-114">可以将源文本拆分为字、 句子、 段落、 页或任何其他条件，并根据他们需要在查询中，然后执行其他拆分。</span><span class="sxs-lookup"><span data-stu-id="2516c-114">You can split the source text into words, sentences, paragraphs, pages, or any other criteria, and then perform additional splits if they are required in your query.</span></span>  
  
 [<span data-ttu-id="2516c-115">如何︰ 在字符串 (LINQ) (Visual Basic 中) 中单词出现次数进行计数</span><span class="sxs-lookup"><span data-stu-id="2516c-115">How to: Count Occurrences of a Word in a String (LINQ) (Visual Basic)</span></span>](how-to-count-occurrences-of-a-word-in-a-string-linq.md)  
 <span data-ttu-id="2516c-116">演示如何使用 LINQ 进行简单查询文本。</span><span class="sxs-lookup"><span data-stu-id="2516c-116">Shows how to use LINQ for simple querying over text.</span></span>  
  
 [<span data-ttu-id="2516c-117">如何︰ 查询包含一组指定的字数 (LINQ) (Visual Basic 中) 的句子</span><span class="sxs-lookup"><span data-stu-id="2516c-117">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic)</span></span>](how-to-query-for-sentences-that-contain-a-specified-set-of-words.md)

 <span data-ttu-id="2516c-118">演示如何将拆分任意边界上的文本文件以及如何针对每个部分执行查询。</span><span class="sxs-lookup"><span data-stu-id="2516c-118">Shows how to split text files on arbitrary boundaries and how to perform queries against each part.</span></span>  
  
 [<span data-ttu-id="2516c-119">如何︰ 查询 (LINQ) (Visual Basic 中) 的字符串中的字符</span><span class="sxs-lookup"><span data-stu-id="2516c-119">How to: Query for Characters in a String (LINQ) (Visual Basic)</span></span>](how-to-query-for-characters-in-a-string-linq.md)  
 <span data-ttu-id="2516c-120">演示字符串是可查询类型。</span><span class="sxs-lookup"><span data-stu-id="2516c-120">Demonstrates that a string is a queryable type.</span></span>  
  
 [<span data-ttu-id="2516c-121">如何︰ 将 LINQ 查询与正则表达式 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2516c-121">How to: Combine LINQ Queries with Regular Expressions (Visual Basic)</span></span>](how-to-combine-linq-queries-with-regular-expressions.md)  
 <span data-ttu-id="2516c-122">演示如何在 LINQ 查询中使用正则表达式，复杂的模式匹配的筛选的查询结果。</span><span class="sxs-lookup"><span data-stu-id="2516c-122">Shows how to use regular expressions in LINQ queries for complex pattern matching on filtered query results.</span></span>  
  
## <a name="querying-semi-structured-data-in-text-format"></a><span data-ttu-id="2516c-123">查询以文本格式的半结构化的数据</span><span class="sxs-lookup"><span data-stu-id="2516c-123">Querying Semi-Structured Data in Text Format</span></span>  
 <span data-ttu-id="2516c-124">许多不同类型的文本文件包含一系列的行，通常具有类似的格式，如制表符分隔或逗号分隔的文件或固定长度的行。</span><span class="sxs-lookup"><span data-stu-id="2516c-124">Many different types of text files consist of a series of lines, often with similar formatting, such as tab- or comma-delimited files or fixed-length lines.</span></span> <span data-ttu-id="2516c-125">此类文本文件读入内存之后，可以使用 LINQ 来查询和/或修改的行。</span><span class="sxs-lookup"><span data-stu-id="2516c-125">After you read such a text file into memory, you can use LINQ to query and/or modify the lines.</span></span> <span data-ttu-id="2516c-126">LINQ 查询还简化了组合来自多个源的数据的任务。</span><span class="sxs-lookup"><span data-stu-id="2516c-126">LINQ queries also simplify the task of combining data from multiple sources.</span></span>  
  
 [<span data-ttu-id="2516c-127">如何︰ 查找两个列表 (LINQ) (Visual Basic 中) 之间的差集</span><span class="sxs-lookup"><span data-stu-id="2516c-127">How to: Find the Set Difference Between Two Lists (LINQ) (Visual Basic)</span></span>](how-to-find-the-set-difference-between-two-lists-linq.md)  
 <span data-ttu-id="2516c-128">演示如何查找位于一个列表，但不是在其他的所有字符串。</span><span class="sxs-lookup"><span data-stu-id="2516c-128">Shows how to find all the strings that are present in one list but not the other.</span></span>  
  
 [<span data-ttu-id="2516c-129">如何︰ 进行排序或筛选器按任意词或字段 (LINQ) (Visual Basic 中) 的文本数据</span><span class="sxs-lookup"><span data-stu-id="2516c-129">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)</span></span>](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)  
 <span data-ttu-id="2516c-130">演示如何基于任意词或字段的文本行进行排序。</span><span class="sxs-lookup"><span data-stu-id="2516c-130">Shows how to sort text lines based on any word or field.</span></span>  
  
 [<span data-ttu-id="2516c-131">如何︰ 重新排列带分隔符的文件 (LINQ) (Visual Basic) 字段</span><span class="sxs-lookup"><span data-stu-id="2516c-131">How to: Reorder the Fields of a Delimited File (LINQ) (Visual Basic)</span></span>](how-to-reorder-the-fields-of-a-delimited-file.md)  
 <span data-ttu-id="2516c-132">演示如何在.csv 文件中的行中的字段重新排序。</span><span class="sxs-lookup"><span data-stu-id="2516c-132">Shows how to reorder fields in a line in a .csv file.</span></span>  
  
 [<span data-ttu-id="2516c-133">如何︰ 组合和比较字符串集合 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2516c-133">How to: Combine and Compare String Collections (LINQ) (Visual Basic)</span></span>](how-to-combine-and-compare-string-collections-linq.md)  
 <span data-ttu-id="2516c-134">演示如何结合使用以各种方式的字符串列表。</span><span class="sxs-lookup"><span data-stu-id="2516c-134">Shows how to combine string lists in various ways.</span></span>  
  
 [<span data-ttu-id="2516c-135">如何︰ 从多个源 (LINQ) (Visual Basic 中) 填充对象集合</span><span class="sxs-lookup"><span data-stu-id="2516c-135">How to: Populate Object Collections from Multiple Sources (LINQ) (Visual Basic)</span></span>](how-to-populate-object-collections-from-multiple-sources-linq.md)  
 <span data-ttu-id="2516c-136">演示如何使用多个文本文件作为数据源来创建对象集合。</span><span class="sxs-lookup"><span data-stu-id="2516c-136">Shows how to create object collections by using multiple text files as data sources.</span></span>  
  
 [<span data-ttu-id="2516c-137">如何︰ 联接不同文件 (LINQ) (Visual Basic 中) 的内容</span><span class="sxs-lookup"><span data-stu-id="2516c-137">How to: Join Content from Dissimilar Files (LINQ) (Visual Basic)</span></span>](how-to-join-content-from-dissimilar-files-linq.md)  
 <span data-ttu-id="2516c-138">演示如何使用匹配的键将两个列表中的字符串合并成单个字符串。</span><span class="sxs-lookup"><span data-stu-id="2516c-138">Shows how to combine strings in two lists into a single string by using a matching key.</span></span>  
  
 [<span data-ttu-id="2516c-139">如何︰ 将一个文件拆分成多个文件，通过使用组 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2516c-139">How to: Split a File Into Many Files by Using Groups (LINQ) (Visual Basic)</span></span>](how-to-split-a-file-into-many-files-by-using-groups-linq.md)  
 <span data-ttu-id="2516c-140">演示如何通过使用同一个文件作为数据源创建新文件。</span><span class="sxs-lookup"><span data-stu-id="2516c-140">Shows how to create new files by using a single file as a data source.</span></span>  
  
 [<span data-ttu-id="2516c-141">如何︰ 在 CSV 文本文件 (LINQ) (Visual Basic 中) 中计算列值</span><span class="sxs-lookup"><span data-stu-id="2516c-141">How to: Compute Column Values in a CSV Text File (LINQ) (Visual Basic)</span></span>](how-to-compute-column-values-in-a-csv-text-file-linq.md)  
 <span data-ttu-id="2516c-142">演示如何以.csv 文件中的文本数据执行数学计算。</span><span class="sxs-lookup"><span data-stu-id="2516c-142">Shows how to perform mathematical computations on text data in .csv files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2516c-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2516c-143">See Also</span></span>  
 <span data-ttu-id="2516c-144">[语言集成查询 (LINQ) (Visual Basic)](index.md) </span><span class="sxs-lookup"><span data-stu-id="2516c-144">[Language-Integrated Query (LINQ) (Visual Basic)](index.md) </span></span>  
<span data-ttu-id="2516c-145"> [如何：从 CSV 文件生成 XML](how-to-generate-xml-from-csv-files.md)</span><span class="sxs-lookup"><span data-stu-id="2516c-145"> [How to: Generate XML from CSV Files](how-to-generate-xml-from-csv-files.md)</span></span>


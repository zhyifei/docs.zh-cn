---
title: "如何︰ 查询包含一组指定的字数 (LINQ) (Visual Basic 中) 的句子 |Microsoft 文档"
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
ms.assetid: a5ae8ced-61fe-4c10-bb8a-95630e50f603
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 6da15fca0044c1b519d9de9e3785977cda344f06
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-query-for-sentences-that-contain-a-specified-set-of-words-linq-visual-basic"></a><span data-ttu-id="4f8dd-102">如何：查询包含一组指定词语的句子 (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4f8dd-102">How to: Query for Sentences that Contain a Specified Set of Words (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="4f8dd-103">此示例演示如何在文本文件中包含的一组指定词语的每个匹配项中找到的句子。</span><span class="sxs-lookup"><span data-stu-id="4f8dd-103">This example shows how to find sentences in a text file that contain matches for each of a specified set of words.</span></span> <span data-ttu-id="4f8dd-104">尽管搜索词的数组是硬编码在此示例中，它可能也将是动态填充在运行时。</span><span class="sxs-lookup"><span data-stu-id="4f8dd-104">Although the array of search terms is hard-coded in this example, it could also be populated dynamically at runtime.</span></span> <span data-ttu-id="4f8dd-105">在此示例中，查询返回的句子上，"过去"包含单词"数据"和"集成"。</span><span class="sxs-lookup"><span data-stu-id="4f8dd-105">In this example, the query returns the sentences that contain the words "Historically," "data," and "integrated."</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f8dd-106">示例</span><span class="sxs-lookup"><span data-stu-id="4f8dd-106">Example</span></span>  
  
```vb  
Class FindSentences  
  
    Shared Sub Main()  
        Dim text As String = "Historically, the world of data and the world of objects " &   
        "have not been well integrated. Programmers work in C# or Visual Basic " &   
        "and also in SQL or XQuery. On the one side are concepts such as classes, " &   
        "objects, fields, inheritance, and .NET Framework APIs. On the other side " &   
        "are tables, columns, rows, nodes, and separate languages for dealing with " &   
        "them. Data types often require translation between the two worlds; there are " &   
        "different standard functions. Because the object world has no notion of query, a " &   
        "query can only be represented as a string without compile-time type checking or " &   
        "IntelliSense support in the IDE. Transferring data from SQL tables or XML trees to " &   
        "objects in memory is often tedious and error-prone."  
  
        ' Split the text block into an array of sentences.  
        Dim sentences As String() = text.Split(New Char() {".", "?", "!"})  
  
        ' Define the search terms. This list could also be dynamically populated at runtime  
        Dim wordsToMatch As String() = {"Historically", "data", "integrated"}  
  
        ' Find sentences that contain all the terms in the wordsToMatch array  
        ' Note that the number of terms to match is not specified at compile time  
        Dim sentenceQuery = From sentence In sentences   
                            Let w = sentence.Split(New Char() {" ", ",", ".", ";", ":"},   
                                                   StringSplitOptions.RemoveEmptyEntries)   
                            Where w.Distinct().Intersect(wordsToMatch).Count = wordsToMatch.Count()   
                            Select sentence  
  
        ' Execute the query  
        For Each str As String In sentenceQuery  
            Console.WriteLine(str)  
        Next  
  
        ' Keep console window open in debug mode.  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
    End Sub  
  
End Class  
' Output:  
' Historically, the world of data and the world of objects have not been well integrated  
```  
  
 <span data-ttu-id="4f8dd-107">查询将起作用，首先将文本拆分成的句子，然后将句子拆分为一个包含每个单词的字符串数组。</span><span class="sxs-lookup"><span data-stu-id="4f8dd-107">The query works by first splitting the text into sentences, and then splitting the sentences into an array of strings that hold each word.</span></span> <span data-ttu-id="4f8dd-108">为每个这些阵列<xref:System.Linq.Enumerable.Distinct%2A>方法中删除所有重复的单词，然后查询执行<xref:System.Linq.Enumerable.Intersect%2A>word 阵列上的操作和`wordsToMatch`数组。</xref:System.Linq.Enumerable.Intersect%2A> </xref:System.Linq.Enumerable.Distinct%2A></span><span class="sxs-lookup"><span data-stu-id="4f8dd-108">For each of these arrays, the <xref:System.Linq.Enumerable.Distinct%2A> method removes all duplicate words, and then the query performs an <xref:System.Linq.Enumerable.Intersect%2A> operation on the word array and the `wordsToMatch` array.</span></span> <span data-ttu-id="4f8dd-109">交集 count 是否的计数相同`wordsToMatch`数组，字中找到所有单词，且返回原始句子。</span><span class="sxs-lookup"><span data-stu-id="4f8dd-109">If the count of the intersection is the same as the count of the `wordsToMatch` array, all words were found in the words and the original sentence is returned.</span></span>  
  
 <span data-ttu-id="4f8dd-110">在调用<xref:System.String.Split%2A>，标点符号使用作为分隔符，以便从字符串中移除。</xref:System.String.Split%2A></span><span class="sxs-lookup"><span data-stu-id="4f8dd-110">In the call to <xref:System.String.Split%2A>, the punctuation marks are used as separators in order to remove them from the string.</span></span> <span data-ttu-id="4f8dd-111">如果您没有不这样做，例如"过去"您可以使用一个字符串，程序将不匹配"过去"在`wordsToMatch`数组。</span><span class="sxs-lookup"><span data-stu-id="4f8dd-111">If you did not do this, for example you could have a string "Historically," that would not match "Historically" in the `wordsToMatch` array.</span></span> <span data-ttu-id="4f8dd-112">您可能需要使用其他分隔符，具体取决于标点的源文本中找到的类型。</span><span class="sxs-lookup"><span data-stu-id="4f8dd-112">You may have to use additional separators, depending on the types of punctuation found in the source text.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4f8dd-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="4f8dd-113">Compiling the Code</span></span>  
 <span data-ttu-id="4f8dd-114">创建一个面向.NET Framework 版本 3.5 或更高版本对 System.Core.dll 的引用与项目和一个`Imports`System.Linq 命名空间的语句。</span><span class="sxs-lookup"><span data-stu-id="4f8dd-114">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f8dd-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4f8dd-115">See Also</span></span>  
 [<span data-ttu-id="4f8dd-116">LINQ 和字符串 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4f8dd-116">LINQ and Strings (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)

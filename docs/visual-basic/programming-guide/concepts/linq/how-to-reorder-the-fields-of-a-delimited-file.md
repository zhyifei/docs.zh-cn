---
title: "如何︰ 重新排列带分隔符的文件 (LINQ) (Visual Basic) 字段 |Microsoft 文档"
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
ms.assetid: c451c7db-663b-4daf-b8ba-a2093095d672
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
ms.openlocfilehash: 8540dff06e146a1846063e11e3382e9457f9e412
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-reorder-the-fields-of-a-delimited-file-linq-visual-basic"></a><span data-ttu-id="6f957-102">如何︰ 重新排列带分隔符的文件 (LINQ) (Visual Basic) 字段</span><span class="sxs-lookup"><span data-stu-id="6f957-102">How to: Reorder the Fields of a Delimited File (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="6f957-103">以逗号分隔值 (CSV) 文件是文本文件，通常用于存储表格数据或其他由行和列的表格数据。</span><span class="sxs-lookup"><span data-stu-id="6f957-103">A comma-separated value (CSV) file is a text file that is often used to store spreadsheet data or other tabular data that is represented by rows and columns.</span></span> <span data-ttu-id="6f957-104">通过使用<xref:System.String.Split%2A>方法来分隔字段，它是非常简单查询并通过使用 LINQ 处理 CSV 文件。</xref:System.String.Split%2A></span><span class="sxs-lookup"><span data-stu-id="6f957-104">By using the <xref:System.String.Split%2A> method to separate the fields, it is very easy to query and manipulate CSV files by using LINQ.</span></span> <span data-ttu-id="6f957-105">事实上，使用相同的方法来重新排列的任何结构化文本; 行部分不受限制到 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="6f957-105">In fact, the same technique can be used to reorder the parts of any structured line of text; it is not limited to CSV files.</span></span>  
  
 <span data-ttu-id="6f957-106">在下面的示例中，假定有三列分别代表学生的"last name，""名字"和"id"。</span><span class="sxs-lookup"><span data-stu-id="6f957-106">In the following example, assume that the three columns represent students' "last name," "first name", and "ID."</span></span> <span data-ttu-id="6f957-107">根据学生的姓氏和名字的字母顺序中的字段。</span><span class="sxs-lookup"><span data-stu-id="6f957-107">The fields are in alphabetical order based on the students' last names.</span></span> <span data-ttu-id="6f957-108">此查询生成新的序列中的 ID 列显示在最前面，后面组合学生的名字和姓氏的第二个列。</span><span class="sxs-lookup"><span data-stu-id="6f957-108">The query produces a new sequence in which the ID column appears first, followed by a second column that combines the student's first name and last name.</span></span> <span data-ttu-id="6f957-109">根据 ID 字段，这些行进行重新排序。</span><span class="sxs-lookup"><span data-stu-id="6f957-109">The lines are reordered according to the ID field.</span></span> <span data-ttu-id="6f957-110">结果保存到一个新文件，不修改原始数据。</span><span class="sxs-lookup"><span data-stu-id="6f957-110">The results are saved into a new file and the original data is not modified.</span></span>  
  
### <a name="to-create-the-data-file"></a><span data-ttu-id="6f957-111">创建数据文件</span><span class="sxs-lookup"><span data-stu-id="6f957-111">To create the data file</span></span>  
  
1.  <span data-ttu-id="6f957-112">将以下行复制到名为 spreadsheet1.csv 纯文本文件。</span><span class="sxs-lookup"><span data-stu-id="6f957-112">Copy the following lines into a plain text file that is named spreadsheet1.csv.</span></span> <span data-ttu-id="6f957-113">将文件保存在项目文件夹中。</span><span class="sxs-lookup"><span data-stu-id="6f957-113">Save the file in your project folder.</span></span>  
  
    ```  
    Adams,Terry,120  
    Fakhouri,Fadi,116  
    Feng,Hanying,117  
    Garcia,Cesar,114  
    Garcia,Debra,115  
    Garcia,Hugo,118  
    Mortensen,Sven,113  
    O'Donnell,Claire,112  
    Omelchenko,Svetlana,111  
    Tucker,Lance,119  
    Tucker,Michael,122  
    Zabokritski,Eugene,121  
    ```  
  
## <a name="example"></a><span data-ttu-id="6f957-114">示例</span><span class="sxs-lookup"><span data-stu-id="6f957-114">Example</span></span>  
  
```vb  
Class CSVFiles  
  
    Shared Sub Main()  
  
        ' Create the IEnumerable data source.  
        Dim lines As String() = System.IO.File.ReadAllLines("../../../spreadsheet1.csv")  
  
        ' Execute the query. Put field 2 first, then  
        ' reverse and combine fields 0 and 1 from the old field  
        Dim lineQuery = From line In lines   
                        Let x = line.Split(New Char() {","})   
                        Order By x(2)   
                        Select x(2) & ", " & (x(1) & " " & x(0))  
  
        ' Execute the query and write out the new file. Note that WriteAllLines  
        ' takes a string array, so ToArray is called on the query.  
        System.IO.File.WriteAllLines("../../../spreadsheet2.csv", lineQuery.ToArray())  
  
        ' Keep console window open in debug mode.  
        Console.WriteLine("Spreadsheet2.csv written to disk. Press any key to exit")  
        Console.ReadKey()  
    End Sub  
End Class  
' Output to spreadsheet2.csv:  
' 111, Svetlana Omelchenko  
' 112, Claire O'Donnell  
' 113, Sven Mortensen  
' 114, Cesar Garcia  
' 115, Debra Garcia  
' 116, Fadi Fakhouri  
' 117, Hanying Feng  
' 118, Hugo Garcia  
' 119, Lance Tucker  
' 120, Terry Adams  
' 121, Eugene Zabokritski  
' 122, Michael Tucker  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6f957-115">编译代码</span><span class="sxs-lookup"><span data-stu-id="6f957-115">Compiling the Code</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f957-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6f957-116">See Also</span></span>  
 <span data-ttu-id="6f957-117">[LINQ 和字符串 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md) </span><span class="sxs-lookup"><span data-stu-id="6f957-117">[LINQ and Strings (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md) </span></span>  
<span data-ttu-id="6f957-118"> [LINQ 和文件目录 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md) </span><span class="sxs-lookup"><span data-stu-id="6f957-118"> [LINQ and File Directories (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md) </span></span>  
<span data-ttu-id="6f957-119"> [如何：从 CSV 文件生成 XML](http://msdn.microsoft.com/library/dd7bab8c-96fa-4343-94d0-9739dd6a74fd)</span><span class="sxs-lookup"><span data-stu-id="6f957-119"> [How to: Generate XML from CSV Files](http://msdn.microsoft.com/library/dd7bab8c-96fa-4343-94d0-9739dd6a74fd)</span></span>

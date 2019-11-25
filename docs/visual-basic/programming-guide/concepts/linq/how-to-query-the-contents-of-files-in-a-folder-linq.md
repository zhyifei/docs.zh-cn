---
title: How to query the contents of files in a folder (LINQ)
ms.date: 07/20/2015
ms.assetid: edacbcd3-f3e4-4429-a8be-28a58dc0dd70
ms.openlocfilehash: 02ffa398c495ca5af77685d62299c59cfc3b9d9c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347616"
---
# <a name="how-to-query-the-contents-of-files-in-a-folder-linq-visual-basic"></a><span data-ttu-id="f82c4-102">How to query the contents of files in a folder (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f82c4-102">How to query the contents of files in a folder (LINQ) (Visual Basic)</span></span>

<span data-ttu-id="f82c4-103">此示例演示如何查询指定目录树中的所有文件、打开每个文件并检查其内容。</span><span class="sxs-lookup"><span data-stu-id="f82c4-103">This example shows how to query over all the files in a specified directory tree, open each file, and inspect its contents.</span></span> <span data-ttu-id="f82c4-104">此类技术可用于对目录树的内容创建索引或反向索引。</span><span class="sxs-lookup"><span data-stu-id="f82c4-104">This type of technique could be used to create indexes or reverse indexes of the contents of a directory tree.</span></span> <span data-ttu-id="f82c4-105">此示例中执行的是简单的字符串搜索。</span><span class="sxs-lookup"><span data-stu-id="f82c4-105">A simple string search is performed in this example.</span></span> <span data-ttu-id="f82c4-106">但是，可使用正则表达式执行类型更复杂的模式匹配。</span><span class="sxs-lookup"><span data-stu-id="f82c4-106">However, more complex types of pattern matching can be performed with a regular expression.</span></span> <span data-ttu-id="f82c4-107">For more information, see [How to: Combine LINQ Queries with Regular Expressions (Visual Basic)](how-to-combine-linq-queries-with-regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="f82c4-107">For more information, see [How to: Combine LINQ Queries with Regular Expressions (Visual Basic)](how-to-combine-linq-queries-with-regular-expressions.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f82c4-108">示例</span><span class="sxs-lookup"><span data-stu-id="f82c4-108">Example</span></span>  
  
```vb
Imports System.IO

Module Module1  
    'QueryContents  
    Public Sub Main()  
  
        ' Modify this path as necessary.  
        Dim startFolder = "C:\Program Files (x86)\Microsoft Visual Studio 14.0"  

        ' Take a snapshot of the folder contents.
        Dim dir As New DirectoryInfo(startFolder)
        Dim fileList = dir.GetFiles("*.*", SearchOption.AllDirectories)

        Dim searchTerm = "Welcome"

        ' Search the contents of each file.
        ' A regular expression created with the RegEx class
        ' could be used instead of the Contains method.
        Dim queryMatchingFiles = From file In fileList _
                                 Where file.Extension = ".html" _
                                 Let fileText = GetFileText(file.FullName) _
                                 Where fileText.Contains(searchTerm) _
                                 Select file.FullName

        Console.WriteLine("The term " & searchTerm & " was found in:")

        ' Execute the query.
        For Each filename In queryMatchingFiles
            Console.WriteLine(filename)
        Next

        ' Keep the console window open in debug mode.
        Console.WriteLine("Press any key to exit")
        Console.ReadKey()

    End Sub

    ' Read the contents of the file. This is done in a separate
    ' function in order to handle potential file system errors.
    Function GetFileText(name As String) As String

        ' If the file has been deleted, the right thing
        ' to do in this case is return an empty string.
        Dim fileContents = String.Empty

        ' If the file has been deleted since we took
        ' the snapshot, ignore it and return the empty string.
        If File.Exists(name) Then
            fileContents = File.ReadAllText(name)
        End If

        Return fileContents

    End Function
End Module
```

## <a name="compiling-the-code"></a><span data-ttu-id="f82c4-109">编译代码</span><span class="sxs-lookup"><span data-stu-id="f82c4-109">Compiling the code</span></span>

<span data-ttu-id="f82c4-110">Create a VB.NET console application project, copy and paste the code sample, and adjust the Startup object value in the project properties.</span><span class="sxs-lookup"><span data-stu-id="f82c4-110">Create a VB.NET console application project, copy and paste the code sample, and adjust the Startup object value in the project properties.</span></span>

## <a name="see-also"></a><span data-ttu-id="f82c4-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="f82c4-111">See also</span></span>

- [<span data-ttu-id="f82c4-112">LINQ to Objects (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f82c4-112">LINQ to Objects (Visual Basic)</span></span>](linq-to-objects.md)
- [<span data-ttu-id="f82c4-113">LINQ 和文件目录 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f82c4-113">LINQ and File Directories (Visual Basic)</span></span>](linq-and-file-directories.md)

---
title: "如何： 查询具有指定的特性或名称 (Visual Basic) 的文件"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b26026a3-3f43-448f-a582-259997af6be0
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2b46750876e683e8ca5801d5c37267bf3d681cfe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-query-for-files-with-a-specified-attribute-or-name-visual-basic"></a><span data-ttu-id="3f74b-102">如何： 查询具有指定的特性或名称 (Visual Basic) 的文件</span><span class="sxs-lookup"><span data-stu-id="3f74b-102">How to: Query for Files with a Specified Attribute or Name (Visual Basic)</span></span>
<span data-ttu-id="3f74b-103">此示例演示了如何在指定目录树中查找具有指定文件扩展名（如“.txt”）的所有文件。</span><span class="sxs-lookup"><span data-stu-id="3f74b-103">This example shows how to find all files that have a specified file name extension (for example ".txt") in a specified directory tree.</span></span> <span data-ttu-id="3f74b-104">它还演示了如何基于时间在树中返回最新或最旧的文件。</span><span class="sxs-lookup"><span data-stu-id="3f74b-104">It also shows how to return either the newest or oldest file in the tree based on the creation time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f74b-105">示例</span><span class="sxs-lookup"><span data-stu-id="3f74b-105">Example</span></span>  
  
```vb  
Module FindFileByExtension  
    Sub Main()  
  
        ' Change the drive\path if necessary  
        Dim root As String = "C:\Program Files\Microsoft Visual Studio 9.0"  
  
        'Take a snapshot of the folder contents  
        Dim dir As New System.IO.DirectoryInfo(root)  
  
        Dim fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories)  
  
        ' This query will produce the full path for all .txt files  
        ' under the specified folder including subfolders.  
        ' It orders the list according to the file name.  
        Dim fileQuery = From file In fileList _  
                        Where file.Extension = ".txt" _  
                        Order By file.Name _  
                        Select file  
  
        For Each file In fileQuery  
            Console.WriteLine(file.FullName)  
        Next  
  
        ' Create and execute a new query by using  
        ' the previous query as a starting point.  
        ' fileQuery is not executed again until the  
        ' call to Last  
        Dim fileQuery2 = From file In fileQuery _  
                         Order By file.CreationTime _  
                         Select file.Name, file.CreationTime  
  
        ' Execute the query  
        Dim newestFile = fileQuery2.Last  
  
        Console.WriteLine("\r\nThe newest .txt file is {0}. Creation time: {1}", _  
                newestFile.Name, newestFile.CreationTime)  
  
        ' Keep the console window open in debug mode  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
  
    End Sub  
End Module  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3f74b-106">编译代码</span><span class="sxs-lookup"><span data-stu-id="3f74b-106">Compiling the Code</span></span>  
 <span data-ttu-id="3f74b-107">创建面向.NET Framework 版本 3.5 或更高版本使用对 System.Core.dll 的引用的项目和`Imports`System.Linq 命名空间的语句。</span><span class="sxs-lookup"><span data-stu-id="3f74b-107">Create a project that targets the .NET Framework version 3.5 or higher with a reference to System.Core.dll and a   `Imports` statement for the System.Linq namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f74b-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f74b-108">See Also</span></span>  
 [<span data-ttu-id="3f74b-109">LINQ to Objects (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3f74b-109">LINQ to Objects (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)  
 [<span data-ttu-id="3f74b-110">LINQ 和文件目录 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3f74b-110">LINQ and File Directories (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)

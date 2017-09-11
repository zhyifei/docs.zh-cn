---
title: "如何︰ 填充 XML 树从文件系统 (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: 34eec79e-7945-4ba8-9f74-d05bb8ec67f6
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b8119c134612aaf03e22644d34d758933a902339
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017


---
# <a name="how-to-populate-an-xml-tree-from-the-file-system-visual-basic"></a><span data-ttu-id="a4934-102">如何︰ 填充 XML 树从文件系统 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a4934-102">How to: Populate an XML Tree from the File System (Visual Basic)</span></span>
<span data-ttu-id="a4934-103">XML 树有一种有用的常见应用，即作为层次结构名称/值数据存储区。</span><span class="sxs-lookup"><span data-stu-id="a4934-103">A common and useful application of XML trees is as a hierarchical name/value data store.</span></span> <span data-ttu-id="a4934-104">您可以使用层次结构数据填充 XML 树，然后对它进行查询、转换和序列化（如有必要）。</span><span class="sxs-lookup"><span data-stu-id="a4934-104">You can populate an XML tree with hierarchical data, and then query it, transform it, and if necessary, serialize it.</span></span> <span data-ttu-id="a4934-105">在这种用法中，很多 XML 特定的语义（如命名空间和空白行为）都不重要。</span><span class="sxs-lookup"><span data-stu-id="a4934-105">In this usage scenario, many of the XML specific semantics, such as namespaces and white space behavior, are not important.</span></span> <span data-ttu-id="a4934-106">相反，你将 XML 树用作内存中的小型单用户层次结构数据库。</span><span class="sxs-lookup"><span data-stu-id="a4934-106">Instead, you are using the XML tree as a small, in memory, single user hierarchical database.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4934-107">示例</span><span class="sxs-lookup"><span data-stu-id="a4934-107">Example</span></span>  
 <span data-ttu-id="a4934-108">下面的示例使用递归从本地文件系统填充 XML 树。</span><span class="sxs-lookup"><span data-stu-id="a4934-108">The following example populates an XML tree from the local file system using recursion.</span></span> <span data-ttu-id="a4934-109">然后查询该树，计算树中所有文件的总大小。</span><span class="sxs-lookup"><span data-stu-id="a4934-109">It then queries the tree, calculating the total of the sizes of all files in the tree.</span></span>  
  
```vb  
Module Module1  
    Function CreateFileSystemXmlTree(ByVal source As String) As XElement  
        Dim di As DirectoryInfo = New DirectoryInfo(source)  
        Return <Dir Name=<%= di.Name %>>  
                   <%= From d In Directory.GetDirectories(source) _  
                       Select CreateFileSystemXmlTree(d) %>  
                   <%= From fi In di.GetFiles() _  
                       Select <File>  
                                  <Name><%= fi.Name %></Name>  
                                  <Length><%= fi.Length %></Length>  
                              </File> %>  
               </Dir>  
    End Function  
  
    Sub Main()  
        Dim fileSystemTree As XElement = CreateFileSystemXmlTree("C:/Tmp")  
        Console.WriteLine(fileSystemTree)  
        Console.WriteLine("------")  
        Dim totalFileSize As Long = _  
            ( _  
                From f In fileSystemTree...<File> _  
                Select CLng(f.<Length>(0)) _  
            ).Sum()  
        Console.WriteLine("Total File Size:{0}", totalFileSize)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="a4934-110">本示例生成类似下面的输出：</span><span class="sxs-lookup"><span data-stu-id="a4934-110">This example produces output similar to the following:</span></span>  
  
```xml  
<Dir Name="Tmp">  
  <Dir Name="ConsoleApplication1">  
    <Dir Name="bin">  
      <Dir Name="Debug">  
        <File>  
          <Name>ConsoleApplication1.exe</Name>  
          <Length>4608</Length>  
        </File>  
        <File>  
          <Name>ConsoleApplication1.pdb</Name>  
          <Length>11776</Length>  
        </File>  
        <File>  
          <Name>ConsoleApplication1.vshost.exe</Name>  
          <Length>9568</Length>  
        </File>  
        <File>  
          <Name>ConsoleApplication1.vshost.exe.manifest</Name>  
          <Length>473</Length>  
        </File>  
      </Dir>  
    </Dir>  
    <Dir Name="obj">  
      <Dir Name="Debug">  
        <Dir Name="TempPE" />  
        <File>  
          <Name>ConsoleApplication1.csproj.FileListAbsolute.txt</Name>  
          <Length>322</Length>  
        </File>  
        <File>  
          <Name>ConsoleApplication1.exe</Name>  
          <Length>4608</Length>  
        </File>  
        <File>  
          <Name>ConsoleApplication1.pdb</Name>  
          <Length>11776</Length>  
        </File>  
      </Dir>  
    </Dir>  
    <Dir Name="Properties">  
      <File>  
        <Name>AssemblyInfo.cs</Name>  
        <Length>1454</Length>  
      </File>  
    </Dir>  
    <File>  
      <Name>ConsoleApplication1.csproj</Name>  
      <Length>2546</Length>  
    </File>  
    <File>  
      <Name>ConsoleApplication1.sln</Name>  
      <Length>937</Length>  
    </File>  
    <File>  
      <Name>ConsoleApplication1.suo</Name>  
      <Length>10752</Length>  
    </File>  
    <File>  
      <Name>Program.cs</Name>  
      <Length>269</Length>  
    </File>  
  </Dir>  
</Dir>  
------  
Total File Size:59089  
```  
  
## <a name="see-also"></a><span data-ttu-id="a4934-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4934-111">See Also</span></span>  
 [<span data-ttu-id="a4934-112">高级查询技术 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a4934-112">Advanced Query Techniques (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-query-techniques-linq-to-xml.md)

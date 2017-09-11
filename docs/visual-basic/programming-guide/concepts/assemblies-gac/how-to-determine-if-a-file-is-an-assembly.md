---
title: "如何︰ 确定文件是否为程序集 (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: de26f410-9bd1-4b55-a343-cc82f81684be
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4bd3404cbdc3b79ff92290a53574080bf197fe9d
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-determine-if-a-file-is-an-assembly-visual-basic"></a><span data-ttu-id="541b7-102">如何︰ 确定文件是否为程序集 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="541b7-102">How to: Determine If a File Is an Assembly (Visual Basic)</span></span>
<span data-ttu-id="541b7-103">当且仅当它处于托管状态，并包含其元数据中的程序集条目，则文件是程序集。</span><span class="sxs-lookup"><span data-stu-id="541b7-103">A file is an assembly if and only if it is managed, and contains an assembly entry in its metadata.</span></span> <span data-ttu-id="541b7-104">程序集和元数据的详细信息，请参阅主题[程序集清单](https://msdn.microsoft.com/library/1w45z383)。</span><span class="sxs-lookup"><span data-stu-id="541b7-104">For more information on assemblies and metadata, see the topic [Assembly Manifest](https://msdn.microsoft.com/library/1w45z383).</span></span>  
  
## <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="541b7-105">如何手动确定文件是否为程序集</span><span class="sxs-lookup"><span data-stu-id="541b7-105">How to manually determine if a file is an assembly</span></span>  
  
1.  <span data-ttu-id="541b7-106">启动[Ildasm.exe （IL 反汇编程序）](https://msdn.microsoft.com/library/f7dy01k1)。</span><span class="sxs-lookup"><span data-stu-id="541b7-106">Start the [Ildasm.exe (IL Disassembler)](https://msdn.microsoft.com/library/f7dy01k1).</span></span>  
  
2.  <span data-ttu-id="541b7-107">加载你要测试的文件。</span><span class="sxs-lookup"><span data-stu-id="541b7-107">Load the file you wish to test.</span></span>  
  
3.  <span data-ttu-id="541b7-108">如果**ILDASM**报表文件不是一个可移植可执行 (PE) 文件，则它不是程序集。</span><span class="sxs-lookup"><span data-stu-id="541b7-108">If **ILDASM** reports that the file is not a portable executable (PE) file, then it is not an assembly.</span></span> <span data-ttu-id="541b7-109">有关详细信息，请参阅主题[如何︰ 查看程序集内容](http://msdn.microsoft.com/library/fb7baaab-4c0d-47ad-8fd3-4591cf834709)。</span><span class="sxs-lookup"><span data-stu-id="541b7-109">For more information, see the topic [How to: View Assembly Contents](http://msdn.microsoft.com/library/fb7baaab-4c0d-47ad-8fd3-4591cf834709).</span></span>  
  
## <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="541b7-110">如何以编程方式确定文件是否为程序集</span><span class="sxs-lookup"><span data-stu-id="541b7-110">How to programmatically determine if a file is an assembly</span></span>  
  
1.  <span data-ttu-id="541b7-111">调用<xref:System.Reflection.AssemblyName.GetAssemblyName%2A>方法，并传递的完整文件路径和要测试的文件的名称。</xref:System.Reflection.AssemblyName.GetAssemblyName%2A></span><span class="sxs-lookup"><span data-stu-id="541b7-111">Call the <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method, passing the full file path and name of the file you are testing.</span></span>  
  
2.  <span data-ttu-id="541b7-112">如果<xref:System.BadImageFormatException>引发异常，该文件不是程序集。</xref:System.BadImageFormatException></span><span class="sxs-lookup"><span data-stu-id="541b7-112">If a <xref:System.BadImageFormatException> exception is thrown, the file is not an assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="541b7-113">示例</span><span class="sxs-lookup"><span data-stu-id="541b7-113">Example</span></span>  
 <span data-ttu-id="541b7-114">此示例测试以查看它是否为程序集 DLL。</span><span class="sxs-lookup"><span data-stu-id="541b7-114">This example tests a DLL to see if it is an assembly.</span></span>  
  
```vb  
Module Module1  
    Sub Main()  
        Try  
            Dim testAssembly As Reflection.AssemblyName =  
                                Reflection.AssemblyName.GetAssemblyName("C:\Windows\Microsoft.NET\Framework\v3.5\System.Net.dll")  
            Console.WriteLine("Yes, the file is an Assembly.")  
        Catch ex As System.IO.FileNotFoundException  
            Console.WriteLine("The file cannot be found.")  
        Catch ex As System.BadImageFormatException  
            Console.WriteLine("The file is not an Assembly.")  
        Catch ex As System.IO.FileLoadException  
            Console.WriteLine("The Assembly has already been loaded.")  
        End Try  
        Console.ReadLine()  
    End Sub  
End Module  
' Output (with .NET Framework 3.5 installed):  
'        Yes, the file is an Assembly.  
```
  
 <span data-ttu-id="541b7-115"><xref:System.Reflection.AssemblyName.GetAssemblyName%2A>方法加载测试文件，并将读取的信息之后，然后释放它。</xref:System.Reflection.AssemblyName.GetAssemblyName%2A></span><span class="sxs-lookup"><span data-stu-id="541b7-115">The <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method loads the test file, and then releases it once the information is read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="541b7-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="541b7-116">See Also</span></span>  
 <span data-ttu-id="541b7-117"><xref:System.Reflection.AssemblyName></xref:System.Reflection.AssemblyName></span><span class="sxs-lookup"><span data-stu-id="541b7-117"><xref:System.Reflection.AssemblyName></span></span>   
<span data-ttu-id="541b7-118"> [编程概念](../../../../visual-basic/programming-guide/concepts/index.md) </span><span class="sxs-lookup"><span data-stu-id="541b7-118"> [Programming Concepts](../../../../visual-basic/programming-guide/concepts/index.md) </span></span>  
<span data-ttu-id="541b7-119"> [程序集和全局程序集缓存 (Visual Basic)](index.md)</span><span class="sxs-lookup"><span data-stu-id="541b7-119"> [Assemblies and the Global Assembly Cache (Visual Basic)](index.md)</span></span>

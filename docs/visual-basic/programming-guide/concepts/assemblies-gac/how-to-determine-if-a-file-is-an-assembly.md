---
title: 如何： 确定文件是否为程序集 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: de26f410-9bd1-4b55-a343-cc82f81684be
ms.openlocfilehash: ced41279e7e192d6d5bed53dbce7378395b32e6d
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44266636"
---
# <a name="how-to-determine-if-a-file-is-an-assembly-visual-basic"></a><span data-ttu-id="6e780-102">如何： 确定文件是否为程序集 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6e780-102">How to: Determine If a File Is an Assembly (Visual Basic)</span></span>
<span data-ttu-id="6e780-103">当且仅当程序集处于托管状态，并在其元数据中包含程序集条目时，该文件才为程序集。</span><span class="sxs-lookup"><span data-stu-id="6e780-103">A file is an assembly if and only if it is managed, and contains an assembly entry in its metadata.</span></span> <span data-ttu-id="6e780-104">有关程序集和元数据的详细信息，请参阅主题[程序集清单](../../../../framework/app-domains/assembly-manifest.md)。</span><span class="sxs-lookup"><span data-stu-id="6e780-104">For more information on assemblies and metadata, see the topic [Assembly Manifest](../../../../framework/app-domains/assembly-manifest.md).</span></span>  
  
## <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="6e780-105">如何手动确定文件是否为程序集</span><span class="sxs-lookup"><span data-stu-id="6e780-105">How to manually determine if a file is an assembly</span></span>  
  
1.  <span data-ttu-id="6e780-106">启动 [Ildasm.exe（IL 反汇编程序）](../../../../framework/tools/ildasm-exe-il-disassembler.md)。</span><span class="sxs-lookup"><span data-stu-id="6e780-106">Start the [Ildasm.exe (IL Disassembler)](../../../../framework/tools/ildasm-exe-il-disassembler.md).</span></span>  
  
2.  <span data-ttu-id="6e780-107">加载要测试的文件。</span><span class="sxs-lookup"><span data-stu-id="6e780-107">Load the file you wish to test.</span></span>  
  
3.  <span data-ttu-id="6e780-108">如果 **ILDASM** 报告文件不是可移植的可执行 (PE) 文件，则不是程序集。</span><span class="sxs-lookup"><span data-stu-id="6e780-108">If **ILDASM** reports that the file is not a portable executable (PE) file, then it is not an assembly.</span></span> <span data-ttu-id="6e780-109">有关详细信息，请参阅主题 [How to: View Assembly Contents](../../../../framework/app-domains/how-to-view-assembly-contents.md)（如何：查看程序集内容）。</span><span class="sxs-lookup"><span data-stu-id="6e780-109">For more information, see the topic [How to: View Assembly Contents](../../../../framework/app-domains/how-to-view-assembly-contents.md).</span></span>  
  
## <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a><span data-ttu-id="6e780-110">如何以编程方式确定文件是否为程序集</span><span class="sxs-lookup"><span data-stu-id="6e780-110">How to programmatically determine if a file is an assembly</span></span>  
  
1.  <span data-ttu-id="6e780-111">调用 <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> 方法，传递要测试的文件的完整文件路径和名称。</span><span class="sxs-lookup"><span data-stu-id="6e780-111">Call the <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method, passing the full file path and name of the file you are testing.</span></span>  
  
2.  <span data-ttu-id="6e780-112">如果引发 <xref:System.BadImageFormatException> 异常，则该文件不是程序集。</span><span class="sxs-lookup"><span data-stu-id="6e780-112">If a <xref:System.BadImageFormatException> exception is thrown, the file is not an assembly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e780-113">示例</span><span class="sxs-lookup"><span data-stu-id="6e780-113">Example</span></span>  
 <span data-ttu-id="6e780-114">此示例测试 DLL 以查看其是否为程序集。</span><span class="sxs-lookup"><span data-stu-id="6e780-114">This example tests a DLL to see if it is an assembly.</span></span>  
  
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
  
 <span data-ttu-id="6e780-115"><xref:System.Reflection.AssemblyName.GetAssemblyName%2A> 方法加载测试文件，然后在读取信息之后释放它。</span><span class="sxs-lookup"><span data-stu-id="6e780-115">The <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> method loads the test file, and then releases it once the information is read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e780-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="6e780-116">See also</span></span>

- <xref:System.Reflection.AssemblyName>  
- [<span data-ttu-id="6e780-117">编程概念</span><span class="sxs-lookup"><span data-stu-id="6e780-117">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)  
- [<span data-ttu-id="6e780-118">程序集和全局程序集缓存 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6e780-118">Assemblies and the Global Assembly Cache (Visual Basic)</span></span>](index.md)

---
title: "无法发出程序集︰&lt;错误信息&gt;|Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30145
- bc30145
dev_langs:
- VB
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d15981a1a2fb31ba377066fa421f5a9979d47a12
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="unable-to-emit-assembly-lterror-messagegt"></a><span data-ttu-id="db5c1-102">无法发出程序集︰&lt;错误消息&gt;</span><span class="sxs-lookup"><span data-stu-id="db5c1-102">Unable to emit assembly: &lt;error message&gt;</span></span>
<span data-ttu-id="db5c1-103">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]编译器调用程序集链接器 (Al.exe，也称作 Alink) 生成的程序集与一个清单，而该链接器创建程序集的发出阶段报告一个错误。</span><span class="sxs-lookup"><span data-stu-id="db5c1-103">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler calls the Assembly Linker (Al.exe, also known as Alink) to generate an assembly with a manifest, with the linker reporting an error in the emission stage of creating the assembly.</span></span>  
  
 <span data-ttu-id="db5c1-104">**错误 ID:** BC30145</span><span class="sxs-lookup"><span data-stu-id="db5c1-104">**Error ID:** BC30145</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="db5c1-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="db5c1-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="db5c1-106">检查引用的错误信息并参考主题[Al.exe 工具错误和警告](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b)的进一步解释和建议。</span><span class="sxs-lookup"><span data-stu-id="db5c1-106">Examine the quoted error message and consult the topic [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) for further explanation and advice.</span></span>  
  
2.  <span data-ttu-id="db5c1-107">请尝试手动签名程序集使用[Al.exe （程序集链接器）](https://msdn.microsoft.com/library/c405shex)或[Sn.exe （强名称工具）](https://msdn.microsoft.com/library/k5b5tt23)。</span><span class="sxs-lookup"><span data-stu-id="db5c1-107">Try signing the assembly manually, using either the [Al.exe (Assembly Linker)](https://msdn.microsoft.com/library/c405shex) or the [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23).</span></span>  
  
3.  <span data-ttu-id="db5c1-108">如果仍然出现错误，则收集有关该情况的信息并通知 Microsoft 产品支持服务。</span><span class="sxs-lookup"><span data-stu-id="db5c1-108">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
### <a name="to-sign-the-assembly-manually"></a><span data-ttu-id="db5c1-109">手动对程序集进行签名</span><span class="sxs-lookup"><span data-stu-id="db5c1-109">To sign the assembly manually</span></span>  
  
1.  <span data-ttu-id="db5c1-110">使用[Sn.exe （强名称工具）](https://msdn.microsoft.com/library/k5b5tt23)创建公钥/私钥对文件。</span><span class="sxs-lookup"><span data-stu-id="db5c1-110">Use the [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23) to create a public/private key pair file.</span></span>  
  
     <span data-ttu-id="db5c1-111">此文件的扩展名为 .snk。</span><span class="sxs-lookup"><span data-stu-id="db5c1-111">This file has a .snk extension.</span></span>  
  
2.  <span data-ttu-id="db5c1-112">从项目中删除生成错误的 COM 引用。</span><span class="sxs-lookup"><span data-stu-id="db5c1-112">Delete the COM reference that is generating the error from your project.</span></span>  
  
3.  <span data-ttu-id="db5c1-113">从 Windows**启动**菜单上，指向**程序**，指向**Microsoft Visual Studio 2008**，指向**Visual Studio Tools**，然后单击**Visual Studio 2008 命令提示**。</span><span class="sxs-lookup"><span data-stu-id="db5c1-113">From the Windows **Start** menu, point to **Programs**, point to **Microsoft Visual Studio 2008**, point to **Visual Studio Tools**, and then click **Visual Studio 2008 Command Prompt**.</span></span>  
  
4.  <span data-ttu-id="db5c1-114">移动到要放置程序集包装的目录。</span><span class="sxs-lookup"><span data-stu-id="db5c1-114">Move to the directory where you want to place your assembly wrapper.</span></span>  
  
5.  <span data-ttu-id="db5c1-115">键入以下代码。</span><span class="sxs-lookup"><span data-stu-id="db5c1-115">Type the following code.</span></span>  
  
    ```  
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>  
    ```  
  
     <span data-ttu-id="db5c1-116">下面是你可能会输入的代码的示例。</span><span class="sxs-lookup"><span data-stu-id="db5c1-116">An example of the code you might enter would be the following.</span></span>  
  
    ```  
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"  
    ```  
  
     <span data-ttu-id="db5c1-117">如果路径或文件包含空格，则使用双引号 (")。</span><span class="sxs-lookup"><span data-stu-id="db5c1-117">Use double quotation marks (") if a path or file contains spaces.</span></span>  
  
6.  <span data-ttu-id="db5c1-118">在 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] 中，添加对刚创建的文件的 .NET 程序集引用。</span><span class="sxs-lookup"><span data-stu-id="db5c1-118">In [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], add a .NET Assembly reference to the file you just created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db5c1-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db5c1-119">See Also</span></span>  
 <span data-ttu-id="db5c1-120">[Al.exe （程序集链接器）](https://msdn.microsoft.com/library/c405shex) </span><span class="sxs-lookup"><span data-stu-id="db5c1-120">[Al.exe (Assembly Linker)](https://msdn.microsoft.com/library/c405shex) </span></span>  
<span data-ttu-id="db5c1-121"> [Al.exe 工具错误和警告](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) </span><span class="sxs-lookup"><span data-stu-id="db5c1-121"> [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) </span></span>  
<span data-ttu-id="db5c1-122"> [Sn.exe （强名称工具）](https://msdn.microsoft.com/library/k5b5tt23) </span><span class="sxs-lookup"><span data-stu-id="db5c1-122"> [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23) </span></span>  
<span data-ttu-id="db5c1-123"> [如何：创建公钥/私钥对](http://msdn.microsoft.com/library/05026813-f3bd-4d7c-9e0b-fc588eb3d114) </span><span class="sxs-lookup"><span data-stu-id="db5c1-123"> [How to: Create a Public-Private Key Pair](http://msdn.microsoft.com/library/05026813-f3bd-4d7c-9e0b-fc588eb3d114) </span></span>  
<span data-ttu-id="db5c1-124"> [与我们交流](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span><span class="sxs-lookup"><span data-stu-id="db5c1-124"> [Talk to Us](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span></span>

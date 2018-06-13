---
title: 无法发出程序集：&lt;错误消息&gt;
ms.date: 07/20/2015
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
ms.openlocfilehash: 8f497069088ad30a3be58d02caa0a32f7f1b21b7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595168"
---
# <a name="unable-to-emit-assembly-lterror-messagegt"></a><span data-ttu-id="de4ea-102">无法发出程序集：&lt;错误消息&gt;</span><span class="sxs-lookup"><span data-stu-id="de4ea-102">Unable to emit assembly: &lt;error message&gt;</span></span>
<span data-ttu-id="de4ea-103">Visual Basic 编译器使用创建程序集的发出阶段中报告错误链接器调用程序集链接器 (Al.exe，也称作 Alink) 生成包含清单的程序集。</span><span class="sxs-lookup"><span data-stu-id="de4ea-103">The Visual Basic compiler calls the Assembly Linker (Al.exe, also known as Alink) to generate an assembly with a manifest, with the linker reporting an error in the emission stage of creating the assembly.</span></span>  
  
 <span data-ttu-id="de4ea-104">**错误 ID:** BC30145</span><span class="sxs-lookup"><span data-stu-id="de4ea-104">**Error ID:** BC30145</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="de4ea-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="de4ea-105">To correct this error</span></span>  
  
1.  <span data-ttu-id="de4ea-106">检查引用的错误信息并参考主题[Al.exe](../../../framework/tools/al-exe-assembly-linker.md)。</span><span class="sxs-lookup"><span data-stu-id="de4ea-106">Examine the quoted error message and consult the topic [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span></span> <span data-ttu-id="de4ea-107">以获得进一步的解释和建议。</span><span class="sxs-lookup"><span data-stu-id="de4ea-107">for further explanation and advice.</span></span>  
  
2.  <span data-ttu-id="de4ea-108">请尝试手动签名程序集使用[Al.exe](../../../framework/tools/al-exe-assembly-linker.md)或[Sn.exe （强名称工具）](../../../framework/tools/sn-exe-strong-name-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="de4ea-108">Try signing the assembly manually, using either the [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) or the [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md).</span></span>  
  
3.  <span data-ttu-id="de4ea-109">如果仍然出现错误，则收集有关该情况的信息并通知 Microsoft 产品支持服务。</span><span class="sxs-lookup"><span data-stu-id="de4ea-109">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
### <a name="to-sign-the-assembly-manually"></a><span data-ttu-id="de4ea-110">手动对程序集进行签名</span><span class="sxs-lookup"><span data-stu-id="de4ea-110">To sign the assembly manually</span></span>  
  
1.  <span data-ttu-id="de4ea-111">使用 [Sn.exe （强名称工具）][Sn.exe （强名称工具）](../../../framework/tools/sn-exe-strong-name-tool.md)) 创建公钥/私钥对文件。</span><span class="sxs-lookup"><span data-stu-id="de4ea-111">Use the [Sn.exe (Strong Name Tool)][Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)) to create a public/private key pair file.</span></span>  
  
     <span data-ttu-id="de4ea-112">此文件的扩展名为 .snk。</span><span class="sxs-lookup"><span data-stu-id="de4ea-112">This file has a .snk extension.</span></span>  
  
2.  <span data-ttu-id="de4ea-113">从项目中删除生成错误的 COM 引用。</span><span class="sxs-lookup"><span data-stu-id="de4ea-113">Delete the COM reference that is generating the error from your project.</span></span>  
  
3.  <span data-ttu-id="de4ea-114">从 Windows**启动**菜单上，指向**程序**，指向**Microsoft Visual Studio 2008**，指向**Visual Studio Tools**，和然后单击**Visual Studio 2008 命令提示**。</span><span class="sxs-lookup"><span data-stu-id="de4ea-114">From the Windows **Start** menu, point to **Programs**, point to **Microsoft Visual Studio 2008**, point to **Visual Studio Tools**, and then click **Visual Studio 2008 Command Prompt**.</span></span>  
  
4.  <span data-ttu-id="de4ea-115">移动到要放置程序集包装的目录。</span><span class="sxs-lookup"><span data-stu-id="de4ea-115">Move to the directory where you want to place your assembly wrapper.</span></span>  
  
5.  <span data-ttu-id="de4ea-116">键入以下代码。</span><span class="sxs-lookup"><span data-stu-id="de4ea-116">Type the following code.</span></span>  
  
    ```  
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>  
    ```  
  
     <span data-ttu-id="de4ea-117">下面是你可能会输入的代码的示例。</span><span class="sxs-lookup"><span data-stu-id="de4ea-117">An example of the code you might enter would be the following.</span></span>  
  
    ```  
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"  
    ```  
  
     <span data-ttu-id="de4ea-118">如果路径或文件包含空格，则使用双引号 (")。</span><span class="sxs-lookup"><span data-stu-id="de4ea-118">Use double quotation marks (") if a path or file contains spaces.</span></span>  
  
6.  <span data-ttu-id="de4ea-119">在 Visual Studio 中，将添加到刚刚创建的文件的.NET 程序集引用。</span><span class="sxs-lookup"><span data-stu-id="de4ea-119">In Visual Studio, add a .NET Assembly reference to the file you just created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de4ea-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="de4ea-120">See Also</span></span>  
 
 <span data-ttu-id="de4ea-121">[Al.exe](../../../framework/tools/al-exe-assembly-linker.md)。</span><span class="sxs-lookup"><span data-stu-id="de4ea-121">[Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span></span>  
 <span data-ttu-id="de4ea-122">[Sn.exe （强名称工具）][Sn.exe （强名称工具）](../../../framework/tools/sn-exe-strong-name-tool.md))</span><span class="sxs-lookup"><span data-stu-id="de4ea-122">[Sn.exe (Strong Name Tool)][Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))</span></span>  
 [<span data-ttu-id="de4ea-123">如何：创建公钥/私钥对</span><span class="sxs-lookup"><span data-stu-id="de4ea-123">How to: Create a Public-Private Key Pair</span></span>](../../../framework/app-domains/how-to-create-a-public-private-key-pair.md)  
 [<span data-ttu-id="de4ea-124">与我们交流</span><span class="sxs-lookup"><span data-stu-id="de4ea-124">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)

---
title: 如何：设置 Visual Studio 命令行的环境变量
ms.date: 09/29/2017
f1_keywords:
- cs.build.commandline
helpviewer_keywords:
- csc.exe, command-line builds
- Visual C#, command-line builds
- command-line compilers, Visual C#
- Vsvars32.bat
- builds [C#], command-line
- compilers, invoking from command line
- Vcvars32.bat file
- command line [C#], building from
- Visual C# compiler, enabling
- compiling source code, from command line
ms.assetid: 7ec09480-5612-4f6a-8d00-ad90ea9bca5d
ms.openlocfilehash: ffc75a01230df078073f163c97a8c77229d3b2a1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54590872"
---
# <a name="how-to-set-environment-variables-for-the-visual-studio-command-line"></a><span data-ttu-id="58167-102">如何：设置 Visual Studio 命令行的环境变量</span><span class="sxs-lookup"><span data-stu-id="58167-102">How to: Set Environment Variables for the Visual Studio Command Line</span></span>

<span data-ttu-id="58167-103">VsDevCmd.bat 文件设置适当的环境变量来生成命令行。</span><span class="sxs-lookup"><span data-stu-id="58167-103">The VsDevCmd.bat file sets the appropriate environment variables to enable command-line builds.</span></span>

> [!NOTE]
> <span data-ttu-id="58167-104">VsDevCmd.bat 文件是一种通过 Visual Studio 2017 交付的新文件。</span><span class="sxs-lookup"><span data-stu-id="58167-104">The VsDevCmd.bat file is a new file delivered with Visual Studio 2017.</span></span> <span data-ttu-id="58167-105">Visual Studio 2015 及更早版本基于相同目的使用 VSVARS32.bat。</span><span class="sxs-lookup"><span data-stu-id="58167-105">Visual Studio 2015 and earlier versions used VSVARS32.bat for the same purpose.</span></span> <span data-ttu-id="58167-106">此文件保存在 \Program Files\Microsoft Visual Studio\\Version\Common7\Tools 或 Program Files (x86)\Microsoft Visual Studio\\Version\Common7\Tools。</span><span class="sxs-lookup"><span data-stu-id="58167-106">This file was stored in \Program Files\Microsoft Visual Studio\\*Version*\Common7\Tools or Program Files (x86)\Microsoft Visual Studio\\*Version*\Common7\Tools.</span></span>
  
<span data-ttu-id="58167-107">如果安装了 Visual Studio 当前版本的计算机上还安装有 Visual Studio 的早期版本，则不可在同一命令提示符窗口中运行不同版本的 VsDevCmd.bat 和 VSVARS32.BAT。</span><span class="sxs-lookup"><span data-stu-id="58167-107">If the current version of Visual Studio is installed on a computer that also has an earlier version of Visual Studio, you should not run VsDevCmd.bat and VSVARS32.BAT from different versions in the same Command Prompt window.</span></span> <span data-ttu-id="58167-108">转而应在其自身的窗口中运行各版本的命令。</span><span class="sxs-lookup"><span data-stu-id="58167-108">Instead, you should run the command for each version in its own window.</span></span>
  
### <a name="to-run-vsdevcmdbat"></a><span data-ttu-id="58167-109">若要运行 VsDevCmd.BAT</span><span class="sxs-lookup"><span data-stu-id="58167-109">To run VsDevCmd.BAT</span></span>  
  
1.  <span data-ttu-id="58167-110">从“开始”菜单，打开“VS 2017 开发人员命令提示”。</span><span class="sxs-lookup"><span data-stu-id="58167-110">From the **Start** menu, open the **Developer Command Prompt for VS 2017**.</span></span>  <span data-ttu-id="58167-111">该提示位于“Visual Studio 2017”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="58167-111">It's in the **Visual Studio 2017** folder.</span></span>
  
2.  <span data-ttu-id="58167-112">更改为安装目录的 \Program Files\Microsoft Visual Studio\\Version\\Offering\Common7\Tools 或 \Program Files (x86)\Microsoft Visual Studio\\Version\\Offering\Common7\Tools 子目录。</span><span class="sxs-lookup"><span data-stu-id="58167-112">Change to the \Program Files\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools or \Program Files (x86)\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools subdirectory of your installation.</span></span>  <span data-ttu-id="58167-113">（Version 为 2017，即当前版本。</span><span class="sxs-lookup"><span data-stu-id="58167-113">(*Version* is *2017* for the current version.</span></span> <span data-ttu-id="58167-114">Offering 是 Enterprise、Professional 或 Community。）</span><span class="sxs-lookup"><span data-stu-id="58167-114">*Offering* is one of *Enterprise*, *Professional* or *Community*.)</span></span>
  
3.  <span data-ttu-id="58167-115">通过键入“VsDevCmd”运行 VsDevCmd.bat。</span><span class="sxs-lookup"><span data-stu-id="58167-115">Run VsDevCmd.bat by typing **VsDevCmd**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="58167-116">VsDevCmd.bat 可能因计算机而异。</span><span class="sxs-lookup"><span data-stu-id="58167-116">VsDevCmd.bat can vary from computer to computer.</span></span> <span data-ttu-id="58167-117">请勿使用其他计算机上的 VsDevCmd.bat 替换缺失或损坏的 VsDevCmd.bat 文件。</span><span class="sxs-lookup"><span data-stu-id="58167-117">Do not replace a missing or damaged VsDevCmd.bat file with a VsDevCmd.bat from another computer.</span></span> <span data-ttu-id="58167-118">而是应重新运行安装程序以替换丢失的文件。</span><span class="sxs-lookup"><span data-stu-id="58167-118">Instead, rerun setup to replace the missing file.</span></span>  

### <a name="available-options-for-vsdevcmdbat"></a><span data-ttu-id="58167-119">适用于 VsDevCmd.BAT 的选项</span><span class="sxs-lookup"><span data-stu-id="58167-119">Available options for VsDevCmd.BAT</span></span>

<span data-ttu-id="58167-120">若要查看适用于 VsDevCmd.BAT 的选项，请运行以下包含 `-help` 选项的命令：</span><span class="sxs-lookup"><span data-stu-id="58167-120">To see the available options for VsDevCmd.BAT, run the command with the `-help` option:</span></span>
```console
VsDevCmd.bat -help
```

## <a name="see-also"></a><span data-ttu-id="58167-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="58167-121">See also</span></span>

- [<span data-ttu-id="58167-122">在命令行上使用 csc.exe 生成</span><span class="sxs-lookup"><span data-stu-id="58167-122">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)

---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: c57ed1699d110959e9faf3dc3d43bcc200851c1c
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005444"
---
# <a name="-noconfig"></a><span data-ttu-id="723f7-102">-noconfig</span><span class="sxs-lookup"><span data-stu-id="723f7-102">-noconfig</span></span>
<span data-ttu-id="723f7-103">指定编译器不应自动引用常用的 .NET Framework 程序集，也不会导入 @no__t 的命名空间和 @no__t。</span><span class="sxs-lookup"><span data-stu-id="723f7-103">Specifies that the compiler should not automatically reference the commonly used .NET Framework assemblies or import the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="723f7-104">语法</span><span class="sxs-lookup"><span data-stu-id="723f7-104">Syntax</span></span>  
  
```console  
-noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="723f7-105">备注</span><span class="sxs-lookup"><span data-stu-id="723f7-105">Remarks</span></span>  
 <span data-ttu-id="723f7-106">@No__t-0 选项告知编译器不要用 Vbc 文件（该文件位于 dcdiag.exe 文件所在的目录中）进行编译。</span><span class="sxs-lookup"><span data-stu-id="723f7-106">The `-noconfig` option tells the compiler not to compile with the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="723f7-107">Vbc 文件引用常用 .NET Framework 程序集，并导入 @no__t 和 @no__t 命名空间。</span><span class="sxs-lookup"><span data-stu-id="723f7-107">The Vbc.rsp file references the commonly used .NET Framework assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span> <span data-ttu-id="723f7-108">除非指定 `-nostdlib` 选项，否则编译器将隐式引用 System.object 程序集。</span><span class="sxs-lookup"><span data-stu-id="723f7-108">The compiler implicitly references the System.dll assembly unless the `-nostdlib` option is specified.</span></span> <span data-ttu-id="723f7-109">@No__t-0 选项指示编译器不能用 Vbc 进行编译或自动引用 System.object 程序集。</span><span class="sxs-lookup"><span data-stu-id="723f7-109">The `-nostdlib` option tells the compiler not to compile with Vbc.rsp or automatically reference the System.dll assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="723f7-110">Mscorlib 和 Microsoft. .dll 程序集始终被引用。</span><span class="sxs-lookup"><span data-stu-id="723f7-110">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
 <span data-ttu-id="723f7-111">您可以修改 Vbc 文件以指定应包括在每个 Vbc 编译中的其他编译器选项（指定 `-noconfig` 选项时除外）。</span><span class="sxs-lookup"><span data-stu-id="723f7-111">You can modify the Vbc.rsp file to specify additional compiler options that should be included in every Vbc.exe compilation (except when specifying the `-noconfig` option).</span></span> <span data-ttu-id="723f7-112">有关详细信息，请参阅 [@（指定响应文件）](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)。</span><span class="sxs-lookup"><span data-stu-id="723f7-112">For more information, see [@ (Specify Response File)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).</span></span>  
  
 <span data-ttu-id="723f7-113">编译器会处理最后传递到 `vbc` 命令的选项。</span><span class="sxs-lookup"><span data-stu-id="723f7-113">The compiler processes the options passed to the `vbc` command last.</span></span> <span data-ttu-id="723f7-114">因此，命令行上的任何选项都将覆盖 Vbc 文件中相同选项的设置。</span><span class="sxs-lookup"><span data-stu-id="723f7-114">Therefore, any option on the command line overrides the setting of the same option in the Vbc.rsp file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="723f7-115">在 Visual Studio 开发环境中，不能使用 `-noconfig` 选项;仅当从命令行进行编译时，它才可用。</span><span class="sxs-lookup"><span data-stu-id="723f7-115">The `-noconfig` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="723f7-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="723f7-116">See also</span></span>

- [<span data-ttu-id="723f7-117">-nostdlib （Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="723f7-117">-nostdlib (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/nostdlib.md)
- [<span data-ttu-id="723f7-118">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="723f7-118">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="723f7-119">@（指定响应文件）</span><span class="sxs-lookup"><span data-stu-id="723f7-119">@ (Specify Response File)</span></span>](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)
- [<span data-ttu-id="723f7-120">-reference （Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="723f7-120">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)

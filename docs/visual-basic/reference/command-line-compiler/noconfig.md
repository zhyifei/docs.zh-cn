---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: ca184fa130d62dc118d0de551ac58f3165064029
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964391"
---
# <a name="-noconfig"></a><span data-ttu-id="fe74c-102">-noconfig</span><span class="sxs-lookup"><span data-stu-id="fe74c-102">-noconfig</span></span>
<span data-ttu-id="fe74c-103">指定编译器不应自动引用常用 .NET Framework 程序集或导入`System`和`Microsoft.VisualBasic`命名空间。</span><span class="sxs-lookup"><span data-stu-id="fe74c-103">Specifies that the compiler should not automatically reference the commonly used .NET Framework assemblies or import the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe74c-104">语法</span><span class="sxs-lookup"><span data-stu-id="fe74c-104">Syntax</span></span>  
  
```  
-noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="fe74c-105">备注</span><span class="sxs-lookup"><span data-stu-id="fe74c-105">Remarks</span></span>  
 <span data-ttu-id="fe74c-106">`-noconfig`选项告诉编译器不要用 vbc 文件 (位于 dcdiag.exe 文件所在的目录中) 进行编译。</span><span class="sxs-lookup"><span data-stu-id="fe74c-106">The `-noconfig` option tells the compiler not to compile with the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="fe74c-107">Vbc 文件引用常用的 .NET Framework 程序集, 并导入`System`和`Microsoft.VisualBasic`命名空间。</span><span class="sxs-lookup"><span data-stu-id="fe74c-107">The Vbc.rsp file references the commonly used .NET Framework assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span> <span data-ttu-id="fe74c-108">除非指定了`-nostdlib`选项, 否则编译器将隐式引用 system.object 程序集。</span><span class="sxs-lookup"><span data-stu-id="fe74c-108">The compiler implicitly references the System.dll assembly unless the `-nostdlib` option is specified.</span></span> <span data-ttu-id="fe74c-109">`-nostdlib`选项告诉编译器不要用 Vbc 编译, 或自动引用 system.object 程序集。</span><span class="sxs-lookup"><span data-stu-id="fe74c-109">The `-nostdlib` option tells the compiler not to compile with Vbc.rsp or automatically reference the System.dll assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fe74c-110">Mscorlib 和 Microsoft. .dll 程序集始终被引用。</span><span class="sxs-lookup"><span data-stu-id="fe74c-110">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
 <span data-ttu-id="fe74c-111">您可以修改 vbc 文件以指定应包括在每个 Vbc 编译中的其他编译器选项 (指定`-noconfig`选项时除外)。</span><span class="sxs-lookup"><span data-stu-id="fe74c-111">You can modify the Vbc.rsp file to specify additional compiler options that should be included in every Vbc.exe compilation (except when specifying the `-noconfig` option).</span></span> <span data-ttu-id="fe74c-112">有关详细信息，请参阅 [@（指定响应文件）](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)。</span><span class="sxs-lookup"><span data-stu-id="fe74c-112">For more information, see [@ (Specify Response File)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).</span></span>  
  
 <span data-ttu-id="fe74c-113">编译器会处理最后传递给`vbc`命令的选项。</span><span class="sxs-lookup"><span data-stu-id="fe74c-113">The compiler processes the options passed to the `vbc` command last.</span></span> <span data-ttu-id="fe74c-114">因此, 命令行上的任何选项都将覆盖 Vbc 文件中相同选项的设置。</span><span class="sxs-lookup"><span data-stu-id="fe74c-114">Therefore, any option on the command line overrides the setting of the same option in the Vbc.rsp file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fe74c-115">此`-noconfig`选项在 Visual Studio 开发环境中不可用; 它仅在从命令行编译时可用。</span><span class="sxs-lookup"><span data-stu-id="fe74c-115">The `-noconfig` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe74c-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="fe74c-116">See also</span></span>

- [<span data-ttu-id="fe74c-117">-nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fe74c-117">-nostdlib (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/nostdlib.md)
- [<span data-ttu-id="fe74c-118">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="fe74c-118">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="fe74c-119">@（指定响应文件）</span><span class="sxs-lookup"><span data-stu-id="fe74c-119">@ (Specify Response File)</span></span>](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)
- [<span data-ttu-id="fe74c-120">-reference (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fe74c-120">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)

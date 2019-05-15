---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: b707899c845b6b08e008fe229497f682c930044a
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2019
ms.locfileid: "65588849"
---
# <a name="-noconfig"></a><span data-ttu-id="bbbfc-102">-noconfig</span><span class="sxs-lookup"><span data-stu-id="bbbfc-102">-noconfig</span></span>
<span data-ttu-id="bbbfc-103">指定编译器应不会自动引用常用的.NET Framework 程序集或导入`System`和`Microsoft.VisualBasic`命名空间。</span><span class="sxs-lookup"><span data-stu-id="bbbfc-103">Specifies that the compiler should not automatically reference the commonly used .NET Framework assemblies or import the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbbfc-104">语法</span><span class="sxs-lookup"><span data-stu-id="bbbfc-104">Syntax</span></span>  
  
```  
-noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="bbbfc-105">备注</span><span class="sxs-lookup"><span data-stu-id="bbbfc-105">Remarks</span></span>  
 <span data-ttu-id="bbbfc-106">`-noconfig`选项告知编译器不使用 Vbc.rsp 文件，位于 Vbc.exe 文件所在的同一目录中进行编译。</span><span class="sxs-lookup"><span data-stu-id="bbbfc-106">The `-noconfig` option tells the compiler not to compile with the Vbc.rsp file, which is located in the same directory as the Vbc.exe file.</span></span> <span data-ttu-id="bbbfc-107">Vbc.rsp 文件引用常用的.NET Framework 程序集并导入`System`和`Microsoft.VisualBasic`命名空间。</span><span class="sxs-lookup"><span data-stu-id="bbbfc-107">The Vbc.rsp file references the commonly used .NET Framework assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span> <span data-ttu-id="bbbfc-108">编译器隐式引用 System.dll 程序集，除非`-nostdlib`指定选项。</span><span class="sxs-lookup"><span data-stu-id="bbbfc-108">The compiler implicitly references the System.dll assembly unless the `-nostdlib` option is specified.</span></span> <span data-ttu-id="bbbfc-109">`-nostdlib`选项告知编译器不能使用 vbc.rsp 进行编译或自动引用 System.dll 程序集。</span><span class="sxs-lookup"><span data-stu-id="bbbfc-109">The `-nostdlib` option tells the compiler not to compile with Vbc.rsp or automatically reference the System.dll assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bbbfc-110">始终引用 Mscorlib.dll 和 Microsoft.VisualBasic.dll 的程序集。</span><span class="sxs-lookup"><span data-stu-id="bbbfc-110">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
 <span data-ttu-id="bbbfc-111">你可以修改 Vbc.rsp 文件以指定应包含每个 Vbc.exe 编译中的其他编译器选项 (除非指定`-noconfig`选项)。</span><span class="sxs-lookup"><span data-stu-id="bbbfc-111">You can modify the Vbc.rsp file to specify additional compiler options that should be included in every Vbc.exe compilation (except when specifying the `-noconfig` option).</span></span> <span data-ttu-id="bbbfc-112">有关详细信息，请参阅 [@（指定响应文件）](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)。</span><span class="sxs-lookup"><span data-stu-id="bbbfc-112">For more information, see [@ (Specify Response File)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).</span></span>  
  
 <span data-ttu-id="bbbfc-113">编译器选项传递给处理`vbc`最后一个命令。</span><span class="sxs-lookup"><span data-stu-id="bbbfc-113">The compiler processes the options passed to the `vbc` command last.</span></span> <span data-ttu-id="bbbfc-114">因此，命令行上的任何选项将替代的 Vbc.rsp 文件中的相同选项的设置。</span><span class="sxs-lookup"><span data-stu-id="bbbfc-114">Therefore, any option on the command line overrides the setting of the same option in the Vbc.rsp file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bbbfc-115">`-noconfig`选项不适用于从 Visual Studio 开发环境中，仅当从命令行编译时便可。</span><span class="sxs-lookup"><span data-stu-id="bbbfc-115">The `-noconfig` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbbfc-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="bbbfc-116">See also</span></span>

- [<span data-ttu-id="bbbfc-117">-nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bbbfc-117">-nostdlib (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/nostdlib.md)
- [<span data-ttu-id="bbbfc-118">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="bbbfc-118">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="bbbfc-119">@（指定响应文件）</span><span class="sxs-lookup"><span data-stu-id="bbbfc-119">@ (Specify Response File)</span></span>](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)
- [<span data-ttu-id="bbbfc-120">-参考 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bbbfc-120">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)

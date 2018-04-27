---
title: -sdkpath
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- sdkpath
- -sdkpath
helpviewer_keywords:
- -sdkpath compiler option [Visual Basic]
- /sdkpath compiler option [Visual Basic]
- sdkpath compiler option [Visual Basic]
ms.assetid: fec8a3f1-b791-4a37-8af7-344859f8212d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5a25755bcbb8d42124cde531f641a611202ae5a1
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="-sdkpath"></a><span data-ttu-id="76fa7-102">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="76fa7-102">-sdkpath</span></span>
<span data-ttu-id="76fa7-103">指定 mscorlib.dll 和 Microsoft.VisualBasic.dll 的位置。</span><span class="sxs-lookup"><span data-stu-id="76fa7-103">Specifies the location of mscorlib.dll and Microsoft.VisualBasic.dll.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76fa7-104">语法</span><span class="sxs-lookup"><span data-stu-id="76fa7-104">Syntax</span></span>  
  
```  
-sdkpath:path  
```  
  
## <a name="arguments"></a><span data-ttu-id="76fa7-105">自变量</span><span class="sxs-lookup"><span data-stu-id="76fa7-105">Arguments</span></span>  
 `path`  
 <span data-ttu-id="76fa7-106">包含的 mscorlib.dll 和 Microsoft.VisualBasic.dll 要用于编译的版本的目录。</span><span class="sxs-lookup"><span data-stu-id="76fa7-106">The directory containing the versions of mscorlib.dll and Microsoft.VisualBasic.dll to use for compilation.</span></span> <span data-ttu-id="76fa7-107">它加载之前，不会验证此路径。</span><span class="sxs-lookup"><span data-stu-id="76fa7-107">This path is not verified until it is loaded.</span></span> <span data-ttu-id="76fa7-108">将目录名称括在双引号 ("") 如果它包含空格。</span><span class="sxs-lookup"><span data-stu-id="76fa7-108">Enclose the directory name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="76fa7-109">备注</span><span class="sxs-lookup"><span data-stu-id="76fa7-109">Remarks</span></span>  
 <span data-ttu-id="76fa7-110">此选项通知 Visual Basic 编译器，以从非默认位置加载的 mscorlib.dll 和 Microsoft.VisualBasic.dll 文件。</span><span class="sxs-lookup"><span data-stu-id="76fa7-110">This option tells the Visual Basic compiler to load the mscorlib.dll and Microsoft.VisualBasic.dll files from a non-default location.</span></span> <span data-ttu-id="76fa7-111">`-sdkpath`选项旨在用于[-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)。</span><span class="sxs-lookup"><span data-stu-id="76fa7-111">The `-sdkpath` option was designed to be used with [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md).</span></span> <span data-ttu-id="76fa7-112">[!INCLUDE[Compact](~/includes/compact-md.md)]使用支持不同版本的这些库，以避免使用的类型和设备上未找到的语言功能。</span><span class="sxs-lookup"><span data-stu-id="76fa7-112">The [!INCLUDE[Compact](~/includes/compact-md.md)] uses different versions of these support libraries to avoid the use of types and language features not found on the devices.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="76fa7-113">`-sdkpath`选项不是可从 Visual Studio 开发环境中; 仅当从命令行进行编译时，它才可用。</span><span class="sxs-lookup"><span data-stu-id="76fa7-113">The `-sdkpath` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="76fa7-114">`-sdkpath`加载 Visual Basic 设备项目时，设置选项。</span><span class="sxs-lookup"><span data-stu-id="76fa7-114">The `-sdkpath` option is set when a Visual Basic device project is loaded.</span></span>  
  
 <span data-ttu-id="76fa7-115">你可以指定通过使用编译器应编译而无需对 Visual Basic 运行时库的引用`-vbruntime`编译器选项。</span><span class="sxs-lookup"><span data-stu-id="76fa7-115">You can specify that the compiler should compile without a reference to the Visual Basic Runtime Library by using the `-vbruntime` compiler option.</span></span> <span data-ttu-id="76fa7-116">有关详细信息，请参阅[-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)。</span><span class="sxs-lookup"><span data-stu-id="76fa7-116">For more information, see [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="76fa7-117">示例</span><span class="sxs-lookup"><span data-stu-id="76fa7-117">Example</span></span>  
 <span data-ttu-id="76fa7-118">下面的代码编译`Myfile.vb`与[!INCLUDE[Compact](~/includes/compact-md.md)]，使用版本的 Mscorlib.dll 和 Microsoft.VisualBasic.dll 的默认安装目录中找到[!INCLUDE[Compact](~/includes/compact-md.md)]C 驱动器上。</span><span class="sxs-lookup"><span data-stu-id="76fa7-118">The following code compiles `Myfile.vb` with the [!INCLUDE[Compact](~/includes/compact-md.md)], using the versions of Mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the [!INCLUDE[Compact](~/includes/compact-md.md)] on the C drive.</span></span> <span data-ttu-id="76fa7-119">通常情况下，将使用的最新版本[!INCLUDE[Compact](~/includes/compact-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="76fa7-119">Typically, you would use the most recent version of the [!INCLUDE[Compact](~/includes/compact-md.md)].</span></span>  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="76fa7-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="76fa7-120">See Also</span></span>  
 [<span data-ttu-id="76fa7-121">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="76fa7-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="76fa7-122">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="76fa7-122">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="76fa7-123">-netcf</span><span class="sxs-lookup"><span data-stu-id="76fa7-123">-netcf</span></span>](../../../visual-basic/reference/command-line-compiler/netcf.md)  
 [<span data-ttu-id="76fa7-124">-vbruntime</span><span class="sxs-lookup"><span data-stu-id="76fa7-124">-vbruntime</span></span>](../../../visual-basic/reference/command-line-compiler/vbruntime.md)

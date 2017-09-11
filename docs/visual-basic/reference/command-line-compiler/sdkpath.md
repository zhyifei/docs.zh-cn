---
title: "/sdkpath |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- sdkpath
- /sdkpath
dev_langs:
- VB
helpviewer_keywords:
- -sdkpath compiler option [Visual Basic]
- /sdkpath compiler option [Visual Basic]
- sdkpath compiler option [Visual Basic]
ms.assetid: fec8a3f1-b791-4a37-8af7-344859f8212d
caps.latest.revision: 15
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
ms.openlocfilehash: 2e32bb403347063edcf0d47fd4a7511a0da1f340
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="sdkpath"></a><span data-ttu-id="072bd-102">/sdkpath</span><span class="sxs-lookup"><span data-stu-id="072bd-102">/sdkpath</span></span>
<span data-ttu-id="072bd-103">指定 Mscorlib.dll 和 Microsoft.VisualBasic.dll 的位置。</span><span class="sxs-lookup"><span data-stu-id="072bd-103">Specifies the location of Mscorlib.dll and Microsoft.VisualBasic.dll.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="072bd-104">语法</span><span class="sxs-lookup"><span data-stu-id="072bd-104">Syntax</span></span>  
  
```  
/sdkpath:path  
```  
  
## <a name="arguments"></a><span data-ttu-id="072bd-105">参数</span><span class="sxs-lookup"><span data-stu-id="072bd-105">Arguments</span></span>  
 `path`  
 <span data-ttu-id="072bd-106">包含要用于编译的 Mscorlib.dll 和 Microsoft.VisualBasic.dll 的版本的目录。</span><span class="sxs-lookup"><span data-stu-id="072bd-106">The directory containing the versions of Mscorlib.dll and Microsoft.VisualBasic.dll to use for compilation.</span></span> <span data-ttu-id="072bd-107">它加载之前，不会验证此路径。</span><span class="sxs-lookup"><span data-stu-id="072bd-107">This path is not verified until it is loaded.</span></span> <span data-ttu-id="072bd-108">将目录名称括在双引号 ("") 如果包含空格。</span><span class="sxs-lookup"><span data-stu-id="072bd-108">Enclose the directory name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="072bd-109">备注</span><span class="sxs-lookup"><span data-stu-id="072bd-109">Remarks</span></span>  
 <span data-ttu-id="072bd-110">此选项可告知[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]编译器从非默认位置加载的 Mscorlib.dll 和 Microsoft.VisualBasic.dll 的文件。</span><span class="sxs-lookup"><span data-stu-id="072bd-110">This option tells the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler to load the Mscorlib.dll and Microsoft.VisualBasic.dll files from a non-default location.</span></span> <span data-ttu-id="072bd-111">`/sdkpath`选项旨在以用于其中[/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)。</span><span class="sxs-lookup"><span data-stu-id="072bd-111">The `/sdkpath` option was designed to be used with [/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md).</span></span> <span data-ttu-id="072bd-112">[!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)]使用支持不同版本的这些库来避免使用的类型和语言功能在设备上找不到。</span><span class="sxs-lookup"><span data-stu-id="072bd-112">The [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] uses different versions of these support libraries to avoid the use of types and language features not found on the devices.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="072bd-113">`/sdkpath`选项不是在 Visual Studio 开发环境中可用; 只有当从命令行进行编译，它才可用。</span><span class="sxs-lookup"><span data-stu-id="072bd-113">The `/sdkpath` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="072bd-114">`/sdkpath`会设置选项[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]加载设备项目。</span><span class="sxs-lookup"><span data-stu-id="072bd-114">The `/sdkpath` option is set when a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] device project is loaded.</span></span>  
  
 <span data-ttu-id="072bd-115">您可以指定通过使用编译器应编译而无需对 Visual Basic 运行库的引用`/vbruntime`编译器选项。</span><span class="sxs-lookup"><span data-stu-id="072bd-115">You can specify that the compiler should compile without a reference to the Visual Basic Runtime Library by using the `/vbruntime` compiler option.</span></span> <span data-ttu-id="072bd-116">有关详细信息，请参阅[/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)。</span><span class="sxs-lookup"><span data-stu-id="072bd-116">For more information, see [/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="072bd-117">示例</span><span class="sxs-lookup"><span data-stu-id="072bd-117">Example</span></span>  
 <span data-ttu-id="072bd-118">下面的代码编译`Myfile.vb`与[!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)]，使用版本的 Mscorlib.dll 和 Microsoft.VisualBasic.dll 的默认安装目录中找到[!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)]C 驱动器上。</span><span class="sxs-lookup"><span data-stu-id="072bd-118">The following code compiles `Myfile.vb` with the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)], using the versions of Mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] on the C drive.</span></span> <span data-ttu-id="072bd-119">通常情况下，将使用的最新版本[!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="072bd-119">Typically, you would use the most recent version of the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)].</span></span>  
  
```  
vbc /netcf /sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="072bd-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="072bd-120">See Also</span></span>  
 <span data-ttu-id="072bd-121">[Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="072bd-121">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="072bd-122"> [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="072bd-122"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="072bd-123"> [/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md) </span><span class="sxs-lookup"><span data-stu-id="072bd-123"> [/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md) </span></span>  
<span data-ttu-id="072bd-124"> [/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)</span><span class="sxs-lookup"><span data-stu-id="072bd-124"> [/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)</span></span>

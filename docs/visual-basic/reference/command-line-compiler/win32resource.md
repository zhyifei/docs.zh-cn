---
title: -win32resource
ms.date: 03/13/2018
f1_keywords:
- -win32resource
- win32resource
helpviewer_keywords:
- /win32resource compiler option [Visual Basic]
- -win32resource compiler option [Visual Basic]
- win32resource compiler option [Visual Basic]
ms.assetid: e226946d-19ce-4cc9-91f5-aed24f77aa2b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ac495e10be2ec1534dc9d9081aef369773d93e17
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="-win32resource"></a><span data-ttu-id="cae5b-102">-win32resource</span><span class="sxs-lookup"><span data-stu-id="cae5b-102">-win32resource</span></span>
<span data-ttu-id="cae5b-103">在输出文件中插入 Win32 资源文件。</span><span class="sxs-lookup"><span data-stu-id="cae5b-103">Inserts a Win32 resource file in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cae5b-104">语法</span><span class="sxs-lookup"><span data-stu-id="cae5b-104">Syntax</span></span>  
  
```  
-win32resource:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="cae5b-105">自变量</span><span class="sxs-lookup"><span data-stu-id="cae5b-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="cae5b-106">要添加到输出文件的资源文件的名称。</span><span class="sxs-lookup"><span data-stu-id="cae5b-106">The name of the resource file to add to your output file.</span></span> <span data-ttu-id="cae5b-107">将文件名括在双引号 ("") 如果它包含空格。</span><span class="sxs-lookup"><span data-stu-id="cae5b-107">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cae5b-108">备注</span><span class="sxs-lookup"><span data-stu-id="cae5b-108">Remarks</span></span>  
 <span data-ttu-id="cae5b-109">你可以使用 Microsoft Windows 资源编译器 (RC) 创建的 Win32 资源文件。</span><span class="sxs-lookup"><span data-stu-id="cae5b-109">You can create a Win32 resource file with the Microsoft Windows Resource Compiler (RC).</span></span>  
  
 <span data-ttu-id="cae5b-110">Win32 资源可以包含版本或位图 （图标） 信息，以帮助识别你的应用程序中**文件资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="cae5b-110">A Win32 resource can contain version or bitmap (icon) information that helps identify your application in **File Explorer**.</span></span> <span data-ttu-id="cae5b-111">如果不指定`-win32resource`，编译器将生成基于程序集版本的版本信息。</span><span class="sxs-lookup"><span data-stu-id="cae5b-111">If you do not specify `-win32resource`, the compiler generates version information based on the assembly version.</span></span> <span data-ttu-id="cae5b-112">`-win32resource`和`-win32icon`选项互斥。</span><span class="sxs-lookup"><span data-stu-id="cae5b-112">The `-win32resource` and `-win32icon` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="cae5b-113">请参阅[-linkresource (Visual Basic 中)](../../../visual-basic/reference/command-line-compiler/linkresource.md)引用[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]资源文件，或[-资源 (Visual Basic 中)](../../../visual-basic/reference/command-line-compiler/resource.md)附加[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]资源文件。</span><span class="sxs-lookup"><span data-stu-id="cae5b-113">See [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file, or [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] resource file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cae5b-114">`-win32resource`选项不是可从 Visual Studio 开发环境中; 仅当从命令行进行编译时，它才可用。</span><span class="sxs-lookup"><span data-stu-id="cae5b-114">The `-win32resource` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cae5b-115">示例</span><span class="sxs-lookup"><span data-stu-id="cae5b-115">Example</span></span>  
 <span data-ttu-id="cae5b-116">下面的代码编译`In.vb`，并将附加的 Win32 资源文件， `Rf.res`:</span><span class="sxs-lookup"><span data-stu-id="cae5b-116">The following code compiles `In.vb` and attaches a Win32 resource file, `Rf.res`:</span></span>  
  
```console  
vbc -win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="cae5b-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="cae5b-117">See Also</span></span>  
 [<span data-ttu-id="cae5b-118">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="cae5b-118">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="cae5b-119">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="cae5b-119">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

---
title: "/win32resource |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /win32resource
- win32resource
dev_langs:
- VB
helpviewer_keywords:
- /win32resource compiler option [Visual Basic]
- -win32resource compiler option [Visual Basic]
- win32resource compiler option [Visual Basic]
ms.assetid: e226946d-19ce-4cc9-91f5-aed24f77aa2b
caps.latest.revision: 13
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
ms.openlocfilehash: dc6bbb5948a5dd505f0fc4d1c8a86650214d657a
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="win32resource"></a><span data-ttu-id="8706a-102">/win32resource</span><span class="sxs-lookup"><span data-stu-id="8706a-102">/win32resource</span></span>
<span data-ttu-id="8706a-103">在输出文件中插入 Win32 资源文件。</span><span class="sxs-lookup"><span data-stu-id="8706a-103">Inserts a Win32 resource file in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8706a-104">语法</span><span class="sxs-lookup"><span data-stu-id="8706a-104">Syntax</span></span>  
  
```  
/win32resource:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="8706a-105">参数</span><span class="sxs-lookup"><span data-stu-id="8706a-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="8706a-106">要添加到输出文件的资源文件的名称。</span><span class="sxs-lookup"><span data-stu-id="8706a-106">The name of the resource file to add to your output file.</span></span> <span data-ttu-id="8706a-107">将文件名括在双引号 ("") 如果包含空格。</span><span class="sxs-lookup"><span data-stu-id="8706a-107">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8706a-108">备注</span><span class="sxs-lookup"><span data-stu-id="8706a-108">Remarks</span></span>  
 <span data-ttu-id="8706a-109">您可以创建 Win32 资源文件与 Microsoft Windows 资源编译器 (RC)。</span><span class="sxs-lookup"><span data-stu-id="8706a-109">You can create a Win32 resource file with the Microsoft Windows Resource Compiler (RC).</span></span>  
  
 <span data-ttu-id="8706a-110">Win32 资源可以包含版本或位图 （图标） 信息，以帮助标识应用程序中的**文件资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="8706a-110">A Win32 resource can contain version or bitmap (icon) information that helps identify your application in **File Explorer**.</span></span> <span data-ttu-id="8706a-111">如果未指定`/win32resource`，编译器将生成基于程序集版本的版本信息。</span><span class="sxs-lookup"><span data-stu-id="8706a-111">If you do not specify `/win32resource`, the compiler generates version information based on the assembly version.</span></span> <span data-ttu-id="8706a-112">`/win32resource`和`/win32icon`是互相排斥的选项。</span><span class="sxs-lookup"><span data-stu-id="8706a-112">The `/win32resource` and `/win32icon` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="8706a-113">请参阅[/linkresource (Visual Basic 中)](../../../visual-basic/reference/command-line-compiler/linkresource.md)引用[!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]资源文件或[/resource (Visual Basic 中)](../../../visual-basic/reference/command-line-compiler/resource.md)附加[!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]资源文件。</span><span class="sxs-lookup"><span data-stu-id="8706a-113">See [/linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] resource file, or [/resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] resource file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8706a-114">`/win32resource`选项不是在 Visual Studio 开发环境中可用; 只有当从命令行进行编译，它才可用。</span><span class="sxs-lookup"><span data-stu-id="8706a-114">The `/win32resource` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8706a-115">示例</span><span class="sxs-lookup"><span data-stu-id="8706a-115">Example</span></span>  
 <span data-ttu-id="8706a-116">下面的代码编译`In.vb`，并将附加 Win32 资源文件， `Rf.res`:</span><span class="sxs-lookup"><span data-stu-id="8706a-116">The following code compiles `In.vb` and attaches a Win32 resource file, `Rf.res`:</span></span>  
  
```  
vbc /win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="8706a-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8706a-117">See Also</span></span>  
 <span data-ttu-id="8706a-118">[Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="8706a-118">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="8706a-119"> [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="8706a-119"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>

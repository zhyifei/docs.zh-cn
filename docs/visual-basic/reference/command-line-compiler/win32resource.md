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
ms.openlocfilehash: cee06adec89aac4b3e3f170df3bf932e466f3070
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004961"
---
# <a name="-win32resource"></a><span data-ttu-id="19d75-102">-win32resource</span><span class="sxs-lookup"><span data-stu-id="19d75-102">-win32resource</span></span>
<span data-ttu-id="19d75-103">将 Win32 资源文件插入到输出文件中。</span><span class="sxs-lookup"><span data-stu-id="19d75-103">Inserts a Win32 resource file in the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19d75-104">语法</span><span class="sxs-lookup"><span data-stu-id="19d75-104">Syntax</span></span>  
  
```console  
-win32resource:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="19d75-105">参数</span><span class="sxs-lookup"><span data-stu-id="19d75-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="19d75-106">要添加到输出文件的资源文件的名称。</span><span class="sxs-lookup"><span data-stu-id="19d75-106">The name of the resource file to add to your output file.</span></span> <span data-ttu-id="19d75-107">如果文件名包含空格，请将文件名用引号（""）引起来。</span><span class="sxs-lookup"><span data-stu-id="19d75-107">Enclose the file name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19d75-108">备注</span><span class="sxs-lookup"><span data-stu-id="19d75-108">Remarks</span></span>  
 <span data-ttu-id="19d75-109">您可以使用 Microsoft Windows 资源编译器（RC）创建 Win32 资源文件。</span><span class="sxs-lookup"><span data-stu-id="19d75-109">You can create a Win32 resource file with the Microsoft Windows Resource Compiler (RC).</span></span>  
  
 <span data-ttu-id="19d75-110">Win32 资源可以包含版本或位图（图标）信息，这些信息有助于在**文件资源管理器**中标识您的应用程序。</span><span class="sxs-lookup"><span data-stu-id="19d75-110">A Win32 resource can contain version or bitmap (icon) information that helps identify your application in **File Explorer**.</span></span> <span data-ttu-id="19d75-111">如果不指定 `-win32resource`，编译器将根据程序集版本生成版本信息。</span><span class="sxs-lookup"><span data-stu-id="19d75-111">If you do not specify `-win32resource`, the compiler generates version information based on the assembly version.</span></span> <span data-ttu-id="19d75-112">@No__t 0 和 @no__t 选项是互斥的。</span><span class="sxs-lookup"><span data-stu-id="19d75-112">The `-win32resource` and `-win32icon` options are mutually exclusive.</span></span>  
  
 <span data-ttu-id="19d75-113">请参阅[-linkresource （Visual Basic）](../../../visual-basic/reference/command-line-compiler/linkresource.md)以引用 .NET Framework 资源文件或[-resource （Visual Basic）](../../../visual-basic/reference/command-line-compiler/resource.md)来附加 .NET Framework 资源文件。</span><span class="sxs-lookup"><span data-stu-id="19d75-113">See [-linkresource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/linkresource.md) to reference a .NET Framework resource file, or [-resource (Visual Basic)](../../../visual-basic/reference/command-line-compiler/resource.md) to attach a .NET Framework resource file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="19d75-114">在 Visual Studio 开发环境中，不能使用 `-win32resource` 选项;仅当从命令行进行编译时，它才可用。</span><span class="sxs-lookup"><span data-stu-id="19d75-114">The `-win32resource` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19d75-115">示例</span><span class="sxs-lookup"><span data-stu-id="19d75-115">Example</span></span>  
 <span data-ttu-id="19d75-116">下面的代码编译 `In.vb` 并附加 Win32 资源文件，`Rf.res`：</span><span class="sxs-lookup"><span data-stu-id="19d75-116">The following code compiles `In.vb` and attaches a Win32 resource file, `Rf.res`:</span></span>  
  
```console  
vbc -win32resource:rf.res in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="19d75-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="19d75-117">See also</span></span>

- [<span data-ttu-id="19d75-118">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="19d75-118">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="19d75-119">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="19d75-119">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

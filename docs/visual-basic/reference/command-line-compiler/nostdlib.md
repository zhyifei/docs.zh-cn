---
title: -nostdlib
ms.date: 03/13/2018
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
ms.openlocfilehash: db6b047f521d8ef44d2bd1b70b654a4233ebb1a7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347916"
---
# <a name="-nostdlib-visual-basic"></a><span data-ttu-id="95b8b-102">-nostdlib （Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="95b8b-102">-nostdlib (Visual Basic)</span></span>
<span data-ttu-id="95b8b-103">导致编译器不自动引用标准库。</span><span class="sxs-lookup"><span data-stu-id="95b8b-103">Causes the compiler not to automatically reference the standard libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95b8b-104">语法</span><span class="sxs-lookup"><span data-stu-id="95b8b-104">Syntax</span></span>  
  
```console  
-nostdlib  
```  
  
## <a name="remarks"></a><span data-ttu-id="95b8b-105">备注</span><span class="sxs-lookup"><span data-stu-id="95b8b-105">Remarks</span></span>  
 <span data-ttu-id="95b8b-106">`-nostdlib` 选项删除对 System.web 程序集的自动引用，并阻止编译器读取 Vbc 文件。</span><span class="sxs-lookup"><span data-stu-id="95b8b-106">The `-nostdlib` option removes the automatic reference to the System.dll assembly and prevents the compiler from reading the Vbc.rsp file.</span></span> <span data-ttu-id="95b8b-107">Dcdiag.exe 文件与 dcdiag.exe 文件位于同一个目录中，引用常用 .NET Framework 程序集并导入 `System` 和 `Microsoft.VisualBasic` 命名空间。</span><span class="sxs-lookup"><span data-stu-id="95b8b-107">The Vbc.rsp file, which is located in the same directory as the Vbc.exe file, references the commonly used .NET Framework assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="95b8b-108">Mscorlib 和 Microsoft. .dll 程序集始终被引用。</span><span class="sxs-lookup"><span data-stu-id="95b8b-108">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="95b8b-109">`-nostdlib` 选项在 Visual Studio 开发环境中不可用;仅当从命令行进行编译时，它才可用。</span><span class="sxs-lookup"><span data-stu-id="95b8b-109">The `-nostdlib` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="95b8b-110">示例</span><span class="sxs-lookup"><span data-stu-id="95b8b-110">Example</span></span>  
 <span data-ttu-id="95b8b-111">下面的代码编译 `T2.vb`，而不引用标准库。</span><span class="sxs-lookup"><span data-stu-id="95b8b-111">The following code compiles `T2.vb` without referencing the standard libraries.</span></span> <span data-ttu-id="95b8b-112">必须将 `_MYTYPE` 条件编译常量设置为字符串 "Empty" 以删除 `My` 对象。</span><span class="sxs-lookup"><span data-stu-id="95b8b-112">You must set the `_MYTYPE` conditional-compilation constant to the string "Empty" to remove the `My` object.</span></span>  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="95b8b-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="95b8b-113">See also</span></span>

- [<span data-ttu-id="95b8b-114">-noconfig</span><span class="sxs-lookup"><span data-stu-id="95b8b-114">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [<span data-ttu-id="95b8b-115">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="95b8b-115">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="95b8b-116">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="95b8b-116">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="95b8b-117">自定义 My 中可用的对象</span><span class="sxs-lookup"><span data-stu-id="95b8b-117">Customizing Which Objects are Available in My</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)

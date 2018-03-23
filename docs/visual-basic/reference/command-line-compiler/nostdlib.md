---
title: -nostdlib (Visual Basic)
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- nostdlib compiler option [Visual Basic]
- -nostdlib compiler option [Visual Basic]
- /nostdlib compiler option [Visual Basic]
ms.assetid: 140381b8-dc96-4ad5-ae11-792c9ed0be4d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 14361c01d13238db8f820b43889716e2528097f5
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2018
---
# <a name="-nostdlib-visual-basic"></a><span data-ttu-id="26aa3-102">-nostdlib (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="26aa3-102">-nostdlib (Visual Basic)</span></span>
<span data-ttu-id="26aa3-103">使编译器不会自动引用标准库。</span><span class="sxs-lookup"><span data-stu-id="26aa3-103">Causes the compiler not to automatically reference the standard libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26aa3-104">语法</span><span class="sxs-lookup"><span data-stu-id="26aa3-104">Syntax</span></span>  
  
```  
-nostdlib  
```  
  
## <a name="remarks"></a><span data-ttu-id="26aa3-105">备注</span><span class="sxs-lookup"><span data-stu-id="26aa3-105">Remarks</span></span>  
 <span data-ttu-id="26aa3-106">`-nostdlib`选项中移除自动对 System.dll 程序集引用，可防止编译器读取 Vbc.rsp 文件。</span><span class="sxs-lookup"><span data-stu-id="26aa3-106">The `-nostdlib` option removes the automatic reference to the System.dll assembly and prevents the compiler from reading the Vbc.rsp file.</span></span> <span data-ttu-id="26aa3-107">Vbc.rsp 文件，它位于 Vbc.exe 文件所在的同一目录中，引用常用[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]程序集和导入`System`和`Microsoft.VisualBasic`命名空间。</span><span class="sxs-lookup"><span data-stu-id="26aa3-107">The Vbc.rsp file, which is located in the same directory as the Vbc.exe file, references the commonly used [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies and imports the `System` and `Microsoft.VisualBasic` namespaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="26aa3-108">始终引用 Mscorlib.dll 和 Microsoft.VisualBasic.dll 的程序集。</span><span class="sxs-lookup"><span data-stu-id="26aa3-108">The Mscorlib.dll and Microsoft.VisualBasic.dll assemblies are always referenced.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="26aa3-109">`-nostdlib`选项不是可从 Visual Studio 开发环境中; 仅当从命令行进行编译时，它才可用。</span><span class="sxs-lookup"><span data-stu-id="26aa3-109">The `-nostdlib` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26aa3-110">示例</span><span class="sxs-lookup"><span data-stu-id="26aa3-110">Example</span></span>  
 <span data-ttu-id="26aa3-111">下面的代码编译`T2.vb`而不引用标准库。</span><span class="sxs-lookup"><span data-stu-id="26aa3-111">The following code compiles `T2.vb` without referencing the standard libraries.</span></span> <span data-ttu-id="26aa3-112">必须设置`_MYTYPE`条件编译常量为字符串"Empty"，以删除`My`对象。</span><span class="sxs-lookup"><span data-stu-id="26aa3-112">You must set the `_MYTYPE` conditional-compilation constant to the string "Empty" to remove the `My` object.</span></span>  
  
```console
vbc -nostdlib -define:_MYTYPE=\"Empty\" T2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="26aa3-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="26aa3-113">See Also</span></span>  
 [<span data-ttu-id="26aa3-114">-noconfig</span><span class="sxs-lookup"><span data-stu-id="26aa3-114">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)  
 [<span data-ttu-id="26aa3-115">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="26aa3-115">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="26aa3-116">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="26aa3-116">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="26aa3-117">自定义 My 中可用的对象</span><span class="sxs-lookup"><span data-stu-id="26aa3-117">Customizing Which Objects are Available in My</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)

---
title: "/keyfile |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
caps.latest.revision: 17
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
ms.openlocfilehash: ec63fd990b8524bbc212a33714ec8380a8c99f32
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="keyfile"></a><span data-ttu-id="f6b0f-102">/keyfile</span><span class="sxs-lookup"><span data-stu-id="f6b0f-102">/keyfile</span></span>
<span data-ttu-id="f6b0f-103">指定包含密钥或密钥对的文件从而为程序集赋予强名称。</span><span class="sxs-lookup"><span data-stu-id="f6b0f-103">Specifies a file containing a key or key pair to give an assembly a strong name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6b0f-104">语法</span><span class="sxs-lookup"><span data-stu-id="f6b0f-104">Syntax</span></span>  
  
```  
/keyfile:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="f6b0f-105">参数</span><span class="sxs-lookup"><span data-stu-id="f6b0f-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="f6b0f-106">必需。</span><span class="sxs-lookup"><span data-stu-id="f6b0f-106">Required.</span></span> <span data-ttu-id="f6b0f-107">包含密钥的文件。</span><span class="sxs-lookup"><span data-stu-id="f6b0f-107">File that contains the key.</span></span> <span data-ttu-id="f6b0f-108">如果文件名包含空格，则将名称括在双引号 ("")。</span><span class="sxs-lookup"><span data-stu-id="f6b0f-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6b0f-109">备注</span><span class="sxs-lookup"><span data-stu-id="f6b0f-109">Remarks</span></span>  
 <span data-ttu-id="f6b0f-110">编译器将公钥插入程序集清单，然后使用私钥对最终程序集进行签名。</span><span class="sxs-lookup"><span data-stu-id="f6b0f-110">The compiler inserts the public key into the assembly manifest and then signs the final assembly with the private key.</span></span> <span data-ttu-id="f6b0f-111">若要生成的密钥文件，请键入`sn -k file`在命令行。</span><span class="sxs-lookup"><span data-stu-id="f6b0f-111">To generate a key file, type `sn -k file` at the command line.</span></span> <span data-ttu-id="f6b0f-112">有关详细信息，请参阅 [Sn.exe （强名称工具）](https://msdn.microsoft.com/library/k5b5tt23)。</span><span class="sxs-lookup"><span data-stu-id="f6b0f-112">For more information, see [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23).</span></span>  
  
 <span data-ttu-id="f6b0f-113">如果在编译时使用`/target:module`，保存在模块和合并到编译为程序集时创建的程序集密钥文件的名称[/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)。</span><span class="sxs-lookup"><span data-stu-id="f6b0f-113">If you compile with `/target:module`, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span></span>  
  
 <span data-ttu-id="f6b0f-114">此外可以将您的加密信息传递给编译器[/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)。</span><span class="sxs-lookup"><span data-stu-id="f6b0f-114">You can also pass your encryption information to the compiler with [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span></span> <span data-ttu-id="f6b0f-115">使用[/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md)如果希望部分签名的程序集。</span><span class="sxs-lookup"><span data-stu-id="f6b0f-115">Use [/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="f6b0f-116">您还可以通过以下方式指定此选项的自定义特性 (<xref:System.Reflection.AssemblyKeyFileAttribute>) 中的任何 Microsoft 中间语言模块的源代码。</xref:System.Reflection.AssemblyKeyFileAttribute></span><span class="sxs-lookup"><span data-stu-id="f6b0f-116">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyFileAttribute>) in the source code for any Microsoft intermediate language module.</span></span>  
  
 <span data-ttu-id="f6b0f-117">两者`/keyfile`和[/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)指定 （通过命令行选项或通过自定义特性） 在同一编译中，编译器将第一次尝试的密钥容器。</span><span class="sxs-lookup"><span data-stu-id="f6b0f-117">In case both `/keyfile` and [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) are specified (either by command-line option or by custom attribute) in the same compilation, the compiler first tries the key container.</span></span> <span data-ttu-id="f6b0f-118">如果成功，则会将该程序集签名的密钥容器中的信息。</span><span class="sxs-lookup"><span data-stu-id="f6b0f-118">If that succeeds, then the assembly is signed with the information in the key container.</span></span> <span data-ttu-id="f6b0f-119">如果编译器没有找到密钥容器，它将尝试使用指定的文件`/keyfile`。</span><span class="sxs-lookup"><span data-stu-id="f6b0f-119">If the compiler does not find the key container, it tries the file specified with `/keyfile`.</span></span> <span data-ttu-id="f6b0f-120">如果此操作成功，则使用密钥文件中的信息签名程序集密钥信息安装到密钥容器中 (类似于`sn -i`)，以便在下一步的编译中，密钥的容器才有效。</span><span class="sxs-lookup"><span data-stu-id="f6b0f-120">If this succeeds, the assembly is signed with the information in the key file, and the key information is installed in the key container (similar to `sn -i`) so that on the next compilation, the key container will be valid.</span></span>  
  
 <span data-ttu-id="f6b0f-121">请注意，一个密钥文件可能包含仅将公钥。</span><span class="sxs-lookup"><span data-stu-id="f6b0f-121">Note that a key file might contain only the public key.</span></span>  
  
 <span data-ttu-id="f6b0f-122">请参阅[创建和使用具有强名称程序集](https://msdn.microsoft.com/library/xwb8f617)有关程序集进行签名的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f6b0f-122">See [Creating and Using Strong-Named Assemblies](https://msdn.microsoft.com/library/xwb8f617) for more information on signing an assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f6b0f-123">`/keyfile`选项不是可从[!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]开发环境中; 只有当从命令行进行编译，它才可用。</span><span class="sxs-lookup"><span data-stu-id="f6b0f-123">The `/keyfile` option is not available from within the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6b0f-124">示例</span><span class="sxs-lookup"><span data-stu-id="f6b0f-124">Example</span></span>  
 <span data-ttu-id="f6b0f-125">下面的代码编译源文件`Input.vb`和指定的密钥文件。</span><span class="sxs-lookup"><span data-stu-id="f6b0f-125">The following code compiles source file `Input.vb` and specifies a key file.</span></span>  
  
```  
vbc /keyfile:myfile.sn input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="f6b0f-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f6b0f-126">See Also</span></span>  
 <span data-ttu-id="f6b0f-127">[程序集和全局程序集缓存](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="f6b0f-127">[Assemblies and the Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="f6b0f-128"> [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="f6b0f-128"> [Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="f6b0f-129"> [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) </span><span class="sxs-lookup"><span data-stu-id="f6b0f-129"> [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) </span></span>  
<span data-ttu-id="f6b0f-130"> [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="f6b0f-130"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>

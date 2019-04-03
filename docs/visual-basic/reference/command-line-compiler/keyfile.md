---
title: -keyfile
ms.date: 03/10/2018
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
ms.openlocfilehash: c13f34c23cad9c909c2c5bd3447f1a8fa53f9b4d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58833295"
---
# <a name="-keyfile"></a><span data-ttu-id="5bdfd-102">-keyfile</span><span class="sxs-lookup"><span data-stu-id="5bdfd-102">-keyfile</span></span>
<span data-ttu-id="5bdfd-103">指定包含密钥或密钥对的文件从而为程序集赋予强名称。</span><span class="sxs-lookup"><span data-stu-id="5bdfd-103">Specifies a file containing a key or key pair to give an assembly a strong name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bdfd-104">语法</span><span class="sxs-lookup"><span data-stu-id="5bdfd-104">Syntax</span></span>  
  
``` 
-keyfile:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="5bdfd-105">自变量</span><span class="sxs-lookup"><span data-stu-id="5bdfd-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="5bdfd-106">必需。</span><span class="sxs-lookup"><span data-stu-id="5bdfd-106">Required.</span></span> <span data-ttu-id="5bdfd-107">包含密钥的文件。</span><span class="sxs-lookup"><span data-stu-id="5bdfd-107">File that contains the key.</span></span> <span data-ttu-id="5bdfd-108">如果文件名包含空格，将名称括在引号 ("")。</span><span class="sxs-lookup"><span data-stu-id="5bdfd-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5bdfd-109">备注</span><span class="sxs-lookup"><span data-stu-id="5bdfd-109">Remarks</span></span>  
 <span data-ttu-id="5bdfd-110">编译器将公钥插入到程序集清单，并使用私钥对进行签名最终程序集。</span><span class="sxs-lookup"><span data-stu-id="5bdfd-110">The compiler inserts the public key into the assembly manifest and then signs the final assembly with the private key.</span></span> <span data-ttu-id="5bdfd-111">若要生成密钥文件，请在命令行键入 `sn -k file`。</span><span class="sxs-lookup"><span data-stu-id="5bdfd-111">To generate a key file, type `sn -k file` at the command line.</span></span> <span data-ttu-id="5bdfd-112">有关详细信息，请参阅[Sn.exe （强名称工具）](../../../framework/tools/sn-exe-strong-name-tool.md))。</span><span class="sxs-lookup"><span data-stu-id="5bdfd-112">For more information, see [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span></span>  
  
 <span data-ttu-id="5bdfd-113">如果使用编译`-target:module`，保存在模块和合并到编译为程序集时创建的程序集密钥文件的名称[/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)。</span><span class="sxs-lookup"><span data-stu-id="5bdfd-113">If you compile with `-target:module`, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span></span>  
  
 <span data-ttu-id="5bdfd-114">也可以使用 [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) 将加密信息传递给编译器。</span><span class="sxs-lookup"><span data-stu-id="5bdfd-114">You can also pass your encryption information to the compiler with [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span></span> <span data-ttu-id="5bdfd-115">如果需要部分签名的程序集，请使用 [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md)。</span><span class="sxs-lookup"><span data-stu-id="5bdfd-115">Use [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="5bdfd-116">此外可以指定此选项的自定义特性 (<xref:System.Reflection.AssemblyKeyFileAttribute>) 为 Microsoft 中间语言的任何模块的源代码中。</span><span class="sxs-lookup"><span data-stu-id="5bdfd-116">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyFileAttribute>) in the source code for any Microsoft intermediate language module.</span></span>  
  
 <span data-ttu-id="5bdfd-117">两者`-keyfile`并[-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) （通过命令行选项或通过自定义特性） 中指定在同一编译中，编译器将首先尝试密钥容器。</span><span class="sxs-lookup"><span data-stu-id="5bdfd-117">In case both `-keyfile` and [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) are specified (either by command-line option or by custom attribute) in the same compilation, the compiler first tries the key container.</span></span> <span data-ttu-id="5bdfd-118">如果成功，则使用密钥容器中的信息对程序集签名。</span><span class="sxs-lookup"><span data-stu-id="5bdfd-118">If that succeeds, then the assembly is signed with the information in the key container.</span></span> <span data-ttu-id="5bdfd-119">如果编译器没有找到密钥容器，它将尝试用指定的文件`-keyfile`。</span><span class="sxs-lookup"><span data-stu-id="5bdfd-119">If the compiler does not find the key container, it tries the file specified with `-keyfile`.</span></span> <span data-ttu-id="5bdfd-120">如果此操作成功、 使用密钥文件中的信息签名程序集和密钥信息安装到密钥容器中 (类似于`sn -i`)，以便下一次编译中，密钥容器将有效。</span><span class="sxs-lookup"><span data-stu-id="5bdfd-120">If this succeeds, the assembly is signed with the information in the key file, and the key information is installed in the key container (similar to `sn -i`) so that on the next compilation, the key container will be valid.</span></span>  
  
 <span data-ttu-id="5bdfd-121">请注意，密钥文件可能仅包含公钥。</span><span class="sxs-lookup"><span data-stu-id="5bdfd-121">Note that a key file might contain only the public key.</span></span>  
  
 <span data-ttu-id="5bdfd-122">请参阅[创建和使用具有强名称程序集](../../../framework/app-domains/create-and-use-strong-named-assemblies.md)有关为程序集签名的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5bdfd-122">See [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) for more information on signing an assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5bdfd-123">`-keyfile`选项不适用于从 Visual Studio 开发环境中，仅当从命令行编译时便可。</span><span class="sxs-lookup"><span data-stu-id="5bdfd-123">The `-keyfile` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5bdfd-124">示例</span><span class="sxs-lookup"><span data-stu-id="5bdfd-124">Example</span></span>  
 <span data-ttu-id="5bdfd-125">下面的代码编译源文件`Input.vb`，并指定密钥文件。</span><span class="sxs-lookup"><span data-stu-id="5bdfd-125">The following code compiles source file `Input.vb` and specifies a key file.</span></span>  
  
```console  
vbc -keyfile:myfile.sn input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="5bdfd-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="5bdfd-126">See also</span></span>

- [<span data-ttu-id="5bdfd-127">.NET 中的程序集</span><span class="sxs-lookup"><span data-stu-id="5bdfd-127">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="5bdfd-128">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="5bdfd-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="5bdfd-129">-参考 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5bdfd-129">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="5bdfd-130">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="5bdfd-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

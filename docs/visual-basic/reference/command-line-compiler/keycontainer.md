---
title: -keycontainer
ms.date: 03/10/2018
helpviewer_keywords:
- -keycontainer compiler option [Visual Basic]
- keycontainer compiler option [Visual Basic]
- /keycontainer compiler option [Visual Basic]
ms.assetid: 6a9bc861-1752-4db1-9f64-b5252f0482cc
ms.openlocfilehash: 18aa82610d337354647a74d2f4ebe768925e2de0
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "56746346"
---
# <a name="-keycontainer"></a><span data-ttu-id="e86cf-102">-keycontainer</span><span class="sxs-lookup"><span data-stu-id="e86cf-102">-keycontainer</span></span>
<span data-ttu-id="e86cf-103">指定密钥对的密钥容器名称从而为程序集赋予强名称。</span><span class="sxs-lookup"><span data-stu-id="e86cf-103">Specifies a key container name for a key pair to give an assembly a strong name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e86cf-104">语法</span><span class="sxs-lookup"><span data-stu-id="e86cf-104">Syntax</span></span>  
  
```  
-keycontainer:container  
```  
  
## <a name="arguments"></a><span data-ttu-id="e86cf-105">自变量</span><span class="sxs-lookup"><span data-stu-id="e86cf-105">Arguments</span></span>  
  
|<span data-ttu-id="e86cf-106">术语</span><span class="sxs-lookup"><span data-stu-id="e86cf-106">Term</span></span>|<span data-ttu-id="e86cf-107">定义</span><span class="sxs-lookup"><span data-stu-id="e86cf-107">Definition</span></span>|  
|---|---|  
|`container`|<span data-ttu-id="e86cf-108">必需。</span><span class="sxs-lookup"><span data-stu-id="e86cf-108">Required.</span></span> <span data-ttu-id="e86cf-109">包含密钥的容器文件。</span><span class="sxs-lookup"><span data-stu-id="e86cf-109">Container file that contains the key.</span></span> <span data-ttu-id="e86cf-110">将文件名括在引号 ("") 如果名称包含空格。</span><span class="sxs-lookup"><span data-stu-id="e86cf-110">Enclose the file name in quotation marks ("") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e86cf-111">备注</span><span class="sxs-lookup"><span data-stu-id="e86cf-111">Remarks</span></span>  
 <span data-ttu-id="e86cf-112">通过将公钥插入到程序集清单，并使用私钥签名最终程序集，编译器创建可共享的组件。</span><span class="sxs-lookup"><span data-stu-id="e86cf-112">The compiler creates the sharable component by inserting a public key into the assembly manifest and by signing the final assembly with the private key.</span></span> <span data-ttu-id="e86cf-113">若要生成密钥文件，请在命令行键入 `sn -k file`。</span><span class="sxs-lookup"><span data-stu-id="e86cf-113">To generate a key file, type `sn -k file` at the command line.</span></span> <span data-ttu-id="e86cf-114">`-i`选项将密钥对安装到容器。</span><span class="sxs-lookup"><span data-stu-id="e86cf-114">The `-i` option installs the key pair into a container.</span></span> <span data-ttu-id="e86cf-115">有关详细信息，请参阅[Sn.exe （强名称工具）](../../../framework/tools/sn-exe-strong-name-tool.md))。</span><span class="sxs-lookup"><span data-stu-id="e86cf-115">For more information, see [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span></span>  
  
 <span data-ttu-id="e86cf-116">如果使用编译`-target:module`，保存在模块和合并到编译为程序集时创建的程序集密钥文件的名称[-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)。</span><span class="sxs-lookup"><span data-stu-id="e86cf-116">If you compile with `-target:module`, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span></span>  
  
 <span data-ttu-id="e86cf-117">还可以将此选项指定为任何 Microsoft 中间语言 (MSIL) 模块的源代码中的自定义特性 (<xref:System.Reflection.AssemblyKeyNameAttribute>)。</span><span class="sxs-lookup"><span data-stu-id="e86cf-117">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyNameAttribute>) in the source code for any Microsoft intermediate language (MSIL) module.</span></span>  
  
 <span data-ttu-id="e86cf-118">此外，可使用 [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) 将加密信息传递给编译器。</span><span class="sxs-lookup"><span data-stu-id="e86cf-118">You can also pass your encryption information to the compiler with [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md).</span></span> <span data-ttu-id="e86cf-119">如果需要部分签名的程序集，请使用 [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md)。</span><span class="sxs-lookup"><span data-stu-id="e86cf-119">Use [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="e86cf-120">请参阅[创建和使用具有强名称程序集](../../../framework/app-domains/create-and-use-strong-named-assemblies.md)有关为程序集签名的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e86cf-120">See [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) for more information on signing an assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e86cf-121">`-keycontainer`选项不适用于从 Visual Studio 开发环境中，仅当从命令行编译时便可。</span><span class="sxs-lookup"><span data-stu-id="e86cf-121">The `-keycontainer` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e86cf-122">示例</span><span class="sxs-lookup"><span data-stu-id="e86cf-122">Example</span></span>  
 <span data-ttu-id="e86cf-123">下面的代码编译源文件`Input.vb`和指定的密钥容器。</span><span class="sxs-lookup"><span data-stu-id="e86cf-123">The following code compiles source file `Input.vb` and specifies a key container.</span></span>  
  
```  
vbc -keycontainer:key1 input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="e86cf-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="e86cf-124">See also</span></span>
- [<span data-ttu-id="e86cf-125">在.NET 中的程序集</span><span class="sxs-lookup"><span data-stu-id="e86cf-125">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="e86cf-126">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="e86cf-126">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="e86cf-127">-keyfile</span><span class="sxs-lookup"><span data-stu-id="e86cf-127">-keyfile</span></span>](../../../visual-basic/reference/command-line-compiler/keyfile.md)
- [<span data-ttu-id="e86cf-128">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="e86cf-128">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

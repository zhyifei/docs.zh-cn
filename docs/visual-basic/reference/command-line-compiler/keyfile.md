---
title: -keyfile
ms.date: 03/10/2018
helpviewer_keywords:
- /keyfile compiler option [Visual Basic]
- keyfile compiler option [Visual Basic]
- -keyfile compiler option [Visual Basic]
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
ms.openlocfilehash: cffc3c5f0ff3dd48ca2c74bde346a967b209dc5f
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266737"
---
# <a name="-keyfile"></a><span data-ttu-id="ae811-102">-keyfile</span><span class="sxs-lookup"><span data-stu-id="ae811-102">-keyfile</span></span>
<span data-ttu-id="ae811-103">指定包含密钥或密钥对的文件从而为程序集赋予强名称。</span><span class="sxs-lookup"><span data-stu-id="ae811-103">Specifies a file containing a key or key pair to give an assembly a strong name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae811-104">语法</span><span class="sxs-lookup"><span data-stu-id="ae811-104">Syntax</span></span>  
  
```console
-keyfile:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="ae811-105">参数</span><span class="sxs-lookup"><span data-stu-id="ae811-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="ae811-106">必需。</span><span class="sxs-lookup"><span data-stu-id="ae811-106">Required.</span></span> <span data-ttu-id="ae811-107">包含密钥的文件。</span><span class="sxs-lookup"><span data-stu-id="ae811-107">File that contains the key.</span></span> <span data-ttu-id="ae811-108">如果文件名包含空格，则用引号 （""） 括上名称。</span><span class="sxs-lookup"><span data-stu-id="ae811-108">If the file name contains a space, enclose the name in quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae811-109">备注</span><span class="sxs-lookup"><span data-stu-id="ae811-109">Remarks</span></span>  
 <span data-ttu-id="ae811-110">编译器将公钥插入程序集清单，然后使用私钥对最终程序集进行签名。</span><span class="sxs-lookup"><span data-stu-id="ae811-110">The compiler inserts the public key into the assembly manifest and then signs the final assembly with the private key.</span></span> <span data-ttu-id="ae811-111">若要生成密钥文件，请在命令行键入 `sn -k file`。</span><span class="sxs-lookup"><span data-stu-id="ae811-111">To generate a key file, type `sn -k file` at the command line.</span></span> <span data-ttu-id="ae811-112">有关详细信息，请参阅[Sn.exe（强名称工具）。](../../../framework/tools/sn-exe-strong-name-tool.md)</span><span class="sxs-lookup"><span data-stu-id="ae811-112">For more information, see [Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md)).</span></span>  
  
 <span data-ttu-id="ae811-113">如果使用 编译，`-target:module`则密钥文件的名称将包含在模块中，并合并[到编译程序集](../../../visual-basic/reference/command-line-compiler/addmodule.md)时创建的程序集中，</span><span class="sxs-lookup"><span data-stu-id="ae811-113">If you compile with `-target:module`, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span></span>  
  
 <span data-ttu-id="ae811-114">您还可以使用[-key 容器](../../../visual-basic/reference/command-line-compiler/keycontainer.md)将加密信息传递给编译器。</span><span class="sxs-lookup"><span data-stu-id="ae811-114">You can also pass your encryption information to the compiler with [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span></span> <span data-ttu-id="ae811-115">如果需要部分签名的程序集，请使用[延迟符号](../../../visual-basic/reference/command-line-compiler/delaysign.md)。</span><span class="sxs-lookup"><span data-stu-id="ae811-115">Use [-delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="ae811-116">您还可以在任何 Microsoft 中间语言模块的源代码中<xref:System.Reflection.AssemblyKeyFileAttribute>指定此选项为自定义属性 （ ） 。</span><span class="sxs-lookup"><span data-stu-id="ae811-116">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyFileAttribute>) in the source code for any Microsoft intermediate language module.</span></span>  
  
 <span data-ttu-id="ae811-117">如果在同`-keyfile`一编译中指定和[-key 容器](../../../visual-basic/reference/command-line-compiler/keycontainer.md)（通过命令行选项或自定义属性），编译器首先尝试密钥容器。</span><span class="sxs-lookup"><span data-stu-id="ae811-117">In case both `-keyfile` and [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) are specified (either by command-line option or by custom attribute) in the same compilation, the compiler first tries the key container.</span></span> <span data-ttu-id="ae811-118">如果成功，则使用密钥容器中的信息对程序集签名。</span><span class="sxs-lookup"><span data-stu-id="ae811-118">If that succeeds, then the assembly is signed with the information in the key container.</span></span> <span data-ttu-id="ae811-119">如果编译器找不到密钥容器，它将尝试使用`-keyfile`指定的文件。</span><span class="sxs-lookup"><span data-stu-id="ae811-119">If the compiler does not find the key container, it tries the file specified with `-keyfile`.</span></span> <span data-ttu-id="ae811-120">如果成功，程序集将使用密钥文件中的信息进行签名，并且密钥信息安装在密钥容器中（类似于`sn -i`），以便在下一次编译时密钥容器将有效。</span><span class="sxs-lookup"><span data-stu-id="ae811-120">If this succeeds, the assembly is signed with the information in the key file, and the key information is installed in the key container (similar to `sn -i`) so that on the next compilation, the key container will be valid.</span></span>  
  
 <span data-ttu-id="ae811-121">请注意，密钥文件可能仅包含公钥。</span><span class="sxs-lookup"><span data-stu-id="ae811-121">Note that a key file might contain only the public key.</span></span>  
  
 <span data-ttu-id="ae811-122">有关对程序集进行签名的详细信息，请参阅[创建和使用强名称程序集](../../../standard/assembly/create-use-strong-named.md)。</span><span class="sxs-lookup"><span data-stu-id="ae811-122">See [Creating and Using Strong-Named Assemblies](../../../standard/assembly/create-use-strong-named.md) for more information on signing an assembly.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ae811-123">该`-keyfile`选项在可视化工作室开发环境中不可用;因此，该选项在可视化工作室开发环境中不可用。它仅在从命令行编译时可用。</span><span class="sxs-lookup"><span data-stu-id="ae811-123">The `-keyfile` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="ae811-124">示例</span><span class="sxs-lookup"><span data-stu-id="ae811-124">Example</span></span>

<span data-ttu-id="ae811-125">以下代码编译源文件`Input.vb`并指定密钥文件。</span><span class="sxs-lookup"><span data-stu-id="ae811-125">The following code compiles source file `Input.vb` and specifies a key file.</span></span>

```console
vbc -keyfile:myfile.sn input.vb
```

## <a name="see-also"></a><span data-ttu-id="ae811-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ae811-126">See also</span></span>

- [<span data-ttu-id="ae811-127">.NET 中的程序集</span><span class="sxs-lookup"><span data-stu-id="ae811-127">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="ae811-128">可视化基本命令行编译器</span><span class="sxs-lookup"><span data-stu-id="ae811-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="ae811-129">-参考（视觉基础）</span><span class="sxs-lookup"><span data-stu-id="ae811-129">-reference (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)
- [<span data-ttu-id="ae811-130">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="ae811-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

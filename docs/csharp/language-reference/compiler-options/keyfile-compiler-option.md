---
title: "-keyfile（C# 编译器选项）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /keyfile
helpviewer_keywords:
- /keyfile compiler option [C#]
- -keyfile compiler option [C#]
- keyfile compiler option [C#]
ms.assetid: 0815f9de-ace4-4e98-b4c6-13c55dea40c2
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d120b325f433108cd1b01dd1c25d2a0e55da401b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="keyfile-c-compiler-options"></a><span data-ttu-id="30dc0-102">/keyfile（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="30dc0-102">/keyfile (C# Compiler Options)</span></span>
<span data-ttu-id="30dc0-103">指定包含加密密钥的文件名。</span><span class="sxs-lookup"><span data-stu-id="30dc0-103">Specifies the filename containing the cryptographic key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30dc0-104">语法</span><span class="sxs-lookup"><span data-stu-id="30dc0-104">Syntax</span></span>  
  
```console  
/keyfile:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="30dc0-105">参数</span><span class="sxs-lookup"><span data-stu-id="30dc0-105">Arguments</span></span>  
  
|<span data-ttu-id="30dc0-106">术语</span><span class="sxs-lookup"><span data-stu-id="30dc0-106">Term</span></span>|<span data-ttu-id="30dc0-107">定义</span><span class="sxs-lookup"><span data-stu-id="30dc0-107">Definition</span></span>|  
|----------|----------------|  
|`file`|<span data-ttu-id="30dc0-108">含有强名称密钥的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="30dc0-108">The name of the file containing the strong name key.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30dc0-109">备注</span><span class="sxs-lookup"><span data-stu-id="30dc0-109">Remarks</span></span>  
 <span data-ttu-id="30dc0-110">使用此选项时，编译器在程序集清单中插入指定字段的公钥，然后使用私钥对最终的程序集进行签名。</span><span class="sxs-lookup"><span data-stu-id="30dc0-110">When this option is used, the compiler inserts the public key from the specified file into the assembly manifest and then signs the final assembly with the private key.</span></span> <span data-ttu-id="30dc0-111">若要生成密钥文件，请在命令行键入 sn-k `file`。</span><span class="sxs-lookup"><span data-stu-id="30dc0-111">To generate a key file, type sn -k `file` at the command line.</span></span>  
  
 <span data-ttu-id="30dc0-112">如果使用 /target:module 进行编译，密钥文件的名称将保存在模块中，并在使用 [/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md) 编译程序集时包含到创建的程序集中。</span><span class="sxs-lookup"><span data-stu-id="30dc0-112">If you compile with **/target:module**, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).</span></span>  
  
 <span data-ttu-id="30dc0-113">也可以使用 [/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md) 将加密信息传递给编译器。</span><span class="sxs-lookup"><span data-stu-id="30dc0-113">You can also pass your encryption information to the compiler with [/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md).</span></span> <span data-ttu-id="30dc0-114">如果需要部分签名的程序集，请使用 [/delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md)。</span><span class="sxs-lookup"><span data-stu-id="30dc0-114">Use [/delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="30dc0-115">如果在同一编译中同时指定 /keyfile 和 /keycontainer（通过命令行选项或通过自定义特性），则 Al.exe 将首先尝试用密钥容器。</span><span class="sxs-lookup"><span data-stu-id="30dc0-115">In case both /keyfile and /keycontainer are specified (either by command line option or by custom attribute) in the same compilation, the compiler will first try the key container.</span></span> <span data-ttu-id="30dc0-116">如果成功，则使用密钥容器中的信息对程序集签名。</span><span class="sxs-lookup"><span data-stu-id="30dc0-116">If that succeeds, then the assembly is signed with the information in the key container.</span></span> <span data-ttu-id="30dc0-117">如果编译器没有找到密钥容器，它将尝试用 /keyfile 指定的文件。</span><span class="sxs-lookup"><span data-stu-id="30dc0-117">If the compiler does not find the key container, it will try the file specified with /keyfile.</span></span> <span data-ttu-id="30dc0-118">如果成功，则使用密钥文件中的信息对程序集签名，并且将密钥信息安装到密钥容器中（类似于 sn -i），以便在下一次编译中，密钥容器选项将生效。</span><span class="sxs-lookup"><span data-stu-id="30dc0-118">If that succeeds, the assembly is signed with the information in the key file and the key information will be installed in the key container (similar to sn -i) so that on the next compilation, the key container will be valid.</span></span>  
  
 <span data-ttu-id="30dc0-119">请注意，密钥文件可能仅包含公钥。</span><span class="sxs-lookup"><span data-stu-id="30dc0-119">Note that a key file might contain only the public key.</span></span>  
  
 <span data-ttu-id="30dc0-120">有关详细信息，请参阅[创建和使用具有强名称的程序集](../../../framework/app-domains/create-and-use-strong-named-assemblies.md)和[延迟为程序集签名](../../../framework/app-domains/delay-sign-assembly.md)。</span><span class="sxs-lookup"><span data-stu-id="30dc0-120">For more information, see [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) and [Delay Signing an Assembly](../../../framework/app-domains/delay-sign-assembly.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="30dc0-121">在 Visual Studio 开发环境中设置此编译器选项</span><span class="sxs-lookup"><span data-stu-id="30dc0-121">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="30dc0-122">打开项目的“属性”  页。</span><span class="sxs-lookup"><span data-stu-id="30dc0-122">Open the **Properties** page for the project.</span></span>  
  
2.  <span data-ttu-id="30dc0-123">单击“签名”属性页。</span><span class="sxs-lookup"><span data-stu-id="30dc0-123">Click the **Signing** property page.</span></span>  
  
3.  <span data-ttu-id="30dc0-124">修改“选择强名称密钥文件”属性。</span><span class="sxs-lookup"><span data-stu-id="30dc0-124">Modify the **Choose a strong name key file** property.</span></span>  
  
 <span data-ttu-id="30dc0-125">可通过 <xref:VSLangProj.ProjectProperties.AssemblyOriginatorKeyFile%2A> 以编程方式访问此编译器选项。</span><span class="sxs-lookup"><span data-stu-id="30dc0-125">You can programmatically access this compiler option with <xref:VSLangProj.ProjectProperties.AssemblyOriginatorKeyFile%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30dc0-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="30dc0-126">See Also</span></span>  
 [<span data-ttu-id="30dc0-127">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="30dc0-127">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="30dc0-128">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="30dc0-128">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

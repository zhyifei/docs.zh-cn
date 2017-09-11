---
title: "-keycontainer（C# 编译器选项）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /keycontainer
dev_langs:
- CSharp
helpviewer_keywords:
- /keycontainer compiler option [C#]
- keycontainer compiler option [C#]
- -keycontainer compiler option [C#]
ms.assetid: b3982b6d-2382-4f7e-bebd-ce98eaa30763
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5d27fa0b80ca6df15394ad1fda149377cac41a8b
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="keycontainer-c-compiler-options"></a><span data-ttu-id="4a4fb-102">/keycontainer（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="4a4fb-102">/keycontainer (C# Compiler Options)</span></span>
<span data-ttu-id="4a4fb-103">指定加密密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="4a4fb-103">Specifies the name of the cryptographic key container.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a4fb-104">语法</span><span class="sxs-lookup"><span data-stu-id="4a4fb-104">Syntax</span></span>  
  
```console  
/keycontainer:string  
```  
  
## <a name="arguments"></a><span data-ttu-id="4a4fb-105">参数</span><span class="sxs-lookup"><span data-stu-id="4a4fb-105">Arguments</span></span>  
 `string`  
 <span data-ttu-id="4a4fb-106">强名称密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="4a4fb-106">The name of the strong name key container.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a4fb-107">备注</span><span class="sxs-lookup"><span data-stu-id="4a4fb-107">Remarks</span></span>  
 <span data-ttu-id="4a4fb-108">使用“/keycontainer”选项时，通过将来自所指定容器的公钥插入到程序集清单并且用私钥签名最终程序集，编译器可创建可共享的组件。</span><span class="sxs-lookup"><span data-stu-id="4a4fb-108">When the **/keycontainer** option is used, the compiler creates a sharable component by inserting a public key from the specified container into the assembly manifest and signing the final assembly with the private key.</span></span> <span data-ttu-id="4a4fb-109">若要生成密钥文件，请在命令行键入 sn-k `file`。</span><span class="sxs-lookup"><span data-stu-id="4a4fb-109">To generate a key file, type sn -k `file` at the command line.</span></span> <span data-ttu-id="4a4fb-110">sn-i 将密钥对安装到容器中。</span><span class="sxs-lookup"><span data-stu-id="4a4fb-110">sn -i installs the key pair into a container.</span></span>  
  
 <span data-ttu-id="4a4fb-111">如果使用 [/target: module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md) 进行编译，当使用 [/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md) 将此模块编译到程序集时，密钥文件的名称将保存在模块中，且会并入程序集。</span><span class="sxs-lookup"><span data-stu-id="4a4fb-111">If you compile with [/target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md), the name of the key file is held in the module and incorporated into the assembly when you compile this module into an assembly with [/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).</span></span>  
  
 <span data-ttu-id="4a4fb-112">还可以将此选项指定为任何 Microsoft 中间语言 (MSIL) 模块的源代码中的自定义特性 (<xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=fullName>)。</span><span class="sxs-lookup"><span data-stu-id="4a4fb-112">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=fullName>) in the source code for any Microsoft intermediate language (MSIL) module.</span></span>  
  
 <span data-ttu-id="4a4fb-113">此外，可使用 [/keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md) 将加密信息传递给编译器。</span><span class="sxs-lookup"><span data-stu-id="4a4fb-113">You can also pass your encryption information to the compiler with [/keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md).</span></span> <span data-ttu-id="4a4fb-114">如果希望将公钥添加到程序集清单，但希望测试完程序集后再对其签名，请使用 [/delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md)。</span><span class="sxs-lookup"><span data-stu-id="4a4fb-114">Use [/delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md) if you want the public key added to the assembly manifest but want to delay signing the assembly until it has been tested.</span></span>  
  
 <span data-ttu-id="4a4fb-115">有关详细信息，请参阅[创建和使用具有强名称的程序集](https://msdn.microsoft.com/library/xwb8f617)和[延迟为程序集签名](../../../framework/app-domains/delay-sign-assembly.md)。</span><span class="sxs-lookup"><span data-stu-id="4a4fb-115">For more information, see [Creating and Using Strong-Named Assemblies](https://msdn.microsoft.com/library/xwb8f617) and [Delay Signing an Assembly](../../../framework/app-domains/delay-sign-assembly.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="4a4fb-116">在 Visual Studio 开发环境中设置此编译器选项</span><span class="sxs-lookup"><span data-stu-id="4a4fb-116">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="4a4fb-117">Visual Studio 开发环境中尚未提供此编译器选项。</span><span class="sxs-lookup"><span data-stu-id="4a4fb-117">This compiler option is not available in the Visual Studio development environment.</span></span>  
  
 <span data-ttu-id="4a4fb-118">可通过 <xref:VSLangProj.ProjectProperties.AssemblyKeyContainerName%2A> 以编程方式访问此编译器选项。</span><span class="sxs-lookup"><span data-stu-id="4a4fb-118">You can programmatically access this compiler option with <xref:VSLangProj.ProjectProperties.AssemblyKeyContainerName%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a4fb-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a4fb-119">See Also</span></span>  
 <span data-ttu-id="4a4fb-120">[（C# 编译器选项）](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="4a4fb-120">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="4a4fb-121">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="4a4fb-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)


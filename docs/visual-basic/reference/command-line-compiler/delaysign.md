---
title: -delaysign
ms.date: 03/10/2018
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
ms.openlocfilehash: 1459484b858137836fcfdcd9db46d8e99a06e9c7
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185204"
---
# <a name="-delaysign"></a><span data-ttu-id="bc5fa-102">-delaysign</span><span class="sxs-lookup"><span data-stu-id="bc5fa-102">-delaysign</span></span>
<span data-ttu-id="bc5fa-103">指定程序集是完全签名的还是部分签名的。</span><span class="sxs-lookup"><span data-stu-id="bc5fa-103">Specifies whether the assembly will be fully or partially signed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc5fa-104">语法</span><span class="sxs-lookup"><span data-stu-id="bc5fa-104">Syntax</span></span>  
  
```  
-delaysign[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="bc5fa-105">自变量</span><span class="sxs-lookup"><span data-stu-id="bc5fa-105">Arguments</span></span>  
 <span data-ttu-id="bc5fa-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="bc5fa-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="bc5fa-107">可选。</span><span class="sxs-lookup"><span data-stu-id="bc5fa-107">Optional.</span></span> <span data-ttu-id="bc5fa-108">如果需要完全签名的程序集，则使用 `-delaysign-`。</span><span class="sxs-lookup"><span data-stu-id="bc5fa-108">Use `-delaysign-` if you want a fully signed assembly.</span></span> <span data-ttu-id="bc5fa-109">使用`-delaysign+`如果想要将公钥放在有符号哈希的程序集和保留空间中。</span><span class="sxs-lookup"><span data-stu-id="bc5fa-109">Use `-delaysign+` if you want to place the public key in the assembly and reserve space for the signed hash.</span></span> <span data-ttu-id="bc5fa-110">默认值为 `-delaysign-`。</span><span class="sxs-lookup"><span data-stu-id="bc5fa-110">The default is `-delaysign-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc5fa-111">备注</span><span class="sxs-lookup"><span data-stu-id="bc5fa-111">Remarks</span></span>  
 <span data-ttu-id="bc5fa-112">`-delaysign`选项没有任何影响，除非用于[-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)或[-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)。</span><span class="sxs-lookup"><span data-stu-id="bc5fa-112">The `-delaysign` option has no effect unless used with [-keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) or [-keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span></span>  
  
 <span data-ttu-id="bc5fa-113">在请求完全签名的程序集时，编译器会对包含清单（程序集元数据）的文件进行哈希处理，并使用私钥对哈希进行签名。</span><span class="sxs-lookup"><span data-stu-id="bc5fa-113">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="bc5fa-114">产生的数字签名存储在包含清单的文件中。</span><span class="sxs-lookup"><span data-stu-id="bc5fa-114">The resulting digital signature is stored in the file that contains the manifest.</span></span> <span data-ttu-id="bc5fa-115">程序集延迟签名时，编译器不会计算和存储文件中的签名，但预留空间，以便可以稍后添加该签名。</span><span class="sxs-lookup"><span data-stu-id="bc5fa-115">When an assembly is delay signed, the compiler does not compute and store the signature but reserves space in the file so the signature can be added later.</span></span>  
  
 <span data-ttu-id="bc5fa-116">例如，通过使用`-delaysign+`，在组织中的开发人员可以分发测试人员可注册到全局程序集缓存和使用程序集的无符号的测试版本。</span><span class="sxs-lookup"><span data-stu-id="bc5fa-116">For example, by using `-delaysign+`, a developer in an organization can distribute unsigned test versions of an assembly that testers can register with the global assembly cache and use.</span></span> <span data-ttu-id="bc5fa-117">在完成工作的程序集时，负责组织的私钥的人员完全可以登录该程序集。</span><span class="sxs-lookup"><span data-stu-id="bc5fa-117">When work on the assembly is completed, the person responsible for the organization's private key can fully sign the assembly.</span></span> <span data-ttu-id="bc5fa-118">这种划分可防止组织的专用密钥泄露，同时允许所有开发人员若要运行的程序集。</span><span class="sxs-lookup"><span data-stu-id="bc5fa-118">This compartmentalization protects the organization's private key from disclosure, while allowing all developers to work on the assemblies.</span></span>  
  
 <span data-ttu-id="bc5fa-119">请参阅[创建和使用具有强名称程序集](../../../framework/app-domains/create-and-use-strong-named-assemblies.md)有关为程序集签名的详细信息。</span><span class="sxs-lookup"><span data-stu-id="bc5fa-119">See [Creating and Using Strong-Named Assemblies](../../../framework/app-domains/create-and-use-strong-named-assemblies.md) for more information on signing an assembly.</span></span>  
  
### <a name="to-set--delaysign-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="bc5fa-120">在 Visual Studio 集成的开发环境中设置-delaysign</span><span class="sxs-lookup"><span data-stu-id="bc5fa-120">To set -delaysign in the Visual Studio integrated development environment</span></span>  
  
1.  <span data-ttu-id="bc5fa-121">在 **“解决方案资源管理器”** 中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="bc5fa-121">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="bc5fa-122">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="bc5fa-122">On the **Project** menu, click **Properties**.</span></span>   
  
2.  <span data-ttu-id="bc5fa-123">单击“签名”选项卡。</span><span class="sxs-lookup"><span data-stu-id="bc5fa-123">Click the **Signing** tab.</span></span>  
  
3.  <span data-ttu-id="bc5fa-124">中的值设置**仅延迟签名**框。</span><span class="sxs-lookup"><span data-stu-id="bc5fa-124">Set the value in the **Delay sign only** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc5fa-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="bc5fa-125">See Also</span></span>  
 [<span data-ttu-id="bc5fa-126">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="bc5fa-126">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="bc5fa-127">-keyfile</span><span class="sxs-lookup"><span data-stu-id="bc5fa-127">-keyfile</span></span>](../../../visual-basic/reference/command-line-compiler/keyfile.md)  
 [<span data-ttu-id="bc5fa-128">-keycontainer</span><span class="sxs-lookup"><span data-stu-id="bc5fa-128">-keycontainer</span></span>](../../../visual-basic/reference/command-line-compiler/keycontainer.md)  
 [<span data-ttu-id="bc5fa-129">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="bc5fa-129">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

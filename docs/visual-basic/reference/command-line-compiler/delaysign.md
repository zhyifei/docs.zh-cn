---
title: /delaysign
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- /delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: dc457a1a32048441f82976488158f223e7e3e087
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2017
---
# <a name="delaysign"></a><span data-ttu-id="58cd7-102">/delaysign</span><span class="sxs-lookup"><span data-stu-id="58cd7-102">/delaysign</span></span>
<span data-ttu-id="58cd7-103">指定程序集是完全签名的还是部分签名的。</span><span class="sxs-lookup"><span data-stu-id="58cd7-103">Specifies whether the assembly will be fully or partially signed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58cd7-104">语法</span><span class="sxs-lookup"><span data-stu-id="58cd7-104">Syntax</span></span>  
  
```  
/delaysign[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="58cd7-105">参数</span><span class="sxs-lookup"><span data-stu-id="58cd7-105">Arguments</span></span>  
 <span data-ttu-id="58cd7-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="58cd7-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="58cd7-107">可选。</span><span class="sxs-lookup"><span data-stu-id="58cd7-107">Optional.</span></span> <span data-ttu-id="58cd7-108">如果需要完全签名的程序集，则使用 `/delaysign-`。</span><span class="sxs-lookup"><span data-stu-id="58cd7-108">Use `/delaysign-` if you want a fully signed assembly.</span></span> <span data-ttu-id="58cd7-109">使用`/delaysign+`如果你想要将公钥放在有符号哈希的程序集和保留空间。</span><span class="sxs-lookup"><span data-stu-id="58cd7-109">Use `/delaysign+` if you want to place the public key in the assembly and reserve space for the signed hash.</span></span> <span data-ttu-id="58cd7-110">默认值为 `/delaysign-`。</span><span class="sxs-lookup"><span data-stu-id="58cd7-110">The default is `/delaysign-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58cd7-111">备注</span><span class="sxs-lookup"><span data-stu-id="58cd7-111">Remarks</span></span>  
 <span data-ttu-id="58cd7-112">`/delaysign`选项没有任何影响，除非用于[/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)或[/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)。</span><span class="sxs-lookup"><span data-stu-id="58cd7-112">The `/delaysign` option has no effect unless used with [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) or [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span></span>  
  
 <span data-ttu-id="58cd7-113">在请求完全签名的程序集时，编译器会对包含清单（程序集元数据）的文件进行哈希处理，并使用私钥对哈希进行签名。</span><span class="sxs-lookup"><span data-stu-id="58cd7-113">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="58cd7-114">产生的数字签名存储在包含清单的文件中。</span><span class="sxs-lookup"><span data-stu-id="58cd7-114">The resulting digital signature is stored in the file that contains the manifest.</span></span> <span data-ttu-id="58cd7-115">在程序集延迟签名时，编译器不会不计算和存储在文件的签名而预留空间，以便稍后可添加签名。</span><span class="sxs-lookup"><span data-stu-id="58cd7-115">When an assembly is delay signed, the compiler does not compute and store the signature but reserves space in the file so the signature can be added later.</span></span>  
  
 <span data-ttu-id="58cd7-116">例如，通过使用`/delaysign+`，组织中的开发人员可以分发的程序集的测试人员可以全局程序集缓存中注册和使用的无符号的测试版本。</span><span class="sxs-lookup"><span data-stu-id="58cd7-116">For example, by using `/delaysign+`, a developer in an organization can distribute unsigned test versions of an assembly that testers can register with the global assembly cache and use.</span></span> <span data-ttu-id="58cd7-117">程序集上的工作完成后，负责组织的私钥的人员可以完全签名的程序集。</span><span class="sxs-lookup"><span data-stu-id="58cd7-117">When work on the assembly is completed, the person responsible for the organization's private key can fully sign the assembly.</span></span> <span data-ttu-id="58cd7-118">这种划分可防止组织的私钥泄露，同时允许所有开发人员能够对程序集。</span><span class="sxs-lookup"><span data-stu-id="58cd7-118">This compartmentalization protects the organization's private key from disclosure, while allowing all developers to work on the assemblies.</span></span>  
  
 <span data-ttu-id="58cd7-119">请参阅[创建和使用具有强名称程序集](../../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)有关程序集进行签名的详细信息。</span><span class="sxs-lookup"><span data-stu-id="58cd7-119">See [Creating and Using Strong-Named Assemblies](../../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md) for more information on signing an assembly.</span></span>  
  
### <a name="to-set-delaysign-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="58cd7-120">在 Visual Studio 中设置 /delaysign 集成开发环境</span><span class="sxs-lookup"><span data-stu-id="58cd7-120">To set /delaysign in the Visual Studio integrated development environment</span></span>  
  
1.  <span data-ttu-id="58cd7-121">在 “解决方案资源管理器”中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="58cd7-121">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="58cd7-122">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="58cd7-122">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="58cd7-123">有关详细信息，请参阅[项目设计器简介](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)。</span><span class="sxs-lookup"><span data-stu-id="58cd7-123">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="58cd7-124">单击“签名”选项卡。</span><span class="sxs-lookup"><span data-stu-id="58cd7-124">Click the **Signing** tab.</span></span>  
  
3.  <span data-ttu-id="58cd7-125">设置中的值**仅延迟签名**框。</span><span class="sxs-lookup"><span data-stu-id="58cd7-125">Set the value in the **Delay sign only** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58cd7-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="58cd7-126">See Also</span></span>  
 [<span data-ttu-id="58cd7-127">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="58cd7-127">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="58cd7-128">/keyfile</span><span class="sxs-lookup"><span data-stu-id="58cd7-128">/keyfile</span></span>](../../../visual-basic/reference/command-line-compiler/keyfile.md)  
 [<span data-ttu-id="58cd7-129">/keycontainer</span><span class="sxs-lookup"><span data-stu-id="58cd7-129">/keycontainer</span></span>](../../../visual-basic/reference/command-line-compiler/keycontainer.md)  
 [<span data-ttu-id="58cd7-130">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="58cd7-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)

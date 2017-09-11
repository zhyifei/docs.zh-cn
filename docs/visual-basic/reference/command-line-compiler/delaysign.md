---
title: "/delaysign |Microsoft 文档"
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
- delaysign compiler option [Visual Basic]
- /delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
caps.latest.revision: 19
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
ms.openlocfilehash: bcc819e08ca7731d91dc77dc831060bcf00a4425
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="delaysign"></a><span data-ttu-id="840f4-102">/delaysign</span><span class="sxs-lookup"><span data-stu-id="840f4-102">/delaysign</span></span>
<span data-ttu-id="840f4-103">指定程序集是完全签名的还是部分签名的。</span><span class="sxs-lookup"><span data-stu-id="840f4-103">Specifies whether the assembly will be fully or partially signed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="840f4-104">语法</span><span class="sxs-lookup"><span data-stu-id="840f4-104">Syntax</span></span>  
  
```  
/delaysign[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="840f4-105">参数</span><span class="sxs-lookup"><span data-stu-id="840f4-105">Arguments</span></span>  
 <span data-ttu-id="840f4-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="840f4-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="840f4-107">可选。</span><span class="sxs-lookup"><span data-stu-id="840f4-107">Optional.</span></span> <span data-ttu-id="840f4-108">如果需要完全签名的程序集，则使用 `/delaysign-`。</span><span class="sxs-lookup"><span data-stu-id="840f4-108">Use `/delaysign-` if you want a fully signed assembly.</span></span> <span data-ttu-id="840f4-109">使用`/delaysign+`如果想要将公钥放在有符号哈希的程序集和保留空间。</span><span class="sxs-lookup"><span data-stu-id="840f4-109">Use `/delaysign+` if you want to place the public key in the assembly and reserve space for the signed hash.</span></span> <span data-ttu-id="840f4-110">默认值为 `/delaysign-`。</span><span class="sxs-lookup"><span data-stu-id="840f4-110">The default is `/delaysign-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="840f4-111">备注</span><span class="sxs-lookup"><span data-stu-id="840f4-111">Remarks</span></span>  
 <span data-ttu-id="840f4-112">`/delaysign`选项没有任何影响，除非用于[/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)或[/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)。</span><span class="sxs-lookup"><span data-stu-id="840f4-112">The `/delaysign` option has no effect unless used with [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) or [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).</span></span>  
  
 <span data-ttu-id="840f4-113">在请求完全签名的程序集时，编译器进行哈希的文件，包含清单 （程序集元数据） 并使用私钥进行签名的哈希处理。</span><span class="sxs-lookup"><span data-stu-id="840f4-113">When you request a fully signed assembly, the compiler hashes the file that contains the manifest (assembly metadata) and signs that hash with the private key.</span></span> <span data-ttu-id="840f4-114">产生的数字签名存储在包含清单的文件中。</span><span class="sxs-lookup"><span data-stu-id="840f4-114">The resulting digital signature is stored in the file that contains the manifest.</span></span> <span data-ttu-id="840f4-115">在程序集延迟签名时，编译器不会不计算，并在文件中存储的签名，但保留空间以便稍后可添加签名。</span><span class="sxs-lookup"><span data-stu-id="840f4-115">When an assembly is delay signed, the compiler does not compute and store the signature but reserves space in the file so the signature can be added later.</span></span>  
  
 <span data-ttu-id="840f4-116">例如，通过使用`/delaysign+`，在组织中的开发人员可以分发未签名的测试版本的程序集的测试人员可以全局程序集缓存中注册和使用。</span><span class="sxs-lookup"><span data-stu-id="840f4-116">For example, by using `/delaysign+`, a developer in an organization can distribute unsigned test versions of an assembly that testers can register with the global assembly cache and use.</span></span> <span data-ttu-id="840f4-117">针对程序集的工作完成后，负责组织的私钥的人员可以完全签名程序集。</span><span class="sxs-lookup"><span data-stu-id="840f4-117">When work on the assembly is completed, the person responsible for the organization's private key can fully sign the assembly.</span></span> <span data-ttu-id="840f4-118">这种划分保护组织的私钥泄露，同时允许所有开发人员能够在程序集上。</span><span class="sxs-lookup"><span data-stu-id="840f4-118">This compartmentalization protects the organization's private key from disclosure, while allowing all developers to work on the assemblies.</span></span>  
  
 <span data-ttu-id="840f4-119">请参阅[创建和使用具有强名称程序集](https://msdn.microsoft.com/library/xwb8f617)有关程序集进行签名的详细信息。</span><span class="sxs-lookup"><span data-stu-id="840f4-119">See [Creating and Using Strong-Named Assemblies](https://msdn.microsoft.com/library/xwb8f617) for more information on signing an assembly.</span></span>  
  
### <a name="to-set-delaysign-in-the-visual-studio-integrated-development-environment"></a><span data-ttu-id="840f4-120">在 Visual Studio 中设置 /delaysign 集成开发环境</span><span class="sxs-lookup"><span data-stu-id="840f4-120">To set /delaysign in the Visual Studio integrated development environment</span></span>  
  
1.  <span data-ttu-id="840f4-121">在 **“解决方案资源管理器”**中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="840f4-121">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="840f4-122">在**项目**菜单上，单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="840f4-122">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="840f4-123">有关详细信息，请参阅[项目设计器简介](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)。</span><span class="sxs-lookup"><span data-stu-id="840f4-123">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="840f4-124">单击**签名**选项卡。</span><span class="sxs-lookup"><span data-stu-id="840f4-124">Click the **Signing** tab.</span></span>  
  
3.  <span data-ttu-id="840f4-125">中的值设置**仅延迟签名**框。</span><span class="sxs-lookup"><span data-stu-id="840f4-125">Set the value in the **Delay sign only** box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="840f4-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="840f4-126">See Also</span></span>  
 <span data-ttu-id="840f4-127">[Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="840f4-127">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="840f4-128"> [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) </span><span class="sxs-lookup"><span data-stu-id="840f4-128"> [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) </span></span>  
<span data-ttu-id="840f4-129"> [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) </span><span class="sxs-lookup"><span data-stu-id="840f4-129"> [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md) </span></span>  
<span data-ttu-id="840f4-130"> [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="840f4-130"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>

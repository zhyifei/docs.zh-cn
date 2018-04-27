---
title: 创建程序集清单时出错：&lt;错误消息&gt;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30140
- vbc30140
helpviewer_keywords:
- BC30140
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4032bbcbf9924eb5aad4e2cb1a6e74df9a472eca
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="error-creating-assembly-manifest-lterror-messagegt"></a><span data-ttu-id="2473f-102">创建程序集清单时出错：&lt;错误消息&gt;</span><span class="sxs-lookup"><span data-stu-id="2473f-102">Error creating assembly manifest: &lt;error message&gt;</span></span>
<span data-ttu-id="2473f-103">Visual Basic 编译器调用程序集链接器 (Al.exe，也称作 Alink) 生成包含清单的程序集。</span><span class="sxs-lookup"><span data-stu-id="2473f-103">The Visual Basic compiler calls the Assembly Linker (Al.exe, also known as Alink) to generate an assembly with a manifest.</span></span> <span data-ttu-id="2473f-104">该链接器已报告在创建程序集的预发出阶段中出错。</span><span class="sxs-lookup"><span data-stu-id="2473f-104">The linker has reported an error in the pre-emission stage of creating the assembly.</span></span>  
  
 <span data-ttu-id="2473f-105">如果指定的密钥文件或密钥容器有问题，就可能发生错误。</span><span class="sxs-lookup"><span data-stu-id="2473f-105">This can occur if there are problems with the key file or the key container specified.</span></span> <span data-ttu-id="2473f-106">若要对程序集进行完全签名，必须提供包含公钥和私钥信息的有效密钥文件。</span><span class="sxs-lookup"><span data-stu-id="2473f-106">To fully sign an assembly, you must provide a valid key file that contains information about the public and private keys.</span></span> <span data-ttu-id="2473f-107">若要延迟对程序集的签名，必须选择“仅延迟签名”复选框，并提供包含公钥信息的有效密钥文件。</span><span class="sxs-lookup"><span data-stu-id="2473f-107">To delay sign an assembly, you must select the **Delay sign only** check box and provide a valid key file that contains information about the public key information.</span></span> <span data-ttu-id="2473f-108">当程序集为延迟签名时，不需要使用私有密钥。</span><span class="sxs-lookup"><span data-stu-id="2473f-108">The private key is not necessary when an assembly is delay-signed.</span></span> <span data-ttu-id="2473f-109">有关详细信息，请参阅[如何：使用强名称为程序集签名](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)。</span><span class="sxs-lookup"><span data-stu-id="2473f-109">For more information, see [How to: Sign an Assembly with a Strong Name](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).</span></span>  
  
 <span data-ttu-id="2473f-110">**错误 ID:** BC30140</span><span class="sxs-lookup"><span data-stu-id="2473f-110">**Error ID:** BC30140</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2473f-111">更正此错误</span><span class="sxs-lookup"><span data-stu-id="2473f-111">To correct this error</span></span>  
  
1.  <span data-ttu-id="2473f-112">检查引用的错误信息并参考主题[Al.exe](../../../framework/tools/al-exe-assembly-linker.md)。</span><span class="sxs-lookup"><span data-stu-id="2473f-112">Examine the quoted error message and consult the topic [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span></span> <span data-ttu-id="2473f-113">错误 AL1019 以获取更多的解释和建议</span><span class="sxs-lookup"><span data-stu-id="2473f-113">for error AL1019 further explanation and advice</span></span>  
  
2.  <span data-ttu-id="2473f-114">如果仍然出现错误，则收集有关该情况的信息并通知 Microsoft 产品支持服务。</span><span class="sxs-lookup"><span data-stu-id="2473f-114">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2473f-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="2473f-115">See Also</span></span>  
 [<span data-ttu-id="2473f-116">如何：使用强名称为程序集签名</span><span class="sxs-lookup"><span data-stu-id="2473f-116">How to: Sign an Assembly with a Strong Name</span></span>](../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md)  
 [<span data-ttu-id="2473f-117">“项目设计器”->“签名”页</span><span class="sxs-lookup"><span data-stu-id="2473f-117">Signing Page, Project Designer</span></span>](/visualstudio/ide/reference/signing-page-project-designer)  
 <span data-ttu-id="2473f-118">[Al.exe](../../../framework/tools/al-exe-assembly-linker.md)。</span><span class="sxs-lookup"><span data-stu-id="2473f-118">[Al.exe](../../../framework/tools/al-exe-assembly-linker.md).</span></span>  
 [<span data-ttu-id="2473f-119">与我们交流</span><span class="sxs-lookup"><span data-stu-id="2473f-119">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)

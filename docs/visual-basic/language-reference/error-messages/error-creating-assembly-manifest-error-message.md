---
title: "创建程序集清单时出错：&lt;错误消息&gt;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30140
- vbc30140
helpviewer_keywords: BC30140
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d846ef88f0c36b49e79b9d11252fcef419dfa0ee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="error-creating-assembly-manifest-lterror-messagegt"></a><span data-ttu-id="f3230-102">创建程序集清单时出错：&lt;错误消息&gt;</span><span class="sxs-lookup"><span data-stu-id="f3230-102">Error creating assembly manifest: &lt;error message&gt;</span></span>
<span data-ttu-id="f3230-103">[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 编译器调用程序集链接器（Al.exe，也称作 Alink）生成包含清单的程序集。</span><span class="sxs-lookup"><span data-stu-id="f3230-103">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler calls the Assembly Linker (Al.exe, also known as Alink) to generate an assembly with a manifest.</span></span> <span data-ttu-id="f3230-104">该链接器已报告在创建程序集的预发出阶段中出错。</span><span class="sxs-lookup"><span data-stu-id="f3230-104">The linker has reported an error in the pre-emission stage of creating the assembly.</span></span>  
  
 <span data-ttu-id="f3230-105">如果指定的密钥文件或密钥容器有问题，就可能发生错误。</span><span class="sxs-lookup"><span data-stu-id="f3230-105">This can occur if there are problems with the key file or the key container specified.</span></span> <span data-ttu-id="f3230-106">若要对程序集进行完全签名，必须提供包含公钥和私钥信息的有效密钥文件。</span><span class="sxs-lookup"><span data-stu-id="f3230-106">To fully sign an assembly, you must provide a valid key file that contains information about the public and private keys.</span></span> <span data-ttu-id="f3230-107">若要延迟对程序集的签名，必须选择“仅延迟签名”复选框，并提供包含公钥信息的有效密钥文件。</span><span class="sxs-lookup"><span data-stu-id="f3230-107">To delay sign an assembly, you must select the **Delay sign only** check box and provide a valid key file that contains information about the public key information.</span></span> <span data-ttu-id="f3230-108">当程序集为延迟签名时，不需要使用私有密钥。</span><span class="sxs-lookup"><span data-stu-id="f3230-108">The private key is not necessary when an assembly is delay-signed.</span></span> <span data-ttu-id="f3230-109">有关详细信息，请参阅[如何： 为程序集 (Visual Studio) 签名](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564)。</span><span class="sxs-lookup"><span data-stu-id="f3230-109">For more information, see [How to: Sign an Assembly (Visual Studio)](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564).</span></span>  
  
 <span data-ttu-id="f3230-110">**错误 ID:** BC30140</span><span class="sxs-lookup"><span data-stu-id="f3230-110">**Error ID:** BC30140</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f3230-111">更正此错误</span><span class="sxs-lookup"><span data-stu-id="f3230-111">To correct this error</span></span>  
  
1.  <span data-ttu-id="f3230-112">检查引用的错误信息并参考主题[Al.exe 工具错误和警告](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b)错误 AL1019 以获取更多的解释和建议</span><span class="sxs-lookup"><span data-stu-id="f3230-112">Examine the quoted error message and consult the topic [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) for error AL1019 further explanation and advice</span></span>  
  
2.  <span data-ttu-id="f3230-113">如果仍然出现错误，则收集有关该情况的信息并通知 Microsoft 产品支持服务。</span><span class="sxs-lookup"><span data-stu-id="f3230-113">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3230-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3230-114">See Also</span></span>  
 [<span data-ttu-id="f3230-115">如何：对程序集进行签名 (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="f3230-115">How to: Sign an Assembly (Visual Studio)</span></span>](http://msdn.microsoft.com/en-us/f468a7d3-234c-4353-924d-8e0ae5896564)  
 [<span data-ttu-id="f3230-116">“项目设计器”->“签名”页</span><span class="sxs-lookup"><span data-stu-id="f3230-116">Signing Page, Project Designer</span></span>](/visualstudio/ide/reference/signing-page-project-designer)  
 [<span data-ttu-id="f3230-117">Al.exe（程序集链接器）</span><span class="sxs-lookup"><span data-stu-id="f3230-117">Al.exe (Assembly Linker)</span></span>](https://msdn.microsoft.com/library/c405shex)  
 [<span data-ttu-id="f3230-118">Al.exe 工具错误和警告</span><span class="sxs-lookup"><span data-stu-id="f3230-118">Al.exe Tool Errors and Warnings</span></span>](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b)  
 [<span data-ttu-id="f3230-119">与我们交流</span><span class="sxs-lookup"><span data-stu-id="f3230-119">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)

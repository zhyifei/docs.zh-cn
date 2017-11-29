---
title: "错误的校验和值、非十六进制数字或奇数个十六进制数字"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc42033
- vbc42033
helpviewer_keywords: BC42033
ms.assetid: 4575554d-3615-46e4-9c6a-18e9c338e4ed
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1158742c8eaa51bcbb5607795f16ae6c2b570db4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="bad-checksum-value-non-hex-digits-or-odd-number-of-hex-digits"></a><span data-ttu-id="ac7a1-102">错误的校验和值、非十六进制数字或奇数个十六进制数字</span><span class="sxs-lookup"><span data-stu-id="ac7a1-102">Bad checksum value, non hex digits or odd number of hex digits</span></span>
<span data-ttu-id="ac7a1-103">校验和值包含无效的十六进制数字，或数字个数为奇数。</span><span class="sxs-lookup"><span data-stu-id="ac7a1-103">A checksum value contains invalid hexadecimal digits or has an odd number of digits.</span></span>  
  
 <span data-ttu-id="ac7a1-104">当 ASP.NET 生成 Visual Basic 源文件（扩展名为 .vb）时，它将计算校验和，并将其放在一个由 `#externalchecksum` 标识的隐藏的源文件中。</span><span class="sxs-lookup"><span data-stu-id="ac7a1-104">When ASP.NET generates a Visual Basic source file (extension .vb), it calculates a checksum and places it in a hidden source file identified by `#externalchecksum`.</span></span> <span data-ttu-id="ac7a1-105">生成 .vb 文件的用户也可以执行此操作，但最好将此过程保留为内部使用。</span><span class="sxs-lookup"><span data-stu-id="ac7a1-105">It is possible for a user generating a .vb file to do this also, but this process is best left to internal use.</span></span>  
  
 <span data-ttu-id="ac7a1-106">默认情况下，此消息是一个警告。</span><span class="sxs-lookup"><span data-stu-id="ac7a1-106">By default, this message is a warning.</span></span> <span data-ttu-id="ac7a1-107">有关隐藏警告或将警告视为错误的信息，请参见 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="ac7a1-107">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="ac7a1-108">**错误 ID:** BC42033</span><span class="sxs-lookup"><span data-stu-id="ac7a1-108">**Error ID:** BC42033</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ac7a1-109">更正此错误</span><span class="sxs-lookup"><span data-stu-id="ac7a1-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="ac7a1-110">如果 ASP.NET 正在生成 Visual Basic 源文件，请重新开始项目生成。</span><span class="sxs-lookup"><span data-stu-id="ac7a1-110">If ASP.NET is generating the Visual Basic source file, restart the project build.</span></span>  
  
2.  <span data-ttu-id="ac7a1-111">如果重新开始后此警告仍然存在，请重新安装 ASP.NET 并重试生成。</span><span class="sxs-lookup"><span data-stu-id="ac7a1-111">If this warning persists after restarting, reinstall ASP.NET and try the build again.</span></span>  
  
3.  <span data-ttu-id="ac7a1-112">如果警告仍然存在或者你没有使用 ASP.NET，请收集有关此情形的信息，并通知 Microsoft 产品支持服务。</span><span class="sxs-lookup"><span data-stu-id="ac7a1-112">If the warning still persists, or if you are not using ASP.NET, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac7a1-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac7a1-113">See Also</span></span>  
 [<span data-ttu-id="ac7a1-114">ASP.NET 概述</span><span class="sxs-lookup"><span data-stu-id="ac7a1-114">ASP.NET Overview</span></span>](https://msdn.microsoft.com/library/4w3ex9c2.aspx)  
 [<span data-ttu-id="ac7a1-115">与我们交流</span><span class="sxs-lookup"><span data-stu-id="ac7a1-115">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)

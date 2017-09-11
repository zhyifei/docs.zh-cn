---
title: "保存临时的 Win32 资源文件时出错&lt;filename&gt;&quot;:&lt;错误信息&gt;|Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30137
- vbc30137
dev_langs:
- VB
helpviewer_keywords:
- BC30137
ms.assetid: 61c23f48-0e06-42fc-be00-5598053c86dd
caps.latest.revision: 11
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
ms.openlocfilehash: ce0090782a930a36b65abf201baf56dc3c271a46
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="error-saving-temporary-win32-resource-file-39ltfilenamegt39-lterror-messagegt"></a><span data-ttu-id="4e351-102">保存临时的 Win32 资源文件时出错&lt;filename&gt;':&lt;错误消息&gt;</span><span class="sxs-lookup"><span data-stu-id="4e351-102">Error saving temporary Win32 resource file &#39;&lt;filename&gt;&#39;: &lt;error message&gt;</span></span>
<span data-ttu-id="4e351-103">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 编译器调用程序集链接器（Al.exe，也称作 Alink）生成包含清单的程序集。</span><span class="sxs-lookup"><span data-stu-id="4e351-103">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler calls the Assembly Linker (Al.exe, also known as Alink) to generate an assembly with a manifest.</span></span> <span data-ttu-id="4e351-104">该链接器在获取文件名以便用于写入内存中资源时报告了一个错误。</span><span class="sxs-lookup"><span data-stu-id="4e351-104">The linker reported an error obtaining a file name for use in writing an in-memory resource.</span></span>  
  
 <span data-ttu-id="4e351-105">**错误 ID:** BC30137</span><span class="sxs-lookup"><span data-stu-id="4e351-105">**Error ID:** BC30137</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4e351-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="4e351-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="4e351-107">检查引用的错误信息并参考主题[Al.exe 工具错误和警告](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b)的进一步解释和建议。</span><span class="sxs-lookup"><span data-stu-id="4e351-107">Examine the quoted error message and consult the topic [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) for further explanation and advice.</span></span>  
  
2.  <span data-ttu-id="4e351-108">如果仍然出现错误，则收集有关该情况的信息并通知 Microsoft 产品支持服务。</span><span class="sxs-lookup"><span data-stu-id="4e351-108">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e351-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4e351-109">See Also</span></span>  
 <span data-ttu-id="4e351-110">[Al.exe （程序集链接器）](https://msdn.microsoft.com/library/c405shex) </span><span class="sxs-lookup"><span data-stu-id="4e351-110">[Al.exe (Assembly Linker)](https://msdn.microsoft.com/library/c405shex) </span></span>  
<span data-ttu-id="4e351-111"> [Al.exe 工具错误和警告](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) </span><span class="sxs-lookup"><span data-stu-id="4e351-111"> [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) </span></span>  
<span data-ttu-id="4e351-112"> [与我们交流](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span><span class="sxs-lookup"><span data-stu-id="4e351-112"> [Talk to Us](https://docs.microsoft.com/visualstudio/ide/talk-to-us)</span></span>

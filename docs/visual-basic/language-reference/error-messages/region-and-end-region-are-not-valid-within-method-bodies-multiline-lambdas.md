---
title: '&#39; #Region &#39;和 &#39; #End 区域 &#39;语句不是在方法正文多行 lambda 内无效'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 614d0c7324bfbf07bc5736c799e8b54937ead081
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="39region39-and-39end-region39-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a><span data-ttu-id="46728-102">&#39; #Region &#39;和 &#39; #End 区域 &#39;语句不是在方法体/多行 lambda 内无效</span><span class="sxs-lookup"><span data-stu-id="46728-102">&#39;#Region&#39; and &#39;#End Region&#39; statements are not valid within method bodies/multiline lambdas</span></span>
<span data-ttu-id="46728-103">`#Region`块必须声明类、 模块或命名空间级别。</span><span class="sxs-lookup"><span data-stu-id="46728-103">The `#Region` block must be declared at a class, module, or namespace level.</span></span> <span data-ttu-id="46728-104">可折叠区域可以包含一个或多个过程，但它无法开头或结尾在过程内。</span><span class="sxs-lookup"><span data-stu-id="46728-104">A collapsible region can include one or more procedures, but it cannot begin or end inside of a procedure.</span></span>  
  
 <span data-ttu-id="46728-105">**错误 ID:** BC32025</span><span class="sxs-lookup"><span data-stu-id="46728-105">**Error ID:** BC32025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="46728-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="46728-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="46728-107">确保前面的过程均已正确终止与`End Function`或`End Sub`语句。</span><span class="sxs-lookup"><span data-stu-id="46728-107">Ensure that the preceding procedure is properly terminated with an `End Function` or `End Sub` statement.</span></span>  
  
2.  <span data-ttu-id="46728-108">确保`#Region`和`#End Region`指令是一种在同一个代码块中。</span><span class="sxs-lookup"><span data-stu-id="46728-108">Ensure that the `#Region` and `#End Region` directives are in the same code block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46728-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="46728-109">See Also</span></span>  
 [<span data-ttu-id="46728-110">#Region 指令</span><span class="sxs-lookup"><span data-stu-id="46728-110">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)

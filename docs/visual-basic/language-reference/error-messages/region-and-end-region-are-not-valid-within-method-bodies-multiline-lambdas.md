---
title: '#Region 和 #End Region 语句不是方法体多行 lambda 内无效'
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: deef3de645040d7c3d95b1a6c8a25fcf10de881b
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58842702"
---
# <a name="region-and-end-region-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a><span data-ttu-id="f68db-102">“#Region”和“#End Region”语句在方法体/多行 lambda 内无效</span><span class="sxs-lookup"><span data-stu-id="f68db-102">'#Region' and '#End Region' statements are not valid within method bodies/multiline lambdas</span></span>
<span data-ttu-id="f68db-103">`#Region`块必须声明类、 模块或命名空间级别。</span><span class="sxs-lookup"><span data-stu-id="f68db-103">The `#Region` block must be declared at a class, module, or namespace level.</span></span> <span data-ttu-id="f68db-104">可折叠区域可以包含一个或多个过程，但它不能开始或结束内部过程。</span><span class="sxs-lookup"><span data-stu-id="f68db-104">A collapsible region can include one or more procedures, but it cannot begin or end inside of a procedure.</span></span>  
  
 <span data-ttu-id="f68db-105">**错误 ID:** BC32025</span><span class="sxs-lookup"><span data-stu-id="f68db-105">**Error ID:** BC32025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f68db-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="f68db-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="f68db-107">确保在前面的过程正确终止与`End Function`或`End Sub`语句。</span><span class="sxs-lookup"><span data-stu-id="f68db-107">Ensure that the preceding procedure is properly terminated with an `End Function` or `End Sub` statement.</span></span>  
  
2.  <span data-ttu-id="f68db-108">絋粄`#Region`和`#End Region`指令是同一个代码块中。</span><span class="sxs-lookup"><span data-stu-id="f68db-108">Ensure that the `#Region` and `#End Region` directives are in the same code block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f68db-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="f68db-109">See also</span></span>

- [<span data-ttu-id="f68db-110">#Region 指令</span><span class="sxs-lookup"><span data-stu-id="f68db-110">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)

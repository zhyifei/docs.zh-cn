---
title: '&#39;#Region&#39;和&#39;#End 区域&#39;语句不是方法体多行 lambda 内无效'
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: 55399cd123ce4d67cc833f2eabe3230acdafc0bf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737210"
---
# <a name="39region39-and-39end-region39-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a><span data-ttu-id="47b84-102">&#39;#Region&#39;和&#39;#End 区域&#39;语句不是方法体/多行 lambda 内无效</span><span class="sxs-lookup"><span data-stu-id="47b84-102">&#39;#Region&#39; and &#39;#End Region&#39; statements are not valid within method bodies/multiline lambdas</span></span>
<span data-ttu-id="47b84-103">`#Region`块必须声明类、 模块或命名空间级别。</span><span class="sxs-lookup"><span data-stu-id="47b84-103">The `#Region` block must be declared at a class, module, or namespace level.</span></span> <span data-ttu-id="47b84-104">可折叠区域可以包含一个或多个过程，但它不能开始或结束内部过程。</span><span class="sxs-lookup"><span data-stu-id="47b84-104">A collapsible region can include one or more procedures, but it cannot begin or end inside of a procedure.</span></span>  
  
 <span data-ttu-id="47b84-105">**错误 ID:** BC32025</span><span class="sxs-lookup"><span data-stu-id="47b84-105">**Error ID:** BC32025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="47b84-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="47b84-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="47b84-107">确保在前面的过程正确终止与`End Function`或`End Sub`语句。</span><span class="sxs-lookup"><span data-stu-id="47b84-107">Ensure that the preceding procedure is properly terminated with an `End Function` or `End Sub` statement.</span></span>  
  
2.  <span data-ttu-id="47b84-108">絋粄`#Region`和`#End Region`指令是同一个代码块中。</span><span class="sxs-lookup"><span data-stu-id="47b84-108">Ensure that the `#Region` and `#End Region` directives are in the same code block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47b84-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="47b84-109">See also</span></span>
- [<span data-ttu-id="47b84-110">#Region 指令</span><span class="sxs-lookup"><span data-stu-id="47b84-110">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)

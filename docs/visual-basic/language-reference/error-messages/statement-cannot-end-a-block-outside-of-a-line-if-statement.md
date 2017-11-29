---
title: "语句不能之外结束块行 &#39; 如果 &#39;语句"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords: BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 73fe3eb44e904366db7d505bbe8c5fef461eb78b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-39if39-statement"></a><span data-ttu-id="c36ab-102">语句不能之外结束块行 &#39; 如果 &#39;语句</span><span class="sxs-lookup"><span data-stu-id="c36ab-102">Statement cannot end a block outside of a line &#39;If&#39; statement</span></span>
<span data-ttu-id="c36ab-103">单线条`If`语句包含用冒号 （:），其中之一是分隔的多条语句`End`控制块的外部的单行语句`If`。</span><span class="sxs-lookup"><span data-stu-id="c36ab-103">A single-line `If` statement contains several statements separated by colons (:), one of which is an `End` statement for a control block outside the single-line `If`.</span></span> <span data-ttu-id="c36ab-104">单行`If`语句不使用`End If`语句。</span><span class="sxs-lookup"><span data-stu-id="c36ab-104">Single-line `If` statements do not use the `End If` statement.</span></span>  
  
 <span data-ttu-id="c36ab-105">**错误 ID:** BC32005</span><span class="sxs-lookup"><span data-stu-id="c36ab-105">**Error ID:** BC32005</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c36ab-106">更正此错误</span><span class="sxs-lookup"><span data-stu-id="c36ab-106">To correct this error</span></span>  
  
-   <span data-ttu-id="c36ab-107">移动单线条`If`外部控制块包含语句`End If`语句。</span><span class="sxs-lookup"><span data-stu-id="c36ab-107">Move the single-line `If` statement outside the control block that contains the `End If` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c36ab-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c36ab-108">See Also</span></span>  
 [<span data-ttu-id="c36ab-109">If...Then...Else 语句</span><span class="sxs-lookup"><span data-stu-id="c36ab-109">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)

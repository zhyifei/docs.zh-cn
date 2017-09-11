---
title: "模块&lt;关键字&gt;(Visual Basic 中) |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ModuleAttribute
dev_langs:
- VB
helpviewer_keywords:
- Module keyword
- Module modifier
- attribute blocks, Module keyword
ms.assetid: d971b940-05ab-4d56-8485-e3b8a661906b
caps.latest.revision: 13
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
ms.openlocfilehash: 7554c397fbfd3cd61cf19f760eb4664e2deb589b
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="module-ltkeywordgt-visual-basic"></a><span data-ttu-id="e988a-102">模块&lt;关键字&gt;(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e988a-102">Module &lt;keyword&gt; (Visual Basic)</span></span>
<span data-ttu-id="e988a-103">指定源文件开头特性应用于当前程序集模块。</span><span class="sxs-lookup"><span data-stu-id="e988a-103">Specifies that an attribute at the beginning of a source file applies to the current assembly module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e988a-104">备注</span><span class="sxs-lookup"><span data-stu-id="e988a-104">Remarks</span></span>  
 <span data-ttu-id="e988a-105">很多特性适用于单个的编程元素，例如一个类或属性。</span><span class="sxs-lookup"><span data-stu-id="e988a-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="e988a-106">通过将附加特性块，在尖括号中的应用此类属性 (`< >`)，直接到声明语句。</span><span class="sxs-lookup"><span data-stu-id="e988a-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="e988a-107">如果属性不仅到下面的元素，而且当前的程序集模块，您的源文件的起始处放置属性块，并确定具有的属性`Module`关键字。</span><span class="sxs-lookup"><span data-stu-id="e988a-107">If an attribute pertains not only to the following element but to the current assembly module, you place the attribute block at the beginning of the source file and identify the attribute with the `Module` keyword.</span></span> <span data-ttu-id="e988a-108">如果它适用于整个程序集，则使用[程序集](../../../visual-basic/language-reference/modifiers/assembly.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="e988a-108">If it applies to the entire assembly, you use the [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) keyword.</span></span>  
  
 <span data-ttu-id="e988a-109">`Module`修饰符不可相同[模块语句](../../../visual-basic/language-reference/statements/module-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="e988a-109">The `Module` modifier is not the same as the [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e988a-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e988a-110">See Also</span></span>  
 <span data-ttu-id="e988a-111">[程序集](../../../visual-basic/language-reference/modifiers/assembly.md) </span><span class="sxs-lookup"><span data-stu-id="e988a-111">[Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) </span></span>  
<span data-ttu-id="e988a-112"> [Module 语句](../../../visual-basic/language-reference/statements/module-statement.md) </span><span class="sxs-lookup"><span data-stu-id="e988a-112"> [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md) </span></span>  
<span data-ttu-id="e988a-113"> [属性概述](../../../visual-basic/programming-guide/concepts/attributes/index.md)</span><span class="sxs-lookup"><span data-stu-id="e988a-113"> [Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md)</span></span>



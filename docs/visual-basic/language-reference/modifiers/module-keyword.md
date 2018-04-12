---
title: 模块&lt;关键字&gt;(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ModuleAttribute
helpviewer_keywords:
- Module keyword [Visual Basic]
- Module modifier
- attribute blocks, Module keyword
ms.assetid: d971b940-05ab-4d56-8485-e3b8a661906b
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1d35ad332229785f8cac76bd8099bccc85c3d3cb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="module-ltkeywordgt-visual-basic"></a><span data-ttu-id="0924c-102">模块&lt;关键字&gt;(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0924c-102">Module &lt;keyword&gt; (Visual Basic)</span></span>
<span data-ttu-id="0924c-103">指定源文件开头特性应用于当前程序集模块。</span><span class="sxs-lookup"><span data-stu-id="0924c-103">Specifies that an attribute at the beginning of a source file applies to the current assembly module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0924c-104">备注</span><span class="sxs-lookup"><span data-stu-id="0924c-104">Remarks</span></span>  
 <span data-ttu-id="0924c-105">许多属性适用于单个编程元素，例如一个类或属性。</span><span class="sxs-lookup"><span data-stu-id="0924c-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="0924c-106">通过将附加特性块，在尖括号中的应用此类属性 (`< >`)，直接向声明语句。</span><span class="sxs-lookup"><span data-stu-id="0924c-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="0924c-107">如果属性不仅到下面的元素，而且当前的程序集模块，将特性块的源文件的开始处的虚拟机和模板，用于标识与特性`Module`关键字。</span><span class="sxs-lookup"><span data-stu-id="0924c-107">If an attribute pertains not only to the following element but to the current assembly module, you place the attribute block at the beginning of the source file and identify the attribute with the `Module` keyword.</span></span> <span data-ttu-id="0924c-108">如果它适用于整个程序集，则使用[程序集](../../../visual-basic/language-reference/modifiers/assembly.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="0924c-108">If it applies to the entire assembly, you use the [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) keyword.</span></span>  
  
 <span data-ttu-id="0924c-109">`Module`修饰符不与相同[模块语句](../../../visual-basic/language-reference/statements/module-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="0924c-109">The `Module` modifier is not the same as the [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0924c-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0924c-110">See Also</span></span>  
 [<span data-ttu-id="0924c-111">Assembly</span><span class="sxs-lookup"><span data-stu-id="0924c-111">Assembly</span></span>](../../../visual-basic/language-reference/modifiers/assembly.md)  
 [<span data-ttu-id="0924c-112">Module 语句</span><span class="sxs-lookup"><span data-stu-id="0924c-112">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
 [<span data-ttu-id="0924c-113">属性概述</span><span class="sxs-lookup"><span data-stu-id="0924c-113">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)


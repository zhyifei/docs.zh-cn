---
title: 模块&lt;关键字&gt;(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ModuleAttribute
helpviewer_keywords:
- Module keyword [Visual Basic]
- Module modifier
- attribute blocks, Module keyword
ms.assetid: d971b940-05ab-4d56-8485-e3b8a661906b
ms.openlocfilehash: 3b4b09469a3f22b5e5c7faa98d5db7b3522ed236
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54586470"
---
# <a name="module-ltkeywordgt-visual-basic"></a><span data-ttu-id="62c21-102">模块&lt;关键字&gt;(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="62c21-102">Module &lt;keyword&gt; (Visual Basic)</span></span>
<span data-ttu-id="62c21-103">指定源文件开头特性应用于当前程序集模块。</span><span class="sxs-lookup"><span data-stu-id="62c21-103">Specifies that an attribute at the beginning of a source file applies to the current assembly module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62c21-104">备注</span><span class="sxs-lookup"><span data-stu-id="62c21-104">Remarks</span></span>  
 <span data-ttu-id="62c21-105">许多属性适用于单个编程元素，如类或属性。</span><span class="sxs-lookup"><span data-stu-id="62c21-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="62c21-106">此类将特性应用通过将附加特性块，在尖括号内 (`< >`)，直接向声明语句。</span><span class="sxs-lookup"><span data-stu-id="62c21-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="62c21-107">如果属性不仅到下面的元素，而且当前的程序集模块，源文件的起始处插入分的特性块和用于标识与特性`Module`关键字。</span><span class="sxs-lookup"><span data-stu-id="62c21-107">If an attribute pertains not only to the following element but to the current assembly module, you place the attribute block at the beginning of the source file and identify the attribute with the `Module` keyword.</span></span> <span data-ttu-id="62c21-108">如果应用于整个程序集，则使用[程序集](../../../visual-basic/language-reference/modifiers/assembly.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="62c21-108">If it applies to the entire assembly, you use the [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md) keyword.</span></span>  
  
 <span data-ttu-id="62c21-109">`Module`修饰符不是与相同[Module 语句](../../../visual-basic/language-reference/statements/module-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="62c21-109">The `Module` modifier is not the same as the [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62c21-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="62c21-110">See also</span></span>
- [<span data-ttu-id="62c21-111">Assembly</span><span class="sxs-lookup"><span data-stu-id="62c21-111">Assembly</span></span>](../../../visual-basic/language-reference/modifiers/assembly.md)
- [<span data-ttu-id="62c21-112">Module 语句</span><span class="sxs-lookup"><span data-stu-id="62c21-112">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)
- [<span data-ttu-id="62c21-113">属性概述</span><span class="sxs-lookup"><span data-stu-id="62c21-113">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)


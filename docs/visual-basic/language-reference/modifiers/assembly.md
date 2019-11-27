---
title: Assembly
ms.date: 07/20/2015
f1_keywords:
- vb.Assembly
- vb.AssemblyAttribute
- Assembly
helpviewer_keywords:
- Assembly modifier
- Assembly keyword [Visual Basic]
- attribute blocks, Assembly keyword
ms.assetid: 925e7471-3bdf-4b51-bb93-cbcfc6efc52f
ms.openlocfilehash: 1385919a1205a60104125fff1bdd24f409a091df
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351637"
---
# <a name="assembly-visual-basic"></a><span data-ttu-id="7d238-102">程序集 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7d238-102">Assembly (Visual Basic)</span></span>
<span data-ttu-id="7d238-103">指定源文件开头的属性应用于整个程序集。</span><span class="sxs-lookup"><span data-stu-id="7d238-103">Specifies that an attribute at the beginning of a source file applies to the entire assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7d238-104">备注</span><span class="sxs-lookup"><span data-stu-id="7d238-104">Remarks</span></span>  
 <span data-ttu-id="7d238-105">许多属性都属于单个编程元素，如类或属性。</span><span class="sxs-lookup"><span data-stu-id="7d238-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="7d238-106">您可以通过将特性块附加到尖括号（`< >`）中的属性块来应用此类属性，以便将其直接附加到声明语句。</span><span class="sxs-lookup"><span data-stu-id="7d238-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="7d238-107">如果某个特性不仅与以下元素有关，而与整个程序集不同，则您将特性块放在源文件的开头，并使用 `Assembly` 关键字标识该特性。</span><span class="sxs-lookup"><span data-stu-id="7d238-107">If an attribute pertains not only to the following element but to the entire assembly, you place the attribute block at the beginning of the source file and identify the attribute with the `Assembly` keyword.</span></span> <span data-ttu-id="7d238-108">如果它适用于当前程序集模块，则使用[module](../../../visual-basic/language-reference/modifiers/module-keyword.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="7d238-108">If it applies to the current assembly module, you use the [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md) keyword.</span></span>  
  
 <span data-ttu-id="7d238-109">你还可以在 AssemblyInfo 文件中将属性应用于程序集，在这种情况下，你不必在主源代码文件中使用属性块。</span><span class="sxs-lookup"><span data-stu-id="7d238-109">You can also apply an attribute to an assembly in the AssemblyInfo.vb file, in which case you do not have to use an attribute block in your main source-code file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d238-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7d238-110">See also</span></span>

- [<span data-ttu-id="7d238-111">Module \<关键字></span><span class="sxs-lookup"><span data-stu-id="7d238-111">Module \<keyword></span></span>](../../../visual-basic/language-reference/modifiers/module-keyword.md)
- [<span data-ttu-id="7d238-112">属性概述</span><span class="sxs-lookup"><span data-stu-id="7d238-112">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)

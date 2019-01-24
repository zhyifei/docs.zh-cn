---
title: 程序集 (Visual Basic)
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
ms.openlocfilehash: e6cb7e7a2520d6bb586dab4ed0af75abb04fabd2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54726463"
---
# <a name="assembly-visual-basic"></a><span data-ttu-id="ffca2-102">程序集 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ffca2-102">Assembly (Visual Basic)</span></span>
<span data-ttu-id="ffca2-103">指定源文件开头特性应用于整个程序集。</span><span class="sxs-lookup"><span data-stu-id="ffca2-103">Specifies that an attribute at the beginning of a source file applies to the entire assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ffca2-104">备注</span><span class="sxs-lookup"><span data-stu-id="ffca2-104">Remarks</span></span>  
 <span data-ttu-id="ffca2-105">许多属性适用于单个编程元素，如类或属性。</span><span class="sxs-lookup"><span data-stu-id="ffca2-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="ffca2-106">此类将特性应用通过将附加特性块，在尖括号内 (`< >`)，直接向声明语句。</span><span class="sxs-lookup"><span data-stu-id="ffca2-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="ffca2-107">如果属性不仅到下面的元素，而且整个程序集，源文件的起始处插入分的特性块和用于标识与特性`Assembly`关键字。</span><span class="sxs-lookup"><span data-stu-id="ffca2-107">If an attribute pertains not only to the following element but to the entire assembly, you place the attribute block at the beginning of the source file and identify the attribute with the `Assembly` keyword.</span></span> <span data-ttu-id="ffca2-108">如果应用于当前程序集模块，则使用[模块](../../../visual-basic/language-reference/modifiers/module-keyword.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="ffca2-108">If it applies to the current assembly module, you use the [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md) keyword.</span></span>  
  
 <span data-ttu-id="ffca2-109">您可以还将特性应用于程序集在 AssemblyInfo.vb 文件中，在这种情况下不需要在主源代码文件中使用特性块。</span><span class="sxs-lookup"><span data-stu-id="ffca2-109">You can also apply an attribute to an assembly in the AssemblyInfo.vb file, in which case you do not have to use an attribute block in your main source-code file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffca2-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="ffca2-110">See also</span></span>
- [<span data-ttu-id="ffca2-111">Module \<关键字></span><span class="sxs-lookup"><span data-stu-id="ffca2-111">Module \<keyword></span></span>](../../../visual-basic/language-reference/modifiers/module-keyword.md)
- [<span data-ttu-id="ffca2-112">属性概述</span><span class="sxs-lookup"><span data-stu-id="ffca2-112">Attributes overview</span></span>](../../../visual-basic/programming-guide/concepts/attributes/index.md)


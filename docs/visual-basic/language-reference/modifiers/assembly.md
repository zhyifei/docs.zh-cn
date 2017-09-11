---
title: "程序集 (Visual Basic 中) |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Assembly
- vb.AssemblyAttribute
- Assembly
dev_langs:
- VB
helpviewer_keywords:
- Assembly modifier
- Assembly keyword
- attribute blocks, Assembly keyword
ms.assetid: 925e7471-3bdf-4b51-bb93-cbcfc6efc52f
caps.latest.revision: 15
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
ms.openlocfilehash: b83102c24c80b7ee6ec4c0ffc4a446e26b7811cf
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="assembly-visual-basic"></a><span data-ttu-id="66213-102">程序集 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="66213-102">Assembly (Visual Basic)</span></span>
<span data-ttu-id="66213-103">指定源文件开头特性应用于整个程序集。</span><span class="sxs-lookup"><span data-stu-id="66213-103">Specifies that an attribute at the beginning of a source file applies to the entire assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66213-104">备注</span><span class="sxs-lookup"><span data-stu-id="66213-104">Remarks</span></span>  
 <span data-ttu-id="66213-105">很多特性适用于单个的编程元素，例如一个类或属性。</span><span class="sxs-lookup"><span data-stu-id="66213-105">Many attributes pertain to an individual programming element, such as a class or property.</span></span> <span data-ttu-id="66213-106">通过将附加特性块，在尖括号中的应用此类属性 (`< >`)，直接到声明语句。</span><span class="sxs-lookup"><span data-stu-id="66213-106">You apply such an attribute by attaching the attribute block, within angle brackets (`< >`), directly to the declaration statement.</span></span>  
  
 <span data-ttu-id="66213-107">如果属性不仅到下面的元素，而且整个程序集，源文件开头插入分特性块和标识与该特性`Assembly`关键字。</span><span class="sxs-lookup"><span data-stu-id="66213-107">If an attribute pertains not only to the following element but to the entire assembly, you place the attribute block at the beginning of the source file and identify the attribute with the `Assembly` keyword.</span></span> <span data-ttu-id="66213-108">如果它适用于当前程序集模块，则使用[模块](../../../visual-basic/language-reference/modifiers/module-keyword.md)关键字。</span><span class="sxs-lookup"><span data-stu-id="66213-108">If it applies to the current assembly module, you use the [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md) keyword.</span></span>  
  
 <span data-ttu-id="66213-109">您还可以将属性为程序集在 AssemblyInfo.vb 文件中，在这种情况下不需要使用主源代码文件中的属性块。</span><span class="sxs-lookup"><span data-stu-id="66213-109">You can also apply an attribute to an assembly in the AssemblyInfo.vb file, in which case you do not have to use an attribute block in your main source-code file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66213-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="66213-110">See Also</span></span>  
 <span data-ttu-id="66213-111">[模块\<关键字&1;>](../../../visual-basic/language-reference/modifiers/module-keyword.md) </span><span class="sxs-lookup"><span data-stu-id="66213-111">[Module \<keyword>](../../../visual-basic/language-reference/modifiers/module-keyword.md) </span></span>  
<span data-ttu-id="66213-112"> [属性概述](../../../visual-basic/programming-guide/concepts/attributes/index.md)</span><span class="sxs-lookup"><span data-stu-id="66213-112"> [Attributes overview](../../../visual-basic/programming-guide/concepts/attributes/index.md)</span></span>



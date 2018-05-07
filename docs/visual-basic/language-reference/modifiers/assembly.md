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
ms.openlocfilehash: 7ee6cddefd5955ee76510ffeb23335f05460657b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="assembly-visual-basic"></a>程序集 (Visual Basic)
指定源文件开头特性应用于整个程序集。  
  
## <a name="remarks"></a>备注  
 许多属性适用于单个编程元素，例如一个类或属性。 通过将附加特性块，在尖括号中的应用此类属性 (`< >`)，直接向声明语句。  
  
 如果属性不仅到下面的元素，而且整个程序集，将特性块的源文件的开始处的虚拟机和模板，用于标识与特性`Assembly`关键字。 如果它适用于当前的程序集模块，则使用[模块](../../../visual-basic/language-reference/modifiers/module-keyword.md)关键字。  
  
 你可以还将特性应用于程序集在 AssemblyInfo.vb 文件中，在这种情况下则不需要主源代码文件中使用特性块。  
  
## <a name="see-also"></a>请参阅  
 [Module \<关键字>](../../../visual-basic/language-reference/modifiers/module-keyword.md)  
 [属性概述](../../../visual-basic/programming-guide/concepts/attributes/index.md)


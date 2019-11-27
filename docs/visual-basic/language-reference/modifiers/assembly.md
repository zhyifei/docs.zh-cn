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
# <a name="assembly-visual-basic"></a>程序集 (Visual Basic)
指定源文件开头的属性应用于整个程序集。  
  
## <a name="remarks"></a>备注  
 许多属性都属于单个编程元素，如类或属性。 您可以通过将特性块附加到尖括号（`< >`）中的属性块来应用此类属性，以便将其直接附加到声明语句。  
  
 如果某个特性不仅与以下元素有关，而与整个程序集不同，则您将特性块放在源文件的开头，并使用 `Assembly` 关键字标识该特性。 如果它适用于当前程序集模块，则使用[module](../../../visual-basic/language-reference/modifiers/module-keyword.md)关键字。  
  
 你还可以在 AssemblyInfo 文件中将属性应用于程序集，在这种情况下，你不必在主源代码文件中使用属性块。  
  
## <a name="see-also"></a>另请参阅

- [Module \<关键字>](../../../visual-basic/language-reference/modifiers/module-keyword.md)
- [属性概述](../../../visual-basic/programming-guide/concepts/attributes/index.md)

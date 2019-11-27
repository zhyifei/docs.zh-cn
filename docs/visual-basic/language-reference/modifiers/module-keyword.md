---
title: 模块 <keyword>
ms.date: 07/20/2015
f1_keywords:
- vb.ModuleAttribute
helpviewer_keywords:
- Module keyword [Visual Basic]
- Module modifier
- attribute blocks, Module keyword
ms.assetid: d971b940-05ab-4d56-8485-e3b8a661906b
ms.openlocfilehash: cd2f762181b5a702f0b0defd5b71bb7bdf129c7b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351549"
---
# <a name="module-keyword-visual-basic"></a>模块 \<关键字 > （Visual Basic）
指定源文件开头的属性应用于当前程序集模块。  
  
## <a name="remarks"></a>备注  
 许多属性都属于单个编程元素，如类或属性。 您可以通过将特性块附加到尖括号（`< >`）中的属性块来应用此类属性，以便将其直接附加到声明语句。  
  
 如果特性不仅与以下元素有关，而与当前程序集模块有关，请将特性块放在源文件的开头，并使用 `Module` 关键字标识特性。 如果它适用于整个程序集，则可以使用[assembly](../../../visual-basic/language-reference/modifiers/assembly.md)关键字。  
  
 `Module` 修饰符与[Module 语句](../../../visual-basic/language-reference/statements/module-statement.md)不同。  
  
## <a name="see-also"></a>另请参阅

- [程序集](../../../visual-basic/language-reference/modifiers/assembly.md)
- [Module 语句](../../../visual-basic/language-reference/statements/module-statement.md)
- [属性概述](../../../visual-basic/programming-guide/concepts/attributes/index.md)

---
title: "程序集 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Assembly
- vb.AssemblyAttribute
- Assembly
helpviewer_keywords:
- Assembly modifier
- Assembly keyword [Visual Basic]
- attribute blocks, Assembly keyword
ms.assetid: 925e7471-3bdf-4b51-bb93-cbcfc6efc52f
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ef4434f0bc520abfc621567fc68e0b8bcfd6e381
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="assembly-visual-basic"></a>程序集 (Visual Basic)
指定源文件开头特性应用于整个程序集。  
  
## <a name="remarks"></a>备注  
 许多属性适用于单个编程元素，例如一个类或属性。 通过将附加特性块，在尖括号中的应用此类属性 (`< >`)，直接向声明语句。  
  
 如果属性不仅到下面的元素，而且整个程序集，将特性块的源文件的开始处的虚拟机和模板，用于标识与特性`Assembly`关键字。 如果它适用于当前的程序集模块，则使用[模块](../../../visual-basic/language-reference/modifiers/module-keyword.md)关键字。  
  
 你可以还将特性应用于程序集在 AssemblyInfo.vb 文件中，在这种情况下则不需要主源代码文件中使用特性块。  
  
## <a name="see-also"></a>另请参阅  
 [Module \<关键字>](../../../visual-basic/language-reference/modifiers/module-keyword.md)  
 [属性概述](../../../visual-basic/programming-guide/concepts/attributes/index.md)


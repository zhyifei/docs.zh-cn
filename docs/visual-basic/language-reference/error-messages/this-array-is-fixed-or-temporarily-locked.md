---
title: 此数组被固定或临时锁定 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID10
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: adff10d4ae61e45402df64ebaa3baf146371ff9e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="this-array-is-fixed-or-temporarily-locked-visual-basic"></a>此数组被固定或临时锁定 (Visual Basic)
此错误具有以下可能的原因：  
  
-   使用`ReDim`若要更改的固定大小数组的元素数。  
  
-   Redimensioning 模块级别动态数组，其中的一个元素具有作为参数传递给过程。 如果元素已传递，数组被锁定以防止释放内存过程内引用参数。  
  
-   尝试将值赋给`Variant`变量包含一个数组，但`Variant`当前已锁定。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  使原始数组而不是由声明它具有固定动态`ReDim`（如果声明数组过程中），或通过声明而无需指定元素的数目 （如果在模块级别声明数组。  
  
2.  确定是否真的需要传递了元素，因为它是在模块中的所有过程内可见。  
  
3.  确定锁定`Variant`并更正它。  
  
## <a name="see-also"></a>另请参阅  
 [阵列](../../../visual-basic/programming-guide/language-features/arrays/index.md)

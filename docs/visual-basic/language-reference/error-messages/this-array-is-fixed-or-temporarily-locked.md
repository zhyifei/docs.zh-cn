---
title: 此数组是固定数组或被临时锁定
ms.date: 07/20/2015
f1_keywords:
- vbrID10
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
ms.openlocfilehash: 8d5e4add2d92a575126fb934ac3874a2e37685f5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350790"
---
# <a name="this-array-is-fixed-or-temporarily-locked-visual-basic"></a>此数组被固定或临时锁定 (Visual Basic)
此错误具有以下可能的原因：  
  
- 使用 `ReDim` 更改固定大小数组的元素数。  
  
- Redimensioning 模块级动态数组，其中一个元素已作为参数传递给过程。 如果传递了某个元素，则会锁定数组，以防在过程中为引用参数释放内存。  
  
- 尝试向包含数组的 `Variant` 变量赋值，但当前已锁定 `Variant`。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1. 通过使用 `ReDim` （如果数组在过程中进行声明）或在不指定元素数的情况下声明（如果数组在模块级别声明），使原始数组成为动态的，而不是固定的。  
  
2. 确定是否确实需要传递元素，因为它在模块中的所有过程中可见。  
  
3. 确定锁定 `Variant` 并对其进行修正。  
  
## <a name="see-also"></a>另请参阅

- [数组](../../../visual-basic/programming-guide/language-features/arrays/index.md)

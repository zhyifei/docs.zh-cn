---
title: 未能完成操作，因为目标目录位于源目录下
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: 253e7ff1d457827a2e1cb9f64eae4bfa971a3798
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54645868"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a>未能完成操作，因为目标目录位于源目录下
循环操作已失败。 循环操作正在循环，因此无法完成。 例如，对象 A 可能会尝试从对象 B 中继承，而后者反之从对象 A 中继承。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   继承时，请确保没有任何循环引用。  
  
## <a name="see-also"></a>请参阅
- [错误类型](../../visual-basic/programming-guide/language-features/error-types.md)
- [调试基础知识：断点](https://msdn.microsoft.com/library/752a02c2-0ac7-4c8b-aa1b-4b2b3b21152e)

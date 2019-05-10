---
title: 未能完成操作，因为目标目录位于源目录下
ms.date: 07/20/2015
f1_keywords:
- vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
ms.openlocfilehash: fca42f91f803a6b12535badcb25cc05cc3d23f6b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64598472"
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a>未能完成操作，因为目标目录位于源目录下
循环操作已失败。 循环操作正在循环，因此无法完成。 例如，对象 A 可能会尝试从对象 B 中继承，而后者反之从对象 A 中继承。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
- 继承时，请确保没有任何循环引用。  
  
## <a name="see-also"></a>请参阅

- [错误类型](../../visual-basic/programming-guide/language-features/error-types.md)
- [在 Visual Studio 调试器中使用断点](/visualstudio/debugger/using-breakpoints)

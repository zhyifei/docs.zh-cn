---
title: "未能完成操作，因为目标目录位于源目录下"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrIO_CyclicOperation
ms.assetid: 850d3a24-5d51-4ac8-a912-630efcd75278
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 429d679157d25655ca73afef14ecd642f7cac37f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="could-not-complete-operation-since-target-directory-is-under-source-directory"></a>未能完成操作，因为目标目录位于源目录下
循环操作已失败。 循环操作正在循环，因此无法完成。 例如，对象 A 可能会尝试从对象 B 中继承，而后者反之从对象 A 中继承。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   继承时，请确保没有任何循环引用。  
  
## <a name="see-also"></a>另请参阅  
 [错误类型](../../visual-basic/programming-guide/language-features/error-types.md)  
 [调试基础知识： 断点](http://msdn.microsoft.com/en-us/752a02c2-0ac7-4c8b-aa1b-4b2b3b21152e)

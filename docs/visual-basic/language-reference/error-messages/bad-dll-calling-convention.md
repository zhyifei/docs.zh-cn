---
title: "错误的 DLL 调用约定"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID49
ms.assetid: 7c7def45-b0ab-450f-ad3f-4383dfd9aed7
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: daa84e82d2fbe1041af56fdd5cc3855efd814ddf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="bad-dll-calling-convention"></a>错误的 DLL 调用约定
自变量传递给动态链接库 (DLL) 必须完全匹配所需要的例程。 调用约定处理数量、 类型和参数的顺序。 程序可能在错误的类型或数量的参数被传递的 DLL 中调用例程。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  请确保所有自变量类型与要调用的例程声明中指定一致。  
  
2.  请确保您要传递要调用的例程的声明中指定的参数的相同数目。  
  
3.  如果 DLL 例程需要按值的自变量，请确保`ByVal`例程的声明中为这些参数指定。  
  
## <a name="see-also"></a>另请参阅  
 [错误类型](../../../visual-basic/programming-guide/language-features/error-types.md)  
 [Call 语句](../../../visual-basic/language-reference/statements/call-statement.md)  
 [Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md)

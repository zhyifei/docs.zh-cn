---
title: "序号无效"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID452
ms.assetid: 7459562b-cd4f-4590-95e0-6126ae3589a5
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d31d0fba19cc16004c0b56786af30603d0c509ea
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ordinal-is-not-valid"></a>序号无效
对动态链接库 (DLL) 的调用指示而不是过程名称，后面使用一个数字使用`#num`语法。 此错误具有以下可能的原因：  
  
-   尝试转换`#num`为序号失败的表达式。  
  
-   `#num`指定 DLL 中未指定任何函数。  
  
-   类型库中有一个无效的声明，从而导致无效的序号在内部使用。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  请确保表达式表示一个有效的数字，或者按名称调用的过程。  
  
2.  请确保`#num`标识 DLL 中的有效函数。  
  
3.  隔离导致问题的注释掉的代码的过程调用。 编写`Declare`语句的过程中和报表的问题类型库供应商联系。  
  
## <a name="see-also"></a>另请参阅  
 [Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md)

---
title: 需要“Optional”
ms.date: 07/20/2015
f1_keywords:
- bc30202
- vbc30202
helpviewer_keywords:
- BC30202
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
ms.openlocfilehash: 0ad0d0890b73103a0678b13409a24190329d37d4
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55266317"
---
# <a name="optional-expected"></a>需要“Optional”
过程声明中的可选自变量后跟一个必需的参数。 每个自变量跟在可选参数还必须是可选的。  
  
 **错误 ID:** BC30202  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  如果参数是要将所需，移动它，以在参数列表中前面的第一个可选参数。  
  
2.  如果此参数是为可选，使用`Optional`关键字。  
  
## <a name="see-also"></a>请参阅
- [可选参数](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)

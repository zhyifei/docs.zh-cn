---
title: Nothing 和字符串 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: d03781209f0f9b021d540bd251c6c6025ad21422
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647162"
---
# <a name="nothing-and-strings-in-visual-basic"></a>Nothing 和字符串 (Visual Basic)
Visual Basic 运行时和[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]评估`Nothing`以不同方式当涉及到字符串。  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a>Visual Basic 运行时和.NET Framework  
 请看下面的示例：  
  
 [!code-vb[VbVbalrStrings#47](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/nothing-and-strings_1.vb)]  
  
 Visual Basic 运行时通常计算结果`Nothing`为一个空字符串 ("")。 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]不存在，但是，并在引发异常，每当尝试对执行字符串操作`Nothing`。  
  
## <a name="see-also"></a>请参阅  
 [Visual Basic 中的字符串简介](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)

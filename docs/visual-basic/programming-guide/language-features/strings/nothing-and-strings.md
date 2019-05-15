---
title: Nothing 和字符串 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: f5c1ea8cc0728b25e8e874963967aed504e466d7
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591343"
---
# <a name="nothing-and-strings-in-visual-basic"></a>Nothing 和字符串 (Visual Basic)
Visual Basic 运行时和.NET Framework 的计算结果`Nothing`以不同的方式时涉及到字符串。  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a>Visual Basic 运行时和.NET Framework  
 请看下面的示例：  
  
 [!code-vb[VbVbalrStrings#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#47)]  
  
 Visual Basic 运行时通常计算结果`Nothing`为空字符串 ("")。 .NET Framework 却没有，但是，并引发异常，只要尝试对其执行字符串操作`Nothing`。  
  
## <a name="see-also"></a>请参阅

- [Visual Basic 中的字符串简介](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)

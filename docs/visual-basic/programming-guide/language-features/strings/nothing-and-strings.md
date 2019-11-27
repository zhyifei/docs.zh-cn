---
title: Nothing 和字符串
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: dfc43748d0754f0a6a29763c42ab82d9937f89f8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344299"
---
# <a name="nothing-and-strings-in-visual-basic"></a>Nothing 和字符串 (Visual Basic)
当涉及到字符串时，Visual Basic 运行时和 .NET Framework 的计算 `Nothing` 有所不同。  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a>Visual Basic 运行时和 .NET Framework  
 请看下面的示例：  
  
 [!code-vb[VbVbalrStrings#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#47)]  
  
 Visual Basic 运行时通常将 `Nothing` 计算为空字符串（""）。 但是，当尝试对 `Nothing`执行字符串操作时，.NET Framework 不会引发异常。  
  
## <a name="see-also"></a>另请参阅

- [Visual Basic 中的字符串简介](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)

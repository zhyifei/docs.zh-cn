---
title: "Nothing 和字符串 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords: strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6ce9f81f23f50e38f6b1ad5e638e8c6ac026e992
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="nothing-and-strings-in-visual-basic"></a>Nothing 和字符串 (Visual Basic)
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]运行时和[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]评估`Nothing`以不同方式当涉及到字符串。  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a>Visual Basic 运行时和.NET Framework  
 请看下面的示例：  
  
 [!code-vb[VbVbalrStrings#47](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/nothing-and-strings_1.vb)]  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]运行时通常计算结果`Nothing`为一个空字符串 ("")。 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]不存在，但是，并在引发异常，每当尝试对执行字符串操作`Nothing`。  
  
## <a name="see-also"></a>另请参阅  
 [Visual Basic 中的字符串简介](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)

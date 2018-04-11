---
title: Ansi (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Ansi
helpviewer_keywords:
- Declare statement [Visual Basic], marshaling strings [Visual Basic]
- ANSI, Visual Basic
- ANSI
ms.assetid: 4f1fa6ff-5557-41ab-b6da-90baf4c15917
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: aa5724eb9123b2776c3a579e4244c55b3129816b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ansi-visual-basic"></a>Ansi (Visual Basic)
指定 Visual Basic 应封送到美国国家标准学会 (ANSI) 值，无论所声明的外部过程的名称的所有字符串。  
  
 在调用在项目外部定义的过程时，Visual Basic 编译器没有正确调用该过程所需的信息的访问。 此信息包括过程所在的位置、 标识的方式、 其调用的序列和返回类型和字符串字符将其设置使用。 [声明语句](../../../visual-basic/language-reference/statements/declare-statement.md)创建对外部过程的引用，并提供这些必需的信息。  
  
 `charsetmodifier`部分`Declare`语句提供期间对外部过程的调用封送处理字符串的字符组信息。 它还会影响 Visual Basic 会外部过程名称的外部文件的搜索。 `Ansi`修饰符指定 Visual Basic 应封送的所有字符串转换为 ANSI 值和应查找而无需在搜索过程中修改其名称的过程。  
  
 如果不指定任何字符集修饰符，则`Ansi`是默认设置。  
  
## <a name="remarks"></a>备注  
 `Ansi`修饰符可用于在此上下文中：  
  
 [Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>智能设备的开发人员说明  
 此关键字不受支持。  
  
## <a name="see-also"></a>另请参阅  
 [Auto](../../../visual-basic/language-reference/modifiers/auto.md)  
 [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)  
 [关键字](../../../visual-basic/language-reference/keywords/index.md)

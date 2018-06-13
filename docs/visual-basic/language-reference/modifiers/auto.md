---
title: Auto (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Auto
helpviewer_keywords:
- Auto keyword [Visual Basic], external references
- Declare statement [Visual Basic], marshaling strings
- Auto keyword [Visual Basic]
- Auto keyword [Visual Basic], marshaling strings
ms.assetid: bf79ba95-a62c-48a5-916f-0ac7a52c13ec
ms.openlocfilehash: 414998b4bef526060e7ba4f584fa071fbd0acaa5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595870"
---
# <a name="auto-visual-basic"></a>Auto (Visual Basic)
指定 Visual Basic 应封送根据.NET Framework 规则基于所声明的外部过程的外部名称的字符串。  
  
 在调用在项目外部定义的过程时，Visual Basic 编译器没有访问它必须具有正确调用过程的信息。 此信息包括过程所在的位置、 标识的方式、 其调用的序列和返回类型和字符串字符将其设置使用。 [声明语句](../../../visual-basic/language-reference/statements/declare-statement.md)创建对外部过程的引用，并提供这些必需的信息。  
  
 `charsetmodifier`部分`Declare`语句提供期间对外部过程的调用封送处理字符串的字符组信息。 它还会影响 Visual Basic 会外部过程名称的外部文件的搜索。 `Auto`修饰符指定 Visual Basic 应封送字符串根据.NET Framework 规则和，它应确定将运行时平台的和可能的基字符集修改外部过程名称，如果初始搜索无法正常工作。 有关详细信息，请参阅"字符集"[声明语句](../../../visual-basic/language-reference/statements/declare-statement.md)。  
  
 如果不指定任何字符集修饰符，则`Ansi`是默认设置。  
  
## <a name="remarks"></a>备注  
 `Auto`修饰符可用于在此上下文中：  
  
 [Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>智能设备的开发人员说明  
 此关键字不受支持。  
  
## <a name="see-also"></a>请参阅  
 [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md)  
 [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)  
 [关键字](../../../visual-basic/language-reference/keywords/index.md)

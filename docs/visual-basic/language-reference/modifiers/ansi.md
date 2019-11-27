---
title: Ansi
ms.date: 07/20/2015
f1_keywords:
- vb.Ansi
helpviewer_keywords:
- Declare statement [Visual Basic], marshaling strings [Visual Basic]
- ANSI, Visual Basic
- ANSI
ms.assetid: 4f1fa6ff-5557-41ab-b6da-90baf4c15917
ms.openlocfilehash: 0c38c2b81af7b4cb8fd1723853a09c5413f805af
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344744"
---
# <a name="ansi-visual-basic"></a>Ansi (Visual Basic)
指定 Visual Basic 应将所有字符串封送到美国国家标准学会（ANSI）值，而不考虑所声明的外部过程的名称。  
  
 调用在项目外部定义的过程时，Visual Basic 编译器无法访问正确调用过程所需的信息。 此信息包括过程的位置、标识方法、调用序列和返回类型，以及它使用的字符串字符集。 [Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md)创建对外部过程的引用并提供此必要信息。  
  
 `Declare` 语句中 `charsetmodifier` 部分提供了在调用外部过程期间封送处理字符串的字符集信息。 它还会影响 Visual Basic 搜索外部文件的外部过程名称的方式。 `Ansi` 修饰符指定 Visual Basic 应将所有字符串封送为 ANSI 值，并应在搜索过程中查找过程而不修改其名称。  
  
 如果未指定字符集修饰符，则默认值为 `Ansi`。  
  
## <a name="remarks"></a>备注  
 `Ansi` 修饰符可用于以下上下文：  
  
 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>智能设备开发人员说明  
 不支持此关键字。  
  
## <a name="see-also"></a>另请参阅

- [Auto](../../../visual-basic/language-reference/modifiers/auto.md)
- [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md)
- [关键字](../../../visual-basic/language-reference/keywords/index.md)

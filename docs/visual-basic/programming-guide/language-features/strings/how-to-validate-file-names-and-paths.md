---
title: 如何：验证文件的名称和在 Visual Basic 中的路径
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], validating
- strings [Visual Basic], validating
- Boolean values [Visual Basic]
- paths [Visual Basic], validating
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
ms.openlocfilehash: c0d39ecbaf9ca23c72e45b8839d268fbc38fe48e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54648444"
---
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a>如何：验证文件的名称和在 Visual Basic 中的路径
此示例返回`Boolean`值，该值指示字符串是否表示文件名称或路径。 验证检查名称是否包含不允许使用的文件系统的字符。  
  
## <a name="example"></a>示例  
 [!code-vb[VbVbcnRegEx#4](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/how-to-validate-file-names-and-paths_1.vb)]  
  
 此示例不会检查，如果名称不正确放置冒号或目录没有名称或名称的长度超过系统定义的最大长度。 它也不会检查应用程序是否具有指定名称的文件系统资源的访问权。  
  
## <a name="see-also"></a>请参阅
- <xref:System.IO.Path.GetInvalidPathChars%2A>
- [在 Visual Basic 中验证字符串](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)

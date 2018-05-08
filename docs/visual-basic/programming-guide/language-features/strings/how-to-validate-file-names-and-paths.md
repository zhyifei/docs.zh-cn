---
title: 如何：在 Visual Basic 中验证文件名和路径
ms.date: 07/20/2015
helpviewer_keywords:
- file names [Visual Basic], validating
- strings [Visual Basic], validating
- Boolean values [Visual Basic]
- paths [Visual Basic], validating
ms.assetid: f673462d-57b7-4120-b13a-6a7592f7ab2c
ms.openlocfilehash: ab3df335bc5bba21d386bb69b12d840990e629fe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-validate-file-names-and-paths-in-visual-basic"></a>如何：在 Visual Basic 中验证文件名和路径
此示例返回`Boolean`值，该值指示字符串是否表示文件名称或路径。 如果名称包含不允许的文件系统的字符的验证检查。  
  
## <a name="example"></a>示例  
 [!code-vb[VbVbcnRegEx#4](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/how-to-validate-file-names-and-paths_1.vb)]  
  
 此示例不会检查，如果未冒号或不具有名称的目录位置名称，不正确或名称的长度超过了系统定义的最大长度。 它也不会检查应用程序是否具有指定名称的文件系统资源的访问权。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.IO.Path.GetInvalidPathChars%2A>  
 [在 Visual Basic 中验证字符串](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)

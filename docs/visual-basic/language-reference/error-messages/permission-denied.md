---
title: 权限被拒绝 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID70
ms.assetid: 71f46756-f522-4814-aab4-492bf9924245
ms.openlocfilehash: b814d041fe312220d30d8faf4674f809d8ddc8ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="permission-denied-visual-basic"></a>权限被拒绝 (Visual Basic)
试图写入写保护的磁盘或访问锁定的文件。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  若要打开写保护的文件，请更改文件的写保护属性。  
  
2.  请确定另一个进程没有已锁定该文件，然后等待直到另一个进程释放它打开的文件。  
  
3.  若要访问注册表，请检查您的用户权限，包括此类型的注册表访问。  
  
## <a name="see-also"></a>请参阅  
 [错误类型](../../../visual-basic/programming-guide/language-features/error-types.md)

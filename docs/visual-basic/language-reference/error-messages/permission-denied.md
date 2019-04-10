---
title: 权限被拒绝 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID70
ms.assetid: 71f46756-f522-4814-aab4-492bf9924245
ms.openlocfilehash: ad75c556748bf5c0f9cef55310c4ffa7b01fd458
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59318821"
---
# <a name="permission-denied-visual-basic"></a>权限被拒绝 (Visual Basic)
尝试写入受写保护的磁盘或访问锁定的文件。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1. 若要打开受写保护的文件，请更改文件的写保护属性。  
  
2. 请确保另一个进程已不锁定该文件，并等待，直到另一个进程释放它打开该文件。  
  
3. 若要访问注册表，请检查您的用户权限，包括此类型的注册表访问。  
  
## <a name="see-also"></a>请参阅

- [错误类型](../../../visual-basic/programming-guide/language-features/error-types.md)

---
title: 加载 DLL 时出错 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID48
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
ms.openlocfilehash: ac21c4d52b248025ee26bac3e511bb5b0a0b668e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="error-in-loading-dll-visual-basic"></a>加载 DLL 时出错 (Visual Basic)
动态链接库 (DLL) 是中指定一个库`Lib`子句`Declare`语句。 此错误的可能原因包括：  
  
-   文件不是可执行的 DLL。  
  
-   文件不是 Microsoft Windows DLL。  
  
-   DLL 引用不存在的另一个 DLL。  
  
-   DLL 或引用的 DLL 不在路径中指定的目录。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   如果源文本文件，因此不 DLL 的可执行文件，该文件，它必须为编译并链接到 DLL 的可执行文件窗体。  
  
-   如果文件不是 Microsoft Windows DLL，获取 Microsoft Windows 等效。  
  
-   如果 DLL 引用不存在的另一个 DLL，获取引用的 DLL 并使其可用。  
  
-   如果 DLL 或引用的 DLL 不是指定的路径的目录，请将 DLL 移动到引用的目录。  
  
## <a name="see-also"></a>请参阅  
 [Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md)

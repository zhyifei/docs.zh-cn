---
title: Stop 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Stop
helpviewer_keywords:
- breakpoints, Stop statements
- Stop statements [Visual Basic], syntax
- Stop statements [Visual Basic]
- execution [Visual Basic], suspending
- processing, interrupting
- processes, interrupting
- execution [Visual Basic], stopping
ms.assetid: c9a9fde0-d649-4662-9bef-bd0146ebc2a7
ms.openlocfilehash: 955a3b6a2f7dc1d0e9823ed6d500ab7f7f9fe5b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="stop-statement-visual-basic"></a>Stop 语句 (Visual Basic)
挂起执行。  
  
## <a name="syntax"></a>语法  
  
```  
Stop  
```  
  
## <a name="remarks"></a>备注  
 你可以将放置`Stop`语句暂停执行的过程中的任何位置。 使用`Stop`语句是相似的代码中设置断点。  
  
 `Stop`语句挂起执行，但与`End`，它不会关闭任何文件或清除任何变量，除非在已编译可执行文件 (.exe) 文件中遇到。  
  
> [!NOTE]
>  如果`Stop`在集成的开发环境 (IDE) 外部运行的代码中遇到语句，将调用调试器。 无论是如此代码是否在调试版本还是发布模式下进行编译。  
  
## <a name="example"></a>示例  
 此示例使用`Stop`语句暂停执行以便每个循环访问`For...Next`循环。  
  
 [!code-vb[VbVbalrStatements#56](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/stop-statement_1.vb)]  
  
## <a name="see-also"></a>请参阅  
 [End 语句](../../../visual-basic/language-reference/statements/end-statement.md)

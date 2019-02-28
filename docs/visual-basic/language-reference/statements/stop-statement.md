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
ms.openlocfilehash: 590ac27ebab881353a69077aabdf7a2def3396a6
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967837"
---
# <a name="stop-statement-visual-basic"></a>Stop 语句 (Visual Basic)
挂起执行。  
  
## <a name="syntax"></a>语法  
  
```  
Stop  
```  
  
## <a name="remarks"></a>备注  
 可以将放置`Stop`语句暂停执行的过程中的任意位置。 使用`Stop`语句是类似于在代码中设置断点。  
  
 `Stop`语句将暂停执行，但不同于`End`，它不会关闭任何文件或清除任何变量，除非遇到编译可执行文件 (.exe) 文件中。  
  
> [!NOTE]
>  如果`Stop`语句遇到在集成的开发环境 (IDE) 外部运行的代码中，将调用调试器。 这是无论代码是否已在调试版本还是发布模式下进行编译，则返回 true。  
  
## <a name="example"></a>示例  
 此示例使用`Stop`语句暂停执行以便每个循环访问`For...Next`循环。  
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a>请参阅
- [End 语句](../../../visual-basic/language-reference/statements/end-statement.md)

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
ms.openlocfilehash: a617038ec51d98c62b6cf7e3c124c8af01305bac
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957623"
---
# <a name="stop-statement-visual-basic"></a>Stop 语句 (Visual Basic)
挂起执行。  
  
## <a name="syntax"></a>语法  
  
```  
Stop  
```  
  
## <a name="remarks"></a>备注  
 您可以在`Stop`过程中的任何位置放置语句来挂起执行。 `Stop`使用语句与在代码中设置断点类似。  
  
 语句暂停执行, 但与此`End`不同, 它不会关闭任何文件或清除任何变量, 除非在已编译的可执行 (.exe) 文件中遇到。 `Stop`  
  
> [!NOTE]
> 如果在集成开发环境 (IDE) 外部运行的代码中遇到语句,则将调用调试器。`Stop` 无论代码是在调试模式下编译还是在发布模式下编译, 都是如此。  
  
## <a name="example"></a>示例  
 此示例使用`Stop`语句`For...Next`通过循环挂起每个迭代的执行。  
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a>请参阅

- [End 语句](../../../visual-basic/language-reference/statements/end-statement.md)

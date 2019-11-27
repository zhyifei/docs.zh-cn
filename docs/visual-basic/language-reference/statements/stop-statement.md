---
title: Stop 语句
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
ms.openlocfilehash: 497c5f207b2228412411cc3eb01976564f82bd6c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346468"
---
# <a name="stop-statement-visual-basic"></a>Stop 语句 (Visual Basic)
挂起执行。  
  
## <a name="syntax"></a>语法  
  
```vb  
Stop  
```  
  
## <a name="remarks"></a>备注  
 可以将 `Stop` 语句放置在过程中的任意位置，以挂起执行。 使用 `Stop` 语句与在代码中设置断点类似。  
  
 `Stop` 语句会挂起执行，但与 `End`不同，它不会关闭任何文件或清除任何变量，除非在已编译的可执行（.exe）文件中遇到该错误。  
  
> [!NOTE]
> 如果在集成开发环境（IDE）外部运行的代码中遇到 `Stop` 语句，则将调用调试器。 无论代码是在调试模式下编译还是在发布模式下编译，都是如此。  
  
## <a name="example"></a>示例  
 此示例使用 `Stop` 语句通过 `For...Next` 循环挂起每个迭代的执行。  
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a>另请参阅

- [End 语句](../../../visual-basic/language-reference/statements/end-statement.md)

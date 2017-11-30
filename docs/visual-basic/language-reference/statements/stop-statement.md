---
title: "Stop 语句 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Stop
helpviewer_keywords:
- breakpoints, Stop statements
- Stop statements [Visual Basic], syntax
- Stop statements [Visual Basic]
- execution [Visual Basic], suspending
- processing, interrupting
- processes, interrupting
- execution [Visual Basic], stopping
ms.assetid: c9a9fde0-d649-4662-9bef-bd0146ebc2a7
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d4b7f04214234837a86bf0c77c0d7b6934e2babd
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
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
  
## <a name="see-also"></a>另请参阅  
 [End 语句](../../../visual-basic/language-reference/statements/end-statement.md)

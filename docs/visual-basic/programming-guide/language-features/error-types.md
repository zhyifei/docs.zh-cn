---
title: 错误类型 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions, types
- errors [Visual Basic], types
- errors [Visual Basic], logic
- errors [Visual Basic], syntax
- logic errors [Visual Basic], Visual Basic
- run-time errors [Visual Basic], types of errors
- syntax errors [Visual Basic], Visual Basic
ms.assetid: 3048aabf-8c97-4e13-9150-853769cb5f6f
ms.openlocfilehash: c11b7f41dee57fc52ca1dff75734ad0b27b6a43a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647106"
---
# <a name="error-types-visual-basic"></a>错误类型 (Visual Basic)
在 Visual Basic 中，错误 (也称为*异常*) 分为三个类别之一： 语法错误、 运行时错误和逻辑错误。  
  
## <a name="syntax-errors"></a>语法错误  
 *语法错误*是指那些编写代码时出现。 Visual Basic 检查你的代码，并在你键入**代码编辑器**窗口，并提醒你如果你的错误，如拼错单词或不正确地使用一个语言元素。 语法错误是最常见的错误类型。 你可以轻松地更正这些编码的环境中就会立即发生。  
  
> [!NOTE]
>  `Option Explicit`语句是一种避免语法错误。 它会强制您可以声明，提前，所有应用程序中使用的变量。 因此，如果这些变量将用在代码中，任何排字错误立即捕获，并且可以固定的。  
  
## <a name="run-time-errors"></a>运行时错误  
 *运行时错误*是指那些仅在编译和运行你的代码后，才出现。 这些技术包括可能看起来是正确的因为它具有语法错误，但不是会执行的代码。 例如，你可以正确编写一行代码以打开文件。 如果文件已损坏，无法执行应用程序，但`Open`函数，它会停止运行。 你可以通过重写故障代码，然后重新编译并重新运行该解决大多数运行时错误。  
  
## <a name="logic-errors"></a>逻辑错误  
 *逻辑错误*是指那些出现一次应用程序正在使用。 它们是以响应用户操作的大多数通常不需要或意外结果。 例如，键入的密钥或其他外部的影响可能会导致应用程序停止工作预期参数中或完全。 逻辑错误通常是最难的类型，若要解决，因为并不总是清除它们发生的位置。  
  
## <a name="see-also"></a>请参阅  
 [Try...Catch...Finally 语句](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [调试器基础知识](/visualstudio/debugger/debugger-basics)

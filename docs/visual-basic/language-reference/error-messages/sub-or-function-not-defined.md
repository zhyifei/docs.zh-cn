---
title: 未定义 Sub 或 Function
ms.date: 07/20/2015
f1_keywords:
- vbrID35
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
ms.openlocfilehash: 8b81460eccb6be8baa2ea7bc68d0f80c9d16398e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349581"
---
# <a name="sub-or-function-not-defined-visual-basic"></a>未定义 Sub 或 Function (Visual Basic)
必须定义 `Sub` 或 `Function` 才能调用。 此错误的可能原因包括：  
  
- 错误的过程名称。  
  
- 尝试从另一个项目调用过程，而无需在 "**引用**" 对话框中显式添加对该项目的引用。  
  
- 指定对调用过程不可见的过程。  
  
- 声明不在指定的库或代码资源中的 Windows 动态链接库（DLL）例程或 Macintosh 代码资源例程。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1. 请确保过程名称拼写正确。  
  
2. 在 "**引用**" 对话框中找到包含要调用的过程的项目的名称。 如果未显示，请单击 "**浏览**" 按钮进行搜索。 选中项目名称左侧的复选框，然后单击 **"确定"** 。  
  
3. 检查例程的名称。  
  
## <a name="see-also"></a>另请参阅

- [错误类型](../../../visual-basic/programming-guide/language-features/error-types.md)
- [管理项目中的引用](/visualstudio/ide/managing-references-in-a-project)
- [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)

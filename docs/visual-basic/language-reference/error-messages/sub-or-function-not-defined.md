---
title: 未定义 Sub 或 Function (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID35
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
ms.openlocfilehash: 58e90d769d5a7f2d88b5c27d1ec7d0d28c8d7b03
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593696"
---
# <a name="sub-or-function-not-defined-visual-basic"></a>未定义 Sub 或 Function (Visual Basic)
A`Sub`或`Function`必须定义为了调用。 此错误的可能原因包括：  
  
-   过程名称拼写错误。  
  
-   尝试调用另一个项目中的过程，而无需显式添加到该项目中的引用**引用**对话框。  
  
-   指定一个对的调用的过程不可见的过程。  
  
-   声明的 Windows 动态链接库 (DLL) 例程或 Macintosh 代码资源例程不在指定的库或代码资源中。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  请确保过程名称拼写正确。  
  
2.  找到包含你想要调用的过程的项目的名称**引用**对话框。 如果没有出现，请单击**浏览**按钮对其进行搜索。 选择的项目名称，左边的复选框，然后单击**确定**。  
  
3.  请检查该例程的名称。  
  
## <a name="see-also"></a>请参阅  
 [错误类型](../../../visual-basic/programming-guide/language-features/error-types.md)  
 [管理项目中的引用](/visualstudio/ide/managing-references-in-a-project)  
 [Sub 语句](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Function 语句](../../../visual-basic/language-reference/statements/function-statement.md)

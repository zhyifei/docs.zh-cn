---
title: End 语句
ms.date: 07/20/2015
f1_keywords:
- vb.End
- End
helpviewer_keywords:
- execution [Visual Basic], ending
- files [Visual Basic], closing
- End keyword [Visual Basic], End statements
- programs [Visual Basic], quitting
- code, exiting
- program termination
- End statement [Visual Basic]
- execution [Visual Basic], stopping
ms.assetid: 0e64467c-0f34-4aab-9ddd-43f8b9d55d90
ms.openlocfilehash: 864ac5ef1713f8ffa93c18accede8ecd5b3b7a8c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604416"
---
# <a name="end-statement"></a>End 语句
会立即终止执行。  
  
## <a name="syntax"></a>语法  
  
```  
End  
```  
  
## <a name="remarks"></a>备注  
 你可以将放置`End`以强制整个应用程序停止运行过程中的任意位置的语句。 `End` 关闭使用打开的任何文件`Open`语句，并清除应用程序的所有变量。 应用程序关闭一旦没有保留对其对象的引用其他程序并没有其代码运行。  
  
> [!NOTE]
>  `End`语句突然，停止执行代码并不会调用`Dispose`或`Finalize`方法或任何其他 Visual Basic 代码。 持有的其他程序对象引用将会失效。 如果`End`内遇到语句`Try`或`Catch`块中，控件不会将传递给相应`Finally`块。  
  
 `Stop`语句挂起执行，但与`End`，它不会关闭任何文件或清除任何变量，除非在已编译可执行文件 (.exe) 文件中遇到。  
  
 因为`End`终止而不顾及应用程序的任何可能已打开的资源，你应尝试彻底关闭然后再使用它。 例如，如果应用程序的任何打开的窗体，你应该先关闭这些控件达到`End`语句。  
  
 应使用`End`尽量少，且仅当你需要立即停止。 终止过程的正常方式 ([Return 语句](../../../visual-basic/language-reference/statements/return-statement.md)和[退出语句](../../../visual-basic/language-reference/statements/exit-statement.md)) 不仅完全关闭过程，但还为调用的代码提供彻底关闭的机会。 控制台应用程序，例如，可以只需`Return`从`Main`过程。  
  
> [!IMPORTANT]
>  `End`语句也会调用<xref:System.Environment.Exit%2A>方法<xref:System.Environment>类<xref:System>命名空间。 <xref:System.Environment.Exit%2A> 你需要具有`UnmanagedCode`权限。 如果你不希望这样做，<xref:System.Security.SecurityException>发生错误。  
  
 当附加关键字后, 跟[结束\<关键字 > 语句](../../../visual-basic/language-reference/statements/end-keyword-statement.md)描述的定义的相应过程或块的末尾。 例如，`End Function`终止的定义`Function`过程。  
  
## <a name="example"></a>示例  
 下面的示例使用`End`语句，终止执行代码，如果用户请求它。  
  
 [!code-vb[VbVersHelp60Controls#64](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/end-statement_1.vb)]  
  
## <a name="smart-device-developer-notes"></a>智能设备的开发人员说明  
 不支持此语句。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Security.Permissions.SecurityPermissionFlag>  
 [Stop 语句](../../../visual-basic/language-reference/statements/stop-statement.md)  
 [结束\<关键字 > 语句](../../../visual-basic/language-reference/statements/end-keyword-statement.md)

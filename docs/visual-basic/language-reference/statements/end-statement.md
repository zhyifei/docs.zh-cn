---
title: End 语句（Visual Basic）
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
ms.openlocfilehash: 66dba1df125a08b8ae05519a0c66edb6da15ceaa
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583417"
---
# <a name="end-statement"></a>End 语句
立即终止执行。  
  
## <a name="syntax"></a>语法  
  
```vb  
End  
```  
  
## <a name="remarks"></a>备注  
 可以将 `End` 语句放置在过程中的任意位置，以强制整个应用程序停止运行。 `End` 关闭使用 `Open` 语句打开的所有文件，并清除应用程序的所有变量。 应用程序将立即关闭，因为没有任何其他程序保留对其对象的引用，并且没有任何代码正在运行。  
  
> [!NOTE]
> @No__t_0 语句会突然停止代码执行，并且不会调用 `Dispose` 或 `Finalize` 方法或其他任何 Visual Basic 代码。 其他程序持有的对象引用已失效。 如果在 `Try` 或 `Catch` 块内遇到 `End` 语句，控件不会传递给相应的 `Finally` 块。  
  
 @No__t_0 语句会挂起执行，但与 `End` 不同，它不会关闭任何文件或清除任何变量，除非在已编译的可执行（.exe）文件中遇到该错误。  
  
 由于 `End` 终止应用程序而不参与任何可能已打开的资源，因此，在使用之前，应尝试完全关闭。 例如，如果您的应用程序打开了任何窗体，则在控制到达 `End` 语句之前应关闭它们。  
  
 应慎用 `End`，且仅在需要立即停止时使用。 终止过程的一般方法（[Return 语句](../../../visual-basic/language-reference/statements/return-statement.md)和[Exit 语句](../../../visual-basic/language-reference/statements/exit-statement.md)）不仅完全关闭过程，而且还使调用代码有机会彻底关闭。 例如，控制台应用程序可以从 `Main` 过程中简单地 `Return`。  
  
> [!IMPORTANT]
> @No__t_0 语句调用 <xref:System> 命名空间中 <xref:System.Environment> 类的 <xref:System.Environment.Exit%2A> 方法。 <xref:System.Environment.Exit%2A> 要求您具有 `UnmanagedCode` 权限。 否则，会发生 <xref:System.Security.SecurityException> 错误。  
  
 后跟一个附加关键字， [end \<keyword > 语句](../../../visual-basic/language-reference/statements/end-keyword-statement.md)指定相应过程或块定义的末尾。 例如，`End Function` 终止 `Function` 过程的定义。  
  
## <a name="example"></a>示例  
 下面的示例使用 `End` 语句在用户请求代码的情况下终止代码执行。  
  
 [!code-vb[VbVersHelp60Controls#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVersHelp60Controls/VB/Form1.vb#64)]  
  
## <a name="smart-device-developer-notes"></a>智能设备开发人员说明  
 不支持此语句。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Security.Permissions.SecurityPermissionFlag>
- [Stop 语句](../../../visual-basic/language-reference/statements/stop-statement.md)
- [End \<keyword > 语句](../../../visual-basic/language-reference/statements/end-keyword-statement.md)

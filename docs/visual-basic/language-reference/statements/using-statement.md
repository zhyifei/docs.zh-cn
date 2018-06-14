---
title: Using 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.using
helpviewer_keywords:
- resource disposal
- Try...Catch...Finally statements, equivalent to Using statement
- resources [Visual Basic], disposing
- Using statement [Visual Basic]
ms.assetid: 665d1580-dd54-4e96-a9a9-6be2a68948f1
ms.openlocfilehash: 725eeb42dc5462022ac1a021c537d701929398ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604960"
---
# <a name="using-statement-visual-basic"></a>Using 语句 (Visual Basic)
声明的开头`Using`阻止并根据需要获取该块控制的系统资源。  
  
## <a name="syntax"></a>语法  
  
```  
Using { resourcelist | resourceexpression }  
    [ statements ]  
End Using  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`resourcelist`|如果未提供所需`resourceexpression`。 该列表的一个或多个系统资源`Using`阻止控件，并用逗号隔开。|  
|`resourceexpression`|如果未提供所需`resourcelist`。 引用变量或表达式引用系统资源，以控制此`Using`块。|  
|`statements`|可选。 语句块的`Using`块将运行。|  
|`End Using`|必须的。 终止的定义`Using`块，并释放它所控制的所有资源。|  
  
 在每个资源`resourcelist`部件具有以下语法和部件：  
  
 `resourcename As New resourcetype [ ( [ arglist ] ) ]`  
  
 -或-  
  
 `resourcename As resourcetype = resourceexpression`  
  
## <a name="resourcelist-parts"></a>resourcelist 部件  
  
|术语|定义|  
|---|---|  
|`resourcename`|必须的。 指系统资源的引用变量，`Using`阻止控件。|  
|`New`|如果存在`Using`语句获取资源。 如果你已获取资源，使用第二个语法替代项。|  
|`resourcetype`|必须的。 资源的类。 类必须实现<xref:System.IDisposable>接口。|  
|`arglist`|可选。 你传递给构造函数来创建的实例的自变量列表的`resourcetype`。 请参阅[参数列表](../../../visual-basic/language-reference/statements/parameter-list.md)。|  
|`resourceexpression`|必须的。 为满足的要求的系统资源引用变量或表达式`resourcetype`。 如果你使用第二个语法替代方法，您必须在将控制权传递给之前获取资源`Using`语句。|  
  
## <a name="remarks"></a>备注  
 有时，代码需要一个非托管的资源，如文件句柄、 COM 包装器或 SQL 连接。 A`Using`块时你的代码已完成，但它们都可确保对一个或多个此类资源处置。 这使它们可供其他代码使用。  
  
 托管释放资源的.NET Framework 垃圾回收器 (GC) 而无需您采取任何额外编码。 不需要`Using`托管资源的块。 但是，你仍可以使用`Using`块以强制释放托管资源而不是等待垃圾回收器。  
  
 A`Using`块都有三个部分： 获取用量、 使用量以及可供使用。  
  
-   *获取*意味着创建变量并将其初始化，以便指系统资源。 `Using`语句可以获取一个或多个资源，也可以在进入块之前获取恰好一个资源，其提供给`Using`语句。 如果你提供`resourceexpression`，您必须在将控制权传递给之前获取资源`Using`语句。  
  
-   *使用情况*意味着访问资源并执行与它们的操作。 之间的语句`Using`和`End Using`表示资源的使用。  
  
-   *处置*意味着调用<xref:System.IDisposable.Dispose%2A>方法中的对象`resourcename`。 这样，要完全终止及其资源的对象。 `End Using`语句释放资源下`Using`块的控件。  
  
## <a name="behavior"></a>行为  
 A`Using`块的行为类似`Try`...`Finally`顺序构造`Try`块使用的资源和`Finally`块释放它们。 因此，`Using`块都可确保释放的资源，无论你如何退出块。 即使发生未经处理的异常，也是如此除<xref:System.StackOverflowException>。  
  
 获取的每个资源变量的作用域`Using`语句仅限于`Using`块。  
  
 如果指定多个中的系统资源`Using`就像你嵌套语句，效果都将是相同`Using`阻止在另一个。  
  
 如果`resourcename`是`Nothing`，不需要调用<xref:System.IDisposable.Dispose%2A>进行，并且会引发任何异常。  
  
## <a name="structured-exception-handling-within-a-using-block"></a>结构化的异常处理在使用块中  
 如果你需要处理中可能发生的异常`Using`块中，你可以添加整个`Try`...`Finally`到它的构造。 如果你需要处理的情况其中`Using`语句不是成功获取资源，你可以测试是否`resourcename`是`Nothing`。  
  
## <a name="structured-exception-handling-instead-of-a-using-block"></a>结构化的异常处理而不使用块  
 如果你需要更好地控制的获取资源，或者需要中的其他代码`Finally`块中，您可以重新编写`Using`作为阻止`Try`...`Finally`构造。 下面的示例演示主干`Try`和`Using`相等，则在购买和处置的构造`resource`。  
  
```vb  
Using resource As New resourceType   
    ' Insert code to work with resource.  
End Using  
  
' For the acquisition and disposal of resource, the following  
' Try construction is equivalent to the Using block.  
Dim resource As New resourceType  
Try   
    ' Insert code to work with resource.  
Finally   
    If resource IsNot Nothing Then  
        resource.Dispose()   
    End If  
End Try   
```  
  
> [!NOTE]
>  内的代码`Using`块不应将分配中的对象`resourcename`给另一个变量。 当您退出`Using`块时，资源将被释放，或另一个变量不能访问它所指向的资源。  
  
## <a name="example"></a>示例  
 下面的示例创建名为 log.txt 并将两个行文本写入文件的文件。 该示例还读取该相同的文件，并显示的文本行。  
  
 因为<xref:System.IO.TextWriter>和<xref:System.IO.TextReader>类实现<xref:System.IDisposable>接口，可以使用代码`Using`语句，以确保该文件正确关闭后写入和读取操作。  
  
 [!code-vb[VbVbalrStatements#50](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/using-statement_1.vb)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.IDisposable>  
 [Try...Catch...Finally 语句](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [如何：释放系统资源](../../../visual-basic/programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)

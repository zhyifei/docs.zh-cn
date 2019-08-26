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
ms.openlocfilehash: 346a26ad5751599831d8b0d3e0497e4d488eb76c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957543"
---
# <a name="using-statement-visual-basic"></a>Using 语句 (Visual Basic)
声明`Using`块的开头, 并根据需要获取块所控制的系统资源。  
  
## <a name="syntax"></a>语法  
  
```  
Using { resourcelist | resourceexpression }  
    [ statements ]  
End Using  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`resourcelist`|如果未提供`resourceexpression`, 则为必需。 此`Using`块控制的一个或多个系统资源的列表 (用逗号分隔)。|  
|`resourceexpression`|如果未提供`resourcelist`, 则为必需。 引用由此`Using`块控制的系统资源的引用变量或表达式。|  
|`statements`|可选。 `Using`块运行的语句块。|  
|`End Using`|必需。 终止`Using`块的定义, 并释放其控制的所有资源。|  
  
 此`resourcelist`部分中的每个资源都具有以下语法和部分:  
  
 `resourcename As New resourcetype [ ( [ arglist ] ) ]`  
  
 或  
  
 `resourcename As resourcetype = resourceexpression`  
  
## <a name="resourcelist-parts"></a>resourcelist 部件  
  
|术语|定义|  
|---|---|  
|`resourcename`|必需。 引用变量, 该变量引用`Using`块所控制的系统资源。|  
|`New`|如果语句获取`Using`资源, 则为必需。 如果已获取资源, 请使用第二种语法替代方法。|  
|`resourcetype`|必需。 资源的类。 类必须实现<xref:System.IDisposable>接口。|  
|`arglist`|可选。 要传递给构造函数来创建实例的`resourcetype`参数的列表。 请参阅[参数列表](../../../visual-basic/language-reference/statements/parameter-list.md)。|  
|`resourceexpression`|必需。 引用满足的要求的`resourcetype`系统资源的变量或表达式。 如果使用第二种语法替代方法, 则必须先获取资源, 然后才能将`Using`控制传递给语句。|  
  
## <a name="remarks"></a>备注  
 有时, 您的代码需要非托管资源, 如文件句柄、COM 包装或 SQL 连接。 当你的代码完成了一个或多个此类资源时,块可保证其释放。`Using` 这使它们可供其他代码使用。  
  
 .NET Framework 垃圾回收器 (GC) 释放托管资源, 而不会对你的部分进行任何额外编码。 对于托管资源, 无`Using`需使用块。 但是, 您仍然可以使用`Using`块来强制处置托管资源, 而不是等待垃圾回收器。  
  
 `Using`块有三个部分: 获取、使用和处理。  
  
- *获取*是指创建一个变量并将其初始化, 以引用系统资源。 语句可以获取一个或多个资源, 也可以在输入块之前获取一个资源, 并将其提供`Using`给语句。 `Using` 如果提供`resourceexpression`, 则必须先获取资源, 然后才能将控制传递`Using`给语句。  
  
- *用法*是指访问资源并对其执行操作。 `Using` 和`End Using`之间的语句表示资源的使用情况。  
  
- 处理是指对<xref:System.IDisposable.Dispose%2A>中`resourcename`的对象调用方法。 这使对象可以干净地终止其资源。 语句释放`Using`块控件下的资源。 `End Using`  
  
## <a name="behavior"></a>行为  
 块的行为`Try`类似于 ... `Using`块使用资源和块处置资源的构造。`Finally` `Try` `Finally` 因此, `Using`无论退出块的方式如何, 块都可保证资源的处置。 即使在发生未经处理的异常的情况下也是如此, 但<xref:System.StackOverflowException>除外。  
  
 `Using`语句获取的每个资源变量的作用域仅限于`Using`块。  
  
 如果在`Using`语句中指定多个系统资源, 则效果与嵌套`Using`块在另一个中时相同。  
  
 如果`resourcename` <xref:System.IDisposable.Dispose%2A>为`Nothing`, 则不进行对的调用, 且不引发异常。  
  
## <a name="structured-exception-handling-within-a-using-block"></a>Using 块中的结构化异常处理  
 如果需要处理可能在`Using`块中发生的异常, 则可以添加一个完整`Try`的 .。。`Finally`构造。 如果需要处理`Using`语句未能成功获取资源的情况, 则可以进行测试以`resourcename`查看是否为`Nothing`。  
  
## <a name="structured-exception-handling-instead-of-a-using-block"></a>结构化异常处理而不是 Using 块  
 如果需要更好地控制资源的获取, 或在`Finally`块中需要其他代码, 则可以将`Using`块重写为`Try`.。。`Finally`构造。 下面的示例显示了`Try`的`Using`采集和处置`resource`中等效的主干和构造。  
  
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
> `Using`块内的代码不应将`resourcename`对象分配给另一个变量。 退出`Using`块后, 资源会被释放, 另一个变量将无法访问它所指向的资源。  
  
## <a name="example"></a>示例  
 下面的示例创建一个名为 ".log" 的文件, 并向该文件写入两行文本。 该示例还读取该文件并显示文本行。  
  
 <xref:System.IDisposable> `Using`由于和类<xref:System.IO.TextReader>实现接口, 因此代码可以使用语句来确保文件在执行写入和读取操作后正确关闭。 <xref:System.IO.TextWriter>  
  
 [!code-vb[VbVbalrStatements#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#50)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.IDisposable>
- [Try...Catch...Finally 语句](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [如何：释放系统资源](../../../visual-basic/programming-guide/language-features/control-flow/how-to-dispose-of-a-system-resource.md)

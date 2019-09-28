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
ms.openlocfilehash: 819af63acb6a1f038300bcb999dcfb904eb8a457
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592092"
---
# <a name="using-statement-visual-basic"></a>Using 语句 (Visual Basic)

声明 @no__t 的块的开头，并根据需要获取块所控制的系统资源。

## <a name="syntax"></a>语法

```vb
Using { resourcelist | resourceexpression }
    [ statements ]
End Using
```

## <a name="parts"></a>部件

|术语|定义|  
|---|---|  
|`resourcelist`|如果未提供 `resourceexpression`，则是必需的。 此 `Using` 块控件的一个或多个系统资源的列表，用逗号分隔。|  
|`resourceexpression`|如果未提供 `resourcelist`，则是必需的。 引用由该 `Using` 块控制的系统资源的引用变量或表达式。|  
|`statements`|可选。 @No__t-0 块运行的语句块。|  
|`End Using`|必需。 终止 `Using` 块的定义，并释放它所控制的所有资源。|  

 @No__t 0 部分中的每个资源都具有以下语法和部分：

 `resourcename As New resourcetype [ ( [ arglist ] ) ]`

 -或-

 `resourcename As resourcetype = resourceexpression`

## <a name="resourcelist-parts"></a>resourcelist 部件

|术语|定义|  
|---|---|  
|`resourcename`|必需。 引用变量，该变量引用 `Using` 块控制的系统资源。|  
|`New`|如果 `Using` 语句获取资源，则是必需的。 如果已获取资源，请使用第二种语法替代方法。|  
|`resourcetype`|必需。 资源的类。 类必须实现 <xref:System.IDisposable> 接口。|  
|`arglist`|可选。 要传递给构造函数的参数列表，以创建 @no__t 的实例。 请参阅[参数列表](parameter-list.md)。|  
|`resourceexpression`|必需。 引用满足 @no__t 的要求的系统资源的变量或表达式。 如果使用第二种语法替代方法，则必须先获取资源，然后才能将控制传递给 `Using` 语句。|  
  
## <a name="remarks"></a>备注

 有时，您的代码需要非托管资源，如文件句柄、COM 包装或 SQL 连接。 当你的代码完成了一个或多个此类资源的操作时，`Using` 块保证处理此类资源。 这使它们可供其他代码使用。

 .NET Framework 垃圾回收器（GC）释放托管资源，而不会对你的部分进行任何额外编码。 托管资源不需要 `Using` 块。 但是，仍可使用 @no__t 0 块强制处置托管资源，而不是等待垃圾回收器。

 @No__t 0 块有三个部分：采集、使用情况和处置。

- *获取*是指创建一个变量并将其初始化，以引用系统资源。 @No__t-0 语句可以获取一个或多个资源，也可以在输入块之前获取一个资源，并将其提供给 @no__t 1 语句。 如果提供 `resourceexpression`，则必须先获取资源，然后才能将控制传递给 @no__t 1 语句。

- *用法*是指访问资源并对其执行操作。 @No__t-0 与 `End Using` 之间的语句表示资源的使用情况。

- *处置*意味着对 `resourcename` 中的对象调用 <xref:System.IDisposable.Dispose%2A> 方法。 这使对象可以干净地终止其资源。 @No__t-0 语句会释放 @no__t 1 块控件下的资源。

## <a name="behavior"></a>行为

 @No__t-0 块的行为类似于 `Try` ... `Finally` 构造，其中，`Try` 块使用资源，`Finally` 块处置它们。 因此，无论退出块的方式如何，@no__t 0 块均可保证资源的释放。 即使在发生未经处理的异常的情况下也是如此 <xref:System.StackOverflowException> 除外。

 @No__t-0 语句获取的每个资源变量的作用域仅限于 @no__t 块。

 如果在 `Using` 语句中指定多个系统资源，则效果与嵌套 `Using` 块在另一个中的情况相同。

 如果 `resourcename` @no__t 为-1，则不会调用 <xref:System.IDisposable.Dispose%2A>，并且不会引发异常。

## <a name="structured-exception-handling-within-a-using-block"></a>Using 块中的结构化异常处理

 如果需要处理可能在 `Using` 块内发生的异常，可以向其添加完整的 `Try` ... @no__t。 如果需要处理 `Using` 语句未能成功获取资源的情况，则可以测试 @no__t 是否 @no__t 为-2。

## <a name="structured-exception-handling-instead-of-a-using-block"></a>结构化异常处理而不是 Using 块

 如果需要更好地控制资源的获取，或在 `Finally` 块中需要额外的代码，则可将 @no__t 1 块重写为 `Try` ... `Finally` 构造。 下面的示例显示了与 `resource` 的获取和处置等效的主干 `Try` 和 @no__t 1 构造。

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
> @No__t-0 块内的代码不应将 `resourcename` 中的对象分配给另一个变量。 退出 `Using` 块时，将释放资源，而另一个变量将无法访问它所指向的资源。

## <a name="example"></a>示例

 下面的示例创建一个名为 ".log" 的文件，并向该文件写入两行文本。 该示例还读取同一文件并显示文本行：

 由于 @no__t 0 和 @no__t 1 类实现了 <xref:System.IDisposable> 接口，因此代码可以使用 `Using` 语句，以确保在执行写入和读取操作后正确关闭文件。

 [!code-vb[VbVbalrStatements#50](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#50)]

## <a name="see-also"></a>请参阅

- <xref:System.IDisposable>
- [Try...Catch...Finally 语句](try-catch-finally-statement.md)
- [如何：释放系统资源 @ no__t-0

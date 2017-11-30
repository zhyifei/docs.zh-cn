---
title: "在 Visual Basic 中实现 IEnumerable"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- control flow [Visual Basic]
- enumerable interfaces
- loop structures [Visual Basic], optimizing performance
- control flow [Visual Basic]
ms.assetid: c60d7589-51f2-4463-a2d5-22506bbc1554
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 45b4008f0bf3ae0f303aa029e7bff5b82ab6f259
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-implementing-ienumerableof-t-in-visual-basic"></a>演练：在 Visual Basic 中实现 IEnumerable(Of T)
<xref:System.Collections.Generic.IEnumerable%601>接口由可以一次返回的值的一个项的序列的类实现。 返回的数据一次的一项是不需要将完整的数据集加载到内存中进行处理它的优势。 只需使用足够的内存来从数据加载单个项。 类实现`IEnumerable(T)`接口可以用于`For Each`循环或 LINQ 查询。  
  
 例如，假设一个应用程序必须读取一个大型文本文件并返回与特定搜索条件匹配的文件中的每个行。 应用程序使用 LINQ 查询返回与指定的条件匹配的文件中的行。 若要查询通过使用 LINQ 查询的文件的内容，应用程序可以加载到一个数组或集合的文件的内容。 但是，将整个文件加载到该数组或集合会占用比需要的更多内存。 LINQ 查询无法使用一个可枚举类、 返回与搜索条件匹配的值改为查询的文件内容。 返回只有少量的查询匹配的值将占用更少的内存。  
  
 你可以创建一个类以实现<xref:System.Collections.Generic.IEnumerable%601>接口来公开为可枚举数据源数据。 类中实现`IEnumerable(T)`接口需要实现的另一个类<xref:System.Collections.Generic.IEnumerator%601>接口来循环访问源数据。 这两个类，可以按顺序为特定类型返回的数据的项。  
  
 在本演练中，你将创建一个类以实现`IEnumerable(Of String)`接口以及实现的类`IEnumerator(Of String)`接口一次读取文本文件的一行。  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-the-enumerable-class"></a>创建可枚举类  
  
|若要创建的可枚举类项目|  
|---|  
|1.在 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 中的“文件”菜单上，指向“新建”，然后单击“项目”。<br />2.在“新建项目”对话框的“项目类型”窗格中，确保选中“Windows”。 在“模板”窗格中，选择“类库”。 在“名称”框中，键入 `StreamReaderEnumerable`，然后单击“确定”。 将显示新项目。<br />3.在**解决方案资源管理器**，右键单击 Class1.vb 文件，然后单击**重命名**。 将文件重命名为 `StreamReaderEnumerable.vb`，然后按 Enter。 重命名文件也会将类重命名为 `StreamReaderEnumerable`。 此类将实现 `IEnumerable(Of String)` 接口。<br />4.右键单击 StreamReaderEnumerable 项目，指向**添加**，然后单击**新项**。 选择**类**模板。 在**名称**框中，键入`StreamReaderEnumerator.vb`单击**确定**。|  
  
 此项目中的第一个类是可枚举类，将实现`IEnumerable(Of String)`接口。 此泛型接口实现<xref:System.Collections.IEnumerable>接口，并保证此类的使用者可以访问值类型化为`String`。  
  
|若要添加代码以实现 IEnumerable|  
|---|  
|1.打开 StreamReaderEnumerable.vb 文件。<br />2.在后面的行上`Public Class StreamReaderEnumerable`，键入以下命令并按 ENTER。<br />     [!code-vb[VbVbalrIteratorWalkthrough#1](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_1.vb)]<br />     [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]自动填充具有所需的成员的类`IEnumerable(Of String)`接口。<br />3.一次，此可枚举类将从文本文件一个行读取的行。 将以下代码添加到要公开将文件路径作为输入参数的公共构造函数的类。<br />     [!code-vb[VbVbalrIteratorWalkthrough#2](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_2.vb)]<br />4.实现<xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>方法`IEnumerable(Of String)`接口将返回的新实例`StreamReaderEnumerator`类。 实现`GetEnumerator`方法`IEnumerable`接口可以成为`Private`，这是因为你必须公开只有的成员`IEnumerable(Of String)`接口。 将代码，[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]为生成`GetEnumerator`方法替换为以下代码。<br />     [!code-vb[VbVbalrIteratorWalkthrough#3](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_3.vb)]|  
  
|若要添加代码以实现 IEnumerator|  
|---|  
|1.打开 StreamReaderEnumerator.vb 文件。<br />2.在后面的行上`Public Class StreamReaderEnumerator`，键入以下命令并按 ENTER。<br />     [!code-vb[VbVbalrIteratorWalkthrough#4](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_4.vb)]<br />     [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]自动填充具有所需的成员的类`IEnumerator(Of String)`接口。<br />3.枚举器类打开文本文件，并执行的文件 I/O，以从文件读取的行。 将以下代码添加到类，以公开将文件路径作为输入参数的公共构造函数并打开文本文件以进行读取。<br />     [!code-vb[VbVbalrIteratorWalkthrough#5](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_5.vb)]<br />4.`Current`属性都`IEnumerator(Of String)`和`IEnumerator`接口从文本文件作为返回当前项`String`。 实现`Current`属性`IEnumerator`接口可以成为`Private`，这是因为你必须公开只有的成员`IEnumerator(Of String)`接口。 将代码，[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]为生成`Current`替换为以下代码的属性。<br />     [!code-vb[VbVbalrIteratorWalkthrough#6](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_6.vb)]<br />5.`MoveNext`方法`IEnumerator`接口导航到文本文件中的下一项并更新返回的值`Current`属性。 如果没有更多的项读取，`MoveNext`方法返回`False`; 否则为`MoveNext`方法返回`True`。 将以下代码添加到 `MoveNext` 方法中。<br />     [!code-vb[VbVbalrIteratorWalkthrough#7](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_7.vb)]<br />6.`Reset`方法`IEnumerator`接口指示迭代器指向的文本文件开始，并清除当前项的值。 将以下代码添加到 `Reset` 方法中。<br />     [!code-vb[VbVbalrIteratorWalkthrough#8](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_8.vb)]<br />7.`Dispose`方法`IEnumerator`接口可保证所有的非托管的资源都释放之前销毁迭代器。 使用的文件句柄`StreamReader`对象是非托管的资源，必须先关闭然后销毁迭代器实例。 将代码，[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]为生成`Dispose`方法替换为以下代码。<br />     [!code-vb[VbVbalrIteratorWalkthrough#9](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_9.vb)]|  
  
## <a name="using-the-sample-iterator"></a>使用示例迭代器  
 你可以控制结构需要实现的对象，以及在代码中使用的可枚举类`IEnumerable`，如`For Next`循环或 LINQ 查询。 下面的示例演示`StreamReaderEnumerable`LINQ 查询中。  
  
 [!code-vb[VbVbalrIteratorWalkthrough#10](../../../../visual-basic/programming-guide/language-features/control-flow/codesnippet/VisualBasic/walkthrough-implementing-ienumerable-of-t_10.vb)]  
  
## <a name="see-also"></a>另请参阅  
 [Visual Basic 中的 LINQ 简介](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [控制流](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [循环结构](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [For Each...Next 语句](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)

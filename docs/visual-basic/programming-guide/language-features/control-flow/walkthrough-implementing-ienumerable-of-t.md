---
title: 实现 IE500
ms.date: 07/31/2018
helpviewer_keywords:
- control flow [Visual Basic]
- enumerable interfaces
- loop structures [Visual Basic], optimizing performance
- control flow [Visual Basic]
ms.assetid: c60d7589-51f2-4463-a2d5-22506bbc1554
ms.openlocfilehash: 4151a680050f234d450d8de5e67a767c54e8df68
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266906"
---
# <a name="walkthrough-implementing-ienumerableof-t-in-visual-basic"></a>演练：在 Visual Basic 中实现 IEnumerable(Of T)
接口<xref:System.Collections.Generic.IEnumerable%601>由类实现，这些类可以一次返回一个项的值序列。 一次返回一个项目的数据的优点是，您不必将完整的数据集加载到内存中才能使用它。 您只需要使用足够的内存从数据加载单个项。 实现接口的`IEnumerable(T)`类可用于`For Each`循环或 LINQ 查询。  
  
 例如，考虑一个应用程序，该应用程序必须读取大型文本文件，并从文件返回与特定搜索条件匹配的每行。 应用程序使用 LINQ 查询从文件返回与指定条件匹配的行。 要使用 LINQ 查询查询文件的内容，应用程序可以将文件的内容加载到数组或集合中。 但是，将整个文件加载到数组或集合中会消耗的内存远远多于所需的内存。 LINQ 查询可以使用枚举类查询文件内容，仅返回与搜索条件匹配的值。 仅返回几个匹配值的查询消耗的内存要少得多。  
  
 您可以创建实现接口的类，<xref:System.Collections.Generic.IEnumerable%601>以将源数据公开为枚举数据。 实现接口的`IEnumerable(T)`类将需要实现<xref:System.Collections.Generic.IEnumerator%601>接口的另一个类来遍经源数据迭代。 这两个类使您能够按顺序将数据项作为特定类型返回。  
  
 在本演练中，您将创建实现接口的`IEnumerable(Of String)`类和实现`IEnumerator(Of String)`接口一次读取一行文本文件的类。  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-the-enumerable-class"></a>创建可枚举类  
  
**创建枚举类项目**

1. 在"可视化基本"中，在 **"文件"** 菜单上，指向 **"新建"，** 然后单击"**项目**"。

1. 在“新建项目”**** 对话框的“项目类型”**** 窗格中，确保选中“Windows”****。 在“模板”**** 窗格中，选择“类库”****。 在“名称”**** 框中，键入 `StreamReaderEnumerable`，然后单击“确定”****。 将显示新项目。

1. 在**解决方案资源管理器**中，右键单击 Class1.vb 文件，然后单击 **"重命名**"。 将文件重命名为 `StreamReaderEnumerable.vb`，然后按 Enter。 重命名文件也会将类重命名为 `StreamReaderEnumerable`。 此类将实现 `IEnumerable(Of String)` 接口。

1. 右键单击 StreamReaderE"项目，指向 **"添加**"，然后单击 **"新项目**"。 选择**类**模板。 在“名称”框中，键入 `StreamReaderEnumerator.vb`，然后单击“确定”********。

 此项目中的第一个类是枚举类，将实现接口`IEnumerable(Of String)`。 此泛型接口实现<xref:System.Collections.IEnumerable>接口，并保证此类的使用者可以访问键入为`String`的值。  
  
**添加代码以实现 IE500**

1. 打开流阅读器数字.vb 文件。

2. 在`Public Class StreamReaderEnumerable`之后的行上键入以下内容，然后按 ENTER。

     [!code-vb[VbVbalrIteratorWalkthrough#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#1)]

   Visual Basic 使用`IEnumerable(Of String)`接口所需的成员自动填充类。
  
3. 此枚举类将一次从文本文件中读取一行。 将以下代码添加到类中，以公开将文件路径作为输入参数的公共构造函数。

     [!code-vb[VbVbalrIteratorWalkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#2)]

4. 接口方法的实现将返回`StreamReaderEnumerator`类的新实例。 <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> `IEnumerable(Of String)` `GetEnumerator`可以实现`IEnumerable``Private`接口的方法，因为您必须只公开`IEnumerable(Of String)`接口的成员。 将 Visual Basic 为`GetEnumerator`方法生成的代码替换为以下代码。

     [!code-vb[VbVbalrIteratorWalkthrough#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#3)]  
  
**添加代码以实现 IEnumerator**

1. 打开流阅读器数字器.vb 文件。

2. 在`Public Class StreamReaderEnumerator`之后的行上键入以下内容，然后按 ENTER。

     [!code-vb[VbVbalrIteratorWalkthrough#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#4)]

   Visual Basic 使用`IEnumerator(Of String)`接口所需的成员自动填充类。

3. 枚举器类打开文本文件并执行文件 I/O 以从文件中读取行。 将以下代码添加到类中，以公开将文件路径作为输入参数的公共构造函数，并打开文本文件进行读取。

     [!code-vb[VbVbalrIteratorWalkthrough#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#5)]

4. `Current``IEnumerator`和 接口的属性将当前项从文本文件返回为`String` `IEnumerator(Of String)` `Current`可以实现`IEnumerator``Private`接口的属性，因为您必须只公开`IEnumerator(Of String)`接口的成员。 将 Visual Basic 为`Current`属性生成的代码替换为以下代码。

     [!code-vb[VbVbalrIteratorWalkthrough#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#6)]

5. 接口的方法导航到文本文件中的下一个项，并更新`Current`属性返回的值。 `MoveNext` `IEnumerator` 如果没有要读取的项，`MoveNext`则方法将返回`False`;否则该方法`MoveNext`将返回`True`。 将以下代码添加到 `MoveNext` 方法中。

     [!code-vb[VbVbalrIteratorWalkthrough#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#7)]

6. `IEnumerator`接口`Reset`的方法指示迭代器指向文本文件的开头并清除当前项值。 将以下代码添加到 `Reset` 方法中。

     [!code-vb[VbVbalrIteratorWalkthrough#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#8)]

7. `IEnumerator`接口`Dispose`的方法保证在销毁迭代器之前释放所有非托管资源。 `StreamReader`对象使用的文件句柄是非托管资源，必须在销毁迭代器实例之前关闭。 将为`Dispose`该方法生成的 Visual Basic 的代码替换为以下代码。

     [!code-vb[VbVbalrIteratorWalkthrough#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#9)]
  
## <a name="using-the-sample-iterator"></a>使用样品迭代器

 可以在代码中使用枚举类以及需要实现`IEnumerable`的对象（如`For Next`循环或 LINQ 查询）的控件结构。 下面的示例显示了 LINQ 查询`StreamReaderEnumerable`中的 。  
  
 [!code-vb[VbVbalrIteratorWalkthrough#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/Module1.vb#10)]  
  
## <a name="see-also"></a>另请参阅

- [Visual Basic 中的 LINQ 简介](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [控制流](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [循环结构](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [For Each...Next 语句](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)

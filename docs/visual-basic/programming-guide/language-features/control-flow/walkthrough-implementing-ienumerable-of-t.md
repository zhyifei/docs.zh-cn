---
title: 实现 IEnumerable
ms.date: 07/31/2018
helpviewer_keywords:
- control flow [Visual Basic]
- enumerable interfaces
- loop structures [Visual Basic], optimizing performance
- control flow [Visual Basic]
ms.assetid: c60d7589-51f2-4463-a2d5-22506bbc1554
ms.openlocfilehash: f40fcf7e0724addc478b261dcd36d09e1d8a751a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333691"
---
# <a name="walkthrough-implementing-ienumerableof-t-in-visual-basic"></a>演练：在 Visual Basic 中实现 IEnumerable(Of T)
<xref:System.Collections.Generic.IEnumerable%601> 接口由可以每次返回一项的值序列的类实现。 一次返回一项数据的优点是，无需将完整的数据集加载到内存中即可使用它。 只需使用足够的内存来加载数据中的单个项。 实现 `IEnumerable(T)` 接口的类可用于 `For Each` 循环或 LINQ 查询。  
  
 例如，假设某个应用程序必须读取一个大型文本文件，并从该文件中返回与特定搜索条件相匹配的每一行。 应用程序使用 LINQ 查询从文件返回与指定条件相匹配的行。 若要通过使用 LINQ 查询来查询文件的内容，应用程序可以将文件的内容加载到数组或集合中。 但是，将整个文件加载到数组或集合会占用比所需的更多的内存。 LINQ 查询可以使用可枚举的类（仅返回与搜索条件匹配的值）来查询文件内容。 仅返回几个匹配值的查询将消耗更少的内存。  
  
 你可以创建一个类来实现 <xref:System.Collections.Generic.IEnumerable%601> 接口，以将源数据作为可枚举数据公开。 实现 `IEnumerable(T)` 接口的类将需要另一个类，该类实现 <xref:System.Collections.Generic.IEnumerator%601> 接口以便循环访问源数据。 这两个类使你能够按特定类型按顺序返回数据项。  
  
 在本演练中，您将创建一个实现 `IEnumerable(Of String)` 接口的类和一个实现 `IEnumerator(Of String)` 接口的类，以便一次一行地读取一个文本文件。  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-the-enumerable-class"></a>创建可枚举类  
  
**创建可枚举类项目**

1. 在 Visual Basic 的 "**文件**" 菜单上，指向 "**新建**"，然后单击 "**项目**"。

1. 在“新建项目”对话框的“项目类型”窗格中，确保选中“Windows”。 在“模板”窗格中，选择“类库”。 在“名称”框中，键入 `StreamReaderEnumerable`，然后单击“确定”。 将显示新项目。

1. 在**解决方案资源管理器**中，右键单击 Class1 文件，然后单击 "**重命名**"。 将文件重命名为 `StreamReaderEnumerable.vb`，然后按 Enter。 重命名文件也会将类重命名为 `StreamReaderEnumerable`。 此类将实现 `IEnumerable(Of String)` 接口。

1. 右键单击 "StreamReaderEnumerable" 项目，指向 "**添加**"，然后单击 "**新建项**"。 选择 "**类**" 模板。 在 "**名称**" 框中，键入 `StreamReaderEnumerator.vb` 然后单击 **"确定"** 。

 此项目中的第一个类是可枚举类并实现 `IEnumerable(Of String)` 接口。 此泛型接口实现 <xref:System.Collections.IEnumerable> 接口，并保证此类的使用者可以访问类型化为 `String`的值。  
  
**添加代码以实现 IEnumerable**

1. 打开 StreamReaderEnumerable 文件。

2. 在 `Public Class StreamReaderEnumerable`后面的行中，键入以下各项，然后按 ENTER。

     [!code-vb[VbVbalrIteratorWalkthrough#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#1)]

   Visual Basic 使用 `IEnumerable(Of String)` 接口所需的成员自动填充类。
  
3. 此可枚举类将一次一行地读取文本文件中的行。 将下面的代码添加到类以公开公共构造函数，该构造函数采用文件路径作为输入参数。

     [!code-vb[VbVbalrIteratorWalkthrough#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#2)]

4. 实现 `IEnumerable(Of String)` 接口的 <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> 方法将返回 `StreamReaderEnumerator` 类的新实例。 可以 `Private`生成 `IEnumerable` 接口的 `GetEnumerator` 方法，因为必须仅公开 `IEnumerable(Of String)` 接口的成员。 将 Visual Basic 为 `GetEnumerator` 方法生成的代码替换为以下代码。

     [!code-vb[VbVbalrIteratorWalkthrough#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#3)]  
  
**添加代码以实现 IEnumerator**

1. 打开 StreamReaderEnumerator 文件。

2. 在 `Public Class StreamReaderEnumerator`后面的行中，键入以下各项，然后按 ENTER。

     [!code-vb[VbVbalrIteratorWalkthrough#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#4)]

   Visual Basic 使用 `IEnumerator(Of String)` 接口所需的成员自动填充类。

3. 枚举器类打开文本文件，并执行文件 i/o 以读取文件中的行。 将下面的代码添加到类，以公开公共构造函数，该构造函数采用文件路径作为输入参数并打开文本文件进行读取。

     [!code-vb[VbVbalrIteratorWalkthrough#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#5)]

4. `IEnumerator(Of String)` 和 `IEnumerator` 接口的 `Current` 属性作为 `String`返回文本文件中的当前项。 可以 `Private`生成 `IEnumerator` 接口的 `Current` 属性，因为必须仅公开 `IEnumerator(Of String)` 接口的成员。 将 Visual Basic 为 `Current` 属性生成的代码替换为以下代码。

     [!code-vb[VbVbalrIteratorWalkthrough#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#6)]

5. `IEnumerator` 接口的 `MoveNext` 方法导航到文本文件中的下一项，并更新 `Current` 属性返回的值。 如果没有更多要读取的项，`MoveNext` 方法返回 `False`;否则，`MoveNext` 方法返回 `True`。 将以下代码添加到 `MoveNext` 方法中。

     [!code-vb[VbVbalrIteratorWalkthrough#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#7)]

6. `IEnumerator` 接口的 `Reset` 方法指示迭代器指向文本文件的开头，并清除当前项值。 将以下代码添加到 `Reset` 方法中。

     [!code-vb[VbVbalrIteratorWalkthrough#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#8)]

7. `IEnumerator` 接口的 `Dispose` 方法保证在迭代器销毁之前释放所有非托管资源。 `StreamReader` 对象所使用的文件句柄是非托管资源，必须在销毁迭代器实例之前关闭。 将 Visual Basic 为 `Dispose` 方法生成的代码替换为以下代码。

     [!code-vb[VbVbalrIteratorWalkthrough#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/StreamReaderIterator.vb#9)] 
  
## <a name="using-the-sample-iterator"></a>使用示例迭代器

 您可以在代码中使用可枚举的类以及需要实现 `IEnumerable`的对象的控制结构，如 `For Next` 循环或 LINQ 查询。 下面的示例演示 LINQ 查询中的 `StreamReaderEnumerable`。  
  
 [!code-vb[VbVbalrIteratorWalkthrough#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIteratorWalkthrough/VB/Module1.vb#10)]  
  
## <a name="see-also"></a>另请参阅

- [Visual Basic 中的 LINQ 简介](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [控制流](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)
- [循环结构](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [For Each...Next 语句](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)

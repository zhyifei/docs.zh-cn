---
title: 如何：从 Visual Basic 中引用 COM 对象
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop [Visual Basic], referencing COM objects
- referencing objects, COM objects from Visual Basic
- objects [Visual Basic], referencing
- COM objects, referencing
- interop assemblies
ms.assetid: 9c518fb4-27d9-4112-9e6a-5a7d0210af6f
ms.openlocfilehash: 49f3da396ca5cd48b0cf454ce1ecd5422c28e38f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33643947"
---
# <a name="how-to-reference-com-objects-from-visual-basic"></a>如何：从 Visual Basic 中引用 COM 对象
在 Visual Basic 中，添加对具有类型库的 COM 对象的引用需要创建互操作程序集的 COM 库。 对 COM 对象的成员的引用将路由到互操作程序集，然后转发到实际的 COM 对象。 从 COM 对象的响应路由到互操作程序集，并将其转发到你[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]应用程序。  
  
 您可以无需通过将 COM 对象的类型信息嵌入在.NET 程序集使用互操作程序集引用的 COM 对象。 若要嵌入类型信息，请设置`Embed Interop Types`属性`True`为 COM 对象的引用。 如果你使用命令行编译器进行编译，请使用`/link`选项来引用 COM 库。 有关详细信息，请参阅[/link (Visual Basic 中)](../../../visual-basic/reference/command-line-compiler/link.md)。  
  
 添加对类型库中的集成的开发环境 (IDE) 的引用时，Visual Basic 会自动创建互操作程序集。 在从命令行处理时，你可以使用 Tlbimp 实用工具来手动创建互操作程序集。  
  
### <a name="to-add-references-to-com-objects"></a>将引用添加到 COM 对象  
  
1.  上**项目**菜单上，选择**添加引用**，然后单击**COM**对话框中的选项卡。  
  
2.  选择你想要从列表中的 COM 对象使用的组件。  
  
3.  若要简化对互操作程序集的访问，将添加`Imports`到顶部的类或模块，你将在其中使用的 COM 对象的语句。 例如，下面的代码示例导入命名空间`INKEDLib`中所引用对象`Microsoft InkEdit Control 1.0`库。  
  
     [!code-vb[VbVbalrInterop#40](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-reference-com-objects_1.vb)]  
  
### <a name="to-create-an-interop-assembly-using-tlbimp"></a>若要创建使用 Tlbimp 为互操作程序集  
  
1.  如果尚不搜索路径的一部分，并且你目前不所在的目录，请将 Tlbimp 的位置添加到搜索路径。  
  
2.  调用 Tlbimp 从命令提示符处，提供以下信息：  
  
    -   包含类型库的 DLL 的名称和位置  
  
    -   名称和命名空间的位置信息的放置位置  
  
    -   名称和目标互操作程序集的位置  
  
     以下代码提供了一个示例：  
  
    ```  
    Tlbimp test3.dll /out:NameSpace1 /out:Interop1.dll  
    ```  
  
     可以使用 Tlbimp 创建互操作程序集的类型库，甚至对于未注册的 COM 对象。 但是，由互操作程序集引用的 COM 对象必须正确注册它们将被用于在计算机上。 可以使用 Regsvr32 实用工具随附 Windows 操作系统的系统来注册 COM 对象。  
  
## <a name="see-also"></a>请参阅  
 [COM 互操作](../../../visual-basic/programming-guide/com-interop/index.md)  
 [Tlbimp.exe（类型库导入程序）](../../../framework/tools/tlbimp-exe-type-library-importer.md)  
 [Tlbexp.exe（类型库导出程序）](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)  
 [演练：使用 COM 对象实现继承](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 [互操作性疑难解答](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)  
 [Imports 语句（.NET 命名空间和类型）](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)

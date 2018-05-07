---
title: 互操作性疑难解答 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interop, deploying assemblies
- assemblies [Visual Basic]
- interop, installing assemblies that share components
- COM objects, troubleshooting
- interop, sharing components
- troubleshooting interoperability [Visual Basic]
- interoperability, troubleshooting
- COM interop [Visual Basic], troubleshooting
- assemblies [Visual Basic], deploying
- troubleshooting Visual Basic, interoperability
- interop assemblies
- interoperability, sharing components
- shared components, using with assemblies
ms.assetid: b324cc1e-b03c-4f39-aea6-6a6d5bfd0e37
ms.openlocfilehash: 65005dbbe42f52b3159c8e595972dace3064f986
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="troubleshooting-interoperability-visual-basic"></a>互操作性疑难解答 (Visual Basic)
当你 COM 和托管的代码之间的互操作[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]，你可能会遇到一个或多个以下的常见问题。  
  
##  <a name="vbconinteroperabilitymarshalinganchor1"></a> 互操作封送处理  
 有时，你可能需要使用数据类型不属于[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]。 互操作程序集处理的大部分工作的 COM 对象，但你可能需要控制向 COM 公开托管的对象时使用的数据类型 例如，类库中的结构必须指定`BStr`非托管字符串发送到由 Visual Basic 6.0 和早期版本创建的 COM 对象的类型。 在这种情况下，你可以使用<xref:System.Runtime.InteropServices.MarshalAsAttribute>若要使作为非托管类型公开的托管的类型的属性。  
  
##  <a name="vbconinteroperabilitymarshalinganchor2"></a> 将固定长度字符串导出到非托管代码  
 在 Visual Basic 6.0 和早期版本中，字符串至 COM 对象导出为没有 null 终止字符的字节的序列。 对于与其他语言的兼容性，Visual Basic.NET 中包括的终止字符导出字符串时。 若要解决此不兼容性的最佳方法是导出的数组作为缺少的终止字符的字符串`Byte`或`Char`。  
  
##  <a name="vbconinteroperabilitymarshalinganchor3"></a> 导出继承层次结构  
 托管的类作为 COM 对象公开时，层次结构平展出。 例如，如果定义一个基类成员，然后继承的派生类中公开为 COM 对象的基类，则使用中的 COM 对象的派生的类的客户端将无法使用继承的成员。 可以仅作为实例的基类，从 COM 对象访问基类成员，然后仅当该基类还创建为 COM 对象。  
  
## <a name="overloaded-methods"></a>重载方法  
 虽然你可以使用 Visual Basic 创建重载的方法，它们不支持由 com 使用。 当包含重载的方法的类公开为 COM 对象时，重载方法会生成新的方法名称。  
  
 例如，考虑具有两个重载的类`Synch`方法。 当类公开为 COM 对象时，可能是新的生成的方法名`Synch`和`Synch_2`。  
  
 重命名可能导致两个问题的 COM 对象的使用者。  
  
1.  客户端可能不希望生成的方法名称。  
  
2.  新的重载添加到类或其基本类时，可以更改为 COM 对象公开的类中的生成的方法名称。 这会导致版本控制问题。  
  
 若要解决这两个问题，请为每个方法的唯一名称，而不是使用重载，当你开发将作为 COM 对象公开的对象时。  
  
##  <a name="vbconinteroperabilitymarshalinganchor4"></a> 使用通过互操作程序集的 COM 对象  
 几乎好像它们是它们表示的 COM 对象的托管的代码替换使用互操作程序集。 但是，因为它们是包装器和不是实际的 COM 对象，是使用互操作程序集和标准程序集之间的一些差异。 这些不同之处包括公开的类，以及数据类型的参数和返回值。  
  
##  <a name="vbconinteroperabilitymarshalinganchor5"></a> 类公开为这两个接口和类  
 与标准的程序集中的类，不同的 COM 类公开为一个接口和一个类，表示的 COM 类互操作程序集中。 接口的名称是相同的 COM 类。 互操作的类的名称是相同的原始的 COM 类，但以单词"类"追加。 例如，假设你的项目必须具有对 COM 对象互操作程序集的引用。 如果 COM 类命名为`MyComClass`，IntelliSense 和对象浏览器显示名为接口`MyComClass`和一个名为类`MyComClassClass`。  
  
##  <a name="vbconinteroperabilitymarshalinganchor6"></a> 创建.NET Framework 类的实例  
 通常情况下，你创建的实例[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]类使用`New`与类名称的语句。 具有互操作程序集中所表示的 COM 类是你可以在其中使用的一个例子`New`语句的接口。 除非你使用了 COM 类`Inherits`语句中，你可以像类一样使用接口。 下面的代码演示如何创建`Command`具有对 Microsoft ActiveX 数据对象 2.8 库 COM 对象的引用的项目中的对象：  
  
 [!code-vb[VbVbalrInterop#20](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_1.vb)]  
  
 但是，如果你使用的 COM 类作为基类的派生类，你必须使用表示的 COM 类，如以下代码所示的互操作类：  
  
 [!code-vb[VbVbalrInterop#21](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_2.vb)]  
  
> [!NOTE]
>  互操作程序集隐式实现表示 COM 类的接口。 不应尝试使用`Implements`将导致语句来实现这些接口或错误。  
  
##  <a name="vbconinteroperabilitymarshalinganchor7"></a> 为参数和返回值的数据类型  
 与不同的是标准程序集的成员，互操作程序集的成员可能有不同于原始对象声明中使用的数据类型。 尽管互操作程序集隐式转换为兼容的公共语言运行时类型的 COM 类型，但你应注意双方用于防止运行时错误的数据类型。 例如，在 Visual Basic 6.0 和早期版本，类型的值中创建的 COM 对象`Integer`假定[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]等效类型`Short`。 建议你使用对象浏览器来检查导入的成员的特征，然后使用它们。  
  
##  <a name="vbconinteroperabilitymarshalinganchor8"></a> 模块级别 COM 方法  
 由大多数 COM 对象创建的 COM 类使用的实例`New`关键字，然后调用对象的方法。 此规则的例外涉及包含的 COM 对象`AppObj`或`GlobalMultiUse`COM 类。 此类类类似于 Visual Basic.NET 类中的模块级别方法。 Visual Basic 6.0 及更早版本隐式创建此类对象的实例为你首次调用其方法之一。 例如，在 Visual Basic 6.0 可添加到 Microsoft DAO 3.6 对象库，并调用引用`DBEngine`而不必首先创建实例的方法：  
  
```vb  
Dim db As DAO.Database  
' Open the database.  
Set db = DBEngine.OpenDatabase("C:\nwind.mdb")  
' Use the database object.  
```  
  
 Visual Basic.NET 要求您始终创建 COM 对象的实例，然后才能使用其方法。 若要在 Visual Basic 中使用这些方法，声明的变量的所需的类，并使用新的关键字将对象分配给对象变量。 `Shared`可以使用关键字，当你想要确保时创建的类只有一个实例。  
  
 [!code-vb[VbVbalrInterop#23](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_3.vb)]  
  
##  <a name="vbconinteroperabilitymarshalinganchor9"></a> 在事件处理程序未处理的错误  
 一个常见的互操作问题涉及处理由 COM 对象引发的事件的事件处理程序中的错误。 除非你专门检查使用的错误，则忽略此类错误`On Error`或`Try...Catch...Finally`语句。 例如，下面的示例是从 Visual Basic.NET 项目具有对 Microsoft ActiveX 数据对象 2.8 库 COM 对象的引用。  
  
 [!code-vb[VbVbalrInterop#24](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_4.vb)]  
  
 此示例将按预期引发错误。 但是，如果你尝试相同示例而不`Try...Catch...Finally`块，该错误忽略就使用`OnError Resume Next`语句。 如果没有错误处理机制除以零的除法运算以静默方式失败。 因为此类错误永远不会引发未处理的异常错误，务必使用某种形式的处理从 COM 对象的事件的事件处理程序中的异常处理。  
  
### <a name="understanding-com-interop-errors"></a>了解 COM 互操作错误  
 如果没有错误处理机制，互操作调用通常产生错误时提供很少信息。 只要可能，使用结构化的错误处理发生时提供有关问题的详细信息。 在调试应用程序时，这可以是特别有用。 例如：  
  
 [!code-vb[VbVbalrInterop#25](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_5.vb)]  
  
 你可以通过检查异常对象的内容找到如错误描述、 HRESULT 和 COM 错误的原因的信息。  
  
##  <a name="vbconinteroperabilitymarshalinganchor10"></a> ActiveX 控件问题  
 使用 Visual Basic 6.0 中的大多数 ActiveX 控件使用 Visual Basic.NET，而问题。 主要的例外是容器控件中或以可视方式包含其他控件的控件。 将无法正常使用 Visual Studio 的较旧控件的一些示例如下所示：  
  
-   Microsoft 窗体 2.0 框架控件  
  
-   Up-down 控件，也称为数值调节钮控件  
  
-   Sheridan 选项卡控件  
  
 有仅几个解决方法不受支持 ActiveX 控件问题。 如果你拥有原始源代码，可以迁移到 Visual Studio 的现有控件。 否则，你可以检查与软件供应商更新。控件替换的 NET 兼容版本不受支持 ActiveX 控件。  
  
##  <a name="vbconinteroperabilitymarshalinganchor11"></a> 传递的控件 ByRef 的 ReadOnly 属性  
 Visual Basic.NET 有时引发 COM 错误，例如，"错误 0x800A017F CTL_E_SETNOTSUPPORTED"传递时`ReadOnly`作为某些较旧的 ActiveX 控件的属性`ByRef`其他过程的参数。 从 Visual Basic 6.0 的类似过程调用不会引发错误，和参数被视为通过值传递。 Visual Basic.NET 错误消息指示你尝试更改一个属性，没有一个属性`Set`过程。  
  
 如果你有权访问所调用的过程，你可以通过使用来防止出现此错误`ByVal`关键字来声明接受的参数`ReadOnly`属性。 例如：  
  
 [!code-vb[VbVbalrInterop#26](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_6.vb)]  
  
 如果你没有访问所调用的过程的源代码，你可以强制要通过添加一组额外的方括号调用过程通过值传递的属性。 例如，在项目中具有对 Microsoft ActiveX 数据对象 2.8 库 COM 对象的引用，你可以使用：  
  
 [!code-vb[VbVbalrInterop#27](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/troubleshooting-interoperability_7.vb)]  
  
##  <a name="vbconinteroperabilitymarshalinganchor12"></a> 部署公开互操作的程序集  
 部署公开的 COM 接口的程序集带来了一些独特的难题。 例如，单独的应用程序都引用同一个 COM 程序集时发生的潜在问题。 安装新版本的程序集和另一个应用程序仍在使用旧版本的程序集时，这种情况很常见。 如果卸载共享 DLL 程序集，您可以无意中使其不可用到其他程序集。  
  
 若要避免此问题，应安装到全局程序集缓存 (GAC) 中的共享程序集和组件使用合并模块。 如果你不能安装在 GAC 中的应用程序，它应安装到 CommonFilesFolder 特定于版本的子目录中。  
  
 不共享的程序集应并排放置在与调用应用程序的目录。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [COM 互操作](../../../visual-basic/programming-guide/com-interop/index.md)  
 [Tlbimp.exe（类型库导入程序）](../../../framework/tools/tlbimp-exe-type-library-importer.md)  
 [Tlbexp.exe（类型库导出程序）](http://msdn.microsoft.com/library/a487d61b-d166-467b-a7ca-d8b52fbff42d)  
 [演练：使用 COM 对象实现继承](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 [Inherits 语句](../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [全局程序集缓存](../../../framework/app-domains/gac.md)

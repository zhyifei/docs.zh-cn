---
title: 演练：调用 Windows API (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- DLLs, calling
- Windows API, walkthroughs
- platform invoke, walkthroughs
- API calls [Visual Basic], walkthroughs [Visual Basic]
- Windows API, calling
- walkthroughs [Visual Basic], API calls
- DllImport attribute, calling Windows API
- Declare statement [Visual Basic], declaring DLL functions
ms.assetid: 9280ca96-7a93-47a3-8d01-6d01be0657cb
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 34bfb732e2d99b259811573a427ae66628c7fc3a
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-calling-windows-apis-visual-basic"></a>演练：调用 Windows API (Visual Basic)
Windows Api 是动态链接库 (Dll) 的 Windows 操作系统的一部分。 你可以使用它们难以编写你自己的等效过程时执行任务。 例如，Windows 提供了一个名为函数`FlashWindowEx`，能让你将应用程序的标题栏显现深色和浅色之间切换。  
  
 在代码中使用 Windows Api 的优点是，它们可节省开发时间，因为它们包含大量已写入的有用的函数和等待使用。 其缺点在于 Windows Api 可能很难使用，并不出现问题时。  
  
 Windows Api 表示一类特殊的互操作性。 Windows Api 并使用托管的代码，并没有内置类型库，并使用有别于那些与 Visual Studio 一起使用的数据类型。 由于这些差异，而是因为 Windows Api 不是 COM 对象，与 Windows Api 互操作性和[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]执行使用平台调用，或 PInvoke。 平台调用是一项服务，使托管代码能够调用在 Dll 中实现的非托管的函数。 有关详细信息，请参阅[使用非托管 DLL 函数](../../../framework/interop/consuming-unmanaged-dll-functions.md)。 你可以通过使用 Visual Basic 中使用 PInvoke`Declare`语句或应用`DllImport`属性设为一个空过程。  
  
 Windows API 调用已在过去，编程的 Visual Basic 的一个重要部分，但很少需要使用 Visual Basic.NET。 只要可能，应使用从托管的代码[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]执行任务，而不是 Windows API 调用。 本演练提供了用于这些情况中的使用的信息是必需的 Windows Api。  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="api-calls-using-declare"></a>使用的 API 调用声明  
 调用 Windows Api 的最常见方法是通过使用`Declare`语句。  
  
#### <a name="to-declare-a-dll-procedure"></a>若要声明一个 DLL 的过程  
  
1.  确定你想要调用，该函数加上其自变量、 自变量类型的名称和返回值，以及的名称和 DLL 包含它的位置。  
  
    > [!NOTE]
    >  有关 Windows Api 的完整信息，请参阅平台 SDK Windows API 中的 Win32 SDK 文档。 有关 Windows Api 使用的常量的详细信息，检查如 Windows.h 平台 SDK 中包含的标头文件。  
  
2.  通过单击打开新的 Windows 应用程序项目**新建**上**文件**菜单上，，然后单击**项目**。 此时将出现 “新建项目” 对话框。  
  
3.  选择**Windows 应用程序**从 Visual Basic 项目模板列表中。 将显示新项目。  
  
4.  添加以下`Declare`函数到类或想要使用该 DLL 的模块：  
  
     [!code-vb[VbVbalrInterop#9](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_1.vb)]  
  
### <a name="parts-of-the-declare-statement"></a>部件的 Declare 语句  
 `Declare`语句包括以下元素。  
  
#### <a name="auto-modifier"></a>Auto 修饰符  
 `Auto`修饰符指示运行时将依据根据公共语言运行时规则 （或已指定的别名） 的方法名称的字符串转换。  
  
#### <a name="lib-and-alias-keywords"></a>Lib 和别名关键字  
 名称以下`Function`关键字是程序用来访问导入的函数的名称。 它可以是你要调用的函数的实际名称相同，也可以使用任何有效的过程名称，然后利用`Alias`关键字来指定要调用的函数的真实名称。  
  
 指定`Lib`关键字后, 跟的名称和包含要调用的函数的 dll 的位置。 不需要指定的 Windows 系统目录中的文件的路径。  
  
 使用`Alias`关键字正在调用的函数的名称不是有效的 Visual Basic 过程名称，或与你的应用程序中的其他项的名称冲突。 `Alias` 指示被调用函数的真实名称。  
  
#### <a name="argument-and-data-type-declarations"></a>自变量和数据类型声明  
 声明参数和其数据类型。 此部分会很困难，因为 Windows 使用的数据类型并不对应于 Visual Studio 数据类型。 Visual Basic 可通过将参数转换为兼容的数据类型，名为的过程为你进行大量工作*封送处理*。 你可以显式控制自变量封送的方式使用<xref:System.Runtime.InteropServices.MarshalAsAttribute>中定义特性<xref:System.Runtime.InteropServices>命名空间。  
  
> [!NOTE]
>  Visual Basic 早期版本允许您可以声明参数`As Any`，这意味着该数据的任何数据就无法使用类型。 Visual Basic 要求对所有使用特定的数据类型`Declare`语句。  
  
#### <a name="windows-api-constants"></a>Windows API 常量  
 某些参数是常量的组合。 例如，`MessageBox`本演练中所示的 API 接受整数自变量调用的`Typ`控制消息框的显示方式。 你可以通过检查来确定这些常量的数值`#define`文件参见 WinUser.h 中的语句。 以十六进制表示，通常显示的数字值，因此你可能想要使用一个计算器来添加它们并转换为十进制数。 例如，如果你想要合并的感叹号样式的常量`MB_ICONEXCLAMATION`0x00000030 和是/无样式`MB_YESNO`0x00000004，你可以将数字并获取结果 0x00000034 52 十进制。 虽然可以直接使用十进制的结果，则最好将这些值作为你的应用程序中的常量声明并将其组合使用`Or`运算符。  
  
###### <a name="to-declare-constants-for-windows-api-calls"></a>若要声明常量用于 Windows API 调用  
  
1.  查阅文档以获取要调用的 Windows 函数。 确定使用的常数的名称以及包含这些常量的数值的.h 文件的名称。  
  
2.  使用文本编辑器，如记事本，若要查看的内容标头 (.h) 文件，并查找与你使用的常量的值。 例如， `MessageBox` API 使用常量`MB_ICONQUESTION`要在消息框中显示一个问号。 定义`MB_ICONQUESTION`参见 WinUser.h 中，且显示，如下所示：  
  
     `#define MB_ICONQUESTION             0x00000020L`  
  
3.  添加等效`Const`到你的类或模块，以使这些常量可供你的应用程序的语句。 例如：  
  
     [!code-vb[VbVbalrInterop#11](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_2.vb)]  
  
###### <a name="to-call-the-dll-procedure"></a>调用 DLL 过程  
  
1.  添加名为的按钮`Button1`启动窗体让你的项目，然后双击它以查看其代码。 显示的事件处理程序按钮。  
  
2.  将代码添加到`Click`你添加的按钮，以调用该过程并提供适当的参数的事件处理程序：  
  
     [!code-vb[VbVbalrInterop#12](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_3.vb)]  
  
3.  按 F5 运行项目。 两种版本同时显示消息框**是**和**否**响应按钮。 单击其中任何一个。  
  
#### <a name="data-marshaling"></a>数据封送处理  
 Visual Basic 会自动将转换数据类型的参数和返回值为 Windows API 调用，但你可以使用`MarshalAs`属性来显式指定的 API 需要的非托管的数据类型。 关于互操作封送处理的详细信息，请参阅[互操作封送处理](../../../framework/interop/interop-marshaling.md)。  
  
###### <a name="to-use-declare-and-marshalas-in-an-api-call"></a>要在 API 调用中使用 Declare 和 MarshalAs  
  
1.  确定所需的参数、 调用数据类型的函数的名称和返回值。  
  
2.  若要简化对访问`MarshalAs`特性，请添加`Imports`语句到类或模块，如以下示例所示的代码的顶部：  
  
     [!code-vb[VbVbalrInterop#13](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_4.vb)]  
  
3.  将导入函数的函数原型添加到类或模块使用的，并应用`MarshalAs`属性设为参数或返回值。 在下面的示例中，需要类型的 API 调用`void*`作为封送`AsAny`:  
  
     [!code-vb[VbVbalrInterop#14](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_5.vb)]  
  
## <a name="api-calls-using-dllimport"></a>使用 DllImport API 调用  
 `DllImport`属性提供了不带类型库 Dll 中调用函数的第二个方法。 `DllImport` 大致相当于使用`Declare`语句，但可以更好地控制函数的调用方式。  
  
 你可以使用`DllImport`与大多数 Windows API 调用，只要调用指共享 (有时称为*静态*) 方法。 不能使用需要的类的实例的方法。 与不同`Declare`语句，`DllImport`调用不能使用`MarshalAs`属性。  
  
#### <a name="to-call-a-windows-api-using-the-dllimport-attribute"></a>若要调用 Windows API 使用 DllImport 特性  
  
1.  通过单击打开新的 Windows 应用程序项目**新建**上**文件**菜单上，，然后单击**项目**。 此时将出现 “新建项目” 对话框。  
  
2.  选择**Windows 应用程序**从 Visual Basic 项目模板列表中。 将显示新项目。  
  
3.  添加名为的按钮`Button2`到启动窗体。  
  
4.  双击`Button2`以打开窗体的代码视图。  
  
5.  若要简化对访问`DllImport`，添加`Imports`语句到启动窗体类的代码的顶部：  
  
     [!code-vb[VbVbalrInterop#13](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_4.vb)]  
  
6.  声明空函数前面`End Class`语句窗体中，并将函数命名`MoveFile`。  
  
7.  应用`Public`和`Shared`修饰符的函数声明和设置的参数来`MoveFile`基于 Windows API 函数使用的参数：  
  
     [!code-vb[VbVbalrInterop#16](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_6.vb)]  
  
     您的函数可以具有任何有效的过程的名称;`DllImport`特性 DLL 中指定的名称。 它还可以处理互操作封送处理的参数和返回值，因此，你可以选择 Visual Studio 数据类型都类似于的数据类型的 API 使用。  
  
8.  应用`DllImport`属性为空函数。 第一个参数是的名称和包含要调用的函数的 dll 的位置。 不需要指定的 Windows 系统目录中的文件的路径。 第二个参数是一个命名的参数，Windows API 中指定函数的名称。 在此示例中，`DllImport`属性强制对调用`MoveFile`转发到`MoveFileW`KERNEL32 中。DLL。 `MoveFileW`方法将文件复制从路径`src`到路径`dst`。  
  
     [!code-vb[VbVbalrInterop#17](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_7.vb)]  
  
9. 将代码添加到`Button2_Click`事件处理程序调用该函数：  
  
     [!code-vb[VbVbalrInterop#18](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_8.vb)]  
  
10. 创建一个名为 Test.txt 文件并将其放在您的硬盘上 C:\Tmp 目录中。 如有必要，请创建 Tmp 目录。  
  
11. 按 F5 键启动该应用程序。 主窗体将出现。  
  
12. 单击**Button2**。 如果可以移动该文件，将显示"该文件已成功移动"消息。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Runtime.InteropServices.DllImportAttribute>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [Auto](../../../visual-basic/language-reference/modifiers/auto.md)  
 [Alias](../../../visual-basic/language-reference/statements/alias-clause.md)  
 [COM 互操作](../../../visual-basic/programming-guide/com-interop/index.md)  
 [在托管代码中创建原型](../../../framework/interop/creating-prototypes-in-managed-code.md)  
 [将委托作为回调方法进行封送](../../../framework/interop/marshaling-a-delegate-as-a-callback-method.md)

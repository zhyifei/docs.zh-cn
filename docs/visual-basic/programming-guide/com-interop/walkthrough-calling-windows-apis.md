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
# <a name="walkthrough-calling-windows-apis-visual-basic"></a><span data-ttu-id="60990-102">演练：调用 Windows API (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="60990-102">Walkthrough: Calling Windows APIs (Visual Basic)</span></span>
<span data-ttu-id="60990-103">Windows Api 是动态链接库 (Dll) 的 Windows 操作系统的一部分。</span><span class="sxs-lookup"><span data-stu-id="60990-103">Windows APIs are dynamic-link libraries (DLLs) that are part of the Windows operating system.</span></span> <span data-ttu-id="60990-104">你可以使用它们难以编写你自己的等效过程时执行任务。</span><span class="sxs-lookup"><span data-stu-id="60990-104">You use them to perform tasks when it is difficult to write equivalent procedures of your own.</span></span> <span data-ttu-id="60990-105">例如，Windows 提供了一个名为函数`FlashWindowEx`，能让你将应用程序的标题栏显现深色和浅色之间切换。</span><span class="sxs-lookup"><span data-stu-id="60990-105">For example, Windows provides a function named `FlashWindowEx` that lets you make the title bar for an application alternate between light and dark shades.</span></span>  
  
 <span data-ttu-id="60990-106">在代码中使用 Windows Api 的优点是，它们可节省开发时间，因为它们包含大量已写入的有用的函数和等待使用。</span><span class="sxs-lookup"><span data-stu-id="60990-106">The advantage of using Windows APIs in your code is that they can save development time because they contain dozens of useful functions that are already written and waiting to be used.</span></span> <span data-ttu-id="60990-107">其缺点在于 Windows Api 可能很难使用，并不出现问题时。</span><span class="sxs-lookup"><span data-stu-id="60990-107">The disadvantage is that Windows APIs can be difficult to work with and unforgiving when things go wrong.</span></span>  
  
 <span data-ttu-id="60990-108">Windows Api 表示一类特殊的互操作性。</span><span class="sxs-lookup"><span data-stu-id="60990-108">Windows APIs represent a special category of interoperability.</span></span> <span data-ttu-id="60990-109">Windows Api 并使用托管的代码，并没有内置类型库，并使用有别于那些与 Visual Studio 一起使用的数据类型。</span><span class="sxs-lookup"><span data-stu-id="60990-109">Windows APIs do not use managed code, do not have built-in type libraries, and use data types that are different than those used with Visual Studio.</span></span> <span data-ttu-id="60990-110">由于这些差异，而是因为 Windows Api 不是 COM 对象，与 Windows Api 互操作性和[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]执行使用平台调用，或 PInvoke。</span><span class="sxs-lookup"><span data-stu-id="60990-110">Because of these differences, and because Windows APIs are not COM objects, interoperability with Windows APIs and the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] is performed using platform invoke, or PInvoke.</span></span> <span data-ttu-id="60990-111">平台调用是一项服务，使托管代码能够调用在 Dll 中实现的非托管的函数。</span><span class="sxs-lookup"><span data-stu-id="60990-111">Platform invoke is a service that enables managed code to call unmanaged functions implemented in DLLs.</span></span> <span data-ttu-id="60990-112">有关详细信息，请参阅[使用非托管 DLL 函数](../../../framework/interop/consuming-unmanaged-dll-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="60990-112">For more information, see [Consuming Unmanaged DLL Functions](../../../framework/interop/consuming-unmanaged-dll-functions.md).</span></span> <span data-ttu-id="60990-113">你可以通过使用 Visual Basic 中使用 PInvoke`Declare`语句或应用`DllImport`属性设为一个空过程。</span><span class="sxs-lookup"><span data-stu-id="60990-113">You can use PInvoke in Visual Basic by using either the `Declare` statement or applying the `DllImport` attribute to an empty procedure.</span></span>  
  
 <span data-ttu-id="60990-114">Windows API 调用已在过去，编程的 Visual Basic 的一个重要部分，但很少需要使用 Visual Basic.NET。</span><span class="sxs-lookup"><span data-stu-id="60990-114">Windows API calls were an important part of Visual Basic programming in the past, but are seldom necessary with Visual Basic .NET.</span></span> <span data-ttu-id="60990-115">只要可能，应使用从托管的代码[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]执行任务，而不是 Windows API 调用。</span><span class="sxs-lookup"><span data-stu-id="60990-115">Whenever possible, you should use managed code from the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] to perform tasks, instead of Windows API calls.</span></span> <span data-ttu-id="60990-116">本演练提供了用于这些情况中的使用的信息是必需的 Windows Api。</span><span class="sxs-lookup"><span data-stu-id="60990-116">This walkthrough provides information for those situations in which using Windows APIs is necessary.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="api-calls-using-declare"></a><span data-ttu-id="60990-117">使用的 API 调用声明</span><span class="sxs-lookup"><span data-stu-id="60990-117">API Calls Using Declare</span></span>  
 <span data-ttu-id="60990-118">调用 Windows Api 的最常见方法是通过使用`Declare`语句。</span><span class="sxs-lookup"><span data-stu-id="60990-118">The most common way to call Windows APIs is by using the `Declare` statement.</span></span>  
  
#### <a name="to-declare-a-dll-procedure"></a><span data-ttu-id="60990-119">若要声明一个 DLL 的过程</span><span class="sxs-lookup"><span data-stu-id="60990-119">To declare a DLL procedure</span></span>  
  
1.  <span data-ttu-id="60990-120">确定你想要调用，该函数加上其自变量、 自变量类型的名称和返回值，以及的名称和 DLL 包含它的位置。</span><span class="sxs-lookup"><span data-stu-id="60990-120">Determine the name of the function you want to call, plus its arguments, argument types, and return value, as well as the name and location of the DLL that contains it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="60990-121">有关 Windows Api 的完整信息，请参阅平台 SDK Windows API 中的 Win32 SDK 文档。</span><span class="sxs-lookup"><span data-stu-id="60990-121">For complete information about the Windows APIs, see the Win32 SDK documentation in the Platform SDK Windows API.</span></span> <span data-ttu-id="60990-122">有关 Windows Api 使用的常量的详细信息，检查如 Windows.h 平台 SDK 中包含的标头文件。</span><span class="sxs-lookup"><span data-stu-id="60990-122">For more information about the constants that Windows APIs use, examine the header files such as Windows.h included with the Platform SDK.</span></span>  
  
2.  <span data-ttu-id="60990-123">通过单击打开新的 Windows 应用程序项目**新建**上**文件**菜单上，，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="60990-123">Open a new Windows Application project by clicking **New** on the **File** menu, and then clicking **Project**.</span></span> <span data-ttu-id="60990-124">此时将出现 “新建项目” 对话框。</span><span class="sxs-lookup"><span data-stu-id="60990-124">The **New Project** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="60990-125">选择**Windows 应用程序**从 Visual Basic 项目模板列表中。</span><span class="sxs-lookup"><span data-stu-id="60990-125">Select **Windows Application** from the list of Visual Basic project templates.</span></span> <span data-ttu-id="60990-126">将显示新项目。</span><span class="sxs-lookup"><span data-stu-id="60990-126">The new project is displayed.</span></span>  
  
4.  <span data-ttu-id="60990-127">添加以下`Declare`函数到类或想要使用该 DLL 的模块：</span><span class="sxs-lookup"><span data-stu-id="60990-127">Add the following `Declare` function either to the class or module in which you want to use the DLL:</span></span>  
  
     [!code-vb[VbVbalrInterop#9](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_1.vb)]  
  
### <a name="parts-of-the-declare-statement"></a><span data-ttu-id="60990-128">部件的 Declare 语句</span><span class="sxs-lookup"><span data-stu-id="60990-128">Parts of the Declare Statement</span></span>  
 <span data-ttu-id="60990-129">`Declare`语句包括以下元素。</span><span class="sxs-lookup"><span data-stu-id="60990-129">The `Declare` statement includes the following elements.</span></span>  
  
#### <a name="auto-modifier"></a><span data-ttu-id="60990-130">Auto 修饰符</span><span class="sxs-lookup"><span data-stu-id="60990-130">Auto modifier</span></span>  
 <span data-ttu-id="60990-131">`Auto`修饰符指示运行时将依据根据公共语言运行时规则 （或已指定的别名） 的方法名称的字符串转换。</span><span class="sxs-lookup"><span data-stu-id="60990-131">The `Auto` modifier instructs the runtime to convert the string based on the method name according to common language runtime rules (or alias name if specified).</span></span>  
  
#### <a name="lib-and-alias-keywords"></a><span data-ttu-id="60990-132">Lib 和别名关键字</span><span class="sxs-lookup"><span data-stu-id="60990-132">Lib and Alias keywords</span></span>  
 <span data-ttu-id="60990-133">名称以下`Function`关键字是程序用来访问导入的函数的名称。</span><span class="sxs-lookup"><span data-stu-id="60990-133">The name following the `Function` keyword is the name your program uses to access the imported function.</span></span> <span data-ttu-id="60990-134">它可以是你要调用的函数的实际名称相同，也可以使用任何有效的过程名称，然后利用`Alias`关键字来指定要调用的函数的真实名称。</span><span class="sxs-lookup"><span data-stu-id="60990-134">It can be the same as the real name of the function you are calling, or you can use any valid procedure name and then employ the `Alias` keyword to specify the real name of the function you are calling.</span></span>  
  
 <span data-ttu-id="60990-135">指定`Lib`关键字后, 跟的名称和包含要调用的函数的 dll 的位置。</span><span class="sxs-lookup"><span data-stu-id="60990-135">Specify the `Lib` keyword, followed by the name and location of the DLL that contains the function you are calling.</span></span> <span data-ttu-id="60990-136">不需要指定的 Windows 系统目录中的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="60990-136">You do not need to specify the path for files located in the Windows system directories.</span></span>  
  
 <span data-ttu-id="60990-137">使用`Alias`关键字正在调用的函数的名称不是有效的 Visual Basic 过程名称，或与你的应用程序中的其他项的名称冲突。</span><span class="sxs-lookup"><span data-stu-id="60990-137">Use the `Alias` keyword if the name of the function you are calling is not a valid Visual Basic procedure name, or conflicts with the name of other items in your application.</span></span> <span data-ttu-id="60990-138">`Alias` 指示被调用函数的真实名称。</span><span class="sxs-lookup"><span data-stu-id="60990-138">`Alias` indicates the true name of the function being called.</span></span>  
  
#### <a name="argument-and-data-type-declarations"></a><span data-ttu-id="60990-139">自变量和数据类型声明</span><span class="sxs-lookup"><span data-stu-id="60990-139">Argument and Data Type Declarations</span></span>  
 <span data-ttu-id="60990-140">声明参数和其数据类型。</span><span class="sxs-lookup"><span data-stu-id="60990-140">Declare the arguments and their data types.</span></span> <span data-ttu-id="60990-141">此部分会很困难，因为 Windows 使用的数据类型并不对应于 Visual Studio 数据类型。</span><span class="sxs-lookup"><span data-stu-id="60990-141">This part can be challenging because the data types that Windows uses do not correspond to Visual Studio data types.</span></span> <span data-ttu-id="60990-142">Visual Basic 可通过将参数转换为兼容的数据类型，名为的过程为你进行大量工作*封送处理*。</span><span class="sxs-lookup"><span data-stu-id="60990-142">Visual Basic does a lot of the work for you by converting arguments to compatible data types, a process called *marshaling*.</span></span> <span data-ttu-id="60990-143">你可以显式控制自变量封送的方式使用<xref:System.Runtime.InteropServices.MarshalAsAttribute>中定义特性<xref:System.Runtime.InteropServices>命名空间。</span><span class="sxs-lookup"><span data-stu-id="60990-143">You can explicitly control how arguments are marshaled by using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute defined in the <xref:System.Runtime.InteropServices> namespace.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="60990-144">Visual Basic 早期版本允许您可以声明参数`As Any`，这意味着该数据的任何数据就无法使用类型。</span><span class="sxs-lookup"><span data-stu-id="60990-144">Previous versions of Visual Basic allowed you to declare parameters `As Any`, meaning that data of any data type could be used.</span></span> <span data-ttu-id="60990-145">Visual Basic 要求对所有使用特定的数据类型`Declare`语句。</span><span class="sxs-lookup"><span data-stu-id="60990-145">Visual Basic requires that you use a specific data type for all `Declare` statements.</span></span>  
  
#### <a name="windows-api-constants"></a><span data-ttu-id="60990-146">Windows API 常量</span><span class="sxs-lookup"><span data-stu-id="60990-146">Windows API Constants</span></span>  
 <span data-ttu-id="60990-147">某些参数是常量的组合。</span><span class="sxs-lookup"><span data-stu-id="60990-147">Some arguments are combinations of constants.</span></span> <span data-ttu-id="60990-148">例如，`MessageBox`本演练中所示的 API 接受整数自变量调用的`Typ`控制消息框的显示方式。</span><span class="sxs-lookup"><span data-stu-id="60990-148">For example, the `MessageBox` API shown in this walkthrough accepts an integer argument called `Typ` that controls how the message box is displayed.</span></span> <span data-ttu-id="60990-149">你可以通过检查来确定这些常量的数值`#define`文件参见 WinUser.h 中的语句。</span><span class="sxs-lookup"><span data-stu-id="60990-149">You can determine the numeric value of these constants by examining the `#define` statements in the file WinUser.h.</span></span> <span data-ttu-id="60990-150">以十六进制表示，通常显示的数字值，因此你可能想要使用一个计算器来添加它们并转换为十进制数。</span><span class="sxs-lookup"><span data-stu-id="60990-150">The numeric values are generally shown in hexadecimal, so you may want to use a calculator to add them and convert to decimal.</span></span> <span data-ttu-id="60990-151">例如，如果你想要合并的感叹号样式的常量`MB_ICONEXCLAMATION`0x00000030 和是/无样式`MB_YESNO`0x00000004，你可以将数字并获取结果 0x00000034 52 十进制。</span><span class="sxs-lookup"><span data-stu-id="60990-151">For example, if you want to combine the constants for the exclamation style `MB_ICONEXCLAMATION` 0x00000030 and the Yes/No style `MB_YESNO` 0x00000004, you can add the numbers and get a result of 0x00000034, or 52 decimal.</span></span> <span data-ttu-id="60990-152">虽然可以直接使用十进制的结果，则最好将这些值作为你的应用程序中的常量声明并将其组合使用`Or`运算符。</span><span class="sxs-lookup"><span data-stu-id="60990-152">Although you can use the decimal result directly, it is better to declare these values as constants in your application and combine them using the `Or` operator.</span></span>  
  
###### <a name="to-declare-constants-for-windows-api-calls"></a><span data-ttu-id="60990-153">若要声明常量用于 Windows API 调用</span><span class="sxs-lookup"><span data-stu-id="60990-153">To declare constants for Windows API calls</span></span>  
  
1.  <span data-ttu-id="60990-154">查阅文档以获取要调用的 Windows 函数。</span><span class="sxs-lookup"><span data-stu-id="60990-154">Consult the documentation for the Windows function you are calling.</span></span> <span data-ttu-id="60990-155">确定使用的常数的名称以及包含这些常量的数值的.h 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="60990-155">Determine the name of the constants it uses and the name of the .h file that contains the numeric values for these constants.</span></span>  
  
2.  <span data-ttu-id="60990-156">使用文本编辑器，如记事本，若要查看的内容标头 (.h) 文件，并查找与你使用的常量的值。</span><span class="sxs-lookup"><span data-stu-id="60990-156">Use a text editor, such as Notepad, to view the contents of the header (.h) file, and find the values associated with the constants you are using.</span></span> <span data-ttu-id="60990-157">例如， `MessageBox` API 使用常量`MB_ICONQUESTION`要在消息框中显示一个问号。</span><span class="sxs-lookup"><span data-stu-id="60990-157">For example, the `MessageBox` API uses the constant `MB_ICONQUESTION` to show a question mark in the message box.</span></span> <span data-ttu-id="60990-158">定义`MB_ICONQUESTION`参见 WinUser.h 中，且显示，如下所示：</span><span class="sxs-lookup"><span data-stu-id="60990-158">The definition for `MB_ICONQUESTION` is in WinUser.h and appears as follows:</span></span>  
  
     `#define MB_ICONQUESTION             0x00000020L`  
  
3.  <span data-ttu-id="60990-159">添加等效`Const`到你的类或模块，以使这些常量可供你的应用程序的语句。</span><span class="sxs-lookup"><span data-stu-id="60990-159">Add equivalent `Const` statements to your class or module to make these constants available to your application.</span></span> <span data-ttu-id="60990-160">例如：</span><span class="sxs-lookup"><span data-stu-id="60990-160">For example:</span></span>  
  
     [!code-vb[VbVbalrInterop#11](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_2.vb)]  
  
###### <a name="to-call-the-dll-procedure"></a><span data-ttu-id="60990-161">调用 DLL 过程</span><span class="sxs-lookup"><span data-stu-id="60990-161">To call the DLL procedure</span></span>  
  
1.  <span data-ttu-id="60990-162">添加名为的按钮`Button1`启动窗体让你的项目，然后双击它以查看其代码。</span><span class="sxs-lookup"><span data-stu-id="60990-162">Add a button named `Button1` to the startup form for your project, and then double-click it to view its code.</span></span> <span data-ttu-id="60990-163">显示的事件处理程序按钮。</span><span class="sxs-lookup"><span data-stu-id="60990-163">The event handler for the button is displayed.</span></span>  
  
2.  <span data-ttu-id="60990-164">将代码添加到`Click`你添加的按钮，以调用该过程并提供适当的参数的事件处理程序：</span><span class="sxs-lookup"><span data-stu-id="60990-164">Add code to the `Click` event handler for the button you added, to call the procedure and provide the appropriate arguments:</span></span>  
  
     [!code-vb[VbVbalrInterop#12](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_3.vb)]  
  
3.  <span data-ttu-id="60990-165">按 F5 运行项目。</span><span class="sxs-lookup"><span data-stu-id="60990-165">Run the project by pressing F5.</span></span> <span data-ttu-id="60990-166">两种版本同时显示消息框**是**和**否**响应按钮。</span><span class="sxs-lookup"><span data-stu-id="60990-166">The message box is displayed with both **Yes** and **No** response buttons.</span></span> <span data-ttu-id="60990-167">单击其中任何一个。</span><span class="sxs-lookup"><span data-stu-id="60990-167">Click either one.</span></span>  
  
#### <a name="data-marshaling"></a><span data-ttu-id="60990-168">数据封送处理</span><span class="sxs-lookup"><span data-stu-id="60990-168">Data Marshaling</span></span>  
 <span data-ttu-id="60990-169">Visual Basic 会自动将转换数据类型的参数和返回值为 Windows API 调用，但你可以使用`MarshalAs`属性来显式指定的 API 需要的非托管的数据类型。</span><span class="sxs-lookup"><span data-stu-id="60990-169">Visual Basic automatically converts the data types of parameters and return values for Windows API calls, but you can use the `MarshalAs` attribute to explicitly specify unmanaged data types that an API expects.</span></span> <span data-ttu-id="60990-170">关于互操作封送处理的详细信息，请参阅[互操作封送处理](../../../framework/interop/interop-marshaling.md)。</span><span class="sxs-lookup"><span data-stu-id="60990-170">For more information about interop marshaling, see [Interop Marshaling](../../../framework/interop/interop-marshaling.md).</span></span>  
  
###### <a name="to-use-declare-and-marshalas-in-an-api-call"></a><span data-ttu-id="60990-171">要在 API 调用中使用 Declare 和 MarshalAs</span><span class="sxs-lookup"><span data-stu-id="60990-171">To use Declare and MarshalAs in an API call</span></span>  
  
1.  <span data-ttu-id="60990-172">确定所需的参数、 调用数据类型的函数的名称和返回值。</span><span class="sxs-lookup"><span data-stu-id="60990-172">Determine the name of the function you want to call, plus its arguments, data types, and return value.</span></span>  
  
2.  <span data-ttu-id="60990-173">若要简化对访问`MarshalAs`特性，请添加`Imports`语句到类或模块，如以下示例所示的代码的顶部：</span><span class="sxs-lookup"><span data-stu-id="60990-173">To simplify access to the `MarshalAs` attribute, add an `Imports` statement to the top of the code for the class or module, as in the following example:</span></span>  
  
     [!code-vb[VbVbalrInterop#13](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_4.vb)]  
  
3.  <span data-ttu-id="60990-174">将导入函数的函数原型添加到类或模块使用的，并应用`MarshalAs`属性设为参数或返回值。</span><span class="sxs-lookup"><span data-stu-id="60990-174">Add a function prototype for the imported function to the class or module you are using, and apply the `MarshalAs` attribute to the parameters or return value.</span></span> <span data-ttu-id="60990-175">在下面的示例中，需要类型的 API 调用`void*`作为封送`AsAny`:</span><span class="sxs-lookup"><span data-stu-id="60990-175">In the following example, an API call that expects the type `void*` is marshaled as `AsAny`:</span></span>  
  
     [!code-vb[VbVbalrInterop#14](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_5.vb)]  
  
## <a name="api-calls-using-dllimport"></a><span data-ttu-id="60990-176">使用 DllImport API 调用</span><span class="sxs-lookup"><span data-stu-id="60990-176">API Calls Using DllImport</span></span>  
 <span data-ttu-id="60990-177">`DllImport`属性提供了不带类型库 Dll 中调用函数的第二个方法。</span><span class="sxs-lookup"><span data-stu-id="60990-177">The `DllImport` attribute provides a second way to call functions in DLLs without type libraries.</span></span> <span data-ttu-id="60990-178">`DllImport` 大致相当于使用`Declare`语句，但可以更好地控制函数的调用方式。</span><span class="sxs-lookup"><span data-stu-id="60990-178">`DllImport` is roughly equivalent to using a `Declare` statement but provides more control over how functions are called.</span></span>  
  
 <span data-ttu-id="60990-179">你可以使用`DllImport`与大多数 Windows API 调用，只要调用指共享 (有时称为*静态*) 方法。</span><span class="sxs-lookup"><span data-stu-id="60990-179">You can use `DllImport` with most Windows API calls as long as the call refers to a shared (sometimes called *static*) method.</span></span> <span data-ttu-id="60990-180">不能使用需要的类的实例的方法。</span><span class="sxs-lookup"><span data-stu-id="60990-180">You cannot use methods that require an instance of a class.</span></span> <span data-ttu-id="60990-181">与不同`Declare`语句，`DllImport`调用不能使用`MarshalAs`属性。</span><span class="sxs-lookup"><span data-stu-id="60990-181">Unlike `Declare` statements, `DllImport` calls cannot use the `MarshalAs` attribute.</span></span>  
  
#### <a name="to-call-a-windows-api-using-the-dllimport-attribute"></a><span data-ttu-id="60990-182">若要调用 Windows API 使用 DllImport 特性</span><span class="sxs-lookup"><span data-stu-id="60990-182">To call a Windows API using the DllImport attribute</span></span>  
  
1.  <span data-ttu-id="60990-183">通过单击打开新的 Windows 应用程序项目**新建**上**文件**菜单上，，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="60990-183">Open a new Windows Application project by clicking **New** on the **File** menu, and then clicking **Project**.</span></span> <span data-ttu-id="60990-184">此时将出现 “新建项目” 对话框。</span><span class="sxs-lookup"><span data-stu-id="60990-184">The **New Project** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="60990-185">选择**Windows 应用程序**从 Visual Basic 项目模板列表中。</span><span class="sxs-lookup"><span data-stu-id="60990-185">Select **Windows Application** from the list of Visual Basic project templates.</span></span> <span data-ttu-id="60990-186">将显示新项目。</span><span class="sxs-lookup"><span data-stu-id="60990-186">The new project is displayed.</span></span>  
  
3.  <span data-ttu-id="60990-187">添加名为的按钮`Button2`到启动窗体。</span><span class="sxs-lookup"><span data-stu-id="60990-187">Add a button named `Button2` to the startup form.</span></span>  
  
4.  <span data-ttu-id="60990-188">双击`Button2`以打开窗体的代码视图。</span><span class="sxs-lookup"><span data-stu-id="60990-188">Double-click `Button2` to open the code view for the form.</span></span>  
  
5.  <span data-ttu-id="60990-189">若要简化对访问`DllImport`，添加`Imports`语句到启动窗体类的代码的顶部：</span><span class="sxs-lookup"><span data-stu-id="60990-189">To simplify access to `DllImport`, add an `Imports` statement to the top of the code for the startup form class:</span></span>  
  
     [!code-vb[VbVbalrInterop#13](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_4.vb)]  
  
6.  <span data-ttu-id="60990-190">声明空函数前面`End Class`语句窗体中，并将函数命名`MoveFile`。</span><span class="sxs-lookup"><span data-stu-id="60990-190">Declare an empty function preceding the `End Class` statement for the form, and name the function `MoveFile`.</span></span>  
  
7.  <span data-ttu-id="60990-191">应用`Public`和`Shared`修饰符的函数声明和设置的参数来`MoveFile`基于 Windows API 函数使用的参数：</span><span class="sxs-lookup"><span data-stu-id="60990-191">Apply the `Public` and `Shared` modifiers to the function declaration and set parameters for `MoveFile` based on the arguments the Windows API function uses:</span></span>  
  
     [!code-vb[VbVbalrInterop#16](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_6.vb)]  
  
     <span data-ttu-id="60990-192">您的函数可以具有任何有效的过程的名称;`DllImport`特性 DLL 中指定的名称。</span><span class="sxs-lookup"><span data-stu-id="60990-192">Your function can have any valid procedure name; the `DllImport` attribute specifies the name in the DLL.</span></span> <span data-ttu-id="60990-193">它还可以处理互操作封送处理的参数和返回值，因此，你可以选择 Visual Studio 数据类型都类似于的数据类型的 API 使用。</span><span class="sxs-lookup"><span data-stu-id="60990-193">It also handles interoperability marshaling for the parameters and return values, so you can choose Visual Studio data types that are similar to the data types the API uses.</span></span>  
  
8.  <span data-ttu-id="60990-194">应用`DllImport`属性为空函数。</span><span class="sxs-lookup"><span data-stu-id="60990-194">Apply the `DllImport` attribute to the empty function.</span></span> <span data-ttu-id="60990-195">第一个参数是的名称和包含要调用的函数的 dll 的位置。</span><span class="sxs-lookup"><span data-stu-id="60990-195">The first parameter is the name and location of the DLL containing the function you are calling.</span></span> <span data-ttu-id="60990-196">不需要指定的 Windows 系统目录中的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="60990-196">You do not need to specify the path for files located in the Windows system directories.</span></span> <span data-ttu-id="60990-197">第二个参数是一个命名的参数，Windows API 中指定函数的名称。</span><span class="sxs-lookup"><span data-stu-id="60990-197">The second parameter is a named argument that specifies the name of the function in the Windows API.</span></span> <span data-ttu-id="60990-198">在此示例中，`DllImport`属性强制对调用`MoveFile`转发到`MoveFileW`KERNEL32 中。DLL。</span><span class="sxs-lookup"><span data-stu-id="60990-198">In this example, the `DllImport` attribute forces calls to `MoveFile` to be forwarded to `MoveFileW` in KERNEL32.DLL.</span></span> <span data-ttu-id="60990-199">`MoveFileW`方法将文件复制从路径`src`到路径`dst`。</span><span class="sxs-lookup"><span data-stu-id="60990-199">The `MoveFileW` method copies a file from the path `src` to the path `dst`.</span></span>  
  
     [!code-vb[VbVbalrInterop#17](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_7.vb)]  
  
9. <span data-ttu-id="60990-200">将代码添加到`Button2_Click`事件处理程序调用该函数：</span><span class="sxs-lookup"><span data-stu-id="60990-200">Add code to the `Button2_Click` event handler to call the function:</span></span>  
  
     [!code-vb[VbVbalrInterop#18](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_8.vb)]  
  
10. <span data-ttu-id="60990-201">创建一个名为 Test.txt 文件并将其放在您的硬盘上 C:\Tmp 目录中。</span><span class="sxs-lookup"><span data-stu-id="60990-201">Create a file named Test.txt and place it in the C:\Tmp directory on your hard drive.</span></span> <span data-ttu-id="60990-202">如有必要，请创建 Tmp 目录。</span><span class="sxs-lookup"><span data-stu-id="60990-202">Create the Tmp directory if necessary.</span></span>  
  
11. <span data-ttu-id="60990-203">按 F5 键启动该应用程序。</span><span class="sxs-lookup"><span data-stu-id="60990-203">Press F5 to start the application.</span></span> <span data-ttu-id="60990-204">主窗体将出现。</span><span class="sxs-lookup"><span data-stu-id="60990-204">The main form appears.</span></span>  
  
12. <span data-ttu-id="60990-205">单击**Button2**。</span><span class="sxs-lookup"><span data-stu-id="60990-205">Click **Button2**.</span></span> <span data-ttu-id="60990-206">如果可以移动该文件，将显示"该文件已成功移动"消息。</span><span class="sxs-lookup"><span data-stu-id="60990-206">The message "The file was moved successfully" is displayed if the file can be moved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60990-207">请参阅</span><span class="sxs-lookup"><span data-stu-id="60990-207">See Also</span></span>  
 <xref:System.Runtime.InteropServices.DllImportAttribute>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="60990-208">Declare 语句</span><span class="sxs-lookup"><span data-stu-id="60990-208">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [<span data-ttu-id="60990-209">Auto</span><span class="sxs-lookup"><span data-stu-id="60990-209">Auto</span></span>](../../../visual-basic/language-reference/modifiers/auto.md)  
 [<span data-ttu-id="60990-210">Alias</span><span class="sxs-lookup"><span data-stu-id="60990-210">Alias</span></span>](../../../visual-basic/language-reference/statements/alias-clause.md)  
 [<span data-ttu-id="60990-211">COM 互操作</span><span class="sxs-lookup"><span data-stu-id="60990-211">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)  
 [<span data-ttu-id="60990-212">在托管代码中创建原型</span><span class="sxs-lookup"><span data-stu-id="60990-212">Creating Prototypes in Managed Code</span></span>](../../../framework/interop/creating-prototypes-in-managed-code.md)  
 [<span data-ttu-id="60990-213">将委托作为回调方法进行封送</span><span class="sxs-lookup"><span data-stu-id="60990-213">Marshaling a Delegate as a Callback Method</span></span>](../../../framework/interop/marshaling-a-delegate-as-a-callback-method.md)

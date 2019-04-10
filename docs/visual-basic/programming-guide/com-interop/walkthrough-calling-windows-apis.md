---
title: 演练：调用 Windows Api (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 8fd63c2abedcd416937e2c281486bdc1716a275f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59332321"
---
# <a name="walkthrough-calling-windows-apis-visual-basic"></a><span data-ttu-id="195e9-102">演练：调用 Windows Api (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="195e9-102">Walkthrough: Calling Windows APIs (Visual Basic)</span></span>
<span data-ttu-id="195e9-103">Windows Api 是动态链接库 (Dll) 的 Windows 操作系统的一部分。</span><span class="sxs-lookup"><span data-stu-id="195e9-103">Windows APIs are dynamic-link libraries (DLLs) that are part of the Windows operating system.</span></span> <span data-ttu-id="195e9-104">您可以使用它们来执行任务时很难编写你自己的等效过程。</span><span class="sxs-lookup"><span data-stu-id="195e9-104">You use them to perform tasks when it is difficult to write equivalent procedures of your own.</span></span> <span data-ttu-id="195e9-105">例如，Windows 提供了一个名为函数`FlashWindowEx`允许您进行应用程序的标题栏在浅色和深色阴影之间切换。</span><span class="sxs-lookup"><span data-stu-id="195e9-105">For example, Windows provides a function named `FlashWindowEx` that lets you make the title bar for an application alternate between light and dark shades.</span></span>  
  
 <span data-ttu-id="195e9-106">在代码中使用 Windows Api 的优点是它们可以节省开发时间，因为它们包含大量有用的功能，已编写并等待使用。</span><span class="sxs-lookup"><span data-stu-id="195e9-106">The advantage of using Windows APIs in your code is that they can save development time because they contain dozens of useful functions that are already written and waiting to be used.</span></span> <span data-ttu-id="195e9-107">缺点是 Windows Api 可能很难处理和铁面无私时出现问题。</span><span class="sxs-lookup"><span data-stu-id="195e9-107">The disadvantage is that Windows APIs can be difficult to work with and unforgiving when things go wrong.</span></span>  
  
 <span data-ttu-id="195e9-108">Windows Api 表示一类特殊的互操作性。</span><span class="sxs-lookup"><span data-stu-id="195e9-108">Windows APIs represent a special category of interoperability.</span></span> <span data-ttu-id="195e9-109">Windows Api 不使用托管的代码，没有内置类型库，并使用不同于与用于 Visual Studio 的数据类型。</span><span class="sxs-lookup"><span data-stu-id="195e9-109">Windows APIs do not use managed code, do not have built-in type libraries, and use data types that are different than those used with Visual Studio.</span></span> <span data-ttu-id="195e9-110">鉴于这些区别，因为 Windows Api 不是 COM 对象，与 Windows Api 互操作性和[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]使用平台执行的调用，简称 PInvoke。</span><span class="sxs-lookup"><span data-stu-id="195e9-110">Because of these differences, and because Windows APIs are not COM objects, interoperability with Windows APIs and the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] is performed using platform invoke, or PInvoke.</span></span> <span data-ttu-id="195e9-111">平台调用是一项服务，它使托管代码能够调用非托管的 Dll 中实现的函数。</span><span class="sxs-lookup"><span data-stu-id="195e9-111">Platform invoke is a service that enables managed code to call unmanaged functions implemented in DLLs.</span></span> <span data-ttu-id="195e9-112">有关详细信息，请参阅[使用非托管 DLL 函数](../../../framework/interop/consuming-unmanaged-dll-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="195e9-112">For more information, see [Consuming Unmanaged DLL Functions](../../../framework/interop/consuming-unmanaged-dll-functions.md).</span></span> <span data-ttu-id="195e9-113">可以通过使用 Visual Basic 中使用 PInvoke`Declare`语句或将应用`DllImport`属性为空的过程。</span><span class="sxs-lookup"><span data-stu-id="195e9-113">You can use PInvoke in Visual Basic by using either the `Declare` statement or applying the `DllImport` attribute to an empty procedure.</span></span>  
  
 <span data-ttu-id="195e9-114">Windows API 调用了 Visual Basic 编程在过去，一个重要部分，但很少需要使用 Visual Basic.NET。</span><span class="sxs-lookup"><span data-stu-id="195e9-114">Windows API calls were an important part of Visual Basic programming in the past, but are seldom necessary with Visual Basic .NET.</span></span> <span data-ttu-id="195e9-115">只要有可能，应使用从托管的代码[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]来执行任务，而不是 Windows API 调用。</span><span class="sxs-lookup"><span data-stu-id="195e9-115">Whenever possible, you should use managed code from the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] to perform tasks, instead of Windows API calls.</span></span> <span data-ttu-id="195e9-116">本演练提供了哪些使用那些情况的信息是必需的 Windows Api。</span><span class="sxs-lookup"><span data-stu-id="195e9-116">This walkthrough provides information for those situations in which using Windows APIs is necessary.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="api-calls-using-declare"></a><span data-ttu-id="195e9-117">使用 API 调用声明</span><span class="sxs-lookup"><span data-stu-id="195e9-117">API Calls Using Declare</span></span>  
 <span data-ttu-id="195e9-118">调用 Windows Api 的最常见方法是使用`Declare`语句。</span><span class="sxs-lookup"><span data-stu-id="195e9-118">The most common way to call Windows APIs is by using the `Declare` statement.</span></span>  
  
#### <a name="to-declare-a-dll-procedure"></a><span data-ttu-id="195e9-119">若要声明 DLL 过程</span><span class="sxs-lookup"><span data-stu-id="195e9-119">To declare a DLL procedure</span></span>  
  
1. <span data-ttu-id="195e9-120">确定你想要调用，该函数及其参数、 参数类型的名称和返回值，以及名称和包含该 DLL 的位置。</span><span class="sxs-lookup"><span data-stu-id="195e9-120">Determine the name of the function you want to call, plus its arguments, argument types, and return value, as well as the name and location of the DLL that contains it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="195e9-121">有关 Windows Api 的完整信息，请参阅平台 SDK Windows API 中的 Win32 SDK 文档。</span><span class="sxs-lookup"><span data-stu-id="195e9-121">For complete information about the Windows APIs, see the Win32 SDK documentation in the Platform SDK Windows API.</span></span> <span data-ttu-id="195e9-122">有关 Windows Api 使用的常量的详细信息，检查如 Windows.h Platform SDK 中包含的标头文件。</span><span class="sxs-lookup"><span data-stu-id="195e9-122">For more information about the constants that Windows APIs use, examine the header files such as Windows.h included with the Platform SDK.</span></span>  
  
2. <span data-ttu-id="195e9-123">通过单击打开一个新的 Windows 应用程序项目**新建**上**文件**菜单中，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="195e9-123">Open a new Windows Application project by clicking **New** on the **File** menu, and then clicking **Project**.</span></span> <span data-ttu-id="195e9-124">此时将出现“新建项目”对话框。</span><span class="sxs-lookup"><span data-stu-id="195e9-124">The **New Project** dialog box appears.</span></span>  
  
3. <span data-ttu-id="195e9-125">选择**Windows 应用程序**从 Visual Basic 项目模板的列表。</span><span class="sxs-lookup"><span data-stu-id="195e9-125">Select **Windows Application** from the list of Visual Basic project templates.</span></span> <span data-ttu-id="195e9-126">显示新的项目。</span><span class="sxs-lookup"><span data-stu-id="195e9-126">The new project is displayed.</span></span>  
  
4. <span data-ttu-id="195e9-127">以下代码添加到`Declare`函数到类或想要使用该 DLL 的模块：</span><span class="sxs-lookup"><span data-stu-id="195e9-127">Add the following `Declare` function either to the class or module in which you want to use the DLL:</span></span>  
  
     [!code-vb[VbVbalrInterop#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#9)]  
  
### <a name="parts-of-the-declare-statement"></a><span data-ttu-id="195e9-128">部件的 Declare 语句</span><span class="sxs-lookup"><span data-stu-id="195e9-128">Parts of the Declare Statement</span></span>  
 <span data-ttu-id="195e9-129">`Declare`语句包括以下元素。</span><span class="sxs-lookup"><span data-stu-id="195e9-129">The `Declare` statement includes the following elements.</span></span>  
  
#### <a name="auto-modifier"></a><span data-ttu-id="195e9-130">Auto 修饰符</span><span class="sxs-lookup"><span data-stu-id="195e9-130">Auto modifier</span></span>  
 <span data-ttu-id="195e9-131">`Auto`修饰符指示运行时转换基于根据公共语言运行时规则 （或已指定的别名） 的方法名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="195e9-131">The `Auto` modifier instructs the runtime to convert the string based on the method name according to common language runtime rules (or alias name if specified).</span></span>  
  
#### <a name="lib-and-alias-keywords"></a><span data-ttu-id="195e9-132">Lib 和别名关键字</span><span class="sxs-lookup"><span data-stu-id="195e9-132">Lib and Alias keywords</span></span>  
 <span data-ttu-id="195e9-133">名称以下`Function`关键字是您的程序用来访问导入的函数的名称。</span><span class="sxs-lookup"><span data-stu-id="195e9-133">The name following the `Function` keyword is the name your program uses to access the imported function.</span></span> <span data-ttu-id="195e9-134">它可以是你要调用的函数的真实名称相同，也可以使用任何有效的过程名称，然后使用`Alias`关键字来指定要调用的函数的真实名称。</span><span class="sxs-lookup"><span data-stu-id="195e9-134">It can be the same as the real name of the function you are calling, or you can use any valid procedure name and then employ the `Alias` keyword to specify the real name of the function you are calling.</span></span>  
  
 <span data-ttu-id="195e9-135">指定`Lib`关键字后, 跟的名称和包含要调用的函数的 DLL 的位置。</span><span class="sxs-lookup"><span data-stu-id="195e9-135">Specify the `Lib` keyword, followed by the name and location of the DLL that contains the function you are calling.</span></span> <span data-ttu-id="195e9-136">不需要指定位于 Windows 系统目录中文件的路径。</span><span class="sxs-lookup"><span data-stu-id="195e9-136">You do not need to specify the path for files located in the Windows system directories.</span></span>  
  
 <span data-ttu-id="195e9-137">使用`Alias`关键字，如果你正在调用的函数的名称不是有效的 Visual Basic 过程名称，或与你的应用程序中其他项的名称冲突。</span><span class="sxs-lookup"><span data-stu-id="195e9-137">Use the `Alias` keyword if the name of the function you are calling is not a valid Visual Basic procedure name, or conflicts with the name of other items in your application.</span></span> `Alias` <span data-ttu-id="195e9-138">指示要调用的函数的真实名称。</span><span class="sxs-lookup"><span data-stu-id="195e9-138">indicates the true name of the function being called.</span></span>  
  
#### <a name="argument-and-data-type-declarations"></a><span data-ttu-id="195e9-139">参数和数据类型声明</span><span class="sxs-lookup"><span data-stu-id="195e9-139">Argument and Data Type Declarations</span></span>  
 <span data-ttu-id="195e9-140">声明的参数和其数据类型。</span><span class="sxs-lookup"><span data-stu-id="195e9-140">Declare the arguments and their data types.</span></span> <span data-ttu-id="195e9-141">此部分会很困难，因为 Windows 使用的数据类型不对应于 Visual Studio 的数据类型。</span><span class="sxs-lookup"><span data-stu-id="195e9-141">This part can be challenging because the data types that Windows uses do not correspond to Visual Studio data types.</span></span> <span data-ttu-id="195e9-142">Visual Basic 通过将参数转换为兼容的数据类型，名为的过程为您完成大量工作*封送处理*。</span><span class="sxs-lookup"><span data-stu-id="195e9-142">Visual Basic does a lot of the work for you by converting arguments to compatible data types, a process called *marshaling*.</span></span> <span data-ttu-id="195e9-143">您可以显式控制参数使用被封送<xref:System.Runtime.InteropServices.MarshalAsAttribute>属性中定义<xref:System.Runtime.InteropServices>命名空间。</span><span class="sxs-lookup"><span data-stu-id="195e9-143">You can explicitly control how arguments are marshaled by using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute defined in the <xref:System.Runtime.InteropServices> namespace.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="195e9-144">Visual Basic 的早期版本允许您声明参数`As Any`，这意味着该数据的任何数据就可以使用类型。</span><span class="sxs-lookup"><span data-stu-id="195e9-144">Previous versions of Visual Basic allowed you to declare parameters `As Any`, meaning that data of any data type could be used.</span></span> <span data-ttu-id="195e9-145">Visual Basic 要求您对所有使用特定的数据类型`Declare`语句。</span><span class="sxs-lookup"><span data-stu-id="195e9-145">Visual Basic requires that you use a specific data type for all `Declare` statements.</span></span>  
  
#### <a name="windows-api-constants"></a><span data-ttu-id="195e9-146">Windows API 常量</span><span class="sxs-lookup"><span data-stu-id="195e9-146">Windows API Constants</span></span>  
 <span data-ttu-id="195e9-147">某些参数是常量的组合。</span><span class="sxs-lookup"><span data-stu-id="195e9-147">Some arguments are combinations of constants.</span></span> <span data-ttu-id="195e9-148">例如，`MessageBox`在本演练中所示的 API 接受整数参数名为`Typ`，它控制如何显示消息框。</span><span class="sxs-lookup"><span data-stu-id="195e9-148">For example, the `MessageBox` API shown in this walkthrough accepts an integer argument called `Typ` that controls how the message box is displayed.</span></span> <span data-ttu-id="195e9-149">可以通过检查来确定这些常量的数值`#define`文件 WinUser.h 中的语句。</span><span class="sxs-lookup"><span data-stu-id="195e9-149">You can determine the numeric value of these constants by examining the `#define` statements in the file WinUser.h.</span></span> <span data-ttu-id="195e9-150">以十六进制格式，通常显示的数字值，因此可能需要使用一个计算器来将它们添加并将转换为十进制。</span><span class="sxs-lookup"><span data-stu-id="195e9-150">The numeric values are generally shown in hexadecimal, so you may want to use a calculator to add them and convert to decimal.</span></span> <span data-ttu-id="195e9-151">例如，如果想要合并的感叹号样式的常量`MB_ICONEXCLAMATION`0x00000030 和是/无样式`MB_YESNO`0x00000004，可以添加数字并获取结果 0x00000034 52 十进制。</span><span class="sxs-lookup"><span data-stu-id="195e9-151">For example, if you want to combine the constants for the exclamation style `MB_ICONEXCLAMATION` 0x00000030 and the Yes/No style `MB_YESNO` 0x00000004, you can add the numbers and get a result of 0x00000034, or 52 decimal.</span></span> <span data-ttu-id="195e9-152">虽然可以直接使用十进制的结果，则最好将这些值声明为你的应用程序中的常量并将其组合使用`Or`运算符。</span><span class="sxs-lookup"><span data-stu-id="195e9-152">Although you can use the decimal result directly, it is better to declare these values as constants in your application and combine them using the `Or` operator.</span></span>  
  
###### <a name="to-declare-constants-for-windows-api-calls"></a><span data-ttu-id="195e9-153">若要声明常量 Windows API 调用</span><span class="sxs-lookup"><span data-stu-id="195e9-153">To declare constants for Windows API calls</span></span>  
  
1. <span data-ttu-id="195e9-154">要调用的 Windows 函数，请参阅文档。</span><span class="sxs-lookup"><span data-stu-id="195e9-154">Consult the documentation for the Windows function you are calling.</span></span> <span data-ttu-id="195e9-155">确定使用的常数的名称以及包含这些常量的数值的.h 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="195e9-155">Determine the name of the constants it uses and the name of the .h file that contains the numeric values for these constants.</span></span>  
  
2. <span data-ttu-id="195e9-156">使用文本编辑器，如记事本，若要查看的内容标头 (.h) 文件，并查找与正在使用的常量相关联的值。</span><span class="sxs-lookup"><span data-stu-id="195e9-156">Use a text editor, such as Notepad, to view the contents of the header (.h) file, and find the values associated with the constants you are using.</span></span> <span data-ttu-id="195e9-157">例如， `MessageBox` API 使用常量`MB_ICONQUESTION`在消息框中显示一个问号。</span><span class="sxs-lookup"><span data-stu-id="195e9-157">For example, the `MessageBox` API uses the constant `MB_ICONQUESTION` to show a question mark in the message box.</span></span> <span data-ttu-id="195e9-158">有关定义`MB_ICONQUESTION`是在 WinUser.h 中，将出现，如下所示：</span><span class="sxs-lookup"><span data-stu-id="195e9-158">The definition for `MB_ICONQUESTION` is in WinUser.h and appears as follows:</span></span>  
  
     `#define MB_ICONQUESTION             0x00000020L`  
  
3. <span data-ttu-id="195e9-159">添加等效`Const`到类或模块，以使这些常量可用于应用程序的语句。</span><span class="sxs-lookup"><span data-stu-id="195e9-159">Add equivalent `Const` statements to your class or module to make these constants available to your application.</span></span> <span data-ttu-id="195e9-160">例如：</span><span class="sxs-lookup"><span data-stu-id="195e9-160">For example:</span></span>  
  
     [!code-vb[VbVbalrInterop#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#11)]  
  
###### <a name="to-call-the-dll-procedure"></a><span data-ttu-id="195e9-161">若要调用的 DLL 过程</span><span class="sxs-lookup"><span data-stu-id="195e9-161">To call the DLL procedure</span></span>  
  
1. <span data-ttu-id="195e9-162">添加名为的按钮`Button1`启动窗体让你的项目，然后双击它以查看其代码。</span><span class="sxs-lookup"><span data-stu-id="195e9-162">Add a button named `Button1` to the startup form for your project, and then double-click it to view its code.</span></span> <span data-ttu-id="195e9-163">显示按钮的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="195e9-163">The event handler for the button is displayed.</span></span>  
  
2. <span data-ttu-id="195e9-164">将代码添加到`Click`您添加的按钮，调用该过程，并提供适当的参数的事件处理程序：</span><span class="sxs-lookup"><span data-stu-id="195e9-164">Add code to the `Click` event handler for the button you added, to call the procedure and provide the appropriate arguments:</span></span>  
  
     [!code-vb[VbVbalrInterop#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#12)]  
  
3. <span data-ttu-id="195e9-165">通过按 F5 运行项目。</span><span class="sxs-lookup"><span data-stu-id="195e9-165">Run the project by pressing F5.</span></span> <span data-ttu-id="195e9-166">消息框显示两个**是**并**否**响应按钮。</span><span class="sxs-lookup"><span data-stu-id="195e9-166">The message box is displayed with both **Yes** and **No** response buttons.</span></span> <span data-ttu-id="195e9-167">单击其中任何一个。</span><span class="sxs-lookup"><span data-stu-id="195e9-167">Click either one.</span></span>  
  
#### <a name="data-marshaling"></a><span data-ttu-id="195e9-168">数据封送处理</span><span class="sxs-lookup"><span data-stu-id="195e9-168">Data Marshaling</span></span>  
 <span data-ttu-id="195e9-169">Visual Basic 会自动将转换的数据类型的参数和返回值为 Windows API 调用，但你可以使用`MarshalAs`属性来显式指定 API 预期的非托管的数据类型。</span><span class="sxs-lookup"><span data-stu-id="195e9-169">Visual Basic automatically converts the data types of parameters and return values for Windows API calls, but you can use the `MarshalAs` attribute to explicitly specify unmanaged data types that an API expects.</span></span> <span data-ttu-id="195e9-170">关于互操作封送处理的详细信息，请参阅[互操作封送处理](../../../framework/interop/interop-marshaling.md)。</span><span class="sxs-lookup"><span data-stu-id="195e9-170">For more information about interop marshaling, see [Interop Marshaling](../../../framework/interop/interop-marshaling.md).</span></span>  
  
###### <a name="to-use-declare-and-marshalas-in-an-api-call"></a><span data-ttu-id="195e9-171">若要在 API 调用中使用 Declare 和 MarshalAs</span><span class="sxs-lookup"><span data-stu-id="195e9-171">To use Declare and MarshalAs in an API call</span></span>  
  
1. <span data-ttu-id="195e9-172">确定你想要的参数、 调用数据类型的函数的名称和返回值。</span><span class="sxs-lookup"><span data-stu-id="195e9-172">Determine the name of the function you want to call, plus its arguments, data types, and return value.</span></span>  
  
2. <span data-ttu-id="195e9-173">若要简化对访问`MarshalAs`特性，请添加`Imports`到类或模块，如以下示例所示的代码的顶部的语句：</span><span class="sxs-lookup"><span data-stu-id="195e9-173">To simplify access to the `MarshalAs` attribute, add an `Imports` statement to the top of the code for the class or module, as in the following example:</span></span>  
  
     [!code-vb[VbVbalrInterop#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#13)]  
  
3. <span data-ttu-id="195e9-174">将导入的函数的函数原型添加到类或模块使用的，并应用`MarshalAs`属性为参数或返回值。</span><span class="sxs-lookup"><span data-stu-id="195e9-174">Add a function prototype for the imported function to the class or module you are using, and apply the `MarshalAs` attribute to the parameters or return value.</span></span> <span data-ttu-id="195e9-175">在下面的示例中，需要类型的 API 调用`void*`被封送为`AsAny`:</span><span class="sxs-lookup"><span data-stu-id="195e9-175">In the following example, an API call that expects the type `void*` is marshaled as `AsAny`:</span></span>  
  
     [!code-vb[VbVbalrInterop#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#14)]  
  
## <a name="api-calls-using-dllimport"></a><span data-ttu-id="195e9-176">使用 DllImport 的 API 调用</span><span class="sxs-lookup"><span data-stu-id="195e9-176">API Calls Using DllImport</span></span>  
 <span data-ttu-id="195e9-177">`DllImport`属性提供不带类型库在 Dll 中调用函数的第二个方法。</span><span class="sxs-lookup"><span data-stu-id="195e9-177">The `DllImport` attribute provides a second way to call functions in DLLs without type libraries.</span></span> `DllImport` <span data-ttu-id="195e9-178">大致相当于使用`Declare`语句，但可以更好地控制函数的调用方式。</span><span class="sxs-lookup"><span data-stu-id="195e9-178">is roughly equivalent to using a `Declare` statement but provides more control over how functions are called.</span></span>  
  
 <span data-ttu-id="195e9-179">可以使用`DllImport`与大多数 Windows API 调用，只要该调用是指在不共享 (有时称为*静态*) 方法。</span><span class="sxs-lookup"><span data-stu-id="195e9-179">You can use `DllImport` with most Windows API calls as long as the call refers to a shared (sometimes called *static*) method.</span></span> <span data-ttu-id="195e9-180">不能使用需要的类实例的方法。</span><span class="sxs-lookup"><span data-stu-id="195e9-180">You cannot use methods that require an instance of a class.</span></span> <span data-ttu-id="195e9-181">与不同`Declare`语句，`DllImport`的调用不能使用`MarshalAs`属性。</span><span class="sxs-lookup"><span data-stu-id="195e9-181">Unlike `Declare` statements, `DllImport` calls cannot use the `MarshalAs` attribute.</span></span>  
  
#### <a name="to-call-a-windows-api-using-the-dllimport-attribute"></a><span data-ttu-id="195e9-182">若要调用 Windows API 使用 DllImport 特性</span><span class="sxs-lookup"><span data-stu-id="195e9-182">To call a Windows API using the DllImport attribute</span></span>  
  
1. <span data-ttu-id="195e9-183">通过单击打开一个新的 Windows 应用程序项目**新建**上**文件**菜单中，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="195e9-183">Open a new Windows Application project by clicking **New** on the **File** menu, and then clicking **Project**.</span></span> <span data-ttu-id="195e9-184">此时将出现“新建项目”对话框。</span><span class="sxs-lookup"><span data-stu-id="195e9-184">The **New Project** dialog box appears.</span></span>  
  
2. <span data-ttu-id="195e9-185">选择**Windows 应用程序**从 Visual Basic 项目模板的列表。</span><span class="sxs-lookup"><span data-stu-id="195e9-185">Select **Windows Application** from the list of Visual Basic project templates.</span></span> <span data-ttu-id="195e9-186">显示新的项目。</span><span class="sxs-lookup"><span data-stu-id="195e9-186">The new project is displayed.</span></span>  
  
3. <span data-ttu-id="195e9-187">添加名为的按钮`Button2`到启动窗体。</span><span class="sxs-lookup"><span data-stu-id="195e9-187">Add a button named `Button2` to the startup form.</span></span>  
  
4. <span data-ttu-id="195e9-188">双击`Button2`以打开窗体的代码视图。</span><span class="sxs-lookup"><span data-stu-id="195e9-188">Double-click `Button2` to open the code view for the form.</span></span>  
  
5. <span data-ttu-id="195e9-189">若要简化对访问`DllImport`，添加`Imports`语句启动窗体类的代码的顶部：</span><span class="sxs-lookup"><span data-stu-id="195e9-189">To simplify access to `DllImport`, add an `Imports` statement to the top of the code for the startup form class:</span></span>  
  
     [!code-vb[VbVbalrInterop#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#13)]  
  
6. <span data-ttu-id="195e9-190">声明一个空的函数，前面`End Class`窗体，并将函数命名为语句`MoveFile`。</span><span class="sxs-lookup"><span data-stu-id="195e9-190">Declare an empty function preceding the `End Class` statement for the form, and name the function `MoveFile`.</span></span>  
  
7. <span data-ttu-id="195e9-191">将应用`Public`并`Shared`函数声明和设置的参数的修饰符`MoveFile`根据 Windows API 函数使用的参数：</span><span class="sxs-lookup"><span data-stu-id="195e9-191">Apply the `Public` and `Shared` modifiers to the function declaration and set parameters for `MoveFile` based on the arguments the Windows API function uses:</span></span>  
  
     [!code-vb[VbVbalrInterop#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#16)]  
  
     <span data-ttu-id="195e9-192">你的函数名称可以是任意有效的过程;`DllImport`属性在 DLL 中指定的名称。</span><span class="sxs-lookup"><span data-stu-id="195e9-192">Your function can have any valid procedure name; the `DllImport` attribute specifies the name in the DLL.</span></span> <span data-ttu-id="195e9-193">它还处理互操作封送处理参数和返回值，因此，可以选择 Visual Studio 的数据类型类似于数据的类型 API 使用。</span><span class="sxs-lookup"><span data-stu-id="195e9-193">It also handles interoperability marshaling for the parameters and return values, so you can choose Visual Studio data types that are similar to the data types the API uses.</span></span>  
  
8. <span data-ttu-id="195e9-194">将应用`DllImport`属性为空函数。</span><span class="sxs-lookup"><span data-stu-id="195e9-194">Apply the `DllImport` attribute to the empty function.</span></span> <span data-ttu-id="195e9-195">第一个参数是名称和包含要调用的函数的 dll 的位置。</span><span class="sxs-lookup"><span data-stu-id="195e9-195">The first parameter is the name and location of the DLL containing the function you are calling.</span></span> <span data-ttu-id="195e9-196">不需要指定位于 Windows 系统目录中文件的路径。</span><span class="sxs-lookup"><span data-stu-id="195e9-196">You do not need to specify the path for files located in the Windows system directories.</span></span> <span data-ttu-id="195e9-197">第二个参数是函数的命名的参数，Windows API 中指定的名称。</span><span class="sxs-lookup"><span data-stu-id="195e9-197">The second parameter is a named argument that specifies the name of the function in the Windows API.</span></span> <span data-ttu-id="195e9-198">在此示例中，`DllImport`属性强制调用`MoveFile`转发到`MoveFileW`KERNEL32 中。DLL。</span><span class="sxs-lookup"><span data-stu-id="195e9-198">In this example, the `DllImport` attribute forces calls to `MoveFile` to be forwarded to `MoveFileW` in KERNEL32.DLL.</span></span> <span data-ttu-id="195e9-199">`MoveFileW`方法将文件复制从路径`src`到路径`dst`。</span><span class="sxs-lookup"><span data-stu-id="195e9-199">The `MoveFileW` method copies a file from the path `src` to the path `dst`.</span></span>  
  
     [!code-vb[VbVbalrInterop#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#17)]  
  
9. <span data-ttu-id="195e9-200">将代码添加到`Button2_Click`事件处理程序调用该函数：</span><span class="sxs-lookup"><span data-stu-id="195e9-200">Add code to the `Button2_Click` event handler to call the function:</span></span>  
  
     [!code-vb[VbVbalrInterop#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrInterop/VB/Class1.vb#18)]  
  
10. <span data-ttu-id="195e9-201">创建一个名为 Test.txt 文件并将其放在硬盘上 C:\Tmp 目录中。</span><span class="sxs-lookup"><span data-stu-id="195e9-201">Create a file named Test.txt and place it in the C:\Tmp directory on your hard drive.</span></span> <span data-ttu-id="195e9-202">如有必要，请创建临时目录。</span><span class="sxs-lookup"><span data-stu-id="195e9-202">Create the Tmp directory if necessary.</span></span>  
  
11. <span data-ttu-id="195e9-203">按 F5 键启动该应用程序。</span><span class="sxs-lookup"><span data-stu-id="195e9-203">Press F5 to start the application.</span></span> <span data-ttu-id="195e9-204">主窗体显示。</span><span class="sxs-lookup"><span data-stu-id="195e9-204">The main form appears.</span></span>  
  
12. <span data-ttu-id="195e9-205">单击**Button2**。</span><span class="sxs-lookup"><span data-stu-id="195e9-205">Click **Button2**.</span></span> <span data-ttu-id="195e9-206">如果可以移动该文件，则会显示"文件已移动已成功"消息。</span><span class="sxs-lookup"><span data-stu-id="195e9-206">The message "The file was moved successfully" is displayed if the file can be moved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="195e9-207">请参阅</span><span class="sxs-lookup"><span data-stu-id="195e9-207">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="195e9-208">Declare Statement</span><span class="sxs-lookup"><span data-stu-id="195e9-208">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="195e9-209">自动</span><span class="sxs-lookup"><span data-stu-id="195e9-209">Auto</span></span>](../../../visual-basic/language-reference/modifiers/auto.md)
- [<span data-ttu-id="195e9-210">Alias</span><span class="sxs-lookup"><span data-stu-id="195e9-210">Alias</span></span>](../../../visual-basic/language-reference/statements/alias-clause.md)
- [<span data-ttu-id="195e9-211">COM 互操作</span><span class="sxs-lookup"><span data-stu-id="195e9-211">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)
- [<span data-ttu-id="195e9-212">在托管代码中创建原型</span><span class="sxs-lookup"><span data-stu-id="195e9-212">Creating Prototypes in Managed Code</span></span>](../../../framework/interop/creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="195e9-213">将委托作为回调方法进行封送</span><span class="sxs-lookup"><span data-stu-id="195e9-213">Marshaling a Delegate as a Callback Method</span></span>](../../../framework/interop/marshaling-a-delegate-as-a-callback-method.md)

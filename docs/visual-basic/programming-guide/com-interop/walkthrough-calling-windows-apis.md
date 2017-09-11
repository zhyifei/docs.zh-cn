---
title: "演练︰ 调用 Windows Api (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- DLLs, calling
- Windows API, walkthroughs
- platform invoke, walkthroughs
- API calls, walkthroughs [Visual Basic]
- Windows API, calling
- walkthroughs [Visual Basic], API calls
- DllImport attribute, calling Windows API
- Declare statement, declaring DLL functions
ms.assetid: 9280ca96-7a93-47a3-8d01-6d01be0657cb
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: ae1ef60e6e27658c872689f5bfe2779493d42e7a
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-calling-windows-apis-visual-basic"></a><span data-ttu-id="86b74-102">演练：调用 Windows API (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="86b74-102">Walkthrough: Calling Windows APIs (Visual Basic)</span></span>
<span data-ttu-id="86b74-103">Windows Api 都是动态链接库 (Dll) 的 Windows 操作系统的一部分。</span><span class="sxs-lookup"><span data-stu-id="86b74-103">Windows APIs are dynamic-link libraries (DLLs) that are part of the Windows operating system.</span></span> <span data-ttu-id="86b74-104">您可以使用它们来执行任务时都很难编写您自己的等效的过程。</span><span class="sxs-lookup"><span data-stu-id="86b74-104">You use them to perform tasks when it is difficult to write equivalent procedures of your own.</span></span> <span data-ttu-id="86b74-105">例如，Windows 提供了一个名为函数`FlashWindowEx`，能让你将应用程序的标题栏显现深色和浅色之间交替。</span><span class="sxs-lookup"><span data-stu-id="86b74-105">For example, Windows provides a function named `FlashWindowEx` that lets you make the title bar for an application alternate between light and dark shades.</span></span>  
  
 <span data-ttu-id="86b74-106">在您的代码中使用 Windows Api 的优点是它们可以节省开发时间，因为它们包含大量有用的功能，已经编写并等待使用。</span><span class="sxs-lookup"><span data-stu-id="86b74-106">The advantage of using Windows APIs in your code is that they can save development time because they contain dozens of useful functions that are already written and waiting to be used.</span></span> <span data-ttu-id="86b74-107">缺点是 Windows Api 可能很难处理和铁面无私出现故障时。</span><span class="sxs-lookup"><span data-stu-id="86b74-107">The disadvantage is that Windows APIs can be difficult to work with and unforgiving when things go wrong.</span></span>  
  
 <span data-ttu-id="86b74-108">Windows Api 表示一类特殊的互操作性。</span><span class="sxs-lookup"><span data-stu-id="86b74-108">Windows APIs represent a special category of interoperability.</span></span> <span data-ttu-id="86b74-109">Windows Api 不使用托管的代码，并没有内置类型库，并使用有别于那些与 Visual Studio 一起使用的数据类型。</span><span class="sxs-lookup"><span data-stu-id="86b74-109">Windows APIs do not use managed code, do not have built-in type libraries, and use data types that are different than those used with Visual Studio.</span></span> <span data-ttu-id="86b74-110">由于这些差异，并且因为 Windows Api 不是 COM 对象，与 Windows Api 互操作性和[!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]执行使用平台调用，或 PInvoke。</span><span class="sxs-lookup"><span data-stu-id="86b74-110">Because of these differences, and because Windows APIs are not COM objects, interoperability with Windows APIs and the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] is performed using platform invoke, or PInvoke.</span></span> <span data-ttu-id="86b74-111">平台调用是一种服务使托管代码能够调用非托管的 Dll 中实现的函数。</span><span class="sxs-lookup"><span data-stu-id="86b74-111">Platform invoke is a service that enables managed code to call unmanaged functions implemented in DLLs.</span></span> <span data-ttu-id="86b74-112">有关详细信息，请参阅[使用非托管 DLL 函数](http://msdn.microsoft.com/library/eca7606e-ebfb-4f47-b8d9-289903fdc045)。</span><span class="sxs-lookup"><span data-stu-id="86b74-112">For more information, see [Consuming Unmanaged DLL Functions](http://msdn.microsoft.com/library/eca7606e-ebfb-4f47-b8d9-289903fdc045).</span></span> <span data-ttu-id="86b74-113">您可以使用中的 PInvoke[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]使用`Declare`语句或应用`DllImport`属性设为一个空过程。</span><span class="sxs-lookup"><span data-stu-id="86b74-113">You can use PInvoke in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] by using either the `Declare` statement or applying the `DllImport` attribute to an empty procedure.</span></span>  
  
 <span data-ttu-id="86b74-114">Windows API 调用了一个重要组成部分[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]编程在过去，但很少必要时使用[!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="86b74-114">Windows API calls were an important part of [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] programming in the past, but are seldom necessary with [!INCLUDE[vbprvblong](../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)].</span></span> <span data-ttu-id="86b74-115">只要有可能，应使用托管的代码的[!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]来执行任务，而不是 Windows API 调用。</span><span class="sxs-lookup"><span data-stu-id="86b74-115">Whenever possible, you should use managed code from the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] to perform tasks, instead of Windows API calls.</span></span> <span data-ttu-id="86b74-116">本演练提供了用于在使用这些情况的信息是必需的 Windows Api。</span><span class="sxs-lookup"><span data-stu-id="86b74-116">This walkthrough provides information for those situations in which using Windows APIs is necessary.</span></span>  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
## <a name="api-calls-using-declare"></a><span data-ttu-id="86b74-117">使用 API 调用声明</span><span class="sxs-lookup"><span data-stu-id="86b74-117">API Calls Using Declare</span></span>  
 <span data-ttu-id="86b74-118">调用 Windows Api 的最常见方法是通过使用`Declare`语句。</span><span class="sxs-lookup"><span data-stu-id="86b74-118">The most common way to call Windows APIs is by using the `Declare` statement.</span></span>  
  
#### <a name="to-declare-a-dll-procedure"></a><span data-ttu-id="86b74-119">若要声明一个 DLL 过程</span><span class="sxs-lookup"><span data-stu-id="86b74-119">To declare a DLL procedure</span></span>  
  
1.  <span data-ttu-id="86b74-120">确定你想要调用，该函数及其参数、 参数类型的名称和返回值，以及名称和包含该 DLL 的位置。</span><span class="sxs-lookup"><span data-stu-id="86b74-120">Determine the name of the function you want to call, plus its arguments, argument types, and return value, as well as the name and location of the DLL that contains it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="86b74-121">有关 Windows Api 的完整信息，请参阅平台 SDK Windows API 中的 Win32 SDK 文档。</span><span class="sxs-lookup"><span data-stu-id="86b74-121">For complete information about the Windows APIs, see the Win32 SDK documentation in the Platform SDK Windows API.</span></span> <span data-ttu-id="86b74-122">有关 Windows Api 使用的常量的详细信息，检查如 Windows.h Platform SDK 中包含的标头文件。</span><span class="sxs-lookup"><span data-stu-id="86b74-122">For more information about the constants that Windows APIs use, examine the header files such as Windows.h included with the Platform SDK.</span></span>  
  
2.  <span data-ttu-id="86b74-123">通过单击以打开新的 Windows 应用程序项目**新建**上**文件**菜单，并单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="86b74-123">Open a new Windows Application project by clicking **New** on the **File** menu, and then clicking **Project**.</span></span> <span data-ttu-id="86b74-124">此时将出现 **“新建项目”** 对话框。</span><span class="sxs-lookup"><span data-stu-id="86b74-124">The **New Project** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="86b74-125">选择**Windows 应用程序**从列表中[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]项目模板。</span><span class="sxs-lookup"><span data-stu-id="86b74-125">Select **Windows Application** from the list of [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] project templates.</span></span> <span data-ttu-id="86b74-126">将显示新项目。</span><span class="sxs-lookup"><span data-stu-id="86b74-126">The new project is displayed.</span></span>  
  
4.  <span data-ttu-id="86b74-127">将以下代码添加`Declare`函数到类或想要使用的 DLL 的模块︰</span><span class="sxs-lookup"><span data-stu-id="86b74-127">Add the following `Declare` function either to the class or module in which you want to use the DLL:</span></span>  
  
     <span data-ttu-id="86b74-128">[!code-vb[VbVbalrInterop #&9;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="86b74-128">[!code-vb[VbVbalrInterop#9](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_1.vb)]</span></span>  
  
### <a name="parts-of-the-declare-statement"></a><span data-ttu-id="86b74-129">部件的 Declare 语句</span><span class="sxs-lookup"><span data-stu-id="86b74-129">Parts of the Declare Statement</span></span>  
 <span data-ttu-id="86b74-130">`Declare`语句包括以下元素。</span><span class="sxs-lookup"><span data-stu-id="86b74-130">The `Declare` statement includes the following elements.</span></span>  
  
#### <a name="auto-modifier"></a><span data-ttu-id="86b74-131">Auto 修饰符</span><span class="sxs-lookup"><span data-stu-id="86b74-131">Auto modifier</span></span>  
 <span data-ttu-id="86b74-132">`Auto`修饰符指示运行时转换基于根据公共语言运行时规则 （或已指定的别名） 的方法名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="86b74-132">The `Auto` modifier instructs the runtime to convert the string based on the method name according to common language runtime rules (or alias name if specified).</span></span>  
  
#### <a name="lib-and-alias-keywords"></a><span data-ttu-id="86b74-133">Lib 和别名关键字</span><span class="sxs-lookup"><span data-stu-id="86b74-133">Lib and Alias keywords</span></span>  
 <span data-ttu-id="86b74-134">名称以下`Function`关键字是您的程序用来访问导入的函数的名称。</span><span class="sxs-lookup"><span data-stu-id="86b74-134">The name following the `Function` keyword is the name your program uses to access the imported function.</span></span> <span data-ttu-id="86b74-135">它可以是您要调用的函数的实际名称相同，也可以使用任何有效的过程名称，然后采用`Alias`关键字来指定要调用的函数的真实名称。</span><span class="sxs-lookup"><span data-stu-id="86b74-135">It can be the same as the real name of the function you are calling, or you can use any valid procedure name and then employ the `Alias` keyword to specify the real name of the function you are calling.</span></span>  
  
 <span data-ttu-id="86b74-136">指定`Lib`关键字后, 跟的名称和包含要调用的函数的 dll 的位置。</span><span class="sxs-lookup"><span data-stu-id="86b74-136">Specify the `Lib` keyword, followed by the name and location of the DLL that contains the function you are calling.</span></span> <span data-ttu-id="86b74-137">不需要指定位于 Windows 系统目录中的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="86b74-137">You do not need to specify the path for files located in the Windows system directories.</span></span>  
  
 <span data-ttu-id="86b74-138">使用`Alias`如果要调用的函数的名称不是有效的关键字[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]过程名称，或者与您的应用程序中的其他项的名称冲突。</span><span class="sxs-lookup"><span data-stu-id="86b74-138">Use the `Alias` keyword if the name of the function you are calling is not a valid [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] procedure name, or conflicts with the name of other items in your application.</span></span> <span data-ttu-id="86b74-139">`Alias`指示要调用的函数的真实名称。</span><span class="sxs-lookup"><span data-stu-id="86b74-139">`Alias` indicates the true name of the function being called.</span></span>  
  
#### <a name="argument-and-data-type-declarations"></a><span data-ttu-id="86b74-140">参数和数据类型声明</span><span class="sxs-lookup"><span data-stu-id="86b74-140">Argument and Data Type Declarations</span></span>  
 <span data-ttu-id="86b74-141">声明的参数和它们的数据类型。</span><span class="sxs-lookup"><span data-stu-id="86b74-141">Declare the arguments and their data types.</span></span> <span data-ttu-id="86b74-142">此部分会很困难，因为 Windows 所使用的数据类型并不对应于 Visual Studio 的数据类型。</span><span class="sxs-lookup"><span data-stu-id="86b74-142">This part can be challenging because the data types that Windows uses do not correspond to Visual Studio data types.</span></span> [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="86b74-143">通过将参数转换为兼容的数据类型，名为的过程为您完成大量工作*封送处理*。</span><span class="sxs-lookup"><span data-stu-id="86b74-143"> does a lot of the work for you by converting arguments to compatible data types, a process called *marshaling*.</span></span> <span data-ttu-id="86b74-144">您可以显式控制参数封送的方式使用<xref:System.Runtime.InteropServices.MarshalAsAttribute>中定义特性<xref:System.Runtime.InteropServices>命名空间。</xref:System.Runtime.InteropServices> </xref:System.Runtime.InteropServices.MarshalAsAttribute></span><span class="sxs-lookup"><span data-stu-id="86b74-144">You can explicitly control how arguments are marshaled by using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute defined in the <xref:System.Runtime.InteropServices> namespace.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="86b74-145">以前版本的[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]允许您声明参数`As Any`，这意味着这些数据的任何数据就可以使用类型。</span><span class="sxs-lookup"><span data-stu-id="86b74-145">Previous versions of [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] allowed you to declare parameters `As Any`, meaning that data of any data type could be used.</span></span> [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="86b74-146">需要对所有使用特定的数据类型`Declare`语句。</span><span class="sxs-lookup"><span data-stu-id="86b74-146"> requires that you use a specific data type for all `Declare` statements.</span></span>  
  
#### <a name="windows-api-constants"></a><span data-ttu-id="86b74-147">Windows API 常量</span><span class="sxs-lookup"><span data-stu-id="86b74-147">Windows API Constants</span></span>  
 <span data-ttu-id="86b74-148">某些参数是常量的组合。</span><span class="sxs-lookup"><span data-stu-id="86b74-148">Some arguments are combinations of constants.</span></span> <span data-ttu-id="86b74-149">例如，`MessageBox`在本演练中所示的 API 接受整数参数调用`Typ`，它控制如何显示消息框。</span><span class="sxs-lookup"><span data-stu-id="86b74-149">For example, the `MessageBox` API shown in this walkthrough accepts an integer argument called `Typ` that controls how the message box is displayed.</span></span> <span data-ttu-id="86b74-150">可以通过检查来确定这些常量的数值`#define`文件 WinUser.h 中的语句。</span><span class="sxs-lookup"><span data-stu-id="86b74-150">You can determine the numeric value of these constants by examining the `#define` statements in the file WinUser.h.</span></span> <span data-ttu-id="86b74-151">以十六进制形式，通常显示的数字值，因此您可能希望使用一个计算器来将它们添加并将转换为十进制。</span><span class="sxs-lookup"><span data-stu-id="86b74-151">The numeric values are generally shown in hexadecimal, so you may want to use a calculator to add them and convert to decimal.</span></span> <span data-ttu-id="86b74-152">例如，如果您想要合并的感叹号样式的常量`MB_ICONEXCLAMATION`0x00000030 和是 / 无样式`MB_YESNO`0x00000004，你可以将数字并获取结果 0x00000034 52 十进制。</span><span class="sxs-lookup"><span data-stu-id="86b74-152">For example, if you want to combine the constants for the exclamation style `MB_ICONEXCLAMATION` 0x00000030 and the Yes/No style `MB_YESNO` 0x00000004, you can add the numbers and get a result of 0x00000034, or 52 decimal.</span></span> <span data-ttu-id="86b74-153">尽管可以直接使用十进制的结果，则最好将这些值声明为您的应用程序中的常量并将其组合使用`Or`运算符。</span><span class="sxs-lookup"><span data-stu-id="86b74-153">Although you can use the decimal result directly, it is better to declare these values as constants in your application and combine them using the `Or` operator.</span></span>  
  
###### <a name="to-declare-constants-for-windows-api-calls"></a><span data-ttu-id="86b74-154">可以声明为 Windows API 调用的常量</span><span class="sxs-lookup"><span data-stu-id="86b74-154">To declare constants for Windows API calls</span></span>  
  
1.  <span data-ttu-id="86b74-155">查阅文档以获取要调用的 Windows 函数。</span><span class="sxs-lookup"><span data-stu-id="86b74-155">Consult the documentation for the Windows function you are calling.</span></span> <span data-ttu-id="86b74-156">确定使用的常数的名称以及包含这些常量的数值的.h 文件的名称。</span><span class="sxs-lookup"><span data-stu-id="86b74-156">Determine the name of the constants it uses and the name of the .h file that contains the numeric values for these constants.</span></span>  
  
2.  <span data-ttu-id="86b74-157">使用文本编辑器，如记事本，若要查看的内容标头 (.h) 文件，并查找与您使用的常量相关联的值。</span><span class="sxs-lookup"><span data-stu-id="86b74-157">Use a text editor, such as Notepad, to view the contents of the header (.h) file, and find the values associated with the constants you are using.</span></span> <span data-ttu-id="86b74-158">例如， `MessageBox` API 使用常数`MB_ICONQUESTION`以在消息框中显示一个问号。</span><span class="sxs-lookup"><span data-stu-id="86b74-158">For example, the `MessageBox` API uses the constant `MB_ICONQUESTION` to show a question mark in the message box.</span></span> <span data-ttu-id="86b74-159">有关定义`MB_ICONQUESTION`都在 WinUser.h 中，且出现，如下所示︰</span><span class="sxs-lookup"><span data-stu-id="86b74-159">The definition for `MB_ICONQUESTION` is in WinUser.h and appears as follows:</span></span>  
  
     `#define MB_ICONQUESTION             0x00000020L`  
  
3.  <span data-ttu-id="86b74-160">添加等效`Const`到类或模块，以使这些常量可供您的应用程序的语句。</span><span class="sxs-lookup"><span data-stu-id="86b74-160">Add equivalent `Const` statements to your class or module to make these constants available to your application.</span></span> <span data-ttu-id="86b74-161">例如：</span><span class="sxs-lookup"><span data-stu-id="86b74-161">For example:</span></span>  
  
     <span data-ttu-id="86b74-162">[!code-vb[VbVbalrInterop #&11;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="86b74-162">[!code-vb[VbVbalrInterop#11](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_2.vb)]</span></span>  
  
###### <a name="to-call-the-dll-procedure"></a><span data-ttu-id="86b74-163">若要调用 DLL 的过程</span><span class="sxs-lookup"><span data-stu-id="86b74-163">To call the DLL procedure</span></span>  
  
1.  <span data-ttu-id="86b74-164">添加名为的按钮`Button1`的启动窗体让你的项目，然后双击它以查看其代码。</span><span class="sxs-lookup"><span data-stu-id="86b74-164">Add a button named `Button1` to the startup form for your project, and then double-click it to view its code.</span></span> <span data-ttu-id="86b74-165">显示的事件处理程序按钮。</span><span class="sxs-lookup"><span data-stu-id="86b74-165">The event handler for the button is displayed.</span></span>  
  
2.  <span data-ttu-id="86b74-166">将代码添加到`Click`您添加的按钮，以调用过程并提供适当的参数的事件处理程序︰</span><span class="sxs-lookup"><span data-stu-id="86b74-166">Add code to the `Click` event handler for the button you added, to call the procedure and provide the appropriate arguments:</span></span>  
  
     <span data-ttu-id="86b74-167">[!code-vb[VbVbalrInterop #&12;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="86b74-167">[!code-vb[VbVbalrInterop#12](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_3.vb)]</span></span>  
  
3.  <span data-ttu-id="86b74-168">通过按 F5 运行项目。</span><span class="sxs-lookup"><span data-stu-id="86b74-168">Run the project by pressing F5.</span></span> <span data-ttu-id="86b74-169">这两种显示消息框**是**和**否**响应按钮。</span><span class="sxs-lookup"><span data-stu-id="86b74-169">The message box is displayed with both **Yes** and **No** response buttons.</span></span> <span data-ttu-id="86b74-170">单击其中一种方法。</span><span class="sxs-lookup"><span data-stu-id="86b74-170">Click either one.</span></span>  
  
#### <a name="data-marshaling"></a><span data-ttu-id="86b74-171">数据封送处理</span><span class="sxs-lookup"><span data-stu-id="86b74-171">Data Marshaling</span></span>  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="86b74-172">自动转换为数据类型的参数和返回值为 Windows API 调用，但您可以使用`MarshalAs`特性显式指定 API 预期的非托管的数据类型。</span><span class="sxs-lookup"><span data-stu-id="86b74-172"> automatically converts the data types of parameters and return values for Windows API calls, but you can use the `MarshalAs` attribute to explicitly specify unmanaged data types that an API expects.</span></span> <span data-ttu-id="86b74-173">关于互操作封送处理的详细信息，请参阅[互操作封送处理](http://msdn.microsoft.com/library/115f7a2f-d422-4605-ab36-13a8dd28142a)。</span><span class="sxs-lookup"><span data-stu-id="86b74-173">For more information about interop marshaling, see [Interop Marshaling](http://msdn.microsoft.com/library/115f7a2f-d422-4605-ab36-13a8dd28142a).</span></span>  
  
###### <a name="to-use-declare-and-marshalas-in-an-api-call"></a><span data-ttu-id="86b74-174">API 调用中使用 Declare 和 MarshalAs</span><span class="sxs-lookup"><span data-stu-id="86b74-174">To use Declare and MarshalAs in an API call</span></span>  
  
1.  <span data-ttu-id="86b74-175">确定所需的参数、 调用数据类型的函数的名称，并返回值。</span><span class="sxs-lookup"><span data-stu-id="86b74-175">Determine the name of the function you want to call, plus its arguments, data types, and return value.</span></span>  
  
2.  <span data-ttu-id="86b74-176">若要简化对访问`MarshalAs`特性，请添加`Imports`到类或模块，如以下示例所示的代码的顶部的语句︰</span><span class="sxs-lookup"><span data-stu-id="86b74-176">To simplify access to the `MarshalAs` attribute, add an `Imports` statement to the top of the code for the class or module, as in the following example:</span></span>  
  
     <span data-ttu-id="86b74-177">[!code-vb[VbVbalrInterop #&13;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="86b74-177">[!code-vb[VbVbalrInterop#13](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_4.vb)]</span></span>  
  
3.  <span data-ttu-id="86b74-178">将导入的函数的函数原型添加到类或模块使用的，并应用`MarshalAs`属性设为参数或返回值。</span><span class="sxs-lookup"><span data-stu-id="86b74-178">Add a function prototype for the imported function to the class or module you are using, and apply the `MarshalAs` attribute to the parameters or return value.</span></span> <span data-ttu-id="86b74-179">在下面的示例中，要求类型的 API 调用`void*`作为封送`AsAny`:</span><span class="sxs-lookup"><span data-stu-id="86b74-179">In the following example, an API call that expects the type `void*` is marshaled as `AsAny`:</span></span>  
  
     <span data-ttu-id="86b74-180">[!code-vb[VbVbalrInterop #&14;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="86b74-180">[!code-vb[VbVbalrInterop#14](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_5.vb)]</span></span>  
  
## <a name="api-calls-using-dllimport"></a><span data-ttu-id="86b74-181">使用 DllImport API 调用</span><span class="sxs-lookup"><span data-stu-id="86b74-181">API Calls Using DllImport</span></span>  
 <span data-ttu-id="86b74-182">`DllImport`属性提供了不带类型库的 Dll 中调用函数的第二个方法。</span><span class="sxs-lookup"><span data-stu-id="86b74-182">The `DllImport` attribute provides a second way to call functions in DLLs without type libraries.</span></span> <span data-ttu-id="86b74-183">`DllImport`大致相当于使用`Declare`语句，但可以更好地控制函数的调用方式。</span><span class="sxs-lookup"><span data-stu-id="86b74-183">`DllImport` is roughly equivalent to using a `Declare` statement but provides more control over how functions are called.</span></span>  
  
 <span data-ttu-id="86b74-184">您可以使用`DllImport`与大多数 Windows API 调用，只要该调用是指共享 (有时称为*静态*) 方法。</span><span class="sxs-lookup"><span data-stu-id="86b74-184">You can use `DllImport` with most Windows API calls as long as the call refers to a shared (sometimes called *static*) method.</span></span> <span data-ttu-id="86b74-185">不能使用需要的类实例的方法。</span><span class="sxs-lookup"><span data-stu-id="86b74-185">You cannot use methods that require an instance of a class.</span></span> <span data-ttu-id="86b74-186">与不同`Declare`语句，`DllImport`调用不能使用`MarshalAs`属性。</span><span class="sxs-lookup"><span data-stu-id="86b74-186">Unlike `Declare` statements, `DllImport` calls cannot use the `MarshalAs` attribute.</span></span>  
  
#### <a name="to-call-a-windows-api-using-the-dllimport-attribute"></a><span data-ttu-id="86b74-187">若要调用 Windows API 使用 DllImport 特性</span><span class="sxs-lookup"><span data-stu-id="86b74-187">To call a Windows API using the DllImport attribute</span></span>  
  
1.  <span data-ttu-id="86b74-188">通过单击以打开新的 Windows 应用程序项目**新建**上**文件**菜单，并单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="86b74-188">Open a new Windows Application project by clicking **New** on the **File** menu, and then clicking **Project**.</span></span> <span data-ttu-id="86b74-189">此时将出现 **“新建项目”** 对话框。</span><span class="sxs-lookup"><span data-stu-id="86b74-189">The **New Project** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="86b74-190">选择**Windows 应用程序**从列表中[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]项目模板。</span><span class="sxs-lookup"><span data-stu-id="86b74-190">Select **Windows Application** from the list of [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] project templates.</span></span> <span data-ttu-id="86b74-191">将显示新项目。</span><span class="sxs-lookup"><span data-stu-id="86b74-191">The new project is displayed.</span></span>  
  
3.  <span data-ttu-id="86b74-192">添加名为的按钮`Button2`到启动窗体。</span><span class="sxs-lookup"><span data-stu-id="86b74-192">Add a button named `Button2` to the startup form.</span></span>  
  
4.  <span data-ttu-id="86b74-193">双击`Button2`打开窗体的代码视图。</span><span class="sxs-lookup"><span data-stu-id="86b74-193">Double-click `Button2` to open the code view for the form.</span></span>  
  
5.  <span data-ttu-id="86b74-194">若要简化对访问`DllImport`，添加`Imports`语句将启动窗体类的代码的顶部︰</span><span class="sxs-lookup"><span data-stu-id="86b74-194">To simplify access to `DllImport`, add an `Imports` statement to the top of the code for the startup form class:</span></span>  
  
     <span data-ttu-id="86b74-195">[!code-vb[VbVbalrInterop #&13;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="86b74-195">[!code-vb[VbVbalrInterop#13](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_4.vb)]</span></span>  
  
6.  <span data-ttu-id="86b74-196">声明一个空函数前面`End Class`语句窗体中，并将函数命名`MoveFile`。</span><span class="sxs-lookup"><span data-stu-id="86b74-196">Declare an empty function preceding the `End Class` statement for the form, and name the function `MoveFile`.</span></span>  
  
7.  <span data-ttu-id="86b74-197">应用`Public`和`Shared`函数声明和设置的参数的修饰符`MoveFile`根据 Windows API 函数使用的参数︰</span><span class="sxs-lookup"><span data-stu-id="86b74-197">Apply the `Public` and `Shared` modifiers to the function declaration and set parameters for `MoveFile` based on the arguments the Windows API function uses:</span></span>  
  
     <span data-ttu-id="86b74-198">[!code-vb[VbVbalrInterop #&16;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="86b74-198">[!code-vb[VbVbalrInterop#16](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_6.vb)]</span></span>  
  
     <span data-ttu-id="86b74-199">您的函数名称可以是任意有效的过程;`DllImport`属性指定的名称与 DLL 中。</span><span class="sxs-lookup"><span data-stu-id="86b74-199">Your function can have any valid procedure name; the `DllImport` attribute specifies the name in the DLL.</span></span> <span data-ttu-id="86b74-200">它还可以处理的参数的互操作封送处理和返回值，以便您可以选择 Visual Studio 的数据类型包含类似于的数据类型的 API 使用。</span><span class="sxs-lookup"><span data-stu-id="86b74-200">It also handles interoperability marshaling for the parameters and return values, so you can choose Visual Studio data types that are similar to the data types the API uses.</span></span>  
  
8.  <span data-ttu-id="86b74-201">应用`DllImport`属性设为空的函数。</span><span class="sxs-lookup"><span data-stu-id="86b74-201">Apply the `DllImport` attribute to the empty function.</span></span> <span data-ttu-id="86b74-202">第一个参数是名称和包含要调用的函数的 dll 的位置。</span><span class="sxs-lookup"><span data-stu-id="86b74-202">The first parameter is the name and location of the DLL containing the function you are calling.</span></span> <span data-ttu-id="86b74-203">不需要指定位于 Windows 系统目录中的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="86b74-203">You do not need to specify the path for files located in the Windows system directories.</span></span> <span data-ttu-id="86b74-204">第二个参数是一个命名的参数，指定 Windows API 中的函数的名称。</span><span class="sxs-lookup"><span data-stu-id="86b74-204">The second parameter is a named argument that specifies the name of the function in the Windows API.</span></span> <span data-ttu-id="86b74-205">在此示例中，`DllImport`属性强制对调用`MoveFile`转发到`MoveFileW`KERNEL32 中。DLL 中。</span><span class="sxs-lookup"><span data-stu-id="86b74-205">In this example, the `DllImport` attribute forces calls to `MoveFile` to be forwarded to `MoveFileW` in KERNEL32.DLL.</span></span> <span data-ttu-id="86b74-206">`MoveFileW`方法将文件复制从路径`src`到路径`dst`。</span><span class="sxs-lookup"><span data-stu-id="86b74-206">The `MoveFileW` method copies a file from the path `src` to the path `dst`.</span></span>  
  
     <span data-ttu-id="86b74-207">[!code-vb[VbVbalrInterop #&17;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="86b74-207">[!code-vb[VbVbalrInterop#17](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_7.vb)]</span></span>  
  
9. <span data-ttu-id="86b74-208">将代码添加到`Button2_Click`事件处理程序调用的函数︰</span><span class="sxs-lookup"><span data-stu-id="86b74-208">Add code to the `Button2_Click` event handler to call the function:</span></span>  
  
     <span data-ttu-id="86b74-209">[!code-vb[VbVbalrInterop #&18;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="86b74-209">[!code-vb[VbVbalrInterop#18](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-calling-windows-apis_8.vb)]</span></span>  
  
10. <span data-ttu-id="86b74-210">创建一个名为 Test.txt 文件并将其放在硬盘上的 C:\Tmp 目录中。</span><span class="sxs-lookup"><span data-stu-id="86b74-210">Create a file named Test.txt and place it in the C:\Tmp directory on your hard drive.</span></span> <span data-ttu-id="86b74-211">如有必要，请创建临时目录。</span><span class="sxs-lookup"><span data-stu-id="86b74-211">Create the Tmp directory if necessary.</span></span>  
  
11. <span data-ttu-id="86b74-212">按 F5 键启动该应用程序。</span><span class="sxs-lookup"><span data-stu-id="86b74-212">Press F5 to start the application.</span></span> <span data-ttu-id="86b74-213">主窗体将显示。</span><span class="sxs-lookup"><span data-stu-id="86b74-213">The main form appears.</span></span>  
  
12. <span data-ttu-id="86b74-214">单击**Button2**。</span><span class="sxs-lookup"><span data-stu-id="86b74-214">Click **Button2**.</span></span> <span data-ttu-id="86b74-215">如果可以移动该文件，将显示"该文件已成功移动"消息。</span><span class="sxs-lookup"><span data-stu-id="86b74-215">The message "The file was moved successfully" is displayed if the file can be moved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86b74-216">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86b74-216">See Also</span></span>  
 <span data-ttu-id="86b74-217"><xref:System.Runtime.InteropServices.DllImportAttribute></xref:System.Runtime.InteropServices.DllImportAttribute></span><span class="sxs-lookup"><span data-stu-id="86b74-217"><xref:System.Runtime.InteropServices.DllImportAttribute></span></span>   
 <span data-ttu-id="86b74-218"><xref:System.Runtime.InteropServices.MarshalAsAttribute></xref:System.Runtime.InteropServices.MarshalAsAttribute></span><span class="sxs-lookup"><span data-stu-id="86b74-218"><xref:System.Runtime.InteropServices.MarshalAsAttribute></span></span>   
<span data-ttu-id="86b74-219"> [Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md) </span><span class="sxs-lookup"><span data-stu-id="86b74-219"> [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) </span></span>  
<span data-ttu-id="86b74-220"> [自动](../../../visual-basic/language-reference/modifiers/auto.md) </span><span class="sxs-lookup"><span data-stu-id="86b74-220"> [Auto](../../../visual-basic/language-reference/modifiers/auto.md) </span></span>  
<span data-ttu-id="86b74-221"> [别名](../../../visual-basic/language-reference/statements/alias-clause.md) </span><span class="sxs-lookup"><span data-stu-id="86b74-221"> [Alias](../../../visual-basic/language-reference/statements/alias-clause.md) </span></span>  
<span data-ttu-id="86b74-222"> [COM 互操作](../../../visual-basic/programming-guide/com-interop/index.md) </span><span class="sxs-lookup"><span data-stu-id="86b74-222"> [COM Interop](../../../visual-basic/programming-guide/com-interop/index.md) </span></span>  
<span data-ttu-id="86b74-223"> [在托管代码中创建原型](http://msdn.microsoft.com/library/ecdcf25d-cae3-4f07-a2b6-8397ac6dc42d) </span><span class="sxs-lookup"><span data-stu-id="86b74-223"> [Creating Prototypes in Managed Code](http://msdn.microsoft.com/library/ecdcf25d-cae3-4f07-a2b6-8397ac6dc42d) </span></span>  
<span data-ttu-id="86b74-224"> [一个委托作为回调方法进行封送](http://msdn.microsoft.com/library/6ddd7866-9804-4571-84de-83f5cc017a5a)</span><span class="sxs-lookup"><span data-stu-id="86b74-224"> [Marshaling a Delegate as a Callback Method](http://msdn.microsoft.com/library/6ddd7866-9804-4571-84de-83f5cc017a5a)</span></span>

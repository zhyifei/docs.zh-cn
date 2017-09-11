---
title: "演练︰ 使用 Visual Basic 创建 COM 对象 |Microsoft 文档"
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
- COM interop, creating COM objects
- COM objects, creating
- COM interop, walkthroughs
- object creation, COM objects
- COM objects, walkthroughs
ms.assetid: 7b07a463-bc72-4392-9ba0-9dfcb697a44f
caps.latest.revision: 30
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
ms.openlocfilehash: 859a8fc7440eecc0cadbfa8ea236dad7cae99247
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-creating-com-objects-with-visual-basic"></a><span data-ttu-id="f52af-102">演练：使用 Visual Basic 创建 COM 对象</span><span class="sxs-lookup"><span data-stu-id="f52af-102">Walkthrough: Creating COM Objects with Visual Basic</span></span>
<span data-ttu-id="f52af-103">创建新的应用程序或组件时，则最好创建.NET Framework 程序集。</span><span class="sxs-lookup"><span data-stu-id="f52af-103">When creating new applications or components, it is best to create .NET Framework assemblies.</span></span> <span data-ttu-id="f52af-104">但是，[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]还可以轻松地公开 com 是.NET Framework 组件</span><span class="sxs-lookup"><span data-stu-id="f52af-104">However, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] also makes it easy to expose a .NET Framework component to COM.</span></span> <span data-ttu-id="f52af-105">这使您可以提供新的组件需要 COM 组件的早期应用程序套件。</span><span class="sxs-lookup"><span data-stu-id="f52af-105">This enables you to provide new components for earlier application suites that require COM components.</span></span> <span data-ttu-id="f52af-106">本演练演示如何使用[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]公开[!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]对象作为 COM 对象，包括使用和不使用 COM 类模板。</span><span class="sxs-lookup"><span data-stu-id="f52af-106">This walkthrough demonstrates how to use [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] to expose [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] objects as COM objects, both with and without the COM class template.</span></span>  
  
 <span data-ttu-id="f52af-107">公开 COM 对象的最简单方法是使用 COM 类模板。</span><span class="sxs-lookup"><span data-stu-id="f52af-107">The easiest way to expose COM objects is by using the COM class template.</span></span> <span data-ttu-id="f52af-108">COM 类模板创建一个新类，，，然后配置你的项目生成的类和互操作性层作为 COM 对象并将其注册到操作系统。</span><span class="sxs-lookup"><span data-stu-id="f52af-108">The COM class template creates a new class, and then configures your project to generate the class and interoperability layer as a COM object and register it with the operating system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f52af-109">尽管您还可以公开的类中创建[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]为要使用的非托管代码的 COM 对象，它不是真正的 COM 对象并不能由[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f52af-109">Although you can also expose a class created in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] as a COM object for unmanaged code to use, it is not a true COM object and cannot be used by [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span> <span data-ttu-id="f52af-110">有关详细信息，请参阅[.NET Framework 应用程序中的 COM 互操作性](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="f52af-110">For more information, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
### <a name="to-create-a-com-object-by-using-the-com-class-template"></a><span data-ttu-id="f52af-111">若要通过使用 COM 类模板创建的 COM 对象</span><span class="sxs-lookup"><span data-stu-id="f52af-111">To create a COM object by using the COM class template</span></span>  
  
1.  <span data-ttu-id="f52af-112">打开一个新的 Windows 应用程序项目，从**文件**菜单上，通过单击**新项目**。</span><span class="sxs-lookup"><span data-stu-id="f52af-112">Open a new Windows Application project from the **File** menu by clicking **New Project**.</span></span>  
  
2.  <span data-ttu-id="f52af-113">在**新项目**对话框中的下**项目类型**字段中，检查是否选中了 Windows。</span><span class="sxs-lookup"><span data-stu-id="f52af-113">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="f52af-114">选择**类库**从**模板**列表，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f52af-114">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="f52af-115">将显示新项目。</span><span class="sxs-lookup"><span data-stu-id="f52af-115">The new project is displayed.</span></span>  
  
3.  <span data-ttu-id="f52af-116">选择**添加新项**从**项目**菜单。</span><span class="sxs-lookup"><span data-stu-id="f52af-116">Select **Add New Item** from the **Project** menu.</span></span> <span data-ttu-id="f52af-117">**添加新项**中会显示对话框。</span><span class="sxs-lookup"><span data-stu-id="f52af-117">The **Add New Item** dialog box is displayed.</span></span>  
  
4.  <span data-ttu-id="f52af-118">选择**COM 类**从**模板**列表，，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="f52af-118">Select **COM Class** from the **Templates** list, and then click **Add**.</span></span> [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="f52af-119">添加一个新类并配置 COM 互操作的新项目。</span><span class="sxs-lookup"><span data-stu-id="f52af-119"> adds a new class and configures the new project for COM interop.</span></span>  
  
5.  <span data-ttu-id="f52af-120">向 COM 类中添加代码，例如属性、 方法和事件。</span><span class="sxs-lookup"><span data-stu-id="f52af-120">Add code such as properties, methods, and events to the COM class.</span></span>  
  
6.  <span data-ttu-id="f52af-121">选择**生成 ClassLibrary1**从**生成**菜单。</span><span class="sxs-lookup"><span data-stu-id="f52af-121">Select **Build ClassLibrary1** from the **Build** menu.</span></span> [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="f52af-122">生成程序集和随操作系统一起注册的 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="f52af-122"> builds the assembly and registers the COM object with the operating system.</span></span>  
  
## <a name="creating-com-objects-without-the-com-class-template"></a><span data-ttu-id="f52af-123">创建 COM 对象不使用 COM 类模板</span><span class="sxs-lookup"><span data-stu-id="f52af-123">Creating COM Objects without the COM Class Template</span></span>  
 <span data-ttu-id="f52af-124">此外可以创建一个手动而不是使用 COM 类模板的 COM 类。</span><span class="sxs-lookup"><span data-stu-id="f52af-124">You can also create a COM class manually instead of using the COM class template.</span></span> <span data-ttu-id="f52af-125">当您正在从命令行或希望更好地控制如何定义 COM 对象时，此过程是很有帮助。</span><span class="sxs-lookup"><span data-stu-id="f52af-125">This procedure is helpful when you are working from the command line or when you want more control over how COM objects are defined.</span></span>  
  
#### <a name="to-set-up-your-project-to-generate-a-com-object"></a><span data-ttu-id="f52af-126">若要设置你的项目以生成一个 COM 对象</span><span class="sxs-lookup"><span data-stu-id="f52af-126">To set up your project to generate a COM object</span></span>  
  
1.  <span data-ttu-id="f52af-127">打开一个新的 Windows 应用程序项目，从**文件**菜单上，通过单击**NewProject**。</span><span class="sxs-lookup"><span data-stu-id="f52af-127">Open a new Windows Application project from the **File** menu by clicking **NewProject**.</span></span>  
  
2.  <span data-ttu-id="f52af-128">在**新项目**对话框中的下**项目类型**字段中，检查是否选中了 Windows。</span><span class="sxs-lookup"><span data-stu-id="f52af-128">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="f52af-129">选择**类库**从**模板**列表，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f52af-129">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="f52af-130">将显示新项目。</span><span class="sxs-lookup"><span data-stu-id="f52af-130">The new project is displayed.</span></span>  
  
3.  <span data-ttu-id="f52af-131">在**解决方案资源管理器**，用鼠标右键单击您的项目，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="f52af-131">In **Solution Explorer**, right-click your project, and then click **Properties**.</span></span> <span data-ttu-id="f52af-132">**项目设计器**显示。</span><span class="sxs-lookup"><span data-stu-id="f52af-132">The **Project Designer** is displayed.</span></span>  
  
4.  <span data-ttu-id="f52af-133">单击“编译”****选项卡。</span><span class="sxs-lookup"><span data-stu-id="f52af-133">Click the **Compile** tab.</span></span>  
  
5.  <span data-ttu-id="f52af-134">选择**为 COM 互操作注册**复选框。</span><span class="sxs-lookup"><span data-stu-id="f52af-134">Select the **Register for COM Interop** check box.</span></span>  
  
#### <a name="to-set-up-the-code-in-your-class-to-create-a-com-object"></a><span data-ttu-id="f52af-135">若要将您的类中的代码设置为创建 COM 对象</span><span class="sxs-lookup"><span data-stu-id="f52af-135">To set up the code in your class to create a COM object</span></span>  
  
1.  <span data-ttu-id="f52af-136">在**解决方案资源管理器**，双击**Class1.vb**以显示其代码。</span><span class="sxs-lookup"><span data-stu-id="f52af-136">In **Solution Explorer**, double-click **Class1.vb** to display its code.</span></span>  
  
2.  <span data-ttu-id="f52af-137">将该类重命名为 `ComClass1`。</span><span class="sxs-lookup"><span data-stu-id="f52af-137">Rename the class to `ComClass1`.</span></span>  
  
3.  <span data-ttu-id="f52af-138">添加以下常量`ComClass1`。</span><span class="sxs-lookup"><span data-stu-id="f52af-138">Add the following constants to `ComClass1`.</span></span> <span data-ttu-id="f52af-139">它们将存储不需要具有 COM 对象的全局唯一标识符 (GUID) 常量。</span><span class="sxs-lookup"><span data-stu-id="f52af-139">They will store the Globally Unique Identifier (GUID) constants that the COM objects are required to have.</span></span>  
  
     <span data-ttu-id="f52af-140">[!code-vb[VbVbalrInterop #&2;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="f52af-140">[!code-vb[VbVbalrInterop#2](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_1.vb)]</span></span>  
  
4.  <span data-ttu-id="f52af-141">在**工具**菜单上，单击**创建 Guid**。</span><span class="sxs-lookup"><span data-stu-id="f52af-141">On the **Tools** menu, click **Create Guid**.</span></span> <span data-ttu-id="f52af-142">在**创建 GUID**对话框中，单击**注册表格式**，然后单击**副本**。</span><span class="sxs-lookup"><span data-stu-id="f52af-142">In the **Create GUID** dialog box, click **Registry Format** and then click **Copy**.</span></span> <span data-ttu-id="f52af-143">单击“退出” ****。</span><span class="sxs-lookup"><span data-stu-id="f52af-143">Click **Exit**.</span></span>  
  
5.  <span data-ttu-id="f52af-144">替换空字符串作为`ClassId`guid 的计算机，移除前导空格和尾随大括号内。</span><span class="sxs-lookup"><span data-stu-id="f52af-144">Replace the empty string for the `ClassId` with the GUID, removing the leading and trailing braces.</span></span> <span data-ttu-id="f52af-145">例如，如果 Guidgen 由提供的 GUID 是`"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"`，则您的代码应出现，如下所示。</span><span class="sxs-lookup"><span data-stu-id="f52af-145">For example, if the GUID provided by Guidgen is `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` then your code should appear as follows.</span></span>  
  
     <span data-ttu-id="f52af-146">[!code-vb[VbVbalrInterop #&3;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="f52af-146">[!code-vb[VbVbalrInterop#3](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_2.vb)]</span></span>  
  
6.  <span data-ttu-id="f52af-147">重复前面的步骤为`InterfaceId`和`EventsId`常量，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="f52af-147">Repeat the previous steps for the `InterfaceId` and `EventsId` constants, as in the following example.</span></span>  
  
     <span data-ttu-id="f52af-148">[!code-vb[VbVbalrInterop #&4;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="f52af-148">[!code-vb[VbVbalrInterop#4](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_3.vb)]</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f52af-149">请确保 Guid 是新且唯一的。否则，COM 组件可能与其他 COM 组件。</span><span class="sxs-lookup"><span data-stu-id="f52af-149">Make sure that the GUIDs are new and unique; otherwise, your COM component could conflict with other COM components.</span></span>  
  
7.  <span data-ttu-id="f52af-150">添加`ComClass`属性设为`ComClass1`，指定的类 ID、 接口 ID 和事件 ID 的 Guid，如以下示例所示︰</span><span class="sxs-lookup"><span data-stu-id="f52af-150">Add the `ComClass` attribute to `ComClass1`, specifying the GUIDs for the Class ID, Interface ID, and Events ID as in the following example:</span></span>  
  
     <span data-ttu-id="f52af-151">[!code-vb[VbVbalrInterop #&5;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="f52af-151">[!code-vb[VbVbalrInterop#5](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_4.vb)]</span></span>  
  
8.  <span data-ttu-id="f52af-152">COM 类必须具有无参数`Public Sub New()`构造函数或类无法正确注册。</span><span class="sxs-lookup"><span data-stu-id="f52af-152">COM classes must have a parameterless `Public Sub New()` constructor, or the class will not register correctly.</span></span> <span data-ttu-id="f52af-153">将无参数构造函数添加到类︰</span><span class="sxs-lookup"><span data-stu-id="f52af-153">Add a parameterless constructor to the class:</span></span>  
  
     <span data-ttu-id="f52af-154">[!code-vb[VbVbalrInterop #&6;](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="f52af-154">[!code-vb[VbVbalrInterop#6](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_5.vb)]</span></span>  
  
9. <span data-ttu-id="f52af-155">将属性、 方法和事件添加到类，它与结束`End Class`语句。</span><span class="sxs-lookup"><span data-stu-id="f52af-155">Add properties, methods, and events to the class, ending it with an `End Class` statement.</span></span> <span data-ttu-id="f52af-156">选择**生成解决方案**从**生成**菜单。</span><span class="sxs-lookup"><span data-stu-id="f52af-156">Select **Build Solution** from the **Build** menu.</span></span> [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="f52af-157">生成程序集和随操作系统一起注册的 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="f52af-157"> builds the assembly and registers the COM object with the operating system.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f52af-158">使用生成的 COM 对象[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]不能由其他使用[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]应用程序因为它们不是真正的 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="f52af-158">The COM objects you generate with [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] cannot be used by other [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] applications because they are not true COM objects.</span></span> <span data-ttu-id="f52af-159">尝试添加对此类 COM 对象的引用将引发错误。</span><span class="sxs-lookup"><span data-stu-id="f52af-159">Attempts to add references to such COM objects will raise an error.</span></span> <span data-ttu-id="f52af-160">有关详细信息，请参阅[.NET Framework 应用程序中的 COM 互操作性](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="f52af-160">For details, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f52af-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f52af-161">See Also</span></span>  
 <span data-ttu-id="f52af-162"><xref:Microsoft.VisualBasic.ComClassAttribute></xref:Microsoft.VisualBasic.ComClassAttribute></span><span class="sxs-lookup"><span data-stu-id="f52af-162"><xref:Microsoft.VisualBasic.ComClassAttribute></span></span>   
<span data-ttu-id="f52af-163"> [COM 互操作](../../../visual-basic/programming-guide/com-interop/index.md) </span><span class="sxs-lookup"><span data-stu-id="f52af-163"> [COM Interop](../../../visual-basic/programming-guide/com-interop/index.md) </span></span>  
<span data-ttu-id="f52af-164"> [演练︰ 用 COM 对象实现继承](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md) </span><span class="sxs-lookup"><span data-stu-id="f52af-164"> [Walkthrough: Implementing Inheritance with COM Objects](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md) </span></span>  
<span data-ttu-id="f52af-165"> [#Region 指令](../../../visual-basic/language-reference/directives/region-directive.md) </span><span class="sxs-lookup"><span data-stu-id="f52af-165"> [#Region Directive](../../../visual-basic/language-reference/directives/region-directive.md) </span></span>  
<span data-ttu-id="f52af-166"> [.NET Framework 应用程序中的 COM 互操作性](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md) </span><span class="sxs-lookup"><span data-stu-id="f52af-166"> [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md) </span></span>  
<span data-ttu-id="f52af-167"> [互操作性疑难解答](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)</span><span class="sxs-lookup"><span data-stu-id="f52af-167"> [Troubleshooting Interoperability](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)</span></span>

---
title: "演练：使用 Visual Basic 创建 COM 对象"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- COM interop [Visual Basic], creating COM objects
- COM objects, creating
- COM interop [Visual Basic], walkthroughs
- object creation [Visual Basic], COM objects
- COM objects, walkthroughs
ms.assetid: 7b07a463-bc72-4392-9ba0-9dfcb697a44f
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ff7d3868a2e3ddaba06ebc6f98c8eacfc7299366
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-creating-com-objects-with-visual-basic"></a><span data-ttu-id="9a76b-102">演练：使用 Visual Basic 创建 COM 对象</span><span class="sxs-lookup"><span data-stu-id="9a76b-102">Walkthrough: Creating COM Objects with Visual Basic</span></span>
<span data-ttu-id="9a76b-103">创建新的应用程序或组件时，则最好创建.NET Framework 程序集。</span><span class="sxs-lookup"><span data-stu-id="9a76b-103">When creating new applications or components, it is best to create .NET Framework assemblies.</span></span> <span data-ttu-id="9a76b-104">但是，[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]还可以轻松地公开给 com。 是.NET Framework 组件</span><span class="sxs-lookup"><span data-stu-id="9a76b-104">However, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] also makes it easy to expose a .NET Framework component to COM.</span></span> <span data-ttu-id="9a76b-105">这使你能够新组件需要 COM 组件的早期应用程序套件。</span><span class="sxs-lookup"><span data-stu-id="9a76b-105">This enables you to provide new components for earlier application suites that require COM components.</span></span> <span data-ttu-id="9a76b-106">本演练演示如何使用[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]公开[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]作为 COM 对象，使用或不使用 COM 类模板的对象。</span><span class="sxs-lookup"><span data-stu-id="9a76b-106">This walkthrough demonstrates how to use [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] to expose [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] objects as COM objects, both with and without the COM class template.</span></span>  
  
 <span data-ttu-id="9a76b-107">公开 COM 对象的最简单方法是使用 COM 类模板。</span><span class="sxs-lookup"><span data-stu-id="9a76b-107">The easiest way to expose COM objects is by using the COM class template.</span></span> <span data-ttu-id="9a76b-108">COM 类模板创建一个新的类，然后配置你的项目生成为 COM 对象的类和互操作性层，并将其注册到操作系统。</span><span class="sxs-lookup"><span data-stu-id="9a76b-108">The COM class template creates a new class, and then configures your project to generate the class and interoperability layer as a COM object and register it with the operating system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9a76b-109">虽然你还可以公开中创建的类[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]作为 COM 对象以供使用的非托管代码，它不是真正的 COM 对象并且不能由[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="9a76b-109">Although you can also expose a class created in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] as a COM object for unmanaged code to use, it is not a true COM object and cannot be used by [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span> <span data-ttu-id="9a76b-110">有关详细信息，请参阅[在.NET Framework 应用程序的 COM 互操作性](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="9a76b-110">For more information, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-com-object-by-using-the-com-class-template"></a><span data-ttu-id="9a76b-111">若要使用 COM 类模板创建的 COM 对象</span><span class="sxs-lookup"><span data-stu-id="9a76b-111">To create a COM object by using the COM class template</span></span>  
  
1.  <span data-ttu-id="9a76b-112">打开一个新的 Windows 应用程序项目，从**文件**菜单中单击**新项目**。</span><span class="sxs-lookup"><span data-stu-id="9a76b-112">Open a new Windows Application project from the **File** menu by clicking **New Project**.</span></span>  
  
2.  <span data-ttu-id="9a76b-113">在**新项目**对话框中的下**项目类型**字段中，检查是否已选中 Windows。</span><span class="sxs-lookup"><span data-stu-id="9a76b-113">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="9a76b-114">选择**类库**从**模板**列表，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9a76b-114">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="9a76b-115">将显示新项目。</span><span class="sxs-lookup"><span data-stu-id="9a76b-115">The new project is displayed.</span></span>  
  
3.  <span data-ttu-id="9a76b-116">选择**添加新项**从**项目**菜单。</span><span class="sxs-lookup"><span data-stu-id="9a76b-116">Select **Add New Item** from the **Project** menu.</span></span> <span data-ttu-id="9a76b-117">随即出现“添加新项”对话框。</span><span class="sxs-lookup"><span data-stu-id="9a76b-117">The **Add New Item** dialog box is displayed.</span></span>  
  
4.  <span data-ttu-id="9a76b-118">选择**COM 类**从**模板**列表，，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="9a76b-118">Select **COM Class** from the **Templates** list, and then click **Add**.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="9a76b-119">添加了一个新类并配置 COM 互操作的新项目。</span><span class="sxs-lookup"><span data-stu-id="9a76b-119"> adds a new class and configures the new project for COM interop.</span></span>  
  
5.  <span data-ttu-id="9a76b-120">将如属性、 方法和事件的代码添加到的 COM 类。</span><span class="sxs-lookup"><span data-stu-id="9a76b-120">Add code such as properties, methods, and events to the COM class.</span></span>  
  
6.  <span data-ttu-id="9a76b-121">选择**生成 ClassLibrary1**从**生成**菜单。</span><span class="sxs-lookup"><span data-stu-id="9a76b-121">Select **Build ClassLibrary1** from the **Build** menu.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="9a76b-122">生成程序集和与操作系统中注册的 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="9a76b-122"> builds the assembly and registers the COM object with the operating system.</span></span>  
  
## <a name="creating-com-objects-without-the-com-class-template"></a><span data-ttu-id="9a76b-123">创建不使用 COM 类模板的 COM 对象</span><span class="sxs-lookup"><span data-stu-id="9a76b-123">Creating COM Objects without the COM Class Template</span></span>  
 <span data-ttu-id="9a76b-124">你还可以创建手动而不是使用 COM 类模板的 COM 类。</span><span class="sxs-lookup"><span data-stu-id="9a76b-124">You can also create a COM class manually instead of using the COM class template.</span></span> <span data-ttu-id="9a76b-125">当你正在从命令行或要更好地控制如何定义 COM 对象时，此过程非常有用。</span><span class="sxs-lookup"><span data-stu-id="9a76b-125">This procedure is helpful when you are working from the command line or when you want more control over how COM objects are defined.</span></span>  
  
#### <a name="to-set-up-your-project-to-generate-a-com-object"></a><span data-ttu-id="9a76b-126">若要将你的项目设置为生成的 COM 对象</span><span class="sxs-lookup"><span data-stu-id="9a76b-126">To set up your project to generate a COM object</span></span>  
  
1.  <span data-ttu-id="9a76b-127">打开一个新的 Windows 应用程序项目，从**文件**菜单中单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="9a76b-127">Open a new Windows Application project from the **File** menu by clicking **NewProject**.</span></span>  
  
2.  <span data-ttu-id="9a76b-128">在**新项目**对话框中的下**项目类型**字段中，检查是否已选中 Windows。</span><span class="sxs-lookup"><span data-stu-id="9a76b-128">In the **New Project** dialog box under the **Project Types** field, check that Windows is selected.</span></span> <span data-ttu-id="9a76b-129">选择**类库**从**模板**列表，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9a76b-129">Select **Class Library** from the **Templates** list, and then click **OK**.</span></span> <span data-ttu-id="9a76b-130">将显示新项目。</span><span class="sxs-lookup"><span data-stu-id="9a76b-130">The new project is displayed.</span></span>  
  
3.  <span data-ttu-id="9a76b-131">在**解决方案资源管理器**，右键单击你的项目，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="9a76b-131">In **Solution Explorer**, right-click your project, and then click **Properties**.</span></span> <span data-ttu-id="9a76b-132">**项目设计器**显示。</span><span class="sxs-lookup"><span data-stu-id="9a76b-132">The **Project Designer** is displayed.</span></span>  
  
4.  <span data-ttu-id="9a76b-133">单击“编译”选项卡。</span><span class="sxs-lookup"><span data-stu-id="9a76b-133">Click the **Compile** tab.</span></span>  
  
5.  <span data-ttu-id="9a76b-134">选择**为 COM 互操作注册**复选框。</span><span class="sxs-lookup"><span data-stu-id="9a76b-134">Select the **Register for COM Interop** check box.</span></span>  
  
#### <a name="to-set-up-the-code-in-your-class-to-create-a-com-object"></a><span data-ttu-id="9a76b-135">若要设置你的类中的代码来创建 COM 对象</span><span class="sxs-lookup"><span data-stu-id="9a76b-135">To set up the code in your class to create a COM object</span></span>  
  
1.  <span data-ttu-id="9a76b-136">在**解决方案资源管理器**，双击**Class1.vb**以显示其代码。</span><span class="sxs-lookup"><span data-stu-id="9a76b-136">In **Solution Explorer**, double-click **Class1.vb** to display its code.</span></span>  
  
2.  <span data-ttu-id="9a76b-137">将该类重命名为 `ComClass1`。</span><span class="sxs-lookup"><span data-stu-id="9a76b-137">Rename the class to `ComClass1`.</span></span>  
  
3.  <span data-ttu-id="9a76b-138">添加到以下常量`ComClass1`。</span><span class="sxs-lookup"><span data-stu-id="9a76b-138">Add the following constants to `ComClass1`.</span></span> <span data-ttu-id="9a76b-139">它们将存储均需要具有 COM 对象的全局唯一标识符 (GUID) 常量。</span><span class="sxs-lookup"><span data-stu-id="9a76b-139">They will store the Globally Unique Identifier (GUID) constants that the COM objects are required to have.</span></span>  
  
     [!code-vb[VbVbalrInterop#2](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_1.vb)]  
  
4.  <span data-ttu-id="9a76b-140">在“工具”菜单上，单击“创建 Guid”。</span><span class="sxs-lookup"><span data-stu-id="9a76b-140">On the **Tools** menu, click **Create Guid**.</span></span> <span data-ttu-id="9a76b-141">在“创建 GUID”对话框中，单击“注册表格式”，然后单击“复制”。</span><span class="sxs-lookup"><span data-stu-id="9a76b-141">In the **Create GUID** dialog box, click **Registry Format** and then click **Copy**.</span></span> <span data-ttu-id="9a76b-142">单击“退出” 。</span><span class="sxs-lookup"><span data-stu-id="9a76b-142">Click **Exit**.</span></span>  
  
5.  <span data-ttu-id="9a76b-143">将空字符串作为`ClassId`guid，删除前导空格和尾随大括号。</span><span class="sxs-lookup"><span data-stu-id="9a76b-143">Replace the empty string for the `ClassId` with the GUID, removing the leading and trailing braces.</span></span> <span data-ttu-id="9a76b-144">例如，如果 GUID 提供 Guidgen 是`"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"`，则你的代码应出现，如下所示。</span><span class="sxs-lookup"><span data-stu-id="9a76b-144">For example, if the GUID provided by Guidgen is `"{2C8B0AEE-02C9-486e-B809-C780A11530FE}"` then your code should appear as follows.</span></span>  
  
     [!code-vb[VbVbalrInterop#3](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_2.vb)]  
  
6.  <span data-ttu-id="9a76b-145">重复前面的步骤为`InterfaceId`和`EventsId`常量，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="9a76b-145">Repeat the previous steps for the `InterfaceId` and `EventsId` constants, as in the following example.</span></span>  
  
     [!code-vb[VbVbalrInterop#4](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_3.vb)]  
  
    > [!NOTE]
    >  <span data-ttu-id="9a76b-146">请确保新的和独特; Guid否则，你的 COM 组件可能与其他 COM 组件发生冲突。</span><span class="sxs-lookup"><span data-stu-id="9a76b-146">Make sure that the GUIDs are new and unique; otherwise, your COM component could conflict with other COM components.</span></span>  
  
7.  <span data-ttu-id="9a76b-147">添加`ComClass`属性设为`ComClass1`，指定的类 ID、 接口 ID 和事件 ID 的 Guid，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="9a76b-147">Add the `ComClass` attribute to `ComClass1`, specifying the GUIDs for the Class ID, Interface ID, and Events ID as in the following example:</span></span>  
  
     [!code-vb[VbVbalrInterop#5](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_4.vb)]  
  
8.  <span data-ttu-id="9a76b-148">COM 类必须具有无参数`Public Sub New()`构造函数或类将不正确注册。</span><span class="sxs-lookup"><span data-stu-id="9a76b-148">COM classes must have a parameterless `Public Sub New()` constructor, or the class will not register correctly.</span></span> <span data-ttu-id="9a76b-149">将无参数构造函数添加到类：</span><span class="sxs-lookup"><span data-stu-id="9a76b-149">Add a parameterless constructor to the class:</span></span>  
  
     [!code-vb[VbVbalrInterop#6](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/walkthrough-creating-com-objects_5.vb)]  
  
9. <span data-ttu-id="9a76b-150">将属性、 方法和事件添加到类，它与结束`End Class`语句。</span><span class="sxs-lookup"><span data-stu-id="9a76b-150">Add properties, methods, and events to the class, ending it with an `End Class` statement.</span></span> <span data-ttu-id="9a76b-151">选择**生成解决方案**从**生成**菜单。</span><span class="sxs-lookup"><span data-stu-id="9a76b-151">Select **Build Solution** from the **Build** menu.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="9a76b-152">生成程序集和与操作系统中注册的 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="9a76b-152"> builds the assembly and registers the COM object with the operating system.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9a76b-153">使用生成的 COM 对象[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]不能由其他[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]应用程序因为它们不是真正的 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="9a76b-153">The COM objects you generate with [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] cannot be used by other [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] applications because they are not true COM objects.</span></span> <span data-ttu-id="9a76b-154">尝试将引用添加到此类的 COM 对象将引发错误。</span><span class="sxs-lookup"><span data-stu-id="9a76b-154">Attempts to add references to such COM objects will raise an error.</span></span> <span data-ttu-id="9a76b-155">有关详细信息，请参阅[在.NET Framework 应用程序的 COM 互操作性](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="9a76b-155">For details, see [COM Interoperability in .NET Framework Applications](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a76b-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9a76b-156">See Also</span></span>  
 <xref:Microsoft.VisualBasic.ComClassAttribute>  
 [<span data-ttu-id="9a76b-157">COM 互操作</span><span class="sxs-lookup"><span data-stu-id="9a76b-157">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)  
 [<span data-ttu-id="9a76b-158">演练：使用 COM 对象实现继承</span><span class="sxs-lookup"><span data-stu-id="9a76b-158">Walkthrough: Implementing Inheritance with COM Objects</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
 [<span data-ttu-id="9a76b-159">#Region 指令</span><span class="sxs-lookup"><span data-stu-id="9a76b-159">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)  
 [<span data-ttu-id="9a76b-160">.NET Framework 应用程序中的 COM 互操作性</span><span class="sxs-lookup"><span data-stu-id="9a76b-160">COM Interoperability in .NET Framework Applications</span></span>](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md)  
 [<span data-ttu-id="9a76b-161">互操作性疑难解答</span><span class="sxs-lookup"><span data-stu-id="9a76b-161">Troubleshooting Interoperability</span></span>](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)

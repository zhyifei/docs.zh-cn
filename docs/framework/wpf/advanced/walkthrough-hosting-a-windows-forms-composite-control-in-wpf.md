---
title: 在 WPF 中承载 Windows 窗体复合控件
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Windows Forms control in WPF [WPF]
- composite controls [WPF], hosting in WPF
ms.assetid: 96fcd78d-1c77-4206-8928-3a0579476ef4
ms.openlocfilehash: 16c09b4bb393fa830412385b4b405dd1fae9878b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745005"
---
# <a name="walkthrough-hosting-a-windows-forms-composite-control-in-wpf"></a><span data-ttu-id="797eb-102">연습: WPF에서 Windows Forms 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="797eb-102">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="797eb-103">에서는 애플리케이션을 만들기 위한 다양한 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-103">provides a rich environment for creating applications.</span></span> <span data-ttu-id="797eb-104">但是，当您对 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 代码有大量投资时，在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序中重复使用至少一些代码，而不是从头重新编写它会更有效。</span><span class="sxs-lookup"><span data-stu-id="797eb-104">However, when you have a substantial investment in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] code, it can be more effective to reuse at least some of that code in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application rather than to rewrite it from scratch.</span></span> <span data-ttu-id="797eb-105">最常见的情况是现有 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="797eb-105">The most common scenario is when you have existing Windows Forms controls.</span></span> <span data-ttu-id="797eb-106">경우에 따라 이러한 컨트롤에 대한 소스 코드에 액세스하지 못할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-106">In some cases, you might not even have access to the source code for these controls.</span></span> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="797eb-107">提供了在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序中承载此类控件的简单过程。</span><span class="sxs-lookup"><span data-stu-id="797eb-107">provides a straightforward procedure for hosting such controls in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="797eb-108">例如，你可以将 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 用于大多数编程，同时承载专用 <xref:System.Windows.Forms.DataGridView> 控件。</span><span class="sxs-lookup"><span data-stu-id="797eb-108">For example, you can use [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] for most of your programming while hosting your specialized <xref:System.Windows.Forms.DataGridView> controls.</span></span>  
  
 <span data-ttu-id="797eb-109">本演练将指导你完成承载 Windows 窗体复合控件以在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序中执行数据输入的应用程序。</span><span class="sxs-lookup"><span data-stu-id="797eb-109">This walkthrough steps you through an application that hosts a Windows Forms composite control to perform data entry in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="797eb-110">복합 컨트롤은 DLL로 패키지됩니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-110">The composite control is packaged in a DLL.</span></span> <span data-ttu-id="797eb-111">이 일반적인 절차는 더 복잡한 애플리케이션 및 컨트롤로 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-111">This general procedure can be extended to more complex applications and controls.</span></span> <span data-ttu-id="797eb-112">本演练的设计与演练的外观和功能几乎完全相同[：在 Windows 窗体中承载 WPF 复合控件](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="797eb-112">This walkthrough is designed to be nearly identical in appearance and functionality to [Walkthrough: Hosting a WPF Composite Control in Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md).</span></span> <span data-ttu-id="797eb-113">주요 차이점은 호스팅 시나리오가 반대라는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-113">The primary difference is that the hosting scenario is reversed.</span></span>  
  
 <span data-ttu-id="797eb-114">이 연습은 두 개의 섹션으로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-114">The walkthrough is divided into two sections.</span></span> <span data-ttu-id="797eb-115">第一部分简要介绍 Windows 窗体复合控件的实现。</span><span class="sxs-lookup"><span data-stu-id="797eb-115">The first section briefly describes the implementation of the Windows Forms composite control.</span></span> <span data-ttu-id="797eb-116">第二部分详细讨论如何在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序中承载复合控件、从控件接收事件以及访问控件的某些属性。</span><span class="sxs-lookup"><span data-stu-id="797eb-116">The second section discusses in detail how to host the composite control in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application, receive events from the control, and access some of the control's properties.</span></span>  
  
 <span data-ttu-id="797eb-117">이 연습에서 설명하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-117">Tasks illustrated in this walkthrough include:</span></span>  
  
- <span data-ttu-id="797eb-118">Windows Forms 복합 컨트롤 구현</span><span class="sxs-lookup"><span data-stu-id="797eb-118">Implementing the Windows Forms composite control.</span></span>  
  
- <span data-ttu-id="797eb-119">WPF 호스트 애플리케이션 구현</span><span class="sxs-lookup"><span data-stu-id="797eb-119">Implementing the WPF host application.</span></span>  
  
 <span data-ttu-id="797eb-120">有关本演练中阐释的任务的完整代码列表，请参阅[在 WPF 中承载 Windows 窗体复合控件示例](https://go.microsoft.com/fwlink/?LinkID=159999)。</span><span class="sxs-lookup"><span data-stu-id="797eb-120">For a complete code listing of the tasks illustrated in this walkthrough, see [Hosting a Windows Forms Composite Control in WPF Sample](https://go.microsoft.com/fwlink/?LinkID=159999).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="797eb-121">先决条件</span><span class="sxs-lookup"><span data-stu-id="797eb-121">Prerequisites</span></span>  

<span data-ttu-id="797eb-122">이 연습을 완료하려면 Visual Studio가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-122">You need Visual Studio to complete this walkthrough.</span></span>
  
## <a name="implementing-the-windows-forms-composite-control"></a><span data-ttu-id="797eb-123">Windows Forms 복합 컨트롤 구현</span><span class="sxs-lookup"><span data-stu-id="797eb-123">Implementing the Windows Forms Composite Control</span></span>  
 <span data-ttu-id="797eb-124">本示例中使用的 Windows 窗体复合控件是一个简单的数据输入窗体。</span><span class="sxs-lookup"><span data-stu-id="797eb-124">The Windows Forms composite control used in this example is a simple data-entry form.</span></span> <span data-ttu-id="797eb-125">이 폼에서는 사용자의 이름 및 주소를 사용한 다음 사용자 지정 이벤트를 사용하여 해당 정보를 호스트에 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-125">This form takes the user's name and address and then uses a custom event to return that information to the host.</span></span> <span data-ttu-id="797eb-126">다음 그림에서는 렌더링된 컨트롤을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-126">The following illustration shows the rendered control.</span></span>  

 <span data-ttu-id="797eb-127">下图显示了一个 Windows 窗体复合控件：</span><span class="sxs-lookup"><span data-stu-id="797eb-127">The following image shows a Windows Forms composite control:</span></span>  

 ![显示简单 Windows 窗体控件的屏幕截图。](./media/walkthrough-hosting-a-windows-forms-composite-control-in-wpf/windows-forms-control.gif)  
  
### <a name="creating-the-project"></a><span data-ttu-id="797eb-129">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="797eb-129">Creating the Project</span></span>  
 <span data-ttu-id="797eb-130">프로젝트를 시작하려면</span><span class="sxs-lookup"><span data-stu-id="797eb-130">To start the project:</span></span>  
  
1. <span data-ttu-id="797eb-131">启动 Visual Studio，然后打开 "**新建项目**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="797eb-131">Launch Visual Studio, and open the **New Project** dialog box.</span></span>  
  
2. <span data-ttu-id="797eb-132">在 "窗口" 类别中，选择 " **Windows 窗体控件库**" 模板。</span><span class="sxs-lookup"><span data-stu-id="797eb-132">In the Window category, select the **Windows Forms Control Library** template.</span></span>  
  
3. <span data-ttu-id="797eb-133">새 프로젝트의 이름을 `MyControls`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-133">Name the new project `MyControls`.</span></span>  
  
4. <span data-ttu-id="797eb-134">对于 "位置"，指定一个便于命名的顶层文件夹，如 `WpfHostingWindowsFormsControl`。</span><span class="sxs-lookup"><span data-stu-id="797eb-134">For the location, specify a conveniently named top-level folder, such as `WpfHostingWindowsFormsControl`.</span></span> <span data-ttu-id="797eb-135">나중에 이 폴더에 호스트 애플리케이션을 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-135">Later, you will put the host application in this folder.</span></span>  
  
5. <span data-ttu-id="797eb-136">**확인**을 클릭하여 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-136">Click **OK** to create the project.</span></span> <span data-ttu-id="797eb-137">默认项目包含一个名为 `UserControl1`的控件。</span><span class="sxs-lookup"><span data-stu-id="797eb-137">The default project contains a single control named `UserControl1`.</span></span>  
  
6. <span data-ttu-id="797eb-138">在解决方案资源管理器中，将 `UserControl1` 重命名为 `MyControl1`。</span><span class="sxs-lookup"><span data-stu-id="797eb-138">In Solution Explorer, rename `UserControl1` to `MyControl1`.</span></span>  
  
 <span data-ttu-id="797eb-139">프로젝트에는 다음과 같은 시스템 DLL에 대한 참조가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-139">Your project should have references to the following system DLLs.</span></span> <span data-ttu-id="797eb-140">이러한 DLL이 기본적으로 포함되지 않은 경우 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-140">If any of these DLLs are not included by default, add them to the project.</span></span>  
  
- <span data-ttu-id="797eb-141">System</span><span class="sxs-lookup"><span data-stu-id="797eb-141">System</span></span>  
  
- <span data-ttu-id="797eb-142">System.Data</span><span class="sxs-lookup"><span data-stu-id="797eb-142">System.Data</span></span>  
  
- <span data-ttu-id="797eb-143">System.Drawing</span><span class="sxs-lookup"><span data-stu-id="797eb-143">System.Drawing</span></span>  
  
- <span data-ttu-id="797eb-144">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="797eb-144">System.Windows.Forms</span></span>  
  
- <span data-ttu-id="797eb-145">System.Xml</span><span class="sxs-lookup"><span data-stu-id="797eb-145">System.Xml</span></span>  
  
### <a name="adding-controls-to-the-form"></a><span data-ttu-id="797eb-146">폼에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="797eb-146">Adding Controls to the Form</span></span>  
 <span data-ttu-id="797eb-147">폼에 컨트롤을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="797eb-147">To add controls to the form:</span></span>  
  
- <span data-ttu-id="797eb-148">在设计器中打开 `MyControl1`。</span><span class="sxs-lookup"><span data-stu-id="797eb-148">Open `MyControl1` in the designer.</span></span>  
  
 <span data-ttu-id="797eb-149">在窗体上，添加五个 <xref:System.Windows.Forms.Label> 控件及其相应的 <xref:System.Windows.Forms.TextBox> 控件，并将其调整大小并按上图所示。</span><span class="sxs-lookup"><span data-stu-id="797eb-149">Add five <xref:System.Windows.Forms.Label> controls and their corresponding <xref:System.Windows.Forms.TextBox> controls, sized and arranged as they are in the preceding illustration, on the form.</span></span> <span data-ttu-id="797eb-150">在此示例中，<xref:System.Windows.Forms.TextBox> 控件被命名为：</span><span class="sxs-lookup"><span data-stu-id="797eb-150">In the example, the <xref:System.Windows.Forms.TextBox> controls are named:</span></span>  
  
- `txtName`  
  
- `txtAddress`  
  
- `txtCity`  
  
- `txtState`  
  
- `txtZip`  
  
 <span data-ttu-id="797eb-151">添加两个标记为 **"确定" 和 "** **取消**" 的 <xref:System.Windows.Forms.Button> 控件。</span><span class="sxs-lookup"><span data-stu-id="797eb-151">Add two <xref:System.Windows.Forms.Button> controls labeled **OK** and **Cancel**.</span></span> <span data-ttu-id="797eb-152">在此示例中，按钮名称分别 `btnOK` 和 `btnCancel`。</span><span class="sxs-lookup"><span data-stu-id="797eb-152">In the example, the button names are `btnOK` and `btnCancel`, respectively.</span></span>  
  
### <a name="implementing-the-supporting-code"></a><span data-ttu-id="797eb-153">지원 코드 구현</span><span class="sxs-lookup"><span data-stu-id="797eb-153">Implementing the Supporting Code</span></span>  
 <span data-ttu-id="797eb-154">코드 보기에서 폼을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-154">Open the form in code view.</span></span> <span data-ttu-id="797eb-155">控件通过引发自定义 `OnButtonClick` 事件将收集的数据返回到其主机。</span><span class="sxs-lookup"><span data-stu-id="797eb-155">The control returns the collected data to its host by raising the custom `OnButtonClick` event.</span></span> <span data-ttu-id="797eb-156">데이터는 이벤트 인수 개체에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-156">The data is contained in the event argument object.</span></span> <span data-ttu-id="797eb-157">다음 코드에서는 이벤트 및 대리자 선언을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-157">The following code shows the event and delegate declaration.</span></span>  
  
 <span data-ttu-id="797eb-158">`MyControl1` 클래스에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-158">Add the following code to the `MyControl1` class.</span></span>  
  
 [!code-csharp[WpfHostingWindowsFormsControl#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#2)]
 [!code-vb[WpfHostingWindowsFormsControl#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#2)]

 <span data-ttu-id="797eb-159">`MyControlEventArgs` 类包含要返回给主机的信息。</span><span class="sxs-lookup"><span data-stu-id="797eb-159">The `MyControlEventArgs` class contains the information to be returned to the host.</span></span>

 <span data-ttu-id="797eb-160">다음 클래스를 폼에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-160">Add the following class to the form.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#3)]
 [!code-vb[WpfHostingWindowsFormsControl#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#3)]

 <span data-ttu-id="797eb-161">当用户单击 **"确定" 或 "** **取消**" 按钮时，<xref:System.Windows.Forms.Control.Click> 事件处理程序将创建一个包含数据的 `MyControlEventArgs` 对象，并引发 `OnButtonClick` 事件。</span><span class="sxs-lookup"><span data-stu-id="797eb-161">When the user clicks the **OK** or **Cancel** button, the <xref:System.Windows.Forms.Control.Click> event handlers create a `MyControlEventArgs` object that contains the data and raises the `OnButtonClick` event.</span></span> <span data-ttu-id="797eb-162">这两个处理程序的唯一区别在于事件参数的 `IsOK` 属性。</span><span class="sxs-lookup"><span data-stu-id="797eb-162">The only difference between the two handlers is the event argument's `IsOK` property.</span></span> <span data-ttu-id="797eb-163">이 속성을 통해 호스트는 클릭한 단추를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-163">This property enables the host to determine which button was clicked.</span></span> <span data-ttu-id="797eb-164">它设置为 "**确定"** 按钮 `true`，`false` "**取消**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="797eb-164">It is set to `true` for the **OK** button, and `false` for the **Cancel** button.</span></span> <span data-ttu-id="797eb-165">다음 코드에서는 두 개의 단추 처리기를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-165">The following code shows the two button handlers.</span></span>

 <span data-ttu-id="797eb-166">`MyControl1` 클래스에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-166">Add the following code to the `MyControl1` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#4)]
 [!code-vb[WpfHostingWindowsFormsControl#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#4)]

### <a name="giving-the-assembly-a-strong-name-and-building-the-assembly"></a><span data-ttu-id="797eb-167">어셈블리에 강력한 이름을 지정하고 어셈블리 빌드</span><span class="sxs-lookup"><span data-stu-id="797eb-167">Giving the Assembly a Strong Name and Building the Assembly</span></span>
 <span data-ttu-id="797eb-168">对于要由 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序引用的程序集，该程序集必须具有强名称。</span><span class="sxs-lookup"><span data-stu-id="797eb-168">For this assembly to be referenced by a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application, it must have a strong name.</span></span> <span data-ttu-id="797eb-169">若要创建强名称，请使用 Sn.exe 创建密钥文件并将其添加到你的项目中。</span><span class="sxs-lookup"><span data-stu-id="797eb-169">To create a strong name, create a key file with Sn.exe and add it to your project.</span></span>

1. <span data-ttu-id="797eb-170">Visual Studio 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-170">Open a Visual Studio command prompt.</span></span> <span data-ttu-id="797eb-171">为此，请单击 "**开始**" 菜单，然后选择 "**所有程序/Microsoft Visual Studio 2010/Visual Studio Tools/Visual Studio 命令提示**"。</span><span class="sxs-lookup"><span data-stu-id="797eb-171">To do so, click the **Start** menu, and then select **All Programs/Microsoft Visual Studio 2010/Visual Studio Tools/Visual Studio Command Prompt**.</span></span> <span data-ttu-id="797eb-172">그러면 사용자 지정된 환경 변수가 있는 콘솔 창이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-172">This launches a console window with customized environment variables.</span></span>

2. <span data-ttu-id="797eb-173">在命令提示符下，使用 `cd` 命令来打开项目文件夹。</span><span class="sxs-lookup"><span data-stu-id="797eb-173">At the command prompt, use the `cd` command to go to your project folder.</span></span>

3. <span data-ttu-id="797eb-174">다음 명령을 실행하여 MyControls.snk라는 키 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-174">Generate a key file named MyControls.snk by running the following command.</span></span>

    ```console
    Sn.exe -k MyControls.snk
    ```

4. <span data-ttu-id="797eb-175">若要在项目中包含密钥文件，请在解决方案资源管理器中右键单击项目名称，然后单击 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="797eb-175">To include the key file in your project, right-click the project name in Solution Explorer and then click **Properties**.</span></span> <span data-ttu-id="797eb-176">在 "项目设计器" 中，单击 "**签名**" 选项卡，选中 "为**程序集签名**" 复选框，然后浏览到密钥文件。</span><span class="sxs-lookup"><span data-stu-id="797eb-176">In the Project Designer, click the **Signing** tab, select the **Sign the assembly** check box and then browse to your key file.</span></span>

5. <span data-ttu-id="797eb-177">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-177">Build the solution.</span></span> <span data-ttu-id="797eb-178">빌드하면 MyControls.dll이라는 DLL이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-178">The build will produce a DLL named MyControls.dll.</span></span>

## <a name="implementing-the-wpf-host-application"></a><span data-ttu-id="797eb-179">WPF 호스트 애플리케이션 구현</span><span class="sxs-lookup"><span data-stu-id="797eb-179">Implementing the WPF Host Application</span></span>
 <span data-ttu-id="797eb-180">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 主机应用程序使用 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 控件来承载 `MyControl1`。</span><span class="sxs-lookup"><span data-stu-id="797eb-180">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] host application uses the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control to host `MyControl1`.</span></span> <span data-ttu-id="797eb-181">应用程序将处理 `OnButtonClick` 事件以接收来自控件的数据。</span><span class="sxs-lookup"><span data-stu-id="797eb-181">The application handles the `OnButtonClick` event to receive the data from the control.</span></span> <span data-ttu-id="797eb-182">它还包含一个选项按钮集合，使你能够从 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序更改控件的某些属性。</span><span class="sxs-lookup"><span data-stu-id="797eb-182">It also has a collection of option buttons that enable you to change some of the control's properties from the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="797eb-183">다음 그림에서는 완료된 애플리케이션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-183">The following illustration shows the finished application.</span></span>

<span data-ttu-id="797eb-184">下图显示了完整的应用程序，包括嵌入在 WPF 应用程序中的控件：</span><span class="sxs-lookup"><span data-stu-id="797eb-184">The following image shows the complete application, including the control embedded in the WPF application:</span></span>

 ![显示嵌入在 WPF 页中的控件的屏幕截图。](./media/walkthrough-hosting-a-windows-forms-composite-control-in-wpf/windows-presentation-foundation-page-control.gif)

### <a name="creating-the-project"></a><span data-ttu-id="797eb-186">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="797eb-186">Creating the Project</span></span>
 <span data-ttu-id="797eb-187">프로젝트를 시작하려면</span><span class="sxs-lookup"><span data-stu-id="797eb-187">To start the project:</span></span>

1. <span data-ttu-id="797eb-188">打开 Visual Studio，然后选择 "**新建项目**"。</span><span class="sxs-lookup"><span data-stu-id="797eb-188">Open Visual Studio, and select **New Project**.</span></span>

2. <span data-ttu-id="797eb-189">在 "窗口" 类别中，选择 " **WPF 应用程序**" 模板。</span><span class="sxs-lookup"><span data-stu-id="797eb-189">In the Window category, select the **WPF Application** template.</span></span>

3. <span data-ttu-id="797eb-190">새 프로젝트의 이름을 `WpfHost`로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-190">Name the new project `WpfHost`.</span></span>

4. <span data-ttu-id="797eb-191">위치에는 MyControls 프로젝트를 포함하는 동일한 최상위 폴더를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-191">For the location, specify the same top-level folder that contains the MyControls project.</span></span>

5. <span data-ttu-id="797eb-192">**확인**을 클릭하여 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-192">Click **OK** to create the project.</span></span>

 <span data-ttu-id="797eb-193">还需要添加对包含 `MyControl1` 和其他程序集的 DLL 的引用。</span><span class="sxs-lookup"><span data-stu-id="797eb-193">You also need to add references to the DLL that contains `MyControl1` and other assemblies.</span></span>

1. <span data-ttu-id="797eb-194">在解决方案资源管理器中右键单击项目名称，然后选择 "**添加引用**"。</span><span class="sxs-lookup"><span data-stu-id="797eb-194">Right-click the project name in Solution Explorer and select **Add Reference**.</span></span>

2. <span data-ttu-id="797eb-195">单击 "**浏览**" 选项卡，然后浏览到包含 mycontrols.dll 的文件夹。</span><span class="sxs-lookup"><span data-stu-id="797eb-195">Click the **Browse** tab, and browse to the folder that contains MyControls.dll.</span></span> <span data-ttu-id="797eb-196">이 연습에서 이 폴더는 MyControls\bin\Debug입니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-196">For this walkthrough, this folder is MyControls\bin\Debug.</span></span>

3. <span data-ttu-id="797eb-197">选择 "Mycontrols.dll"，然后单击 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="797eb-197">Select MyControls.dll, and then click **OK**.</span></span>

4. <span data-ttu-id="797eb-198">添加对 WindowsFormsIntegration 程序集的引用，该程序集名为 WindowsFormsIntegration。</span><span class="sxs-lookup"><span data-stu-id="797eb-198">Add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

### <a name="implementing-the-basic-layout"></a><span data-ttu-id="797eb-199">기본 레이아웃 구현</span><span class="sxs-lookup"><span data-stu-id="797eb-199">Implementing the Basic Layout</span></span>
 <span data-ttu-id="797eb-200">主机应用程序的 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 是在 Mainwindow.xaml 中实现的。</span><span class="sxs-lookup"><span data-stu-id="797eb-200">The [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] of the host application is implemented in MainWindow.xaml.</span></span> <span data-ttu-id="797eb-201">此文件包含用于定义布局的 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 标记，并承载 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="797eb-201">This file contains [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup that defines the layout, and hosts the Windows Forms control.</span></span> <span data-ttu-id="797eb-202">애플리케이션은 세 가지 영역으로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-202">The application is divided into three regions:</span></span>

- <span data-ttu-id="797eb-203">"**控件属性**" 面板，其中包含选项按钮的集合，您可以使用这些按钮来修改所承载控件的各种属性。</span><span class="sxs-lookup"><span data-stu-id="797eb-203">The **Control Properties** panel, which contains a collection of option buttons that you can use to modify various properties of the hosted control.</span></span>

- <span data-ttu-id="797eb-204">"**控制面板**" 中的数据，其中包含多个 <xref:System.Windows.Controls.TextBlock> 元素，这些元素显示从寄宿控件返回的数据。</span><span class="sxs-lookup"><span data-stu-id="797eb-204">The **Data from Control** panel, which contains several <xref:System.Windows.Controls.TextBlock> elements that display the data returned from the hosted control.</span></span>

- <span data-ttu-id="797eb-205">호스트된 컨트롤 자체.</span><span class="sxs-lookup"><span data-stu-id="797eb-205">The hosted control itself.</span></span>

 <span data-ttu-id="797eb-206">기본 레이아웃은 다음과 같은 XAML로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-206">The basic layout is shown in the following XAML.</span></span> <span data-ttu-id="797eb-207">本示例中省略了宿主 `MyControl1` 所需的标记，但稍后将对此进行讨论。</span><span class="sxs-lookup"><span data-stu-id="797eb-207">The markup that is needed to host `MyControl1` is omitted from this example, but will be discussed later.</span></span>

 <span data-ttu-id="797eb-208">MainWindow.xaml의 XAML을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-208">Replace the XAML in MainWindow.xaml with the following.</span></span> <span data-ttu-id="797eb-209">如果使用 Visual Basic，请将类更改为 `x:Class="MainWindow"`。</span><span class="sxs-lookup"><span data-stu-id="797eb-209">If you are using Visual Basic, change the class to `x:Class="MainWindow"`.</span></span>

 [!code-xaml[WpfHostingWindowsFormsControl#100](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#100)]

 <span data-ttu-id="797eb-210">第一个 <xref:System.Windows.Controls.StackPanel> 元素包含多组 <xref:System.Windows.Controls.RadioButton> 控件，这些控件可用于修改所承载控件的各种默认属性。</span><span class="sxs-lookup"><span data-stu-id="797eb-210">The first <xref:System.Windows.Controls.StackPanel> element contains several sets of <xref:System.Windows.Controls.RadioButton> controls that enable you to modify various default properties of the hosted control.</span></span> <span data-ttu-id="797eb-211">后跟一个承载 `MyControl1`的 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素。</span><span class="sxs-lookup"><span data-stu-id="797eb-211">That is followed by a <xref:System.Windows.Forms.Integration.WindowsFormsHost> element, which hosts `MyControl1`.</span></span> <span data-ttu-id="797eb-212">最后一个 <xref:System.Windows.Controls.StackPanel> 元素包含多个显示由寄宿控件返回的数据的 <xref:System.Windows.Controls.TextBlock> 元素。</span><span class="sxs-lookup"><span data-stu-id="797eb-212">The final <xref:System.Windows.Controls.StackPanel> element contains several <xref:System.Windows.Controls.TextBlock> elements that display the data that is returned by the hosted control.</span></span> <span data-ttu-id="797eb-213">元素的顺序以及 "<xref:System.Windows.Controls.DockPanel.Dock%2A>" 和 "<xref:System.Windows.FrameworkElement.Height%2A>" 属性 "设置将承载的控件嵌入到窗口中，无间隔或失真。</span><span class="sxs-lookup"><span data-stu-id="797eb-213">The ordering of the elements and the <xref:System.Windows.Controls.DockPanel.Dock%2A> and <xref:System.Windows.FrameworkElement.Height%2A> attribute settings embed the hosted control into the window with no gaps or distortion.</span></span>

#### <a name="hosting-the-control"></a><span data-ttu-id="797eb-214">컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="797eb-214">Hosting the Control</span></span>
 <span data-ttu-id="797eb-215">之前的 XAML 的以下编辑版本侧重于承载 `MyControl1`所需的元素。</span><span class="sxs-lookup"><span data-stu-id="797eb-215">The following edited version of the previous XAML focuses on the elements that are needed to host `MyControl1`.</span></span>

 [!code-xaml[WpfHostingWindowsFormsControl#101](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#101)]
[!code-xaml[WpfHostingWindowsFormsControl#102](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#102)]

 <span data-ttu-id="797eb-216">`xmlns` 命名空间映射特性创建对包含所承载控件的 `MyControls` 命名空间的引用。</span><span class="sxs-lookup"><span data-stu-id="797eb-216">The `xmlns` namespace mapping attribute creates a reference to the `MyControls` namespace that contains the hosted control.</span></span> <span data-ttu-id="797eb-217">此映射使你能够以 `<mcl:MyControl1>`形式表示 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中的 `MyControl1`。</span><span class="sxs-lookup"><span data-stu-id="797eb-217">This mapping enables you to represent `MyControl1` in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] as `<mcl:MyControl1>`.</span></span>

 <span data-ttu-id="797eb-218">XAML의 두 요소가 호스팅을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-218">Two elements in the XAML handle the hosting:</span></span>

- <span data-ttu-id="797eb-219">`WindowsFormsHost` 表示 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素，使用该元素可以在 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 应用程序中承载 Windows 窗体控件。</span><span class="sxs-lookup"><span data-stu-id="797eb-219">`WindowsFormsHost` represents the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element that enables you to host a Windows Forms control in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>

- <span data-ttu-id="797eb-220">`mcl:MyControl1`（表示 `MyControl1`）将添加到 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素的子集合。</span><span class="sxs-lookup"><span data-stu-id="797eb-220">`mcl:MyControl1`, which represents `MyControl1`, is added to the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's child collection.</span></span> <span data-ttu-id="797eb-221">因此，此 Windows 窗体控件将呈现为 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 窗口的一部分，您可以从应用程序与控件进行通信。</span><span class="sxs-lookup"><span data-stu-id="797eb-221">As a result, this Windows Forms control is rendered as part of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] window, and you can communicate with the control from the application.</span></span>

### <a name="implementing-the-code-behind-file"></a><span data-ttu-id="797eb-222">코드 숨김 파일 구현</span><span class="sxs-lookup"><span data-stu-id="797eb-222">Implementing the Code-Behind File</span></span>
 <span data-ttu-id="797eb-223">代码隐藏文件（Mainwindow.xaml 或 MainWindow.xaml.cs）包含实现上一部分所述的 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 功能的过程代码。</span><span class="sxs-lookup"><span data-stu-id="797eb-223">The code-behind file, MainWindow.xaml.vb or MainWindow.xaml.cs, contains the procedural code that implements the functionality of the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] discussed in the preceding section.</span></span> <span data-ttu-id="797eb-224">기본 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-224">The primary tasks are:</span></span>

- <span data-ttu-id="797eb-225">将事件处理程序附加到 `MyControl1`的 `OnButtonClick` 事件。</span><span class="sxs-lookup"><span data-stu-id="797eb-225">Attaching an event handler to `MyControl1`'s `OnButtonClick` event.</span></span>

- <span data-ttu-id="797eb-226">根据设置选项按钮集合的方式修改 `MyControl1`的各种属性。</span><span class="sxs-lookup"><span data-stu-id="797eb-226">Modifying various properties of `MyControl1`, based on how the collection of option buttons are set.</span></span>

- <span data-ttu-id="797eb-227">컨트롤에서 수집한 데이터 표시.</span><span class="sxs-lookup"><span data-stu-id="797eb-227">Displaying the data collected by the control.</span></span>

#### <a name="initializing-the-application"></a><span data-ttu-id="797eb-228">애플리케이션 초기화</span><span class="sxs-lookup"><span data-stu-id="797eb-228">Initializing the Application</span></span>
 <span data-ttu-id="797eb-229">初始化代码包含在窗口的 <xref:System.Windows.FrameworkElement.Loaded> 事件的事件处理程序中，并将事件处理程序附加到控件的 `OnButtonClick` 事件。</span><span class="sxs-lookup"><span data-stu-id="797eb-229">The initialization code is contained in an event handler for the window's <xref:System.Windows.FrameworkElement.Loaded> event and attaches an event handler to the control's `OnButtonClick` event.</span></span>

 <span data-ttu-id="797eb-230">在 Mainwindow.xaml 或 MainWindow.xaml.cs 中，将以下代码添加到 `MainWindow` 类。</span><span class="sxs-lookup"><span data-stu-id="797eb-230">In MainWindow.xaml.vb or MainWindow.xaml.cs, add the following code to the `MainWindow` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#11)]
 [!code-vb[WpfHostingWindowsFormsControl#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#11)]

 <span data-ttu-id="797eb-231">由于前面所述的 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 将 `MyControl1` 添加到 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素的子元素集合中，因此可以将 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素的 <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> 强制转换为获取对 `MyControl1`的引用。</span><span class="sxs-lookup"><span data-stu-id="797eb-231">Because the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] discussed previously added `MyControl1` to the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's child element collection, you can cast the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> to get the reference to `MyControl1`.</span></span> <span data-ttu-id="797eb-232">然后，可以使用该引用将事件处理程序附加到 `OnButtonClick`。</span><span class="sxs-lookup"><span data-stu-id="797eb-232">You can then use that reference to attach an event handler to `OnButtonClick`.</span></span>

 <span data-ttu-id="797eb-233">除了提供对控件本身的引用外，<xref:System.Windows.Forms.Integration.WindowsFormsHost> 公开了许多控件属性，您可以从应用程序中对其进行操作。</span><span class="sxs-lookup"><span data-stu-id="797eb-233">In addition to providing a reference to the control itself, <xref:System.Windows.Forms.Integration.WindowsFormsHost> exposes a number of the control's properties, which you can manipulate from the application.</span></span> <span data-ttu-id="797eb-234">초기화 코드는 나중에 애플리케이션에서 사용할 수 있도록 private 전역 변수에 해당 값을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-234">The initialization code assigns those values to private global variables for later use in the application.</span></span>

 <span data-ttu-id="797eb-235">因此，您可以轻松访问 `MyControls` DLL 中的类型，将以下 `Imports` 或 `using` 语句添加到文件的顶部。</span><span class="sxs-lookup"><span data-stu-id="797eb-235">So that you can easily access the types in the `MyControls` DLL, add the following `Imports` or `using` statement to the top of the file.</span></span>

```vb
Imports MyControls
```

```csharp
using MyControls;
```

#### <a name="handling-the-onbuttonclick-event"></a><span data-ttu-id="797eb-236">OnButtonClick 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="797eb-236">Handling the OnButtonClick Event</span></span>
 <span data-ttu-id="797eb-237">当用户单击控件的任一按钮时，`MyControl1` 引发 `OnButtonClick` 事件。</span><span class="sxs-lookup"><span data-stu-id="797eb-237">`MyControl1` raises the `OnButtonClick` event when the user clicks either of the control's buttons.</span></span>

 <span data-ttu-id="797eb-238">`MainWindow` 클래스에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-238">Add the following code to the `MainWindow` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#12)]
 [!code-vb[WpfHostingWindowsFormsControl#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#12)]

 <span data-ttu-id="797eb-239">文本框中的数据将打包到 `MyControlEventArgs` 对象中。</span><span class="sxs-lookup"><span data-stu-id="797eb-239">The data in the text boxes is packed into the `MyControlEventArgs` object.</span></span> <span data-ttu-id="797eb-240">如果用户单击 **"确定"** 按钮，事件处理程序将提取数据并将其显示在下面的面板中 `MyControl1`。</span><span class="sxs-lookup"><span data-stu-id="797eb-240">If the user clicks the **OK** button, the event handler extracts the data and displays it in the panel below `MyControl1`.</span></span>

#### <a name="modifying-the-controls-properties"></a><span data-ttu-id="797eb-241">컨트롤의 속성 수정</span><span class="sxs-lookup"><span data-stu-id="797eb-241">Modifying the Control’s Properties</span></span>
 <span data-ttu-id="797eb-242"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 元素公开几个托管控件的默认属性。</span><span class="sxs-lookup"><span data-stu-id="797eb-242">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element exposes several of the hosted control's default properties.</span></span> <span data-ttu-id="797eb-243">결과적으로 애플리케이션의 스타일과 더 가깝게 일치하도록 컨트롤의 모양을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-243">As a result, you can change the appearance of the control to match the style of your application more closely.</span></span> <span data-ttu-id="797eb-244">왼쪽 패널의 옵션 단추 집합을 사용하여 사용자는 여러 가지 색 및 글꼴 속성을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-244">The sets of option buttons in the left panel enable the user to modify several color and font properties.</span></span> <span data-ttu-id="797eb-245">每组按钮都具有 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 事件的处理程序，该处理程序检测用户的选项按钮选择并更改控件上的相应属性。</span><span class="sxs-lookup"><span data-stu-id="797eb-245">Each set of buttons has a handler for the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event, which detects the user's option button selections and changes the corresponding property on the control.</span></span>

 <span data-ttu-id="797eb-246">`MainWindow` 클래스에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-246">Add the following code to the `MainWindow` class.</span></span>

 [!code-csharp[WpfHostingWindowsFormsControl#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#13)]
 [!code-vb[WpfHostingWindowsFormsControl#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#13)]  
  
 <span data-ttu-id="797eb-247">애플리케이션을 빌드 및 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-247">Build and run the application.</span></span> <span data-ttu-id="797eb-248">在 Windows 窗体复合控件中添加一些文本，然后单击 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="797eb-248">Add some text in the Windows Forms composite control and then click **OK**.</span></span> <span data-ttu-id="797eb-249">텍스트가 레이블에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-249">The text appears in the labels.</span></span> <span data-ttu-id="797eb-250">컨트롤에 대한 효과를 확인하려면 다른 라디오 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="797eb-250">Click the different radio buttons to see the effect on the control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="797eb-251">另请参阅</span><span class="sxs-lookup"><span data-stu-id="797eb-251">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="797eb-252">Visual Studio에서 XAML 디자인</span><span class="sxs-lookup"><span data-stu-id="797eb-252">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="797eb-253">연습: WPF에서 Windows Forms 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="797eb-253">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [<span data-ttu-id="797eb-254">연습: Windows Forms에서 WPF 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="797eb-254">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)

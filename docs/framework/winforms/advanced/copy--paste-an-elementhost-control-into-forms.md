---
title: "演练：将 ElementHost 控件复制并粘贴到单独的 Windows 窗体中"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 6e81bb13-577c-46c3-a1cf-8d15969fb83e
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 579bce312296d9799f9f7c739f740e2c9111ccff
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-copying-and-pasting-an-elementhost-control-into-separate-windows-forms"></a><span data-ttu-id="0203d-102">演练：将 ElementHost 控件复制并粘贴到单独的 Windows 窗体中</span><span class="sxs-lookup"><span data-stu-id="0203d-102">Walkthrough: Copying and Pasting an ElementHost Control into Separate Windows Forms</span></span>
<span data-ttu-id="0203d-103">本演练显示了如何将 Windows Presentation Foundation (WPF) 控件从一个 Windows 窗体复制到其他 Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="0203d-103">This walkthrough shows you how to copy a Windows Presentation Foundation (WPF) control from one Windows Form to another.</span></span>  
  
 <span data-ttu-id="0203d-104">在本演练中，你将要执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="0203d-104">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="0203d-105">创建项目。</span><span class="sxs-lookup"><span data-stu-id="0203d-105">Create the project.</span></span>  
  
-   <span data-ttu-id="0203d-106">复制 WPF 控件。</span><span class="sxs-lookup"><span data-stu-id="0203d-106">Copy a WPF Control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0203d-107">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="0203d-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="0203d-108">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="0203d-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="0203d-109">有关详细信息，请参阅 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="0203d-109">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0203d-110">系统必备</span><span class="sxs-lookup"><span data-stu-id="0203d-110">Prerequisites</span></span>  
 <span data-ttu-id="0203d-111">你需要以下组件来完成本演练：</span><span class="sxs-lookup"><span data-stu-id="0203d-111">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)]<span data-ttu-id="0203d-112">。</span><span class="sxs-lookup"><span data-stu-id="0203d-112">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="0203d-113">创建项目</span><span class="sxs-lookup"><span data-stu-id="0203d-113">Creating the Project</span></span>  
 <span data-ttu-id="0203d-114">第一步是创建 Windows 窗体项目。</span><span class="sxs-lookup"><span data-stu-id="0203d-114">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0203d-115">承载 WPF 内容时，仅支持 C# 和 Visual Basic 项目。</span><span class="sxs-lookup"><span data-stu-id="0203d-115">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="0203d-116">要创建项目</span><span class="sxs-lookup"><span data-stu-id="0203d-116">To create the project</span></span>  
  
-   <span data-ttu-id="0203d-117">创建新的 Windows 窗体应用程序项目中 Visual Basic 或 Visual C# 名为`CopyElementHost`。</span><span class="sxs-lookup"><span data-stu-id="0203d-117">Create a new Windows Forms Application project in Visual Basic or Visual C# named `CopyElementHost`.</span></span>  
  
## <a name="copying-a-wpf-control"></a><span data-ttu-id="0203d-118">复制 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="0203d-118">Copying a WPF Control</span></span>  
 <span data-ttu-id="0203d-119">将 WPF 控件添加到项目后，可将它复制到项目中的其他窗体。</span><span class="sxs-lookup"><span data-stu-id="0203d-119">After you add a WPF control to the project, you can copy it to other forms in the project.</span></span>  
  
#### <a name="to-copy-a-wpf-control"></a><span data-ttu-id="0203d-120">复制 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="0203d-120">To copy a WPF control</span></span>  
  
1.  <span data-ttu-id="0203d-121">将新的 WPF <xref:System.Windows.Controls.UserControl> 项目添加到解决方案。</span><span class="sxs-lookup"><span data-stu-id="0203d-121">Add a new WPF <xref:System.Windows.Controls.UserControl> project to the solution.</span></span> <span data-ttu-id="0203d-122">使用控件类型的默认名称，`UserControl1.xaml`。</span><span class="sxs-lookup"><span data-stu-id="0203d-122">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="0203d-123">有关详细信息，请参阅[演练： 创建新 WPF 内容在设计时的 Windows 窗体上](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)。</span><span class="sxs-lookup"><span data-stu-id="0203d-123">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2.  <span data-ttu-id="0203d-124">生成项目。</span><span class="sxs-lookup"><span data-stu-id="0203d-124">Build the project.</span></span>  
  
3.  <span data-ttu-id="0203d-125">在 Windows 窗体设计器中打开 `Form1`。</span><span class="sxs-lookup"><span data-stu-id="0203d-125">Open `Form1` in the Windows Forms Designer.</span></span>  
  
4.  <span data-ttu-id="0203d-126">从**工具箱**的一个实例拖`UserControl1`拖到窗体。</span><span class="sxs-lookup"><span data-stu-id="0203d-126">From the **Toolbox**, drag an instance of `UserControl1` onto the form.</span></span>  
  
     <span data-ttu-id="0203d-127">`UserControl1` 的实例托管在名为 `elementHost1` 的新 <xref:System.Windows.Forms.Integration.ElementHost> 控件中。</span><span class="sxs-lookup"><span data-stu-id="0203d-127">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
5.  <span data-ttu-id="0203d-128">选择`elementHost1` 后，按 CTRL + C 将它复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="0203d-128">With `elementHost1` selected, press CTRL+C to copy it to the clipboard.</span></span>  
  
6.  <span data-ttu-id="0203d-129">向项目添加新的 Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="0203d-129">Add a new Windows Form to the project.</span></span> <span data-ttu-id="0203d-130">使用窗体类型的默认名称：`Form2`。</span><span class="sxs-lookup"><span data-stu-id="0203d-130">Use the default name for the form type, `Form2`.</span></span>  
  
7.  <span data-ttu-id="0203d-131">在 Windows 窗体设计器中打开 `Form2` 的情况下，按 CTRL+V 将 `elementHost1` 的副本粘贴到窗体。</span><span class="sxs-lookup"><span data-stu-id="0203d-131">With `Form2` open in the Windows Forms Designer, press CTRL+V to paste a copy of `elementHost1` onto the form.</span></span>  
  
     <span data-ttu-id="0203d-132">复制的控件名称也命名为 `elementHost1`，因为它是 `Form2` 类的私有字段。</span><span class="sxs-lookup"><span data-stu-id="0203d-132">The copied control is also named `elementHost1`, because it is a private field of the `Form2` class.</span></span> <span data-ttu-id="0203d-133">`Form1` 类中不存在与 `elementHost1` 的名称冲突。</span><span class="sxs-lookup"><span data-stu-id="0203d-133">There is no name collision with the `elementHost1` in the `Form1` class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0203d-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="0203d-134">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="0203d-135">迁移和互操作性</span><span class="sxs-lookup"><span data-stu-id="0203d-135">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [<span data-ttu-id="0203d-136">使用 WPF 控件</span><span class="sxs-lookup"><span data-stu-id="0203d-136">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [<span data-ttu-id="0203d-137">WPF 设计器</span><span class="sxs-lookup"><span data-stu-id="0203d-137">WPF Designer</span></span>](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)

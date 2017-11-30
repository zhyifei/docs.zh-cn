---
title: "演练：在 Windows 窗体应用程序中使用数据流"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TPL dataflow library, in Windows Forms
- Task Parallel Library, dataflows
- Windows Forms, and TPL
ms.assetid: 9c65cdf7-660c-409f-89ea-59d7ec8e127c
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d2775cc99020fd99d6e7d79cdf3e1ffcc3219146
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-using-dataflow-in-a-windows-forms-application"></a><span data-ttu-id="66a80-102">演练：在 Windows 窗体应用程序中使用数据流</span><span class="sxs-lookup"><span data-stu-id="66a80-102">Walkthrough: Using Dataflow in a Windows Forms Application</span></span>
<span data-ttu-id="66a80-103">本文档演示如何创建在 Windows 窗体应用程序中执行图像处理的数据流块网络。</span><span class="sxs-lookup"><span data-stu-id="66a80-103">This document demonstrates how to create a network of dataflow blocks that perform image processing in a Windows Forms application.</span></span>  
  
 <span data-ttu-id="66a80-104">此示例从指定的文件夹加载图像文件、创建复合图像，并显示结果。</span><span class="sxs-lookup"><span data-stu-id="66a80-104">This example loads image files from the specified folder, creates a composite image, and displays the result.</span></span> <span data-ttu-id="66a80-105">本示例使用数据流模型通过网络路由图像。</span><span class="sxs-lookup"><span data-stu-id="66a80-105">The example uses the dataflow model to route images through the network.</span></span> <span data-ttu-id="66a80-106">在数据流模型中，程序的独立组件之间通过发送消息进行通信。</span><span class="sxs-lookup"><span data-stu-id="66a80-106">In the dataflow model, independent components of a program communicate with one another by sending messages.</span></span> <span data-ttu-id="66a80-107">某个组件收到一条消息时，它会执行某项操作，然后将结果传递给另一个组件。</span><span class="sxs-lookup"><span data-stu-id="66a80-107">When a component receives a message, it performs some action and then passes the result to another component.</span></span> <span data-ttu-id="66a80-108">相比之下，在控制流模型中，应用程序使用控制结构（例如条件语句和循环等等）控制程序中操作的顺序。</span><span class="sxs-lookup"><span data-stu-id="66a80-108">Compare this with the control flow model, in which an application uses control structures, for example, conditional statements, loops, and so on, to control the order of operations in a program.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="66a80-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="66a80-109">Prerequisites</span></span>  
 <span data-ttu-id="66a80-110">开始本演练之前，请阅读[数据流](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)。</span><span class="sxs-lookup"><span data-stu-id="66a80-110">Read [Dataflow](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) before you start this walkthrough.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="66a80-111">TPL 数据流库（<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> 命名空间）不是随 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 一起分发的。</span><span class="sxs-lookup"><span data-stu-id="66a80-111">The TPL Dataflow Library (<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> namespace) is not distributed with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span> <span data-ttu-id="66a80-112">若要安装<xref:System.Threading.Tasks.Dataflow>命名空间中，打开你的项目中[!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)]，选择**管理 NuGet 包**从项目菜单，然后联机搜索`Microsoft.Tpl.Dataflow`包。</span><span class="sxs-lookup"><span data-stu-id="66a80-112">To install the <xref:System.Threading.Tasks.Dataflow> namespace, open your project in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], choose **Manage NuGet Packages** from the Project menu, and search online for the `Microsoft.Tpl.Dataflow` package.</span></span>  
 
  
## <a name="sections"></a><span data-ttu-id="66a80-113">部分</span><span class="sxs-lookup"><span data-stu-id="66a80-113">Sections</span></span>  
 <span data-ttu-id="66a80-114">本演练包含以下各节：</span><span class="sxs-lookup"><span data-stu-id="66a80-114">This walkthrough contains the following sections:</span></span>  
  
-   [<span data-ttu-id="66a80-115">创建 Windows 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="66a80-115">Creating the Windows Forms Application</span></span>](#winforms)  
  
-   [<span data-ttu-id="66a80-116">创建数据流网络</span><span class="sxs-lookup"><span data-stu-id="66a80-116">Creating the Dataflow Network</span></span>](#network)  
  
-   [<span data-ttu-id="66a80-117">将数据流网络连接到用户界面</span><span class="sxs-lookup"><span data-stu-id="66a80-117">Connecting the Dataflow Network to the User Interface</span></span>](#ui)  
  
-   [<span data-ttu-id="66a80-118">完整示例</span><span class="sxs-lookup"><span data-stu-id="66a80-118">The Complete Example</span></span>](#complete)  
  
<a name="winforms"></a>   
## <a name="creating-the-windows-forms-application"></a><span data-ttu-id="66a80-119">创建 Windows 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="66a80-119">Creating the Windows Forms Application</span></span>  
 <span data-ttu-id="66a80-120">本节介绍如何创建基本 Windows 窗体应用程序并将控件添加到主窗体。</span><span class="sxs-lookup"><span data-stu-id="66a80-120">This section describes how to create the basic Windows Forms application and add controls to the main form.</span></span>  
  
#### <a name="to-create-the-windows-forms-application"></a><span data-ttu-id="66a80-121">创建 Windows 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="66a80-121">To Create the Windows Forms Application</span></span>  
  
1.  <span data-ttu-id="66a80-122">在 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 中，创建一个 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] 或 Visual Basic **Windows 窗体应用程序**项目。</span><span class="sxs-lookup"><span data-stu-id="66a80-122">In [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], create a [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] or Visual Basic **Windows Forms Application** project.</span></span> <span data-ttu-id="66a80-123">在本文档中，该项目名为 `CompositeImages`。</span><span class="sxs-lookup"><span data-stu-id="66a80-123">In this document, the project is named `CompositeImages`.</span></span>  
  
2.  <span data-ttu-id="66a80-124">在窗体设计器中主窗体，Form1.cs (对于 Form1.vb [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)])，添加<xref:System.Windows.Forms.ToolStrip>控件。</span><span class="sxs-lookup"><span data-stu-id="66a80-124">On the form designer for the main form, Form1.cs (Form1.vb for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), add a <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
3.  <span data-ttu-id="66a80-125">添加<xref:System.Windows.Forms.ToolStripButton>控制转移到<xref:System.Windows.Forms.ToolStrip>控件。</span><span class="sxs-lookup"><span data-stu-id="66a80-125">Add a <xref:System.Windows.Forms.ToolStripButton> control to the <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="66a80-126">设置<xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A>属性<xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>和<xref:System.Windows.Forms.ToolStripItem.Text%2A>属性**选择文件夹**。</span><span class="sxs-lookup"><span data-stu-id="66a80-126">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> and the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to **Choose Folder**.</span></span>  
  
4.  <span data-ttu-id="66a80-127">添加第二个<xref:System.Windows.Forms.ToolStripButton>控制转移到<xref:System.Windows.Forms.ToolStrip>控件。</span><span class="sxs-lookup"><span data-stu-id="66a80-127">Add a second <xref:System.Windows.Forms.ToolStripButton> control to the <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="66a80-128">设置<xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A>属性<xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>、<xref:System.Windows.Forms.ToolStripItem.Text%2A>属性**取消**，和<xref:System.Windows.Forms.ToolStripItem.Enabled%2A>属性`False`。</span><span class="sxs-lookup"><span data-stu-id="66a80-128">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>, the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to **Cancel**, and the <xref:System.Windows.Forms.ToolStripItem.Enabled%2A> property to `False`.</span></span>  
  
5.  <span data-ttu-id="66a80-129">添加<xref:System.Windows.Forms.PictureBox>到主窗体的对象。</span><span class="sxs-lookup"><span data-stu-id="66a80-129">Add a <xref:System.Windows.Forms.PictureBox> object to the main form.</span></span> <span data-ttu-id="66a80-130">将 <xref:System.Windows.Forms.Control.Dock%2A> 属性设置为 <xref:System.Windows.Forms.DockStyle.Fill>。</span><span class="sxs-lookup"><span data-stu-id="66a80-130">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
<a name="network"></a>   
## <a name="creating-the-dataflow-network"></a><span data-ttu-id="66a80-131">创建数据流网络</span><span class="sxs-lookup"><span data-stu-id="66a80-131">Creating the Dataflow Network</span></span>  
 <span data-ttu-id="66a80-132">本节介绍如何创建执行图像处理的数据流网络。</span><span class="sxs-lookup"><span data-stu-id="66a80-132">This section describes how to create the dataflow network that performs image processing.</span></span>  
  
#### <a name="to-create-the-dataflow-network"></a><span data-ttu-id="66a80-133">创建数据流网络</span><span class="sxs-lookup"><span data-stu-id="66a80-133">To Create the Dataflow Network</span></span>  
  
1.  <span data-ttu-id="66a80-134">向项目中添加对 System.Threading.Tasks.Dataflow.dll 的引用。</span><span class="sxs-lookup"><span data-stu-id="66a80-134">Add a reference to System.Threading.Tasks.Dataflow.dll to your project.</span></span>  
  
2.  <span data-ttu-id="66a80-135">确保 Form1.cs（对于 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] 则为 Form1.vb）包含以下 `using`（在 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] 中为 `Using`）语句：</span><span class="sxs-lookup"><span data-stu-id="66a80-135">Ensure that Form1.cs (Form1.vb for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) contains the following `using` (`Using` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) statements:</span></span>  
  
     [!code-csharp[TPLDataflow_CompositeImages#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#1)]  
  
3.  <span data-ttu-id="66a80-136">将以下数据成员添加到 `Form1` 类：</span><span class="sxs-lookup"><span data-stu-id="66a80-136">Add the following data members to the `Form1` class:</span></span>  
  
     [!code-csharp[TPLDataflow_CompositeImages#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#2)]  
  
4.  <span data-ttu-id="66a80-137">将下面的 `CreateImageProcessingNetwork` 方法添加到 `Form1` 类。</span><span class="sxs-lookup"><span data-stu-id="66a80-137">Add the following method, `CreateImageProcessingNetwork`, to the `Form1` class.</span></span> <span data-ttu-id="66a80-138">此方法创建图像处理网络。</span><span class="sxs-lookup"><span data-stu-id="66a80-138">This method creates the image processing network.</span></span>  
  
     [!code-csharp[TPLDataflow_CompositeImages#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#3)]  
  
5.  <span data-ttu-id="66a80-139">实现 `LoadBitmaps` 方法。</span><span class="sxs-lookup"><span data-stu-id="66a80-139">Implement the `LoadBitmaps` method.</span></span>  
  
     [!code-csharp[TPLDataflow_CompositeImages#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#4)]  
  
6.  <span data-ttu-id="66a80-140">实现 `CreateCompositeBitmap` 方法。</span><span class="sxs-lookup"><span data-stu-id="66a80-140">Implement the `CreateCompositeBitmap` method.</span></span>  
  
     [!code-csharp[TPLDataflow_CompositeImages#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#5)]  
  
    > [!NOTE]
    >  <span data-ttu-id="66a80-141">C# 版本`CreateCompositeBitmap`方法使用指针来启用高效处理的<xref:System.Drawing.Bitmap?displayProperty=nameWithType>对象。</span><span class="sxs-lookup"><span data-stu-id="66a80-141">The C# version of the `CreateCompositeBitmap` method uses pointers to enable efficient processing of the <xref:System.Drawing.Bitmap?displayProperty=nameWithType> objects.</span></span> <span data-ttu-id="66a80-142">因此，若要使用 [unsafe](~/docs/csharp/language-reference/keywords/unsafe.md) 关键字，必须在项目中启用“允许不安全代码”选项。</span><span class="sxs-lookup"><span data-stu-id="66a80-142">Therefore, you must enable the **Allow unsafe code** option in your project in order to use the [unsafe](~/docs/csharp/language-reference/keywords/unsafe.md) keyword.</span></span> <span data-ttu-id="66a80-143">有关如何启用中的不安全代码的详细信息[!INCLUDE[csprcs](../../../includes/csprcs-md.md)]项目，请参阅 [生成页，项目设计器 (C#)] https://msdn.microsoft.com/library/kb4wyys2)。</span><span class="sxs-lookup"><span data-stu-id="66a80-143">For more information about how to enable unsafe code in a [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] project, see [Build Page, Project Designer (C#)]https://msdn.microsoft.com/library/kb4wyys2).</span></span>  
  
 <span data-ttu-id="66a80-144">下表描述了网络的成员。</span><span class="sxs-lookup"><span data-stu-id="66a80-144">The following table describes the members of the network.</span></span>  
  
|<span data-ttu-id="66a80-145">成员</span><span class="sxs-lookup"><span data-stu-id="66a80-145">Member</span></span>|<span data-ttu-id="66a80-146">类型</span><span class="sxs-lookup"><span data-stu-id="66a80-146">Type</span></span>|<span data-ttu-id="66a80-147">描述</span><span class="sxs-lookup"><span data-stu-id="66a80-147">Description</span></span>|  
|------------|----------|-----------------|  
|`loadBitmaps`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|<span data-ttu-id="66a80-148">采用文件夹路径作为输入并且生成的集合<xref:System.Drawing.Bitmap>作为输出的对象。</span><span class="sxs-lookup"><span data-stu-id="66a80-148">Takes a folder path as input and produces a collection of <xref:System.Drawing.Bitmap> objects as output.</span></span>|  
|`createCompositeBitmap`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|<span data-ttu-id="66a80-149">采用集合<xref:System.Drawing.Bitmap>对象作为输入并生成复合位图作为输出。</span><span class="sxs-lookup"><span data-stu-id="66a80-149">Takes a collection of <xref:System.Drawing.Bitmap> objects as input and produces a composite bitmap as output.</span></span>|  
|`displayCompositeBitmap`|<xref:System.Threading.Tasks.Dataflow.ActionBlock%601>|<span data-ttu-id="66a80-150">在窗体上显示复合位图。</span><span class="sxs-lookup"><span data-stu-id="66a80-150">Displays the composite bitmap on the form.</span></span>|  
|`operationCancelled`|<xref:System.Threading.Tasks.Dataflow.ActionBlock%601>|<span data-ttu-id="66a80-151">显示图像以表示操作取消并使用户能够选择其他文件夹。</span><span class="sxs-lookup"><span data-stu-id="66a80-151">Displays an image to indicate that the operation is canceled and enables the user to select another folder.</span></span>|  
  
 <span data-ttu-id="66a80-152">若要连接的数据流块以形成网络，此示例使用<xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="66a80-152">To connect the dataflow blocks to form a network, this example uses the <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> method.</span></span> <span data-ttu-id="66a80-153"><xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A>方法包含可采用的重载的版本<xref:System.Predicate%601>对象，用于确定目标块是接受还是拒绝消息。</span><span class="sxs-lookup"><span data-stu-id="66a80-153">The <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> method contains an overloaded version that takes a <xref:System.Predicate%601> object that determines whether the target block accepts or rejects a message.</span></span> <span data-ttu-id="66a80-154">此筛选机制使消息块只接收特定值。</span><span class="sxs-lookup"><span data-stu-id="66a80-154">This filtering mechanism enables message blocks to receive only certain values.</span></span> <span data-ttu-id="66a80-155">在此示例中，网络能以两种方式进行分支。</span><span class="sxs-lookup"><span data-stu-id="66a80-155">In this example, the network can branch in one of two ways.</span></span> <span data-ttu-id="66a80-156">主分支从磁盘加载图像，创建复合图像并在窗体上显示该图像。</span><span class="sxs-lookup"><span data-stu-id="66a80-156">The main branch loads the images from disk, creates the composite image, and displays that image on the form.</span></span> <span data-ttu-id="66a80-157">备用分支取消当前操作。</span><span class="sxs-lookup"><span data-stu-id="66a80-157">The alternate branch cancels the current operation.</span></span> <span data-ttu-id="66a80-158"><xref:System.Predicate%601>对象启用沿主分支以切换到备用分支通过拒绝特定消息的数据流块。</span><span class="sxs-lookup"><span data-stu-id="66a80-158">The <xref:System.Predicate%601> objects enable the dataflow blocks along the main branch to switch to the alternative branch by rejecting certain messages.</span></span> <span data-ttu-id="66a80-159">例如，如果用户取消了操作，数据流块 `createCompositeBitmap` 将生成 `null`（在 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] 中为 `Nothing`）作为其输出。</span><span class="sxs-lookup"><span data-stu-id="66a80-159">For example, if the user cancels the operation, the dataflow block `createCompositeBitmap` produces `null` (`Nothing` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) as its output.</span></span> <span data-ttu-id="66a80-160">数据流块 `displayCompositeBitmap` 拒绝 `null` 输入值，因此该消息将传递到 `operationCancelled`。</span><span class="sxs-lookup"><span data-stu-id="66a80-160">The dataflow block `displayCompositeBitmap` rejects `null` input values, and therefore, the message is offered to `operationCancelled`.</span></span> <span data-ttu-id="66a80-161">数据流块 `operationCancelled` 接受所有消息，并因此显示图像以表示操作取消。</span><span class="sxs-lookup"><span data-stu-id="66a80-161">The dataflow block `operationCancelled` accepts all messages and therefore, displays an image to indicate that the operation is canceled.</span></span>  
  
 <span data-ttu-id="66a80-162">下图显示图像处理网络。</span><span class="sxs-lookup"><span data-stu-id="66a80-162">The following illustration shows the image processing network.</span></span>  
  
 <span data-ttu-id="66a80-163">![图像处理网络](../../../docs/standard/parallel-programming/media/dataflowwinforms.png "DataflowWinForms")</span><span class="sxs-lookup"><span data-stu-id="66a80-163">![The image processing network](../../../docs/standard/parallel-programming/media/dataflowwinforms.png "DataflowWinForms")</span></span>  
  
 <span data-ttu-id="66a80-164">因为 `displayCompositeBitmap` 和 `operationCancelled` 数据流块是在用户界面上操作，所以这些操作要在用户界面线程上执行，这一点很重要。</span><span class="sxs-lookup"><span data-stu-id="66a80-164">Because the `displayCompositeBitmap` and `operationCancelled` dataflow blocks act on the user interface, it is important that these actions occur on the user-interface thread.</span></span> <span data-ttu-id="66a80-165">若要实现此目的，在构造期间，每个这些对象提供<xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions>具有对象<xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A>属性设置为<xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="66a80-165">To accomplish this, during construction, these objects each provide a <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> object that has the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> property set to <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="66a80-166"><xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> 方法会创建一个在当前同步上下文中执行工作的 <xref:System.Threading.Tasks.TaskScheduler> 对象。</span><span class="sxs-lookup"><span data-stu-id="66a80-166">The <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> method creates a <xref:System.Threading.Tasks.TaskScheduler> object that performs work on the current synchronization context.</span></span> <span data-ttu-id="66a80-167">因为 `CreateImageProcessingNetwork` 方法是通过“选择文件夹”按钮的处理程序调用的，而该处理程序在用户界面线程上运行，所以 `displayCompositeBitmap` 和 `operationCancelled` 数据流块的操作也在用户界面线程上运行。</span><span class="sxs-lookup"><span data-stu-id="66a80-167">Because the `CreateImageProcessingNetwork` method is called from the handler of the **Choose Folder** button, which runs on the user-interface thread, the actions for the `displayCompositeBitmap` and `operationCancelled` dataflow blocks also run on the user-interface thread.</span></span>  
  
 <span data-ttu-id="66a80-168">此示例使用共享的取消标记而不是设置<xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A>属性因为<xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A>属性永久取消数据流块执行。</span><span class="sxs-lookup"><span data-stu-id="66a80-168">This example uses a shared cancellation token instead of setting the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> property because the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> property permanently cancels dataflow block execution.</span></span> <span data-ttu-id="66a80-169">利用取消标记，此示例可多次重复使用同一数据流网络，即使用户取消一个或多个操作也是如此。</span><span class="sxs-lookup"><span data-stu-id="66a80-169">A cancellation token enables this example to reuse the same dataflow network multiple times, even when the user cancels one or more operations.</span></span> <span data-ttu-id="66a80-170">有关示例，使用<xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A>若要永久取消数据流块的执行，请参阅[如何： 取消数据流块](../../../docs/standard/parallel-programming/how-to-cancel-a-dataflow-block.md)。</span><span class="sxs-lookup"><span data-stu-id="66a80-170">For an example that uses <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> to permanently cancel the execution of a dataflow block, see [How to: Cancel a Dataflow Block](../../../docs/standard/parallel-programming/how-to-cancel-a-dataflow-block.md).</span></span>  
  
<a name="ui"></a>   
## <a name="connecting-the-dataflow-network-to-the-user-interface"></a><span data-ttu-id="66a80-171">将数据流网络连接到用户界面</span><span class="sxs-lookup"><span data-stu-id="66a80-171">Connecting the Dataflow Network to the User Interface</span></span>  
 <span data-ttu-id="66a80-172">本节介绍如何将数据流网络连接到用户界面。</span><span class="sxs-lookup"><span data-stu-id="66a80-172">This section describes how to connect the dataflow network to the user interface.</span></span> <span data-ttu-id="66a80-173">复合图像创建和操作取消都是从“选择文件夹”和“取消”按钮启动的。</span><span class="sxs-lookup"><span data-stu-id="66a80-173">The creation of the composite image and cancellation of the operation are initiated from the **Choose Folder** and **Cancel** buttons.</span></span> <span data-ttu-id="66a80-174">用户选择以上任一按钮时，都会以异步方式启动相应操作。</span><span class="sxs-lookup"><span data-stu-id="66a80-174">When the user chooses either of these buttons, the appropriate action is initiated in an asynchronous manner.</span></span>  
  
#### <a name="to-connect-the-dataflow-network-to-the-user-interface"></a><span data-ttu-id="66a80-175">将数据流网络连接到用户界面</span><span class="sxs-lookup"><span data-stu-id="66a80-175">To Connect the Dataflow Network to the User Interface</span></span>  
  
1.  <span data-ttu-id="66a80-176">在主窗体的窗体设计器上, 创建的事件处理程序<xref:System.Windows.Forms.ToolStripItem.Click>事件**选择文件夹**按钮。</span><span class="sxs-lookup"><span data-stu-id="66a80-176">On the form designer for the main form, create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event for the **Choose Folder** button.</span></span>  
  
2.  <span data-ttu-id="66a80-177">实现<xref:System.Windows.Forms.ToolStripItem.Click>事件**选择文件夹**按钮。</span><span class="sxs-lookup"><span data-stu-id="66a80-177">Implement the <xref:System.Windows.Forms.ToolStripItem.Click> event for the **Choose Folder** button.</span></span>  
  
     [!code-csharp[TPLDataflow_CompositeImages#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#6)]  
  
3.  <span data-ttu-id="66a80-178">在主窗体的窗体设计器上, 创建的事件处理程序<xref:System.Windows.Forms.ToolStripItem.Click>事件**取消**按钮。</span><span class="sxs-lookup"><span data-stu-id="66a80-178">On the form designer for the main form, create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event for the **Cancel** button.</span></span>  
  
4.  <span data-ttu-id="66a80-179">实现<xref:System.Windows.Forms.ToolStripItem.Click>事件**取消**按钮。</span><span class="sxs-lookup"><span data-stu-id="66a80-179">Implement the <xref:System.Windows.Forms.ToolStripItem.Click> event for the **Cancel** button.</span></span>  
  
     [!code-csharp[TPLDataflow_CompositeImages#7](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#7)]  
  
<a name="complete"></a>   
## <a name="the-complete-example"></a><span data-ttu-id="66a80-180">完整示例</span><span class="sxs-lookup"><span data-stu-id="66a80-180">The Complete Example</span></span>  
 <span data-ttu-id="66a80-181">下面的示例显示此演练的完整代码。</span><span class="sxs-lookup"><span data-stu-id="66a80-181">The following example shows the complete code for this walkthrough.</span></span>  
  
 [!code-csharp[TPLDataflow_CompositeImages#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_compositeimages/cs/compositeimages/form1.cs#100)]  
  
 <span data-ttu-id="66a80-182">下图显示公共 \Sample Pictures\ 文件夹的典型输出。</span><span class="sxs-lookup"><span data-stu-id="66a80-182">The following illustration shows typical output for the common \Sample Pictures\ folder.</span></span>  
  
 <span data-ttu-id="66a80-183">![Windows 窗体应用程序](../../../docs/standard/parallel-programming/media/tpldataflow-compositeimages.gif "TPLDataflow_CompositeImages")</span><span class="sxs-lookup"><span data-stu-id="66a80-183">![The Windows Forms Application](../../../docs/standard/parallel-programming/media/tpldataflow-compositeimages.gif "TPLDataflow_CompositeImages")</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="66a80-184">后续步骤</span><span class="sxs-lookup"><span data-stu-id="66a80-184">Next Steps</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66a80-185">另请参阅</span><span class="sxs-lookup"><span data-stu-id="66a80-185">See Also</span></span>  
 [<span data-ttu-id="66a80-186">数据流</span><span class="sxs-lookup"><span data-stu-id="66a80-186">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)

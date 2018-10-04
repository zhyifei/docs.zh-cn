---
title: 移除设计器添加到 XAML 文件的视图状态
ms.date: 03/30/2017
ms.assetid: a801ce22-8699-483c-a392-7bb3834aae4f
ms.openlocfilehash: 0d4dccb16796893df58f709e011657457cc71670
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "48781682"
---
# <a name="removing-the-view-state-the-designer-adds-to-an-xaml-file"></a><span data-ttu-id="0100b-102">移除设计器添加到 XAML 文件的视图状态</span><span class="sxs-lookup"><span data-stu-id="0100b-102">Removing the View State the Designer Adds to an XAML File</span></span>
<span data-ttu-id="0100b-103">此示例演示如何创建派生自 <xref:System.Windows.Markup.XamlWriter> 的类以及如何从 XAML 文件中移除视图状态。</span><span class="sxs-lookup"><span data-stu-id="0100b-103">This sample demonstrates how to create a class that derives from <xref:System.Windows.Markup.XamlWriter> and removes view state from a XAML file.</span></span> [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] <span data-ttu-id="0100b-104">会将信息写入称作视图状态的 XAML 文档中。</span><span class="sxs-lookup"><span data-stu-id="0100b-104"> writes information into the XAML document, which is known as view state.</span></span> <span data-ttu-id="0100b-105">视图状态是指设计时所需的信息（如布局定位），运行时不需要此信息。</span><span class="sxs-lookup"><span data-stu-id="0100b-105">View state refers to the information that is required at design time, such as layout positioning, that is not required at runtime.</span></span> [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)] <span data-ttu-id="0100b-106">将此信息插入正在编辑的 XAML 文档中。</span><span class="sxs-lookup"><span data-stu-id="0100b-106"> inserts this information into the XAML document as it is edited.</span></span> [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)] <span data-ttu-id="0100b-107">使用 `mc:Ignorable` 特性将视图状态写入 XAML 文件中，因此在运行时加载 XAML 文件时不会加载此信息。</span><span class="sxs-lookup"><span data-stu-id="0100b-107"> writes the view state into the XAML file with the `mc:Ignorable` attribute, so this information is not loaded when the runtime loads the XAML file.</span></span> <span data-ttu-id="0100b-108">此示例演示如何创建一个类，此类将在处理 XAML 节点时移除视图状态信息。</span><span class="sxs-lookup"><span data-stu-id="0100b-108">This sample demonstrates how to create a class that removes that view state information while processing XAML nodes.</span></span>

## <a name="discussion"></a><span data-ttu-id="0100b-109">讨论</span><span class="sxs-lookup"><span data-stu-id="0100b-109">Discussion</span></span>
 <span data-ttu-id="0100b-110">此示例演示如何创建自定义编写器。</span><span class="sxs-lookup"><span data-stu-id="0100b-110">This sample demonstrates how to create a custom writer.</span></span>

 <span data-ttu-id="0100b-111">若要生成自定义 XAML 编写器，请创建一个从 <xref:System.Windows.Markup.XamlWriter> 继承的类。</span><span class="sxs-lookup"><span data-stu-id="0100b-111">To build a custom XAML writer, create a class that inherits from <xref:System.Windows.Markup.XamlWriter>.</span></span> <span data-ttu-id="0100b-112">XAML 编写器经常嵌套的它是典型来跟踪的"内部"XAML 编写器。</span><span class="sxs-lookup"><span data-stu-id="0100b-112">As XAML writers are often nested, it is typical to keep track of an "inner" XAML writer.</span></span> <span data-ttu-id="0100b-113">这些"内部编写器可以看作对 XAML 编写器，您可以有多个入口点执行工作，然后将处理委托给堆栈的其余部分的剩余堆栈的引用。</span><span class="sxs-lookup"><span data-stu-id="0100b-113">These "inner’ writers can be thought of as the reference to the remaining stack of XAML writers, allowing you to have multiple entry points to do work and then delegate processing to the remainder of the stack.</span></span>

 <span data-ttu-id="0100b-114">在此示例中，有几个需要注意的地方。</span><span class="sxs-lookup"><span data-stu-id="0100b-114">In this sample, there are a few items of interest.</span></span> <span data-ttu-id="0100b-115">其中一个需要注意的是，检查要编写的项是否来自某个设计器命名空间。</span><span class="sxs-lookup"><span data-stu-id="0100b-115">One is the check to see whether the item being written is from a designer namespace.</span></span> <span data-ttu-id="0100b-116">请注意，此操作还将消除工作流中对该设计器命名空间的其他类型的使用。</span><span class="sxs-lookup"><span data-stu-id="0100b-116">Note that this also strips out the use of other types from the designer namespace in a workflow.</span></span>

```csharp
static Boolean IsDesignerAttachedProperty(XamlMember xamlMember)
{
    return xamlMember.IsAttachable &&
        xamlMember.PreferredXamlNamespace.Equals(c_sapNamespaceURI, StringComparison.OrdinalIgnoreCase);
}

const String c_sapNamespaceURI = "http://schemas.microsoft.com/netfx/2009/xaml/activities/presentation";

// The next item of interest is the constructor, where the utilization of the inner XAML writer is seen.
public ViewStateCleaningWriter(XamlWriter innerWriter)
{
    this.InnerWriter = innerWriter;
    this.MemberStack = new Stack<XamlMember>();
}

XamlWriter InnerWriter {get; set; }
Stack<XamlMember> MemberStack {get; set; }
```

 <span data-ttu-id="0100b-117">另外，此操作还将创建在遍历节点流时使用的 XAML 成员的堆栈。</span><span class="sxs-lookup"><span data-stu-id="0100b-117">This also creates a stack of XAML members that are used while traversing the node stream.</span></span> <span data-ttu-id="0100b-118">此示例的剩余工作主要包含在<!--zz  <xref:System.Windows.Markup.XamlWriter.WriteStartMember%2A>-->`System.Windows.Markup.XamlWriter.WriteStartMember`方法。</span><span class="sxs-lookup"><span data-stu-id="0100b-118">The remaining work of this sample is largely contained in the <!--zz  <xref:System.Windows.Markup.XamlWriter.WriteStartMember%2A>--> `System.Windows.Markup.XamlWriter.WriteStartMember` method.</span></span>

```csharp
public override void WriteStartMember(XamlMember xamlMember)
{
    MemberStack.Push(xamlMember);

    if (IsDesignerAttachedProperty(xamlMember))
    {
        m_attachedPropertyDepth++;
    }

    if (m_attachedPropertyDepth > 0)
    {
        return;
    }

    InnerWriter.WriteStartMember(xamlMember);
}
```

 <span data-ttu-id="0100b-119">然后，后续方法将检查它们是否仍包含在视图状态容器中，如果是这样，则返回且不在编写器堆栈中向下传递节点。</span><span class="sxs-lookup"><span data-stu-id="0100b-119">Subsequent methods then check to see whether they are still contained in a view state container, and if so, return, and do not pass the node down the writer stack.</span></span>

```csharp
public override void WriteValue(Object value)
{
    if (m_attachedPropertyDepth > 0)
    {
        return;
    }

    InnerWriter.WriteValue(value);
}
```

 <span data-ttu-id="0100b-120">若要使用自定义 XAML 编写器，则必须在 XAML 编写器堆栈中将其链接起来。</span><span class="sxs-lookup"><span data-stu-id="0100b-120">To use a custom XAML writer, you must chain it together in a stack of XAML writers.</span></span> <span data-ttu-id="0100b-121">下面的代码演示如何执行此操作。</span><span class="sxs-lookup"><span data-stu-id="0100b-121">The following code shows how this can be used.</span></span>

```csharp
XmlWriterSettings writerSettings = new XmlWriterSettings {  Indent = true };
XmlWriter xmlWriter = XmlWriter.Create(File.OpenWrite(args[1]), writerSettings);
XamlXmlWriter xamlWriter = new XamlXmlWriter(xmlWriter, new XamlSchemaContext());
XamlServices.Save(new ViewStateCleaningWriter(ActivityXamlServices.CreateBuilderWriter(xamlWriter)), ab);
```

#### <a name="to-use-this-sample"></a><span data-ttu-id="0100b-122">使用此示例</span><span class="sxs-lookup"><span data-stu-id="0100b-122">To use this sample</span></span>

1. <span data-ttu-id="0100b-123">使用 Visual Studio 2010 打开 ViewStateCleaningWriter.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="0100b-123">Using Visual Studio 2010, open the ViewStateCleaningWriter.sln solution file.</span></span>

2. <span data-ttu-id="0100b-124">打开命令提示符，导航到生成 ViewStageCleaningWriter.exe 的目录。</span><span class="sxs-lookup"><span data-stu-id="0100b-124">Open a command prompt and navigate to the directory where the ViewStageCleaningWriter.exe is built.</span></span>

3. <span data-ttu-id="0100b-125">在 Workflow1.xaml 文件上运行 ViewStateCleaningWriter.exe。</span><span class="sxs-lookup"><span data-stu-id="0100b-125">Run ViewStateCleaningWriter.exe on the Workflow1.xaml file.</span></span>

   <span data-ttu-id="0100b-126">下面的示例演示了可执行文件的语法。</span><span class="sxs-lookup"><span data-stu-id="0100b-126">The syntax for the executable is shown in the following example.</span></span>

   ```console
   ViewStateCleaningWriter.exe [input file] [output file]
   ```

   <span data-ttu-id="0100b-127">这将输出到一个 XAML 文件\[outfile]，其中包含所有删除其视图状态信息。</span><span class="sxs-lookup"><span data-stu-id="0100b-127">This outputs a XAML file to \[outfile], which has all its view state information removed.</span></span>

> [!NOTE]
> <span data-ttu-id="0100b-128">已为 <xref:System.Activities.Statements.Sequence> 工作流移除大量虚拟化提示。</span><span class="sxs-lookup"><span data-stu-id="0100b-128">For a <xref:System.Activities.Statements.Sequence> workflow, a number of virtualization hints are removed.</span></span> <span data-ttu-id="0100b-129">这将导致设计器在下次加载时重新计算布局。</span><span class="sxs-lookup"><span data-stu-id="0100b-129">This causes the designer to recalculate layout the next time it is loaded.</span></span> <span data-ttu-id="0100b-130">在对 <xref:System.Activities.Statements.Flowchart> 使用此示例时，将移除所有定位和行路由信息，并且在后续加载到设计器中时，所有活动将在屏幕左侧堆叠。</span><span class="sxs-lookup"><span data-stu-id="0100b-130">When you use this sample for a <xref:System.Activities.Statements.Flowchart>, all positioning and line routing information are removed and on subsequent loading into the designer, all activities are stacked on the left side of the screen.</span></span>

#### <a name="to-create-a-sample-xaml-file-for-use-with-this-sample"></a><span data-ttu-id="0100b-131">创建与此示例一起使用的示例 XAML 文件</span><span class="sxs-lookup"><span data-stu-id="0100b-131">To create a sample XAML file for use with this sample</span></span>

1. <span data-ttu-id="0100b-132">打开 Visual Studio 2010。</span><span class="sxs-lookup"><span data-stu-id="0100b-132">Open Visual Studio 2010.</span></span>

2. <span data-ttu-id="0100b-133">创建新的工作流控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="0100b-133">Create a new Workflow Console Application.</span></span>

3. <span data-ttu-id="0100b-134">将几个活动拖放到画布上。</span><span class="sxs-lookup"><span data-stu-id="0100b-134">Drag and drop a few activities onto the canvas</span></span>

4. <span data-ttu-id="0100b-135">保存工作流 XAML 文件。</span><span class="sxs-lookup"><span data-stu-id="0100b-135">Save the workflow XAML file.</span></span>

5. <span data-ttu-id="0100b-136">检测 XAML 文件以查看视图状态附加属性。</span><span class="sxs-lookup"><span data-stu-id="0100b-136">Inspect the XAML file to see the view state attached properties.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0100b-137">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="0100b-137">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0100b-138">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="0100b-138">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="0100b-139">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="0100b-139">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0100b-140">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="0100b-140">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ViewStateCleaningWriter`

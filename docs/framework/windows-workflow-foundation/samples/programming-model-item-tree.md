---
title: 编程模型项树
ms.date: 03/30/2017
ms.assetid: 0229efde-19ac-4bdc-a187-c6227a7bd1a5
ms.openlocfilehash: efda69ac568b0ad9c5fdcf4d42722c5b7dadd3f3
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715669"
---
# <a name="programming-model-item-tree"></a><span data-ttu-id="5dded-102">编程模型项树</span><span class="sxs-lookup"><span data-stu-id="5dded-102">Programming Model Item Tree</span></span>
<span data-ttu-id="5dded-103">此示例演示如何使用 Windows Presentation Foundation （WPF）树视图中的声明性数据绑定导航 <xref:System.Activities.Presentation.Model.ModelItem> 树。</span><span class="sxs-lookup"><span data-stu-id="5dded-103">This sample demonstrates how to navigate the <xref:System.Activities.Presentation.Model.ModelItem> tree using declarative data binding from the Windows Presentation Foundation (WPF) Tree View.</span></span>

## <a name="sample-details"></a><span data-ttu-id="5dded-104">示例详细信息</span><span class="sxs-lookup"><span data-stu-id="5dded-104">Sample Details</span></span>
 <span data-ttu-id="5dded-105"><xref:System.Activities.Presentation.Model.ModelItem> 树是 Windows 工作流设计器基础结构用来公开有关正在编辑的基础实例的数据的抽象。</span><span class="sxs-lookup"><span data-stu-id="5dded-105">The <xref:System.Activities.Presentation.Model.ModelItem> tree is the abstraction that is used by the Windows Workflow Designer infrastructure to expose the data about the underlying instance being edited.</span></span> <span data-ttu-id="5dded-106">下图是工作流设计器中的基础结构的各层的描述。</span><span class="sxs-lookup"><span data-stu-id="5dded-106">The following illustration is a depiction of the various layers of infrastructure within the Workflow Designer.</span></span>

 ![显示工作流设计器的体系结构的关系图。](./media/programming-model-item-tree/workflow-designer-architecture.jpg)

 <span data-ttu-id="5dded-108"><xref:System.Activities.Presentation.Model.ModelItem> 包含一个指向基础值的指针和一个 <xref:System.Activities.Presentation.Model.ModelProperty> 对象的集合。</span><span class="sxs-lookup"><span data-stu-id="5dded-108">A <xref:System.Activities.Presentation.Model.ModelItem> consists of a pointer to the underlying value, as well as a collection of <xref:System.Activities.Presentation.Model.ModelProperty> objects.</span></span> <span data-ttu-id="5dded-109">反过来，<xref:System.Activities.Presentation.Model.ModelProperty> 对象又包含诸如属性的名称和类型这样的数据，而指向值的指针又是另一个 <xref:System.Activities.Presentation.Model.ModelItem>。</span><span class="sxs-lookup"><span data-stu-id="5dded-109">A <xref:System.Activities.Presentation.Model.ModelProperty> object in turn, consists of data such as the name and type of the property and then a pointer to the value, which in turn, is another <xref:System.Activities.Presentation.Model.ModelItem>.</span></span> <span data-ttu-id="5dded-110">值转换器用于操作从 <xref:System.Activities.Presentation.Model.ModelItem> 返回的某些 <xref:System.Activities.Presentation.Model.ModelProperty>，使它们在树视图中正确显示。</span><span class="sxs-lookup"><span data-stu-id="5dded-110">A value converter is used to manipulate some of the <xref:System.Activities.Presentation.Model.ModelItem>s returned from a <xref:System.Activities.Presentation.Model.ModelProperty> to make them appear correctly in the tree view.</span></span> <span data-ttu-id="5dded-111">然后，此示例演示如何使用命令性语法对 <xref:System.Activities.Presentation.Model.ModelItem> 树进行命令式编程，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="5dded-111">The sample then demonstrates how to imperatively program against the <xref:System.Activities.Presentation.Model.ModelItem> tree using the imperative syntax, as seen in the following example.</span></span>

```csharp
ModelItem mi = wd.Context.Services.GetService<ModelService>().Root;
ModelProperty mp = mi.Properties["Activities"];
mp.Collection.Add(new Persist());
ModelItem justAdded = mp.Collection.Last();
justAdded.Properties["DisplayName"].SetValue("new name");
```

#### <a name="to-use-this-sample"></a><span data-ttu-id="5dded-112">使用此示例</span><span class="sxs-lookup"><span data-stu-id="5dded-112">To use this sample</span></span>

1. <span data-ttu-id="5dded-113">在 Visual Studio 2010 中打开 ProgrammingModelItemTree 解决方案。</span><span class="sxs-lookup"><span data-stu-id="5dded-113">Open the ProgrammingModelItemTree.sln solution in Visual Studio 2010.</span></span>

2. <span data-ttu-id="5dded-114">通过从 "**生成**" 菜单中选择 "**生成解决方案**" 来生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="5dded-114">Build the solution by selecting **Build Solution** from the **Build** menu.</span></span>

3. <span data-ttu-id="5dded-115">按“F5”运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="5dded-115">Press F5 to run the application.</span></span> <span data-ttu-id="5dded-116">然后，将显示 WPF 窗体。</span><span class="sxs-lookup"><span data-stu-id="5dded-116">The WPF form is then displayed.</span></span>

4. <span data-ttu-id="5dded-117">单击 "**加载 WF** " 按钮加载 <xref:System.Activities.Presentation.Model.ModelItem> 并将其绑定到树视图。</span><span class="sxs-lookup"><span data-stu-id="5dded-117">Click the **Load WF** button to load the <xref:System.Activities.Presentation.Model.ModelItem> and bind it to the tree view.</span></span>

5. <span data-ttu-id="5dded-118">单击 "**更改模型项树**" 按钮执行前面的代码，以将一个项添加到树中并设置属性。</span><span class="sxs-lookup"><span data-stu-id="5dded-118">Clicking the **Change Model Item Tree** button executes the preceding code to add an item into the tree and set a property.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5dded-119">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="5dded-119">The samples may already be installed on your computer.</span></span> <span data-ttu-id="5dded-120">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="5dded-120">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="5dded-121">如果此目录不存在，请参阅[.NET Framework 4 的 Windows Communication Foundation （wcf）和 Windows Workflow Foundation （WF）示例](https://www.microsoft.com/download/details.aspx?id=21459)以下载所有 WINDOWS COMMUNICATION FOUNDATION （wcf）和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="5dded-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5dded-122">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="5dded-122">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ProgrammingModelItemTree`  
  
## <a name="see-also"></a><span data-ttu-id="5dded-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5dded-123">See also</span></span>

- <xref:System.Windows.Data.IValueConverter>

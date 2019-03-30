---
title: 编程模型项树
ms.date: 03/30/2017
ms.assetid: 0229efde-19ac-4bdc-a187-c6227a7bd1a5
ms.openlocfilehash: 428012cf483595a280ef70b488ed1f344474948a
ms.sourcegitcommit: 15ab532fd5e1f8073a4b678922d93b68b521bfa0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2019
ms.locfileid: "58653842"
---
# <a name="programming-model-item-tree"></a><span data-ttu-id="c7ea3-102">编程模型项树</span><span class="sxs-lookup"><span data-stu-id="c7ea3-102">Programming Model Item Tree</span></span>
<span data-ttu-id="c7ea3-103">此示例演示如何导航<xref:System.Activities.Presentation.Model.ModelItem>树使用的 Windows Presentation Foundation (WPF) 树视图中的声明性数据绑定。</span><span class="sxs-lookup"><span data-stu-id="c7ea3-103">This sample demonstrates how to navigate the <xref:System.Activities.Presentation.Model.ModelItem> tree using declarative data binding from the Windows Presentation Foundation (WPF) Tree View.</span></span>

## <a name="sample-details"></a><span data-ttu-id="c7ea3-104">示例详细信息</span><span class="sxs-lookup"><span data-stu-id="c7ea3-104">Sample Details</span></span>
 <span data-ttu-id="c7ea3-105"><xref:System.Activities.Presentation.Model.ModelItem> 树是 [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] 基础结构用来公开有关要编辑的基础实例的数据的抽象。</span><span class="sxs-lookup"><span data-stu-id="c7ea3-105">The <xref:System.Activities.Presentation.Model.ModelItem> tree is the abstraction that is used by the [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] infrastructure to expose the data about the underlying instance being edited.</span></span> <span data-ttu-id="c7ea3-106">下图描述了 [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)] 中的基础结构的各层。</span><span class="sxs-lookup"><span data-stu-id="c7ea3-106">The following illustration is a depiction of the various layers of infrastructure within the [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].</span></span>

 ![显示工作流设计器体系结构的关系图。](./media/programming-model-item-tree/workflow-designer-architecture.jpg)

 <span data-ttu-id="c7ea3-108"><xref:System.Activities.Presentation.Model.ModelItem> 包含一个指向基础值的指针和一个 <xref:System.Activities.Presentation.Model.ModelProperty> 对象的集合。</span><span class="sxs-lookup"><span data-stu-id="c7ea3-108">A <xref:System.Activities.Presentation.Model.ModelItem> consists of a pointer to the underlying value, as well as a collection of <xref:System.Activities.Presentation.Model.ModelProperty> objects.</span></span> <span data-ttu-id="c7ea3-109">反过来，<xref:System.Activities.Presentation.Model.ModelProperty> 对象又包含诸如属性的名称和类型这样的数据，而指向值的指针又是另一个 <xref:System.Activities.Presentation.Model.ModelItem>。</span><span class="sxs-lookup"><span data-stu-id="c7ea3-109">A <xref:System.Activities.Presentation.Model.ModelProperty> object in turn, consists of data such as the name and type of the property and then a pointer to the value, which in turn, is another <xref:System.Activities.Presentation.Model.ModelItem>.</span></span> <span data-ttu-id="c7ea3-110">值转换器用于操作从 <xref:System.Activities.Presentation.Model.ModelItem> 返回的某些 <xref:System.Activities.Presentation.Model.ModelProperty>，使它们在树视图中正确显示。</span><span class="sxs-lookup"><span data-stu-id="c7ea3-110">A value converter is used to manipulate some of the <xref:System.Activities.Presentation.Model.ModelItem>s returned from a <xref:System.Activities.Presentation.Model.ModelProperty> to make them appear correctly in the tree view.</span></span> <span data-ttu-id="c7ea3-111">然后，此示例演示如何使用命令性语法对 <xref:System.Activities.Presentation.Model.ModelItem> 树进行命令式编程，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="c7ea3-111">The sample then demonstrates how to imperatively program against the <xref:System.Activities.Presentation.Model.ModelItem> tree using the imperative syntax, as seen in the following example.</span></span>

```csharp
ModelItem mi = wd.Context.Services.GetService<ModelService>().Root;
ModelProperty mp = mi.Properties["Activities"];
mp.Collection.Add(new Persist());
ModelItem justAdded = mp.Collection.Last();
justAdded.Properties["DisplayName"].SetValue("new name");
```

#### <a name="to-use-this-sample"></a><span data-ttu-id="c7ea3-112">使用此示例</span><span class="sxs-lookup"><span data-stu-id="c7ea3-112">To use this sample</span></span>

1.  <span data-ttu-id="c7ea3-113">在 Visual Studio 2010 中打开 ProgrammingModelItemTree.sln 解决方案。</span><span class="sxs-lookup"><span data-stu-id="c7ea3-113">Open the ProgrammingModelItemTree.sln solution in Visual Studio 2010.</span></span>

2.  <span data-ttu-id="c7ea3-114">通过选择生成解决方案**生成解决方案**从**生成**菜单。</span><span class="sxs-lookup"><span data-stu-id="c7ea3-114">Build the solution by selecting **Build Solution** from the **Build** menu.</span></span>

3.  <span data-ttu-id="c7ea3-115">按 F5 运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="c7ea3-115">Press F5 to run the application.</span></span> <span data-ttu-id="c7ea3-116">这将显示 [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] 格式。</span><span class="sxs-lookup"><span data-stu-id="c7ea3-116">The [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] form is then displayed.</span></span>

4.  <span data-ttu-id="c7ea3-117">单击**加载 WF**按钮以加载<xref:System.Activities.Presentation.Model.ModelItem>并将其绑定到树视图。</span><span class="sxs-lookup"><span data-stu-id="c7ea3-117">Click the **Load WF** button to load the <xref:System.Activities.Presentation.Model.ModelItem> and bind it to the tree view.</span></span>

5.  <span data-ttu-id="c7ea3-118">单击**更改模型项树**按钮执行前面的代码，将项添加到树并设置一个属性。</span><span class="sxs-lookup"><span data-stu-id="c7ea3-118">Clicking the **Change Model Item Tree** button executes the preceding code to add an item into the tree and set a property.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="c7ea3-119">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="c7ea3-119">The samples may already be installed on your computer.</span></span> <span data-ttu-id="c7ea3-120">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="c7ea3-120">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="c7ea3-121">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="c7ea3-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c7ea3-122">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="c7ea3-122">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ProgrammingModelItemTree`  
  
## <a name="see-also"></a><span data-ttu-id="c7ea3-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="c7ea3-123">See also</span></span>
- <xref:System.Windows.Data.IValueConverter>

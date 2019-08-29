---
title: 编程模型项树
ms.date: 03/30/2017
ms.assetid: 0229efde-19ac-4bdc-a187-c6227a7bd1a5
ms.openlocfilehash: f2d89cb2a3b0f6167f043148ea793ec1c264a556
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2019
ms.locfileid: "70038176"
---
# <a name="programming-model-item-tree"></a>编程模型项树
此示例演示如何使用 "Windows Presentation Foundation <xref:System.Activities.Presentation.Model.ModelItem> (WPF)" 树视图中的声明性数据绑定导航树。

## <a name="sample-details"></a>示例详细信息
 <xref:System.Activities.Presentation.Model.ModelItem> 树是 [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] 基础结构用来公开有关要编辑的基础实例的数据的抽象。 下图描述了 [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)] 中的基础结构的各层。

 ![显示工作流设计器的体系结构的关系图。](./media/programming-model-item-tree/workflow-designer-architecture.jpg)

 <xref:System.Activities.Presentation.Model.ModelItem> 包含一个指向基础值的指针和一个 <xref:System.Activities.Presentation.Model.ModelProperty> 对象的集合。 反过来，<xref:System.Activities.Presentation.Model.ModelProperty> 对象又包含诸如属性的名称和类型这样的数据，而指向值的指针又是另一个 <xref:System.Activities.Presentation.Model.ModelItem>。 值转换器用于操作从 <xref:System.Activities.Presentation.Model.ModelItem> 返回的某些 <xref:System.Activities.Presentation.Model.ModelProperty>，使它们在树视图中正确显示。 然后，此示例演示如何使用命令性语法对 <xref:System.Activities.Presentation.Model.ModelItem> 树进行命令式编程，如下面的示例所示。

```csharp
ModelItem mi = wd.Context.Services.GetService<ModelService>().Root;
ModelProperty mp = mi.Properties["Activities"];
mp.Collection.Add(new Persist());
ModelItem justAdded = mp.Collection.Last();
justAdded.Properties["DisplayName"].SetValue("new name");
```

#### <a name="to-use-this-sample"></a>使用此示例

1. 在 Visual Studio 2010 中打开 ProgrammingModelItemTree 解决方案。

2. 通过从 "**生成**" 菜单中选择 "**生成解决方案**" 来生成解决方案。

3. 按 F5 运行该应用程序。 然后, 将显示 WPF 窗体。

4. 单击 "**负载 WF** " 按钮加载<xref:System.Activities.Presentation.Model.ModelItem> , 并将其绑定到树视图。

5. 单击 "**更改模型项树**" 按钮执行前面的代码, 以将一个项添加到树中并设置属性。

> [!IMPORTANT]
> 您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> 如果此目录不存在, 请参阅[.NET Framework 4 的 Windows Communication Foundation (wcf) 和 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)以下载所有 Windows Communication Foundation (wcf) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ProgrammingModelItemTree`  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Data.IValueConverter>

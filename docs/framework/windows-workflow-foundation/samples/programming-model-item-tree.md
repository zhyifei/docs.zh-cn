---
title: 编程模型项树
ms.date: 03/30/2017
ms.assetid: 0229efde-19ac-4bdc-a187-c6227a7bd1a5
ms.openlocfilehash: f14b140fdac95f3763cc5625841a725793876fa4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142688"
---
# <a name="programming-model-item-tree"></a>编程模型项树
此示例演示如何使用 Windows 演示文稿<xref:System.Activities.Presentation.Model.ModelItem>基础 （WPF） 树视图的声明性数据绑定导航树。

## <a name="sample-details"></a>示例详细信息
 树<xref:System.Activities.Presentation.Model.ModelItem>是 Windows 工作流设计器基础结构用于公开有关正在编辑的基础实例的数据的抽象。 下图描述了工作流设计器中的各种基础结构层。

 ![显示工作流设计器体系结构的图表。](./media/programming-model-item-tree/workflow-designer-architecture.jpg)

 <xref:System.Activities.Presentation.Model.ModelItem> 包含一个指向基础值的指针和一个 <xref:System.Activities.Presentation.Model.ModelProperty> 对象的集合。 反过来，<xref:System.Activities.Presentation.Model.ModelProperty> 对象又包含诸如属性的名称和类型这样的数据，而指向值的指针又是另一个 <xref:System.Activities.Presentation.Model.ModelItem>。 值转换器用于操作从 <xref:System.Activities.Presentation.Model.ModelItem> 返回的某些 <xref:System.Activities.Presentation.Model.ModelProperty>，使它们在树视图中正确显示。 然后，此示例演示如何使用命令性语法对 <xref:System.Activities.Presentation.Model.ModelItem> 树进行命令式编程，如下面的示例所示。

```csharp
ModelItem mi = wd.Context.Services.GetService<ModelService>().Root;
ModelProperty mp = mi.Properties["Activities"];
mp.Collection.Add(new Persist());
ModelItem justAdded = mp.Collection.Last();
justAdded.Properties["DisplayName"].SetValue("new name");
```

#### <a name="to-use-this-sample"></a>使用此示例

1. 在 Visual Studio 2010 中打开编程模型项目Tree.sln 解决方案。

2. 通过从 **"生成"** 菜单中选择**生成解决方案**来生成解决方案。

3. 按 F5 运行应用程序。 然后显示 WPF 窗体。

4. 单击 **"加载 WF"** 按钮以<xref:System.Activities.Presentation.Model.ModelItem>加载 并绑定到树视图。

5. 单击 **"更改模型项树"** 按钮将执行前面的代码，以将项添加到树中并设置属性。

> [!IMPORTANT]
> 您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> 如果此目录不存在，请转到[Windows 通信基础 （WCF） 和 Windows 工作流基础 （WF） 示例 .NET 框架 4](https://www.microsoft.com/download/details.aspx?id=21459)以下载[!INCLUDE[wf1](../../../../includes/wf1-md.md)]所有 Windows 通信基础 （WCF） 和示例。 此示例位于以下目录：  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ProgrammingModelItemTree`  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Data.IValueConverter>

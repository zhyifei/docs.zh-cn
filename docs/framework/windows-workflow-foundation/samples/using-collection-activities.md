---
title: 使用集合活动
ms.date: 03/30/2017
ms.assetid: e1977cf8-1695-4071-b946-7046fe39601e
ms.openlocfilehash: 3c30a7fb46d9b155ec645a7b6845715d808d63b6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="using-collection-activities"></a>使用集合活动
此示例演示如何将集合活动（<xref:System.Activities.Statements.AddToCollection%601>、<xref:System.Activities.Statements.ClearCollection%601>、<xref:System.Activities.Statements.ExistsInCollection%601> 和 <xref:System.Activities.Statements.RemoveFromCollection%601>）与实现 <xref:System.Collections.ICollection> 接口的类一起使用，以及如何创建一个自定义活动，该活动循环访问集合以输出集合中每个元素的内容。 命名为 `PrintCollection` 的自定义活动向控制台输出名为 `Numbers` 的集合的项成员。  
  
 下表描述了可提供工作流的集合操作的四个活动。  
  
|活动名称|描述|  
|-------------------|-----------------|  
|<xref:System.Activities.Statements.AddToCollection%601>|向集合中添加项。|  
|<xref:System.Activities.Statements.ClearCollection%601>|清除集合中的所有项。|  
|<xref:System.Activities.Statements.ExistsInCollection%601>|如果集合中存在指定项，则返回 `true`。|  
|<xref:System.Activities.Statements.RemoveFromCollection%601>|从集合中移除项。|  
  
 此示例包含两个解决方案，一个位于 CodedWorkflow 目录下，另一个位于 DesignerWorkflow 目录下。 它们演示了出于同一个目的使用活动的两种不同方式。  
  
|解决方案|描述|主要文件|  
|-|-|-|  
|CodedWorkflow|示例客户端应用程序，它演示如何以编程方式调用集合活动。|**PrintCollection.cs**： 用于向控制台输出集合中的每个项的帮助器活动。<br /><br /> **Program.cs**： 以编程方式生成一个顺序活动包含一系列集合活动，并执行它。|  
|DesignerWorkflow|示例客户端应用程序，它演示如何在工作流设计器中以声明方式使用集合活动。|**CollectionWorkflow.xaml**： 使用集合活动的设计器以声明方式创建工作流。<br /><br /> **PrintCollection.cs**： 用于向控制台输出集合中的每个项的帮助器活动。<br /><br /> **Program.cs**： 调用在 CollectionWorkflow.xaml 中描述的工作流。|  
  
 在此演示中，使用一个名为 `Numbers` 的自定义活动在控制台上输出 `PrintCollection` 集合的项成员。  
  
#### <a name="to-use-this-sample"></a>使用此示例  
  
1.  使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 Collection.sln 解决方案文件。  
  
2.  要生成解决方案，按 Ctrl+Shift+B。  
  
3.  若要运行解决方案，请按 Ctrl+F5。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Collection`
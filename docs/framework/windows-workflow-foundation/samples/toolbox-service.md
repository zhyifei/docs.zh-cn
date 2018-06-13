---
title: 工具箱服务
ms.date: 03/30/2017
ms.assetid: 742212d0-445e-41ed-9739-9ee848ce7f1b
ms.openlocfilehash: 0b3ea56d28d202bd8356fea1783b6675a708631d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33516186"
---
# <a name="toolbox-service"></a>工具箱服务
此示例演示如何根据工作流的上下文来更新 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 工具箱活动。 此示例包含一个工作流，此工作流基于是否选择了自定义活动来更改工具箱的内容。  
  
## <a name="discussion"></a>讨论  
 在工作流创作期间，客户通常希望他们的工具箱是上下文相关的。 例如，用户可能希望确保，在将特定活动添加到工作流时，工具箱会显示一些其他活动。 如果从工作流中移除这些活动，则工具箱应根据域要求做出相应的响应。  
  
 在重新承载的工作流设计器中，您可以控制工具箱控件并确保，主机会根据工作流中的模型更改，在工具箱控件中触发适当的更改。 但是，在 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 中，用户无法控制工具箱，因此需要一个接口来修改工具箱的内容。 `IActivityToolboxService` 正是这样一个接口。  
  
 该 API 提供以下四个方法。  
  
```  
public interface IActivityToolboxService   
{   
        void AddCategory(string categoryName);   
        void RemoveCategory(string categoryName);   
        void AddItem(string qualifiedTypeName, string categoryName);   
        void RemoveItem(string qualifiedTypeName, string categoryName);   
        IList<string> EnumCategories();   
        IList<string> EnumItems(string categoryName);   
}  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1.  使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 WorkflowSimulator.sln 解决方案文件。  
  
2.  按 Ctrl+Shift+B 生成解决方案。  
  
3.  打开 Workflow.xaml 文件。  
  
4.  添加**CustomActivity**通过拖放工具箱中。 请注意，调用的附加工具箱类别：**新 WF 类别**包含一个附加活动**分配**。  
  
5.  现在取消选择**CustomActivity**通过将另一个活动拖到它。  
  
6.  项**分配**类别中**新 WF 类别**现在移除工具箱下。 此外，由于该类别中没有剩下其他任何项，因此还将移除该类别。  
  
7.  选择**CustomActivity**再次和类别和**分配**活动添加回来。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\IActivityToolboxService`

---
title: 配置工作流服务中的序列化
ms.date: 03/30/2017
ms.assetid: aa70b290-a2ee-4c3c-90ea-d0a7665096ae
ms.openlocfilehash: f894f2e044e35bb278f975ef2385a6b22a8bea49
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185338"
---
# <a name="configuring-serialization-in-a-workflow-service"></a>配置工作流服务中的序列化
工作流服务是 Windows 通信基础 （WCF） 服务，因此可以选择使用<xref:System.Runtime.Serialization.DataContractSerializer>（默认） 或<xref:System.Xml.Serialization.XmlSerializer>。 编写非工作流服务时，将在服务或操作协定上指定要使用的序列化程序的类型。 创建 WCF 工作流服务时，您不会在代码中指定这些协定，而是在运行时通过协定推断生成这些协定。 有关协定推理的详细信息，请参阅[在工作流中使用协定](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md)。  序列化程序是使用 <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> 属性指定的。 这可在设计器中进行设置，如下图所示。  
  
 ![在属性窗口中设置序列化程序选项属性。](./media/configuring-serialization-in-a-workflow-service/setting-serializer-property.png)  
  
 序列化程序也可在代码中进行设置，如下面的示例所示。  
  
```csharp  
Receive approveExpense = new Receive  
            {  
                OperationName = "ApproveExpense",  
                CanCreateInstance = true,  
                ServiceContractName = "FinanceService",  
                SerializerOption = SerializerOption.DataContractSerializer,  
                Content = ReceiveContent.Create(new OutArgument<Expense>(expense))  
            };  
```  
  
  也可在工作流服务上指定已知类型。 有关已知类型的详细信息，请参阅[数据协定已知类型](data-contract-known-types.md)。 可在设计器或代码中指定已知类型。 要在设计器中指定已知类型，请单击 **"属性"窗口中**"已知类型"属性旁边的省略号按钮，了解<xref:System.ServiceModel.Activities.Receive>活动，如下图所示。
  
 !["已知类型"属性对话框的屏幕截图。](./media/configuring-serialization-in-a-workflow-service/known-types-properties.png)  
  
 这将显示允许您搜索和指定已知类型的类型集合编辑器。  
  
 ![类型集合编辑器的屏幕截图。](./media/configuring-serialization-in-a-workflow-service/type-collection-editor.gif)  
  
 单击"**添加新类型**"链接，然后使用下拉列表选择或搜索要添加到已知类型集合的类型。 若要在代码中指定已知类型，请使用 <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> 属性，如下面的示例所示。  
  
```csharp
Receive approveExpense = new Receive  
            {  
                OperationName = "ApproveExpense",  
                CanCreateInstance = true,  
                ServiceContractName = "FinanceService",  
                SerializerOption = SerializerOption.DataContractSerializer,  
                Content = ReceiveContent.Create(new OutArgument<Expense>(expense))  
            };  
            approveExpense.KnownTypes.Add(typeof(Travel));  
            approveExpense.KnownTypes.Add(typeof(Meal));  
```

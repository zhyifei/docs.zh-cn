---
title: 配置工作流服务中的序列化
ms.date: 03/30/2017
ms.assetid: aa70b290-a2ee-4c3c-90ea-d0a7665096ae
ms.openlocfilehash: 67d8807e5ff45db2e8662586861d969e14ceaa8d
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "48583683"
---
# <a name="configuring-serialization-in-a-workflow-service"></a>配置工作流服务中的序列化
工作流服务是 Windows Communication Foundation (WCF) 服务，因此可以选择是否使用任一<xref:System.Runtime.Serialization.DataContractSerializer>（默认值） 或<xref:System.Xml.Serialization.XmlSerializer>。 编写非工作流服务时，将在服务或操作协定上指定要使用的序列化程序的类型。 创建 WCF 工作流服务时未指定这些协定在代码中，但而不是它们在生成运行时通过协定推理。 有关协定推理的详细信息，请参阅[在工作流中使用协定](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md)。  序列化程序是使用 <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> 属性指定的。 这可在设计器中进行设置，如下图所示。  
  
 ![设置序列化程序](../../../../docs/framework/wcf/feature-details/media/settingserialzier.png "SettingSerialzier")  
  
 序列化程序也可在代码中进行设置，如下面的示例所示。  
  
```  
Receive approveExpense = new Receive  
            {  
                OperationName = "ApproveExpense",  
                CanCreateInstance = true,  
                ServiceContractName = "FinanceService",  
                SerializerOption = SerializerOption.DataContractSerializer,  
                Content = ReceiveContent.Create(new OutArgument<Expense>(expense))  
            };  
```  
  
 也可在工作流服务上指定已知类型。 有关已知类型的详细信息请参阅[Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)。 可在设计器或代码中指定已知类型。 若要在设计器中指定已知类型，请在属性窗口中单击 <xref:System.ServiceModel.Activities.Receive> 活动的 KnownTypes 属性旁边的省略号按钮，如下图所示。  
  
 ![KnownTypes 属性](../../../../docs/framework/wcf/feature-details/media/knowntypes.png "KnownTypes")  
  
 这将显示“类型集合编辑器”，您可以在其中搜索和指定已知类型。  
  
 ![添加已知的类型](../../../../docs/framework/wcf/feature-details/media/typecollectionseditor.gif "TypeCollectionsEditor")  
  
 单击**添加新类型**链接并使用下拉菜单选择或搜索某个类型将添加到已知的类型集合。 若要在代码中指定已知类型，请使用 <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> 属性，如下面的示例所示。  
  
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

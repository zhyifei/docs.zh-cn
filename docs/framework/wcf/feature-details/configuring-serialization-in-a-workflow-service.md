---
title: "配置工作流服务中的序列化"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aa70b290-a2ee-4c3c-90ea-d0a7665096ae
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 78f963f61c7ec67d6104a90c047ce78b0470568a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="configuring-serialization-in-a-workflow-service"></a>配置工作流服务中的序列化
工作流服务是 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 服务，因此可以选择使用 <xref:System.Runtime.Serialization.DataContractSerializer>（默认）或 <xref:System.Xml.Serialization.XmlSerializer>。 编写非工作流服务时，将在服务或操作协定上指定要使用的序列化程序的类型。 创建 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 工作流服务时，不会在代码中指定这些协定，而是在运行时通过协定推理生成这些协定。 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]协定推理，请参阅[工作流中使用协定](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md)。  序列化程序是使用 <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> 属性指定的。 这可在设计器中进行设置，如下图所示。  
  
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
  
 也可在工作流服务上指定已知类型。 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]已知类型，请参阅[数据协定已知类型](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)。 可在设计器或代码中指定已知类型。 若要在设计器中指定已知类型，请在属性窗口中单击 <xref:System.ServiceModel.Activities.Receive> 活动的 KnownTypes 属性旁边的省略号按钮，如下图所示。  
  
 ![KnownTypes 属性](../../../../docs/framework/wcf/feature-details/media/knowntypes.png "KnownTypes")  
  
 这将显示“类型集合编辑器”，您可以在其中搜索和指定已知类型。  
  
 ![添加已知的类型](../../../../docs/framework/wcf/feature-details/media/typecollectionseditor.gif "TypeCollectionsEditor")  
  
 单击**添加新类型**链接，并使用下拉菜单选择或搜索某个类型添加到已知的类型集合。 若要在代码中指定已知类型，请使用 <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> 属性，如下面的示例所示。  
  
```  
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
  
 若要查看完整的代码示例显示如何配置工作流服务的序列化请参阅[设置工作流服务中的消息格式](../../../../docs/framework/windows-workflow-foundation/samples/formatting-messages-in-workflow-services.md)。

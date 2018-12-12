---
title: 配置工作流服务中的序列化
ms.date: 03/30/2017
ms.assetid: aa70b290-a2ee-4c3c-90ea-d0a7665096ae
ms.openlocfilehash: 63a5860bd428fd4ce7fe01d7901427c85b2d5609
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53154107"
---
# <a name="configuring-serialization-in-a-workflow-service"></a><span data-ttu-id="cd69c-102">配置工作流服务中的序列化</span><span class="sxs-lookup"><span data-stu-id="cd69c-102">Configuring Serialization in a Workflow Service</span></span>
<span data-ttu-id="cd69c-103">工作流服务是 Windows Communication Foundation (WCF) 服务，因此可以选择是否使用任一<xref:System.Runtime.Serialization.DataContractSerializer>（默认值） 或<xref:System.Xml.Serialization.XmlSerializer>。</span><span class="sxs-lookup"><span data-stu-id="cd69c-103">Workflow services are Windows Communication Foundation (WCF) services and so have the option of using either the <xref:System.Runtime.Serialization.DataContractSerializer> (the default) or the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="cd69c-104">编写非工作流服务时，将在服务或操作协定上指定要使用的序列化程序的类型。</span><span class="sxs-lookup"><span data-stu-id="cd69c-104">When writing non-workflow services the type of serializer to use is specified on the service or operation contract.</span></span> <span data-ttu-id="cd69c-105">创建 WCF 工作流服务时未指定这些协定在代码中，但而不是它们在生成运行时通过协定推理。</span><span class="sxs-lookup"><span data-stu-id="cd69c-105">When creating WCF workflow services you don’t specify these contracts in code, but rather they are generated at runtime by contract inference.</span></span> <span data-ttu-id="cd69c-106">有关协定推理的详细信息，请参阅[在工作流中使用协定](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md)。</span><span class="sxs-lookup"><span data-stu-id="cd69c-106">For more information about contract inference, see  [Using Contracts in Workflow](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).</span></span>  <span data-ttu-id="cd69c-107">序列化程序是使用 <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> 属性指定的。</span><span class="sxs-lookup"><span data-stu-id="cd69c-107">The serializer is specified using the <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> property.</span></span> <span data-ttu-id="cd69c-108">这可在设计器中进行设置，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="cd69c-108">This can be set in the designer as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="cd69c-109">![设置序列化程序](../../../../docs/framework/wcf/feature-details/media/settingserialzier.png "SettingSerialzier")</span><span class="sxs-lookup"><span data-stu-id="cd69c-109">![Setting the serializer](../../../../docs/framework/wcf/feature-details/media/settingserialzier.png "SettingSerialzier")</span></span>  
  
 <span data-ttu-id="cd69c-110">序列化程序也可在代码中进行设置，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="cd69c-110">The serializer can also be set in code as shown in the following example,</span></span>  
  
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
  
 <span data-ttu-id="cd69c-111">也可在工作流服务上指定已知类型。</span><span class="sxs-lookup"><span data-stu-id="cd69c-111">Known types can be specified on Workflow services as well.</span></span> <span data-ttu-id="cd69c-112">有关已知类型的详细信息请参阅[Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)。</span><span class="sxs-lookup"><span data-stu-id="cd69c-112">For more information about Known Types see [Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md).</span></span> <span data-ttu-id="cd69c-113">可在设计器或代码中指定已知类型。</span><span class="sxs-lookup"><span data-stu-id="cd69c-113">Known types can be specified in the designer or in code.</span></span> <span data-ttu-id="cd69c-114">若要在设计器中指定已知类型，请在属性窗口中单击 <xref:System.ServiceModel.Activities.Receive> 活动的 KnownTypes 属性旁边的省略号按钮，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="cd69c-114">To specify known types in the designer, click the ellipsis button next to the KnownTypes property in the properties window for a <xref:System.ServiceModel.Activities.Receive> activity as shown in the following illustration.</span></span>  
  
 <span data-ttu-id="cd69c-115">![KnownTypes 属性](../../../../docs/framework/wcf/feature-details/media/knowntypes.png "KnownTypes")</span><span class="sxs-lookup"><span data-stu-id="cd69c-115">![KnownTypes property](../../../../docs/framework/wcf/feature-details/media/knowntypes.png "KnownTypes")</span></span>  
  
 <span data-ttu-id="cd69c-116">这将显示“类型集合编辑器”，您可以在其中搜索和指定已知类型。</span><span class="sxs-lookup"><span data-stu-id="cd69c-116">This will display the Type Collections Editor that will allow you to search for and specify known types.</span></span>  
  
 <span data-ttu-id="cd69c-117">![添加已知的类型](../../../../docs/framework/wcf/feature-details/media/typecollectionseditor.gif "TypeCollectionsEditor")</span><span class="sxs-lookup"><span data-stu-id="cd69c-117">![Adding Known Types](../../../../docs/framework/wcf/feature-details/media/typecollectionseditor.gif "TypeCollectionsEditor")</span></span>  
  
 <span data-ttu-id="cd69c-118">单击**添加新类型**链接并使用下拉菜单选择或搜索某个类型将添加到已知的类型集合。</span><span class="sxs-lookup"><span data-stu-id="cd69c-118">Click the **Add new type** link and use the drop down to select or search for a type to add to the known types collection.</span></span> <span data-ttu-id="cd69c-119">若要在代码中指定已知类型，请使用 <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> 属性，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="cd69c-119">To specify known types in code use the <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> property as shown in the following example.</span></span>  
  
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

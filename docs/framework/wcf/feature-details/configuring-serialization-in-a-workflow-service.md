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
# <a name="configuring-serialization-in-a-workflow-service"></a><span data-ttu-id="a161e-102">配置工作流服务中的序列化</span><span class="sxs-lookup"><span data-stu-id="a161e-102">Configuring Serialization in a Workflow Service</span></span>
<span data-ttu-id="a161e-103">工作流服务是 Windows 通信基础 （WCF） 服务，因此可以选择使用<xref:System.Runtime.Serialization.DataContractSerializer>（默认） 或<xref:System.Xml.Serialization.XmlSerializer>。</span><span class="sxs-lookup"><span data-stu-id="a161e-103">Workflow services are Windows Communication Foundation (WCF) services and so have the option of using either the <xref:System.Runtime.Serialization.DataContractSerializer> (the default) or the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="a161e-104">编写非工作流服务时，将在服务或操作协定上指定要使用的序列化程序的类型。</span><span class="sxs-lookup"><span data-stu-id="a161e-104">When writing non-workflow services the type of serializer to use is specified on the service or operation contract.</span></span> <span data-ttu-id="a161e-105">创建 WCF 工作流服务时，您不会在代码中指定这些协定，而是在运行时通过协定推断生成这些协定。</span><span class="sxs-lookup"><span data-stu-id="a161e-105">When creating WCF workflow services you don’t specify these contracts in code, but rather they are generated at runtime by contract inference.</span></span> <span data-ttu-id="a161e-106">有关协定推理的详细信息，请参阅[在工作流中使用协定](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md)。</span><span class="sxs-lookup"><span data-stu-id="a161e-106">For more information about contract inference, see  [Using Contracts in Workflow](../../../../docs/framework/wcf/feature-details/using-contracts-in-workflow.md).</span></span>  <span data-ttu-id="a161e-107">序列化程序是使用 <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> 属性指定的。</span><span class="sxs-lookup"><span data-stu-id="a161e-107">The serializer is specified using the <xref:System.ServiceModel.Activities.Receive.SerializerOption%2A> property.</span></span> <span data-ttu-id="a161e-108">这可在设计器中进行设置，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="a161e-108">This can be set in the designer as shown in the following illustration.</span></span>  
  
 ![在属性窗口中设置序列化程序选项属性。](./media/configuring-serialization-in-a-workflow-service/setting-serializer-property.png)  
  
 <span data-ttu-id="a161e-110">序列化程序也可在代码中进行设置，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="a161e-110">The serializer can also be set in code as shown in the following example,</span></span>  
  
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
  
  <span data-ttu-id="a161e-111">也可在工作流服务上指定已知类型。</span><span class="sxs-lookup"><span data-stu-id="a161e-111">Known types can be specified on Workflow services as well.</span></span> <span data-ttu-id="a161e-112">有关已知类型的详细信息，请参阅[数据协定已知类型](data-contract-known-types.md)。</span><span class="sxs-lookup"><span data-stu-id="a161e-112">For more information about Known Types, see [Data Contract Known Types](data-contract-known-types.md).</span></span> <span data-ttu-id="a161e-113">可在设计器或代码中指定已知类型。</span><span class="sxs-lookup"><span data-stu-id="a161e-113">Known types can be specified in the designer or in code.</span></span> <span data-ttu-id="a161e-114">要在设计器中指定已知类型，请单击 **"属性"窗口中**"已知类型"属性旁边的省略号按钮，了解<xref:System.ServiceModel.Activities.Receive>活动，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="a161e-114">To specify known types in the designer, click the ellipsis button next to the KnownTypes property in the **Properties Window** for a <xref:System.ServiceModel.Activities.Receive> activity as shown in the following illustration.</span></span>
  
 !["已知类型"属性对话框的屏幕截图。](./media/configuring-serialization-in-a-workflow-service/known-types-properties.png)  
  
 <span data-ttu-id="a161e-116">这将显示允许您搜索和指定已知类型的类型集合编辑器。</span><span class="sxs-lookup"><span data-stu-id="a161e-116">This displays the Type Collections Editor that allows you to search for and specify known types.</span></span>  
  
 ![类型集合编辑器的屏幕截图。](./media/configuring-serialization-in-a-workflow-service/type-collection-editor.gif)  
  
 <span data-ttu-id="a161e-118">单击"**添加新类型**"链接，然后使用下拉列表选择或搜索要添加到已知类型集合的类型。</span><span class="sxs-lookup"><span data-stu-id="a161e-118">Click the **Add new type** link and use the drop down to select or search for a type to add to the known types collection.</span></span> <span data-ttu-id="a161e-119">若要在代码中指定已知类型，请使用 <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> 属性，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="a161e-119">To specify known types in code use the <xref:System.ServiceModel.Activities.Receive.KnownTypes%2A> property as shown in the following example.</span></span>  
  
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

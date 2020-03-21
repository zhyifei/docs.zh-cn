---
title: 服务和事务
ms.date: 03/30/2017
helpviewer_keywords:
- service contracts [WCF], designing services and transactions
ms.assetid: 864813ff-2709-4376-912d-f5c8d318c460
ms.openlocfilehash: 4c59b83448f5a2c448843c12dae99c442441441f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143273"
---
# <a name="services-and-transactions"></a><span data-ttu-id="33b21-102">服务和事务</span><span class="sxs-lookup"><span data-stu-id="33b21-102">Services and Transactions</span></span>
<span data-ttu-id="33b21-103">Windows 通信基础 （WCF） 应用程序可以从客户端内部启动事务，并在服务操作中协调事务。</span><span class="sxs-lookup"><span data-stu-id="33b21-103">Windows Communication Foundation (WCF) applications can initiate a transaction from within a client and coordinate the transaction within the service operation.</span></span> <span data-ttu-id="33b21-104">客户端可以启动事务和调用多个服务操作，并可确保服务操作作为一个单元提交或回滚。</span><span class="sxs-lookup"><span data-stu-id="33b21-104">Clients can initiate a transaction and invoke several service operations and ensure that the service operations are either committed or rolled back as a single unit.</span></span>  
  
 <span data-ttu-id="33b21-105">通过为需要客户端事务的服务操作指定 <xref:System.ServiceModel.ServiceBehaviorAttribute> 并设置其 <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> 和 <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> 属性，可以启用服务协定中的事务行为。</span><span class="sxs-lookup"><span data-stu-id="33b21-105">You can enable the transaction behavior in the service contract by specifying a <xref:System.ServiceModel.ServiceBehaviorAttribute> and setting its <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> and <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> properties for service operations that require client transactions.</span></span> <span data-ttu-id="33b21-106"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> 参数指定在没有引发未处理异常的情况下，在其中执行方法的事务是否自动完成。</span><span class="sxs-lookup"><span data-stu-id="33b21-106">The <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> parameter specifies whether the transaction in which the method executes is automatically completed if no unhandled exceptions are thrown.</span></span> <span data-ttu-id="33b21-107">有关这些属性的详细信息，请参阅[服务模型事务属性](./feature-details/servicemodel-transaction-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="33b21-107">For more information about these attributes, see [ServiceModel Transaction Attributes](./feature-details/servicemodel-transaction-attributes.md).</span></span>  
  
 <span data-ttu-id="33b21-108">在服务操作中执行并由资源管理器管理的工作（如记录数据库更新）是客户端事务的一部分。</span><span class="sxs-lookup"><span data-stu-id="33b21-108">The work that is performed in the service operations and managed by a resource manager, such as logging database updates, is part of the client’s transaction.</span></span>  
  
 <span data-ttu-id="33b21-109">下面的示例演示如何使用 <xref:System.ServiceModel.ServiceBehaviorAttribute> 和 <xref:System.ServiceModel.OperationBehaviorAttribute> 属性来控制服务端的事务行为。</span><span class="sxs-lookup"><span data-stu-id="33b21-109">The following sample demonstrates usage of the <xref:System.ServiceModel.ServiceBehaviorAttribute> and <xref:System.ServiceModel.OperationBehaviorAttribute> attributes to control service-side transaction behavior.</span></span>  
  
```csharp
[ServiceBehavior(TransactionIsolationLevel = System.Transactions.IsolationLevel.Serializable)]  
public class CalculatorService: ICalculatorLog  
{  
    [OperationBehavior(TransactionScopeRequired = true,  
                           TransactionAutoComplete = true)]  
    public double Add(double n1, double n2)  
    {  
        recordToLog($"Added {n1} to {n2}");
        return n1 + n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,
                               TransactionAutoComplete = true)]  
    public double Subtract(double n1, double n2)  
    {  
        recordToLog($"Subtracted {n1} from {n2}");
        return n1 - n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,
                                       TransactionAutoComplete = true)]  
    public double Multiply(double n1, double n2)  
    {  
        recordToLog($"Multiplied {n1} by {n2}");
        return n1 * n2;  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,
                                       TransactionAutoComplete = true)]  
    public double Divide(double n1, double n2)  
    {  
        recordToLog($"Divided {n1} by {n2}", n1, n2);
        return n1 / n2;  
    }  
  
}  
```  
  
 <span data-ttu-id="33b21-110">您可以通过配置客户端和服务绑定来使用 WS-Atomic交易协议，并将[\<事务流>](../configure-apps/file-schema/wcf/transactionflow.md)元素设置为`true`，从而启用事务和事务流，如以下示例配置所示。</span><span class="sxs-lookup"><span data-stu-id="33b21-110">You can enable transactions and transaction flow by configuring the client and service bindings to use the WS-AtomicTransaction protocol, and setting the [\<transactionFlow>](../configure-apps/file-schema/wcf/transactionflow.md) element to `true`, as shown in the following sample configuration.</span></span>  
  
```xml  
<client>  
    <endpoint address="net.tcp://localhost/ServiceModelSamples/service"
          binding="netTcpBinding"
          bindingConfiguration="netTcpBindingWSAT"
          contract="Microsoft.ServiceModel.Samples.ICalculatorLog" />  
</client>  
  
<bindings>  
    <netTcpBinding>  
        <binding name="netTcpBindingWSAT"  
                transactionFlow="true"  
                transactionProtocol="WSAtomicTransactionOctober2004" />  
     </netTcpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="33b21-111">客户端可以通过创建 <xref:System.Transactions.TransactionScope>，然后在该事务范围内调用服务操作来开始该事务。</span><span class="sxs-lookup"><span data-stu-id="33b21-111">Clients can begin a transaction by creating a <xref:System.Transactions.TransactionScope> and invoking service operations within the scope of the transaction.</span></span>  
  
```csharp
using (TransactionScope ts = new TransactionScope(TransactionScopeOption.RequiresNew))  
{  
    //Do work here  
    ts.Complete();  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="33b21-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33b21-112">See also</span></span>

- [<span data-ttu-id="33b21-113">System.ServiceModel 中的事务性支持</span><span class="sxs-lookup"><span data-stu-id="33b21-113">Transactional Support in System.ServiceModel</span></span>](./feature-details/transactional-support-in-system-servicemodel.md)
- [<span data-ttu-id="33b21-114">事务模型</span><span class="sxs-lookup"><span data-stu-id="33b21-114">Transaction Models</span></span>](./feature-details/transaction-models.md)
- [<span data-ttu-id="33b21-115">WS 事务流</span><span class="sxs-lookup"><span data-stu-id="33b21-115">WS Transaction Flow</span></span>](./samples/ws-transaction-flow.md)

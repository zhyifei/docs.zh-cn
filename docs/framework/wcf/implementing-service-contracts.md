---
title: 实现服务协定
ms.date: 03/30/2017
helpviewer_keywords:
- implementing service contracts [WCF]
ms.assetid: aefb6f56-47e3-4f24-ab0a-9bc07bf9885f
ms.openlocfilehash: 4e6570291571815781ce543f5991ae40ed57d1e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33499370"
---
# <a name="implementing-service-contracts"></a><span data-ttu-id="a8bd5-102">实现服务协定</span><span class="sxs-lookup"><span data-stu-id="a8bd5-102">Implementing Service Contracts</span></span>
<span data-ttu-id="a8bd5-103">服务是一个类，会在一个或多个终结点公开客户端可用的功能。</span><span class="sxs-lookup"><span data-stu-id="a8bd5-103">A service is a class that exposes functionality available to clients at one or more endpoints.</span></span> <span data-ttu-id="a8bd5-104">若要创建服务时，编写实现 Windows Communication Foundation (WCF) 协定的类。</span><span class="sxs-lookup"><span data-stu-id="a8bd5-104">To create a service, write a class that implements a Windows Communication Foundation (WCF) contract.</span></span> <span data-ttu-id="a8bd5-105">可以通过两种方法执行此操作。</span><span class="sxs-lookup"><span data-stu-id="a8bd5-105">You can do this in one of two ways.</span></span> <span data-ttu-id="a8bd5-106">可以将协定单独定义为接口，然后创建一个实现该接口的类。</span><span class="sxs-lookup"><span data-stu-id="a8bd5-106">You can define the contract separately as an interface and then create a class that implements that interface.</span></span> <span data-ttu-id="a8bd5-107">或者，可以通过将 <xref:System.ServiceModel.ServiceContractAttribute> 属性放在该类本身，将 <xref:System.ServiceModel.OperationContractAttribute> 属性放在服务的客户端可用的方法上，来直接创建类和协定。</span><span class="sxs-lookup"><span data-stu-id="a8bd5-107">Alternatively, you can create the class and contract directly by placing the <xref:System.ServiceModel.ServiceContractAttribute> attribute on the class itself and the <xref:System.ServiceModel.OperationContractAttribute> attribute on the methods available to the clients of the service.</span></span>  
  
## <a name="creating-a-service-class"></a><span data-ttu-id="a8bd5-108">创建服务类</span><span class="sxs-lookup"><span data-stu-id="a8bd5-108">Creating a service class</span></span>  
 <span data-ttu-id="a8bd5-109">下面的示例是实现已单独定义的 `IMath` 协定的服务。</span><span class="sxs-lookup"><span data-stu-id="a8bd5-109">The following is an example of a service that implements an `IMath` contract that has been defined separately.</span></span>  
  
```csharp  
// Define the IMath contract.  
[ServiceContract]  
public interface IMath  
{  
    [OperationContract]   
    double Add(double A, double B);  
  
    [OperationContract]  
    double Multiply (double A, double B);  
}  
  
// Implement the IMath contract in the MathService class.  
public class MathService : IMath  
{  
    public double Add (double A, double B) { return A + B; }  
    public double Multiply (double A, double B) { return A * B; }  
}  
```  
  
 <span data-ttu-id="a8bd5-110">或者，服务可以直接公开协定。</span><span class="sxs-lookup"><span data-stu-id="a8bd5-110">Alternatively, a service can expose a contract directly.</span></span> <span data-ttu-id="a8bd5-111">下面的示例是定义和实现 `MathService` 协定的服务类。</span><span class="sxs-lookup"><span data-stu-id="a8bd5-111">The following is an example of a service class that defines and implements a `MathService` contract.</span></span>  
  
```csharp  
// Define the MathService contract directly on the service class.  
[ServiceContract]  
class MathService  
{  
    [OperationContract]  
    public double Add(double A, double B) { return A + B; }  
    [OperationContract]  
    private double Multiply (double A, double B) { return A * B; }  
}  
```  
  
 <span data-ttu-id="a8bd5-112">请注意，上面的服务公开不同的协定，因为协定名称是不同的。</span><span class="sxs-lookup"><span data-stu-id="a8bd5-112">Note that the preceding services expose different contracts because the contract names are different.</span></span> <span data-ttu-id="a8bd5-113">在第一个示例中，公开的协定命名为“`IMath`”，而在第二个示例中，协定命名为“`MathService`”。</span><span class="sxs-lookup"><span data-stu-id="a8bd5-113">In the first case, the exposed contract is named "`IMath`" while in the second case the contract is named "`MathService`".</span></span>  
  
 <span data-ttu-id="a8bd5-114">您可以在服务和操作实现级别设置一些配置，如并发性和实例化。</span><span class="sxs-lookup"><span data-stu-id="a8bd5-114">You can set a few things at the service and operation implementation levels, such as concurrency and instancing.</span></span> <span data-ttu-id="a8bd5-115">有关详细信息，请参阅[设计和实现服务](../../../docs/framework/wcf/designing-and-implementing-services.md)。</span><span class="sxs-lookup"><span data-stu-id="a8bd5-115">For more information, see [Designing and Implementing Services](../../../docs/framework/wcf/designing-and-implementing-services.md).</span></span>  
  
 <span data-ttu-id="a8bd5-116">在实现服务协定后，必须为该服务创建一个或多个终结点。</span><span class="sxs-lookup"><span data-stu-id="a8bd5-116">After implementing a service contract, you must create one or more endpoints for the service.</span></span> <span data-ttu-id="a8bd5-117">有关详细信息，请参阅[终结点创建概述](../../../docs/framework/wcf/endpoint-creation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="a8bd5-117">For more information, see [Endpoint Creation Overview](../../../docs/framework/wcf/endpoint-creation-overview.md).</span></span> <span data-ttu-id="a8bd5-118">有关如何运行服务的详细信息，请参阅[托管服务](../../../docs/framework/wcf/hosting-services.md)。</span><span class="sxs-lookup"><span data-stu-id="a8bd5-118">For more information about how to run a service, see [Hosting Services](../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8bd5-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="a8bd5-119">See Also</span></span>  
 [<span data-ttu-id="a8bd5-120">设计和实现服务</span><span class="sxs-lookup"><span data-stu-id="a8bd5-120">Designing and Implementing Services</span></span>](../../../docs/framework/wcf/designing-and-implementing-services.md)  
 [<span data-ttu-id="a8bd5-121">如何：使用协定类创建服务</span><span class="sxs-lookup"><span data-stu-id="a8bd5-121">How to: Create a Service with a Contract Class</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-wcf-contract-with-a-class.md)  
 [<span data-ttu-id="a8bd5-122">如何：使用协定接口创建服务</span><span class="sxs-lookup"><span data-stu-id="a8bd5-122">How to: Create a Service with a Contract Interface</span></span>](../../../docs/framework/wcf/feature-details/how-to-create-a-service-with-a-contract-interface.md)  
 [<span data-ttu-id="a8bd5-123">指定服务运行时行为</span><span class="sxs-lookup"><span data-stu-id="a8bd5-123">Specifying Service Run-Time Behavior</span></span>](../../../docs/framework/wcf/specifying-service-run-time-behavior.md)

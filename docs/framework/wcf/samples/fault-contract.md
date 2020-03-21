---
title: 错误协定
ms.date: 03/30/2017
ms.assetid: b31b140e-dc3b-408b-b3c7-10b6fe769725
ms.openlocfilehash: c8e93f73d150132c9d6750b81ba2ade944808d40
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183665"
---
# <a name="fault-contract"></a><span data-ttu-id="72d5f-102">错误协定</span><span class="sxs-lookup"><span data-stu-id="72d5f-102">Fault Contract</span></span>
<span data-ttu-id="72d5f-103">“错误协定”示例演示如何将错误信息从服务传达到客户端。</span><span class="sxs-lookup"><span data-stu-id="72d5f-103">The Fault Contract sample demonstrates how to communicate error information from a service to a client.</span></span> <span data-ttu-id="72d5f-104">该示例基于[入门](../../../../docs/framework/wcf/samples/getting-started-sample.md)，并将一些附加代码添加到服务中，以将内部异常转换为故障。</span><span class="sxs-lookup"><span data-stu-id="72d5f-104">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), with some additional code added to the service to convert an internal exception to a fault.</span></span> <span data-ttu-id="72d5f-105">客户端试图执行除数为零的运算以在服务上强制产生错误情况。</span><span class="sxs-lookup"><span data-stu-id="72d5f-105">The client attempts to perform division by zero to force an error condition on the service.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="72d5f-106">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="72d5f-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="72d5f-107">已将计算器协定修改为包括 <xref:System.ServiceModel.FaultContractAttribute>，如下面的示例代码所示。</span><span class="sxs-lookup"><span data-stu-id="72d5f-107">The calculator contract has been modified to include a <xref:System.ServiceModel.FaultContractAttribute> as shown in the following sample code.</span></span>  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    int Add(int n1, int n2);  
    [OperationContract]  
    int Subtract(int n1, int n2);  
    [OperationContract]  
    int Multiply(int n1, int n2);  
    [OperationContract]  
    [FaultContract(typeof(MathFault))]  
    int Divide(int n1, int n2);  
}  
```  
  
 <span data-ttu-id="72d5f-108"><xref:System.ServiceModel.FaultContractAttribute> 属性指示 `Divide` 运算可能返回一个 `MathFault` 类型的错误。</span><span class="sxs-lookup"><span data-stu-id="72d5f-108">The <xref:System.ServiceModel.FaultContractAttribute> attribute indicates that the `Divide` operation may return a fault of type `MathFault`.</span></span> <span data-ttu-id="72d5f-109">错误可以是可序列化的任何类型。</span><span class="sxs-lookup"><span data-stu-id="72d5f-109">A fault can be of any type that can be serialized.</span></span> <span data-ttu-id="72d5f-110">在本例中，`MathFault` 为数据协定，如下所示：</span><span class="sxs-lookup"><span data-stu-id="72d5f-110">In this case, the `MathFault` is a data contract, as follows:</span></span>  
  
```csharp
[DataContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public class MathFault  
{
    private string operation;  
    private string problemType;  
  
    [DataMember]  
    public string Operation  
    {  
        get { return operation; }  
        set { operation = value; }  
    }  
  
    [DataMember]
    public string ProblemType  
    {  
        get { return problemType; }  
        set { problemType = value; }  
    }  
}  
```  
  
 <span data-ttu-id="72d5f-111">如下面的示例代码所示，发生除数为零异常时，`Divide` 方法引发 <xref:System.ServiceModel.FaultException%601> 异常。</span><span class="sxs-lookup"><span data-stu-id="72d5f-111">The `Divide` method throws a <xref:System.ServiceModel.FaultException%601> exception when a divide by zero exception occurs as shown in the following sample code.</span></span> <span data-ttu-id="72d5f-112">此异常导致向客户端发送一个错误。</span><span class="sxs-lookup"><span data-stu-id="72d5f-112">This exception results in a fault being sent to the client.</span></span>  
  
```csharp
public int Divide(int n1, int n2)  
{  
    try  
    {  
        return n1 / n2;  
    }  
    catch (DivideByZeroException)  
    {  
        MathFault mf = new MathFault();  
        mf.operation = "division";  
        mf.problemType = "divide by zero";  
        throw new FaultException<MathFault>(mf);  
    }  
}  
```  
  
 <span data-ttu-id="72d5f-113">通过请求除数为零，客户端代码强制产生错误。</span><span class="sxs-lookup"><span data-stu-id="72d5f-113">The client code forces an error by requesting a division by zero.</span></span> <span data-ttu-id="72d5f-114">运行示例时，操作请求和响应将显示在客户端控制台窗口中。</span><span class="sxs-lookup"><span data-stu-id="72d5f-114">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="72d5f-115">您会看到将除数为零报告为错误。</span><span class="sxs-lookup"><span data-stu-id="72d5f-115">You see the division by zero being reported as a fault.</span></span> <span data-ttu-id="72d5f-116">在客户端窗口中按 Enter 可以关闭客户端。</span><span class="sxs-lookup"><span data-stu-id="72d5f-116">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Add(15,3) = 18  
Subtract(145,76) = 69  
Multiply(9,81) = 729  
FaultException<MathFault>: Math fault while doing division. Problem: divide by zero  
  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="72d5f-117">客户端通过捕获相应 `FaultException<MathFault>` 异常来完成此操作：</span><span class="sxs-lookup"><span data-stu-id="72d5f-117">The client does this by catching the appropriate `FaultException<MathFault>` exception:</span></span>  
  
```csharp
catch (FaultException<MathFault> e)  
{  
    Console.WriteLine("FaultException<MathFault>: Math fault while doing " + e.Detail.operation + ". Problem: " + e.Detail.problemType);  
    client.Abort();  
}  
```  
  
 <span data-ttu-id="72d5f-118">默认情况下，不可预期的异常的详细信息不发送到客户端，以防止服务实现的详细信息泄露出服务的安全边界。</span><span class="sxs-lookup"><span data-stu-id="72d5f-118">By default, the details of unexpected exceptions are not sent to the client to prevent details of the service implementation from escaping the secure boundary of the service.</span></span> <span data-ttu-id="72d5f-119">`FaultContract` 提供一种方法来描述协定中的故障并将某些类型的异常标记为适合传输到客户端。</span><span class="sxs-lookup"><span data-stu-id="72d5f-119">`FaultContract` provides a way to describe faults in a contract and mark certain types of exceptions as appropriate for transmission to the client.</span></span> <span data-ttu-id="72d5f-120">`FaultException<T>` 提供了用于向使用者发送故障的运行时机制。</span><span class="sxs-lookup"><span data-stu-id="72d5f-120">`FaultException<T>` provides the run-time mechanism for sending faults to consumers.</span></span>  
  
 <span data-ttu-id="72d5f-121">但是，在调试时查看服务失败的内部详细信息很有用。</span><span class="sxs-lookup"><span data-stu-id="72d5f-121">However, it is useful to see the internal details of a service failure when debugging.</span></span> <span data-ttu-id="72d5f-122">若要关闭上述安全行为，您可以指示在发送到客户端的错误中必须包括服务器上每个未处理的异常的详细信息。</span><span class="sxs-lookup"><span data-stu-id="72d5f-122">To turn off the secure behavior previously described, you can indicate that the details of every unhandled exception on the server should be included in the fault that is sent to the client.</span></span> <span data-ttu-id="72d5f-123">这是通过将 <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A> 设置为 `true` 来完成的。</span><span class="sxs-lookup"><span data-stu-id="72d5f-123">This is accomplished by setting <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A> to `true`.</span></span> <span data-ttu-id="72d5f-124">你可以在代码中或在配置中设置它，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="72d5f-124">You can either set it in code, or in configuration as shown in the following sample.</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <serviceMetadata httpGetEnabled="True"/>  
      <serviceDebug includeExceptionDetailInFaults="True" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="72d5f-125">此外，必须通过将配置文件中的服务`behaviorConfiguration`属性设置为"计算器服务行为"来与服务关联。</span><span class="sxs-lookup"><span data-stu-id="72d5f-125">Further, the behavior must be associated with the service by setting the `behaviorConfiguration` attribute of the service in the configuration file to "CalculatorServiceBehavior".</span></span>  
  
 <span data-ttu-id="72d5f-126">若要在客户端上捕获这样的错误，必须捕获非泛型 <xref:System.ServiceModel.FaultException>。</span><span class="sxs-lookup"><span data-stu-id="72d5f-126">To catch such faults on the client, the non-generic <xref:System.ServiceModel.FaultException> must be caught.</span></span>  
  
 <span data-ttu-id="72d5f-127">此行为仅用于调试目的，切勿在生产中启用它。</span><span class="sxs-lookup"><span data-stu-id="72d5f-127">This behavior should only be used for debugging purposes and should never be enabled in production.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="72d5f-128">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="72d5f-128">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="72d5f-129">确保已为 Windows[通信基础示例执行一次性设置过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="72d5f-129">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="72d5f-130">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="72d5f-130">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="72d5f-131">要在单机或跨计算机配置中运行示例，请按照[运行 Windows 通信基础示例中的](../../../../docs/framework/wcf/samples/running-the-samples.md)说明操作。</span><span class="sxs-lookup"><span data-stu-id="72d5f-131">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="72d5f-132">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="72d5f-132">The samples may already be installed on your machine.</span></span> <span data-ttu-id="72d5f-133">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="72d5f-133">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="72d5f-134">如果此目录不存在，请转到[Windows 通信基础 （WCF） 和 Windows 工作流基础 （WF） 示例 .NET 框架 4](https://www.microsoft.com/download/details.aspx?id=21459)以下载[!INCLUDE[wf1](../../../../includes/wf1-md.md)]所有 Windows 通信基础 （WCF） 和示例。</span><span class="sxs-lookup"><span data-stu-id="72d5f-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="72d5f-135">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="72d5f-135">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Faults`  

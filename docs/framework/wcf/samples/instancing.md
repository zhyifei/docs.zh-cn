---
title: "实例化"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service behaviors, instancing sample
- Instancing Sample [Windows Communication Foundation]
ms.assetid: c290fa54-f6ae-45a1-9186-d9504ebc6ee6
caps.latest.revision: "40"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ef9a87d8cfbf4070fd0b5108e093c6b9a4e9daa5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="instancing"></a>实例化
“实例化”示例演示实例化行为设置，此设置控制如何响应客户端请求来创建服务类的实例。 示例基于[入门](../../../../docs/framework/wcf/samples/getting-started-sample.md)，该类实现`ICalculator`服务协定。 本示例定义从 `ICalculatorInstance` 继承的新协定 `ICalculator`。 用 `ICalculatorInstance` 指定的协定提供了三个附加操作，用于检查服务实例的状态。 通过更改实例化设置，运行客户端时可以观察到行为中的更改。  
  
 在此示例中，客户端是一个控制台应用程序 (.exe)，服务是由 Internet 信息服务 (IIS) 承载的。  
  
> [!NOTE]
>  本主题的最后介绍了此示例的设置过程和生成说明。  
  
 可以使用下列实例化模式：  
  
-   <xref:System.ServiceModel.InstanceContextMode.PerCall>：为每个客户端请求创建一个新的服务实例。  
  
-   <xref:System.ServiceModel.InstanceContextMode.PerSession>：为每个新的客户端会话创建一个新的实例，并在该会话的生存期内对其进行维护（这需要能够支持会话的绑定）。  
  
-   <xref:System.ServiceModel.InstanceContextMode.Single>：服务类的单个实例处理应用程序生存期内的所有客户端请求。  
  
 服务类使用以下代码示例中显示的 `[ServiceBehavior(InstanceContextMode=<setting>)]` 属性来指定实例化行为。 通过更改注释掉的行，可以观察每个实例模式的行为。 更改实例化模式之后要记着重新生成服务。 没有要在客户端上指定的实例化相关设置。  
  
```  
// Enable one of the following instance modes to compare instancing behaviors.  
 [ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
  
// PerCall creates a new instance for each operation.  
//[ServiceBehavior(InstanceContextMode = InstanceContextMode.PerCall)]  
  
// Singleton creates a single instance for application lifetime.  
//[ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
public class CalculatorService : ICalculatorInstance  
{  
    static Object syncObject = new object();  
    static int instanceCount;  
    int instanceId;  
    int operationCount;  
  
    public CalculatorService()  
    {  
        lock (syncObject)  
        {  
            instanceCount++;  
            instanceId = instanceCount;  
        }  
    }  
  
    public double Add(double n1, double n2)  
    {  
        operationCount++;  
        return n1 + n2;  
    }  
  
    public double Subtract(double n1, double n2)  
    {  
        Interlocked.Increment(ref operationCount);  
        return n1 - n2;  
    }  
  
    public double Multiply(double n1, double n2)  
    {  
        Interlocked.Increment(ref operationCount);  
        return n1 * n2;  
    }  
  
    public double Divide(double n1, double n2)  
    {  
        Interlocked.Increment(ref operationCount);  
        return n1 / n2;  
    }  
  
    public string GetInstanceContextMode()  
    {   // Return the InstanceContextMode of the service  
        ServiceHost host = (ServiceHost)OperationContext.Current.Host;  
        ServiceBehaviorAttribute behavior = host.Description.Behaviors.Find<ServiceBehaviorAttribute>();  
        return behavior.InstanceContextMode.ToString();  
    }  
  
    public int GetInstanceId()  
    {   // Return the id for this instance  
        return instanceId;  
    }  
  
    public int GetOperationCount()  
    {   // Return the number of ICalculator operations performed   
        // on this instance  
        lock (syncObject)  
        {  
            return operationCount;  
        }  
    }  
}  
  
static void Main()  
{  
    // Create a client.  
    CalculatorInstanceClient client = new CalculatorInstanceClient();  
    string instanceMode = client.GetInstanceContextMode();  
    Console.WriteLine("InstanceContextMode: {0}", instanceMode);  
    DoCalculations(client);  
  
    // Create a second client.  
    CalculatorInstanceClient client2 = new CalculatorInstanceClient();  
  
    DoCalculations(client2);  
  
    Console.WriteLine();  
    Console.WriteLine("Press <ENTER> to terminate client.");  
    Console.ReadLine();  
}  
```  
  
 运行示例时，操作请求和响应将显示在客户端控制台窗口中。 会显示运行服务时所使用的实例模式。 执行每个操作后，显示实例 ID 和操作计数以反映实例化模式的行为。 在客户端窗口中按 Enter 可以关闭客户端。  
  
### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1.  确保已执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。  
  
2.  若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。  
  
3.  若要在单或跨计算机配置上运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Instancing`  
  
## <a name="see-also"></a>另请参阅

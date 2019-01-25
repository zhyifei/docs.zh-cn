---
title: Windows 消息安全
ms.date: 03/30/2017
helpviewer_keywords:
- WS Security
ms.assetid: d2221d1c-c9cb-48d1-b044-a3b4445c7f05
ms.openlocfilehash: a39d43084457d07a1b2064d80226c1186e42686a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54585167"
---
# <a name="message-security-windows"></a><span data-ttu-id="13b2c-102">Windows 消息安全</span><span class="sxs-lookup"><span data-stu-id="13b2c-102">Message Security Windows</span></span>
<span data-ttu-id="13b2c-103">本示例演示如何将 <xref:System.ServiceModel.WSHttpBinding> 绑定配置为使用具有 Windows 身份验证的消息级安全性。</span><span class="sxs-lookup"><span data-stu-id="13b2c-103">This sample demonstrates how to configure a <xref:System.ServiceModel.WSHttpBinding> binding to use message-level security with Windows authentication.</span></span> <span data-ttu-id="13b2c-104">此示例基于[Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="13b2c-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="13b2c-105">在此示例中，服务由 Internet 信息服务 (IIS) 承载，客户端是一个控制台应用程序 (.exe)。</span><span class="sxs-lookup"><span data-stu-id="13b2c-105">In this sample, the service is hosted in Internet Information Services (IIS) and the client is a console application (.exe).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13b2c-106">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="13b2c-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="13b2c-107">默认安全设置[ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)是使用 Windows 身份验证的消息安全。</span><span class="sxs-lookup"><span data-stu-id="13b2c-107">The default security for the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) is message security using Windows authentication.</span></span> <span data-ttu-id="13b2c-108">此示例中的配置文件显式设置`mode`的属性[\<安全 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)到`Message`并`clientCredentialType`属性为`Windows`。</span><span class="sxs-lookup"><span data-stu-id="13b2c-108">The configuration files in this sample explicitly set the `mode` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) to `Message` and the `clientCredentialType` attribute to `Windows`.</span></span> <span data-ttu-id="13b2c-109">这些值是此绑定的默认值，但为了演示其用法，已对这些值进行了显式配置，如下面的示例配置所示。</span><span class="sxs-lookup"><span data-stu-id="13b2c-109">These values are the default values for this binding, but they have been explicitly configured, as shown in the following sample configuration to demonstrate their use.</span></span>  
  
```xml  
<bindings>  
    <wsHttpBinding>  
        <binding>  
            <security mode="Message">  
                <message clientCredentialType="Windows"/>  
            </security>  
        </binding>  
    </wsHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="13b2c-110">客户端终结点配置由服务终结点的绝对地址、绑定和协定组成。</span><span class="sxs-lookup"><span data-stu-id="13b2c-110">The client endpoint configuration consists of an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="13b2c-111">该客户端绑定是使用相应的 `securityMode` 和 `authenticationMode` 配置的。</span><span class="sxs-lookup"><span data-stu-id="13b2c-111">The client binding is configured with the appropriate `securityMode` and `authenticationMode`.</span></span>  
  
```xml  
<system.serviceModel>  
  <client>  
    <endpoint address=  
            "http://localhost/servicemodelsamples/service.svc"   
            binding="wsHttpBinding"   
            bindingConfiguration="Binding1"   
            contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  </client>  
  
  <bindings>  
    <wsHttpBinding>  
      <!-- The default security for the WSHttpBinding is -->  
      <!-- Message security using Windows authentication. -->  
      <!-- This configuration explicitly defines the security mode -->  
      <!-- as Message and the clientCredentialType as Windows -->  
      <!-- for demonstration purposes. -->  
      <binding name="Binding1">  
        <security mode="Message">  
          <message clientCredentialType="Windows"/>  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="13b2c-112">为了演示如何使用 <xref:System.ServiceModel.OperationContext.ServiceSecurityContext%2A> 来访问调用方的标识，服务源代码已进行了修改。</span><span class="sxs-lookup"><span data-stu-id="13b2c-112">The service source code has been modified to demonstrate how the <xref:System.ServiceModel.OperationContext.ServiceSecurityContext%2A> can be used to access the identity of the caller.</span></span>  

```csharp
public string GetCallerIdentity()  
{  
    // The Windows identity of the caller can be accessed on the ServiceSecurityContext.WindowsIdentity.  
    return OperationContext.Current.ServiceSecurityContext.WindowsIdentity.Name;  
}  
```

 <span data-ttu-id="13b2c-113">运行示例时，操作请求和响应将显示在客户端控制台窗口中。</span><span class="sxs-lookup"><span data-stu-id="13b2c-113">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="13b2c-114">调用的第一个方法 `GetCallerIdentity` 将调用方标识的名称返回给客户端。</span><span class="sxs-lookup"><span data-stu-id="13b2c-114">The first method called - `GetCallerIdentity` - returns the name of the caller identity back to the client.</span></span> <span data-ttu-id="13b2c-115">在控制台窗口中按 Enter 可以关闭客户端。</span><span class="sxs-lookup"><span data-stu-id="13b2c-115">Press ENTER in the console window to shut down the client.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="13b2c-116">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="13b2c-116">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="13b2c-117">请确保您具有执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="13b2c-117">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="13b2c-118">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="13b2c-118">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="13b2c-119">若要在单或跨计算机配置中运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="13b2c-119">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13b2c-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="13b2c-120">See also</span></span>

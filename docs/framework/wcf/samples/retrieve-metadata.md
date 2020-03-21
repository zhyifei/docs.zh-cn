---
title: 检索元数据
ms.date: 03/30/2017
ms.assetid: e8a6ef8c-a195-495a-a15e-7d92bdf0b28c
ms.openlocfilehash: 9b1adf4ed2a09625ca19016f531936002fff757d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183391"
---
# <a name="retrieve-metadata"></a>检索元数据
本示例演示如何实现一个客户端，它能从服务中动态检索元数据以选择用来通信的终结点。 此示例基于[入门](../../../../docs/framework/wcf/samples/getting-started-sample.md)。 已修改服务以公开两个终结点：使用`basicHttpBinding`绑定在基地址的终结点，以及使用`wsHttpBinding`绑定在 [*基地址*]/安全处的安全终结点。 不必使用终结点地址和绑定配置客户端，客户端可以使用 <xref:System.ServiceModel.Description.MetadataExchangeClient> 类动态检索服务的元数据，然后使用 <xref:System.ServiceModel.Description.ServiceEndpointCollection> 类以 <xref:System.ServiceModel.Description.WsdlImporter> 的形式导入元数据。  
  
> [!NOTE]
> 本主题的最后介绍了此示例的设置过程和生成说明。  
  
 客户端应用程序使用导入的 <xref:System.ServiceModel.Description.ServiceEndpointCollection> 来创建与服务通信的客户端。 客户端应用程序会遍历每个检索到的终结点并与每个实现 `ICalculator` 协定的终结点通信。 会为相应的地址和绑定提供检索到的终结点，以便将客户端配置成可与每个终结点通信，如下面的示例代码所示。  
  
```csharp
// Create a MetadataExchangeClient for retrieving metadata.  
EndpointAddress mexAddress = new EndpointAddress(ConfigurationManager.AppSettings["mexAddress"]);  
MetadataExchangeClient mexClient = new MetadataExchangeClient(mexAddress);  
  
// Retrieve the metadata for all endpoints using metadata exchange protocol (mex).  
MetadataSet metadataSet = mexClient.GetMetadata();  
  
//Convert the metadata into endpoints.  
WsdlImporter importer = new WsdlImporter(metadataSet);  
ServiceEndpointCollection endpoints = importer.ImportAllEndpoints();  
  
CalculatorClient client = null;  
ContractDescription contract = ContractDescription.GetContract(typeof(ICalculator));  
// Communicate with each endpoint that supports the ICalculator contract.  
foreach (ServiceEndpoint ep in endpoints)  
{  
    if (ep.Contract.Namespace.Equals(contract.Namespace) && ep.Contract.Name.Equals(contract.Name))  
    {  
        // Create a client using the endpoint address and binding.  
        client = new CalculatorClient(ep.Binding, new EndpointAddress(ep.Address.Uri));  
        Console.WriteLine("Communicate with endpoint: ");  
        Console.WriteLine("   AddressPath={0}", ep.Address.Uri.PathAndQuery);  
        Console.WriteLine("   Binding={0}", ep.Binding.Name);  
        // Call operations.  
        DoCalculations(client);  
  
        //Closing the client gracefully closes the connection and cleans up resources.  
        client.Close();  
    }  
}  
```  
  
 客户端控制台窗口将显示发送到每个终结点的操作，同时显示地址路径和绑定名称。  
  
### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1. 确保已为 Windows[通信基础示例执行一次性设置过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。  
  
2. 要生成解决方案的 C#、C++ 或 Visual Basic .NET 版本，请按照[生成 Windows 通信基础示例](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明操作。  
  
3. 要在单机或跨计算机配置中运行示例，请按照[运行 Windows 通信基础示例中的](../../../../docs/framework/wcf/samples/running-the-samples.md)说明操作。  
  
> [!IMPORTANT]
> 您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> 如果此目录不存在，请转到[Windows 通信基础 （WCF） 和 Windows 工作流基础 （WF） 示例 .NET 框架 4](https://www.microsoft.com/download/details.aspx?id=21459)以下载[!INCLUDE[wf1](../../../../includes/wf1-md.md)]所有 Windows 通信基础 （WCF） 和示例。 此示例位于以下目录：  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\RetrieveMetadata`  

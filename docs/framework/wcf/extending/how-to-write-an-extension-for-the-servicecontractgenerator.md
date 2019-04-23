---
title: 如何：编写 ServiceContractGenerator 的扩展
ms.date: 03/30/2017
ms.assetid: 876ca823-bd16-4bdf-9e0f-02092df90e51
ms.openlocfilehash: c9e10efccf0d51e6b78aace1296d227a78a9f91d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59340615"
---
# <a name="how-to-write-an-extension-for-the-servicecontractgenerator"></a><span data-ttu-id="89c9a-102">如何：编写 ServiceContractGenerator 的扩展</span><span class="sxs-lookup"><span data-stu-id="89c9a-102">How to: Write an Extension for the ServiceContractGenerator</span></span>
<span data-ttu-id="89c9a-103">本主题描述如何编写 <xref:System.ServiceModel.Description.ServiceContractGenerator> 的扩展。</span><span class="sxs-lookup"><span data-stu-id="89c9a-103">This topic describes how to write an extension for the <xref:System.ServiceModel.Description.ServiceContractGenerator>.</span></span> <span data-ttu-id="89c9a-104">这可以通过对操作行为实现 <xref:System.ServiceModel.Description.IOperationContractGenerationExtension> 接口或者对协定行为实现 <xref:System.ServiceModel.Description.IServiceContractGenerationExtension> 接口来完成。</span><span class="sxs-lookup"><span data-stu-id="89c9a-104">This can be done by implementing the <xref:System.ServiceModel.Description.IOperationContractGenerationExtension> interface on an operation behavior or implementing the <xref:System.ServiceModel.Description.IServiceContractGenerationExtension> interface on a contract behavior.</span></span> <span data-ttu-id="89c9a-105">本主题演示如何对协定行为实现 <xref:System.ServiceModel.Description.IServiceContractGenerationExtension> 接口。</span><span class="sxs-lookup"><span data-stu-id="89c9a-105">This topic shows how to implement the <xref:System.ServiceModel.Description.IServiceContractGenerationExtension> interface on a contract behavior.</span></span>  
  
 <span data-ttu-id="89c9a-106"><xref:System.ServiceModel.Description.ServiceContractGenerator> 从 <xref:System.ServiceModel.Description.ServiceEndpoint>、<xref:System.ServiceModel.Description.ContractDescription> 和 <xref:System.ServiceModel.Channels.Binding> 实例生成服务协定、客户端类型和客户端配置。</span><span class="sxs-lookup"><span data-stu-id="89c9a-106">The <xref:System.ServiceModel.Description.ServiceContractGenerator> generates service contracts, client types, and client configurations from <xref:System.ServiceModel.Description.ServiceEndpoint>, <xref:System.ServiceModel.Description.ContractDescription>, and <xref:System.ServiceModel.Channels.Binding> instances.</span></span> <span data-ttu-id="89c9a-107">通常，需要先从服务元数据导入 <xref:System.ServiceModel.Description.ServiceEndpoint>、<xref:System.ServiceModel.Description.ContractDescription> 和 <xref:System.ServiceModel.Channels.Binding> 实例，然后使用这些实例生成调用服务的代码。</span><span class="sxs-lookup"><span data-stu-id="89c9a-107">Typically, you import <xref:System.ServiceModel.Description.ServiceEndpoint>, <xref:System.ServiceModel.Description.ContractDescription>, and <xref:System.ServiceModel.Channels.Binding> instances from service metadata and then use these instances to generate code to call the service.</span></span> <span data-ttu-id="89c9a-108">在本示例中，<xref:System.ServiceModel.Description.IWsdlImportExtension> 实现用于处理 WSDL 批注，然后将代码生成扩展添加到导入的协定中，以生成对已生成代码的注释。</span><span class="sxs-lookup"><span data-stu-id="89c9a-108">In this example, an <xref:System.ServiceModel.Description.IWsdlImportExtension> implementation is used to process WSDL annotations and then add code generation extensions to the imported contracts to generate comments on the generated code.</span></span>  
  
### <a name="to-write-an-extension-for-the-servicecontractgenerator"></a><span data-ttu-id="89c9a-109">编写 ServiceContractGenerator 的扩展</span><span class="sxs-lookup"><span data-stu-id="89c9a-109">To write an extension for the ServiceContractGenerator</span></span>  
  
1. <span data-ttu-id="89c9a-110">实现 <xref:System.ServiceModel.Description.IServiceContractGenerationExtension>。</span><span class="sxs-lookup"><span data-stu-id="89c9a-110">Implement <xref:System.ServiceModel.Description.IServiceContractGenerationExtension>.</span></span> <span data-ttu-id="89c9a-111">若要修改已生成的服务协定，请使用传入 <xref:System.ServiceModel.Description.ServiceContractGenerationContext> 方法的 <xref:System.ServiceModel.Description.IServiceContractGenerationExtension.GenerateContract%28System.ServiceModel.Description.ServiceContractGenerationContext%29> 实例。</span><span class="sxs-lookup"><span data-stu-id="89c9a-111">To modify the generated service contract, use the <xref:System.ServiceModel.Description.ServiceContractGenerationContext> instance passed into the <xref:System.ServiceModel.Description.IServiceContractGenerationExtension.GenerateContract%28System.ServiceModel.Description.ServiceContractGenerationContext%29> method.</span></span>  
  
    ```  
    public void GenerateContract(ServiceContractGenerationContext context)  
    {  
        Console.WriteLine("In generate contract.");  
    context.ContractType.Comments.AddRange(Formatter.FormatComments(commentText));  
    }  
    ```  
  
2. <span data-ttu-id="89c9a-112">在同一个类上实现 <xref:System.ServiceModel.Description.IWsdlImportExtension>。</span><span class="sxs-lookup"><span data-stu-id="89c9a-112">Implement <xref:System.ServiceModel.Description.IWsdlImportExtension> on the same class.</span></span> <span data-ttu-id="89c9a-113">通过将代码生成扩展添加到导入的 <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> 实例，<xref:System.ServiceModel.Description.ContractDescription> 方法可以处理特定的 WSDL 扩展（此例中为 WSDL 批注）。</span><span class="sxs-lookup"><span data-stu-id="89c9a-113">The <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> method can process a specific WSDL extension (WSDL annotations in this case) by adding a code generation extension to the imported <xref:System.ServiceModel.Description.ContractDescription> instance.</span></span>  
  
    ```  
    public void ImportContract(WsdlImporter importer, WsdlContractConversionContext context)  
       {  
                // Contract documentation  
             if (context.WsdlPortType.Documentation != null)  
             {  
                    context.Contract.Behaviors.Add(new WsdlDocumentationImporter(context.WsdlPortType.Documentation));  
             }  
             // Operation documentation  
             foreach (Operation operation in context.WsdlPortType.Operations)  
             {  
                if (operation.Documentation != null)  
                {  
                   OperationDescription operationDescription = context.Contract.Operations.Find(operation.Name);  
                   if (operationDescription != null)  
                   {  
                            operationDescription.Behaviors.Add(new WsdlDocumentationImporter(operation.Documentation));  
                   }  
                }  
             }  
          }  
          public void BeforeImport(ServiceDescriptionCollection wsdlDocuments, XmlSchemaSet xmlSchemas, ICollection<XmlElement> policy)   
            {  
                Console.WriteLine("BeforeImport called.");  
            }  
  
          public void ImportEndpoint(WsdlImporter importer, WsdlEndpointConversionContext context)   
            {  
                Console.WriteLine("ImportEndpoint called.");  
            }  
    ```  
  
3. <span data-ttu-id="89c9a-114">将 WSDL 导入程序添加到客户端配置中。</span><span class="sxs-lookup"><span data-stu-id="89c9a-114">Add the WSDL importer to your client configuration.</span></span>  
  
    ```xml  
    <metadata>  
      <wsdlImporters>  
        <extension type="Microsoft.WCF.Documentation.WsdlDocumentationImporter, WsdlDocumentation" />  
      </wsdlImporters>  
    </metadata>  
    ```  
  
4. <span data-ttu-id="89c9a-115">在客户端代码中，创建一个 `MetadataExchangeClient` 并调用 `GetMetadata`。</span><span class="sxs-lookup"><span data-stu-id="89c9a-115">In the client code, create a `MetadataExchangeClient` and call `GetMetadata`.</span></span>  
  
    ```  
    MetadataExchangeClient mexClient = new MetadataExchangeClient(metadataAddress);  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet metaDocs = mexClient.GetMetadata();  
    ```  
  
5. <span data-ttu-id="89c9a-116">创建一个 `WsdlImporter` 并调用 `ImportAllContracts`。</span><span class="sxs-lookup"><span data-stu-id="89c9a-116">Create a `WsdlImporter` and call `ImportAllContracts`.</span></span>  
  
    ```  
    WsdlImporter importer = new WsdlImporter(metaDocs);            System.Collections.ObjectModel.Collection<ContractDescription> contracts = importer.ImportAllContracts();  
    ```  
  
6. <span data-ttu-id="89c9a-117">创建一个 `ServiceContractGenerator` 并为每个协定调用 `GenerateServiceContractType`。</span><span class="sxs-lookup"><span data-stu-id="89c9a-117">Create a `ServiceContractGenerator` and call `GenerateServiceContractType` for each contract.</span></span>  
  
    ```  
    ServiceContractGenerator generator = new ServiceContractGenerator();  
    foreach (ContractDescription contract in contracts)  
    {  
       generator.GenerateServiceContractType(contract);  
    }  
    if (generator.Errors.Count != 0)  
       throw new Exception("There were errors during code compilation.");  
    ```  
  
7. <span data-ttu-id="89c9a-118">会为实现 <xref:System.ServiceModel.Description.IServiceContractGenerationExtension.GenerateContract%28System.ServiceModel.Description.ServiceContractGenerationContext%29> 的给定协定上的每个协定行为自动调用 <xref:System.ServiceModel.Description.IServiceContractGenerationExtension>。</span><span class="sxs-lookup"><span data-stu-id="89c9a-118"><xref:System.ServiceModel.Description.IServiceContractGenerationExtension.GenerateContract%28System.ServiceModel.Description.ServiceContractGenerationContext%29> is called automatically for each contract behavior on a given contract that implements <xref:System.ServiceModel.Description.IServiceContractGenerationExtension>.</span></span> <span data-ttu-id="89c9a-119">然后，此方法可以修改传入的 <xref:System.ServiceModel.Description.ServiceContractGenerationContext>。</span><span class="sxs-lookup"><span data-stu-id="89c9a-119">This method can then modify the <xref:System.ServiceModel.Description.ServiceContractGenerationContext> passed in.</span></span> <span data-ttu-id="89c9a-120">在此示例中，添加了注释。</span><span class="sxs-lookup"><span data-stu-id="89c9a-120">In this example comments are added.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89c9a-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="89c9a-121">See also</span></span>

- [<span data-ttu-id="89c9a-122">元数据</span><span class="sxs-lookup"><span data-stu-id="89c9a-122">Metadata</span></span>](../../../../docs/framework/wcf/feature-details/metadata.md)
- [<span data-ttu-id="89c9a-123">如何：导入自定义 WSDL</span><span class="sxs-lookup"><span data-stu-id="89c9a-123">How to: Import Custom WSDL</span></span>](../../../../docs/framework/wcf/extending/how-to-import-custom-wsdl.md)

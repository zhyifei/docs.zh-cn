---
title: 如何：导入自定义 WSDL
ms.date: 03/30/2017
ms.assetid: ddc3718d-ce60-44f6-92af-a5c67477dd99
ms.openlocfilehash: d9a4609f08a95bbecca81aa6667102a0e4a73c67
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61767073"
---
# <a name="how-to-import-custom-wsdl"></a><span data-ttu-id="728a5-102">如何：导入自定义 WSDL</span><span class="sxs-lookup"><span data-stu-id="728a5-102">How to: Import Custom WSDL</span></span>
<span data-ttu-id="728a5-103">本主题描述如何导入自定义 WSDL。</span><span class="sxs-lookup"><span data-stu-id="728a5-103">This topic describes how to import custom WSDL.</span></span> <span data-ttu-id="728a5-104">若要处理自定义 WSDL，必须实现 <xref:System.ServiceModel.Description.IWsdlImportExtension> 接口。</span><span class="sxs-lookup"><span data-stu-id="728a5-104">To handle the custom WSDL, you must implement the <xref:System.ServiceModel.Description.IWsdlImportExtension> interface.</span></span>  
  
### <a name="to-import-custom-wsdl"></a><span data-ttu-id="728a5-105">导入自定义 WSDL</span><span class="sxs-lookup"><span data-stu-id="728a5-105">To import custom WSDL</span></span>  
  
1. <span data-ttu-id="728a5-106">实现 <xref:System.ServiceModel.Description.IWsdlImportExtension>。</span><span class="sxs-lookup"><span data-stu-id="728a5-106">Implement <xref:System.ServiceModel.Description.IWsdlImportExtension>.</span></span> <span data-ttu-id="728a5-107">实现 <xref:System.ServiceModel.Description.IWsdlImportExtension.BeforeImport%28System.Web.Services.Description.ServiceDescriptionCollection%2CSystem.Xml.Schema.XmlSchemaSet%2CSystem.Collections.Generic.ICollection%7BSystem.Xml.XmlElement%7D%29> 方法，以便在导入元数据之前对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="728a5-107">Implement the <xref:System.ServiceModel.Description.IWsdlImportExtension.BeforeImport%28System.Web.Services.Description.ServiceDescriptionCollection%2CSystem.Xml.Schema.XmlSchemaSet%2CSystem.Collections.Generic.ICollection%7BSystem.Xml.XmlElement%7D%29> method to modify the metadata before it is imported.</span></span> <span data-ttu-id="728a5-108">实现 <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportEndpoint%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlEndpointConversionContext%29> 和 <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> 方法，以便修改从元数据导入的协定和终结点。</span><span class="sxs-lookup"><span data-stu-id="728a5-108">Implement the <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportEndpoint%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlEndpointConversionContext%29> and <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> methods to modify contracts and endpoints imported from the metadata.</span></span> <span data-ttu-id="728a5-109">若要访问所导入的协定或终结点，请使用相应的上下文对象（<xref:System.ServiceModel.Description.WsdlContractConversionContext> 或 <xref:System.ServiceModel.Description.WsdlEndpointConversionContext>）：</span><span class="sxs-lookup"><span data-stu-id="728a5-109">To access the imported contract or endpoint, use the corresponding context object (<xref:System.ServiceModel.Description.WsdlContractConversionContext> or <xref:System.ServiceModel.Description.WsdlEndpointConversionContext>):</span></span>  
  
    ```  
    public class WsdlDocumentationImporter : IWsdlImportExtension  
       {  
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
       }  
    ```  
  
2. <span data-ttu-id="728a5-110">将客户端应用程序配置为使用自定义 WSDL 导入程序。</span><span class="sxs-lookup"><span data-stu-id="728a5-110">Configure the client application to use the custom WSDL importer.</span></span> <span data-ttu-id="728a5-111">请注意，如果使用的是 Svcutil.exe，则应将此配置添加到 Svcutil.exe (Svcutil.exe.config) 的配置文件中：</span><span class="sxs-lookup"><span data-stu-id="728a5-111">Note that if you are using Svcutil.exe, you should add this configuration to the configuration file for Svcutil.exe (Svcutil.exe.config):</span></span>  
  
    ```xml  
    <system.serviceModel>  
          <client>  
            <endpoint   
              address="http://localhost:8000/Fibonacci"   
              binding="wsHttpBinding"  
              contract="IFibonacci"  
            />  
            <metadata>  
              <wsdlImporters>  
                <extension type="Microsoft.WCF.Documentation.WsdlDocumentationImporter, WsdlDocumentation" />  
              </wsdlImporters>  
            </metadata>  
          </client>  
        </system.serviceModel>  
    ```  
  
3. <span data-ttu-id="728a5-112">创建一个新的 <xref:System.ServiceModel.Description.WsdlImporter> 实例（并将其传入包含要导入的 WSDL 文档的 <xref:System.ServiceModel.Description.MetadataSet> 实例），然后调用 <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>：</span><span class="sxs-lookup"><span data-stu-id="728a5-112">Create a new <xref:System.ServiceModel.Description.WsdlImporter> instance (passing in the <xref:System.ServiceModel.Description.MetadataSet> instance that contains the WSDL documents that you want to import), and call <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>:</span></span>  
  
    ```  
    WsdlImporter importer = new WsdlImporter(metaDocs);          System.Collections.ObjectModel.Collection<ContractDescription> contracts  = importer.ImportAllContracts();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="728a5-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="728a5-113">See also</span></span>

- [<span data-ttu-id="728a5-114">元数据</span><span class="sxs-lookup"><span data-stu-id="728a5-114">Metadata</span></span>](../../../../docs/framework/wcf/feature-details/metadata.md)
- [<span data-ttu-id="728a5-115">导出和导入元数据</span><span class="sxs-lookup"><span data-stu-id="728a5-115">Exporting and Importing Metadata</span></span>](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md)
- [<span data-ttu-id="728a5-116">自定义 WSDL 发布</span><span class="sxs-lookup"><span data-stu-id="728a5-116">Custom WSDL Publication</span></span>](../../../../docs/framework/wcf/samples/custom-wsdl-publication.md)

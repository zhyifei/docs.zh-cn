---
title: 如何：使用 Svcutil.exe 将元数据从已编译的服务代码中导出
ms.date: 03/30/2017
ms.assetid: 95d0aed3-16a2-4398-89bb-39418eeb7355
ms.openlocfilehash: cb1cb03a078eeb273c69cc3c49b3ef2173c0a49c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59084903"
---
# <a name="how-to-use-svcutilexe-to-export-metadata-from-compiled-service-code"></a><span data-ttu-id="43ec7-102">如何：使用 Svcutil.exe 将元数据从已编译的服务代码中导出</span><span class="sxs-lookup"><span data-stu-id="43ec7-102">How to: Use Svcutil.exe to Export Metadata from Compiled Service Code</span></span>
<span data-ttu-id="43ec7-103">Svcutil.exe 可以导出已编译程序集中的服务、协定和数据类型的元数据，如下所示：</span><span class="sxs-lookup"><span data-stu-id="43ec7-103">Svcutil.exe can export metadata for services, contracts, and data types in compiled assemblies, as follows:</span></span>  
  
-   <span data-ttu-id="43ec7-104">若要使用 Svcutil.exe 为一组程序集导出所有已编译服务协定的元数据，请将这些程序集指定为输入参数。</span><span class="sxs-lookup"><span data-stu-id="43ec7-104">To export metadata for all compiled service contracts for a set of assemblies using Svcutil.exe, specify the assemblies as input parameters.</span></span> <span data-ttu-id="43ec7-105">这是默认行为。</span><span class="sxs-lookup"><span data-stu-id="43ec7-105">This is the default behavior.</span></span>  
  
-   <span data-ttu-id="43ec7-106">若要使用 Svcutil.exe 导出已编译服务的元数据，请将该（这些）服务程序集指定为输入参数。</span><span class="sxs-lookup"><span data-stu-id="43ec7-106">To export metadata for a compiled service using Svcutil.exe, specify the service assembly or assemblies as input parameters.</span></span> <span data-ttu-id="43ec7-107">必须使用 `/serviceName` 选项来指示要导出的服务的配置名称。</span><span class="sxs-lookup"><span data-stu-id="43ec7-107">You must use the `/serviceName` option to indicate the configuration name of the service you want to export.</span></span> <span data-ttu-id="43ec7-108">Svcutil.exe 自动为指定的可执行程序集加载配置文件。</span><span class="sxs-lookup"><span data-stu-id="43ec7-108">Svcutil.exe automatically loads the configuration file for the specified executable assembly.</span></span>  
  
-   <span data-ttu-id="43ec7-109">若要导出一组程序集内的所有数据协定类型，请使用 `/dataContractOnly` 选项。</span><span class="sxs-lookup"><span data-stu-id="43ec7-109">To export all data contract types within a set of assemblies, use the `/dataContractOnly` option.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43ec7-110">请使用 `/reference` 选项来指定所有相关程序集的文件路径。</span><span class="sxs-lookup"><span data-stu-id="43ec7-110">Use the `/reference` option to specify the file paths to any dependent assemblies.</span></span>  
  
### <a name="to-export-metadata-for-compiled-service-contracts"></a><span data-ttu-id="43ec7-111">导出已编译服务协定的元数据</span><span class="sxs-lookup"><span data-stu-id="43ec7-111">To export metadata for compiled service contracts</span></span>  
  
1.  <span data-ttu-id="43ec7-112">将服务协定实现编译为一个或多个类库。</span><span class="sxs-lookup"><span data-stu-id="43ec7-112">Compile your service contract implementations into one or more class libraries.1</span></span>  
  
2.  <span data-ttu-id="43ec7-113">在已编译程序集上运行 Svcutil.exe。</span><span class="sxs-lookup"><span data-stu-id="43ec7-113">Run Svcutil.exe on the compiled assemblies.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="43ec7-114">您可能需要使用 `/reference` 开关指定任意相关程序集的文件路径。</span><span class="sxs-lookup"><span data-stu-id="43ec7-114">You might need to use the `/reference` switch to specify the file path to any dependent assemblies.</span></span>  
  
    ```  
    svcutil.exe Contracts.dll  
    ```  
  
### <a name="to-export-metadata-for-a-compiled-service"></a><span data-ttu-id="43ec7-115">导出已编译服务的元数据</span><span class="sxs-lookup"><span data-stu-id="43ec7-115">To export metadata for a compiled service</span></span>  
  
1.  <span data-ttu-id="43ec7-116">将服务实现编译为可执行程序集。</span><span class="sxs-lookup"><span data-stu-id="43ec7-116">Compile your service implementation into an executable assembly.</span></span>  
  
2.  <span data-ttu-id="43ec7-117">为服务可执行程序集创建一个配置文件，并添加服务配置。</span><span class="sxs-lookup"><span data-stu-id="43ec7-117">Create a configuration file for your service executable and add a service configuration.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.serviceModel>  
        <services>  
          <service name="MyService" >  
            <endpoint address="finder" contract="IPeopleFinder" binding="wsHttpBinding" />  
          </service>  
        </services>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
3.  <span data-ttu-id="43ec7-118">在使用 `/serviceName` 开关指定服务的配置名称的已编译服务可执行程序集上运行 Svcutil.exe。</span><span class="sxs-lookup"><span data-stu-id="43ec7-118">Run Svcutil.exe on the compiled service executable using the `/serviceName` switch to specify the configuration name of the service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="43ec7-119">您可能需要使用 `/reference` 开关指定任意相关程序集的文件路径。</span><span class="sxs-lookup"><span data-stu-id="43ec7-119">You might need to use the `/reference` switch to specify the file path to any dependent assemblies.</span></span>  
  
    ```  
    svcutil.exe /serviceName:MyService Service.exe /reference:path/Contracts.dll  
    ```  
  
### <a name="to-export-metadata-for-compiled-data-contracts"></a><span data-ttu-id="43ec7-120">导出已编译数据协定的元数据</span><span class="sxs-lookup"><span data-stu-id="43ec7-120">To export metadata for compiled data contracts</span></span>  
  
1.  <span data-ttu-id="43ec7-121">将数据协定实现编译为一个或多个类库。</span><span class="sxs-lookup"><span data-stu-id="43ec7-121">Compile your data contract implementations into one or more class libraries.</span></span>  
  
2.  <span data-ttu-id="43ec7-122">在使用 `/dataContract` 开关指定应仅生成数据协定元数据的已编译程序集上运行 Svcutil.exe。</span><span class="sxs-lookup"><span data-stu-id="43ec7-122">Run Svcutil.exe on the compiled assemblies using the `/dataContract` switch to specify that only metadata for data contracts should be generated.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="43ec7-123">您可能需要使用 `/reference` 开关指定任意相关程序集的文件路径。</span><span class="sxs-lookup"><span data-stu-id="43ec7-123">You might need to use the `/reference` switch to specify the file path to any dependent assemblies.</span></span>  
  
    ```  
    svcutil.exe /dataContractOnly Contracts.dll  
    ```  
  
## <a name="example"></a><span data-ttu-id="43ec7-124">示例</span><span class="sxs-lookup"><span data-stu-id="43ec7-124">Example</span></span>  
 <span data-ttu-id="43ec7-125">下面的示例演示如何为单个服务实现和配置生成元数据。</span><span class="sxs-lookup"><span data-stu-id="43ec7-125">The following example demonstrates how to generate metadata for a simple service implementation and configuration.</span></span>  
  
 <span data-ttu-id="43ec7-126">导出服务协定的元数据。</span><span class="sxs-lookup"><span data-stu-id="43ec7-126">To export metadata for the service contract.</span></span>  
  
```  
svcutil.exe Contracts.dll  
```  
  
 <span data-ttu-id="43ec7-127">导出数据协定的元数据。</span><span class="sxs-lookup"><span data-stu-id="43ec7-127">To export metadata for the data contracts.</span></span>  
  
```  
svcutil.exe /dataContractOnly Contracts.dll  
```  
  
 <span data-ttu-id="43ec7-128">导出服务实现的元数据。</span><span class="sxs-lookup"><span data-stu-id="43ec7-128">To export metadata for the service implementation.</span></span>  
  
```  
svcutil.exe /serviceName:MyService Service.exe /reference:<path>/Contracts.dll  
```  
  
 <span data-ttu-id="43ec7-129">`<path>` 是 Contracts.dll 的路径。</span><span class="sxs-lookup"><span data-stu-id="43ec7-129">The `<path>` is the path to Contracts.dll.</span></span>  
  
```  
// The following service contract and data contracts are compiled into   
// Contracts.dll.  
[ServiceContract(ConfigurationName="IPeopleFinder")]  
public interface IPersonFinder  
{  
    [OperationContract]  
    Address GetAddress(Person s);  
}  
  
[DataContract]  
public class Person  
{  
    [DataMember]  
    public string firstName;  
    [DataMember]  
    public string lastName;  
    [DataMember]  
    public int age;  
}  
  
[DataContract]  
public class Address  
{  
    [DataMember]  
    public string city;  
    [DataMember]  
    public string state;  
    [DataMember]  
    public string street;  
    [DataMember]  
    public int zipCode;  
    [DataMember]  
    public Person person;  
}  
  
// The following service implementation is compiled into Service.exe.     
// This service uses the contracts specified in Contracts.dll.  
[ServiceBehavior(ConfigurationName = "MyService")]  
public class MyService : IPersonFinder  
{  
    public Address GetAddress(Person person)  
    {  
        Address address = new Address();  
        address.person = person;  
        return address;  
    }  
}  
  
<!-- The following is the configuration file for Service.exe. -->  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="MyService">  
         <endpoint  address="finder"  
                    binding="basicHttpBinding"  
                    contract="IPeopleFinder"/>  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="43ec7-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="43ec7-130">See also</span></span>

- [<span data-ttu-id="43ec7-131">ServiceModel 元数据实用工具 (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="43ec7-131">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="43ec7-132">导出和导入元数据</span><span class="sxs-lookup"><span data-stu-id="43ec7-132">Exporting and Importing Metadata</span></span>](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md)

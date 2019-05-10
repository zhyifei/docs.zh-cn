---
title: 如何：使用 XmlSerializer 改善 WCF 客户端应用程序的启动时间
ms.date: 03/30/2017
ms.assetid: 21093451-0bc3-4b1a-9a9d-05f7f71fa7d0
ms.openlocfilehash: b163f4478794797ea910e39ba2368c602218f13b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64586094"
---
# <a name="how-to-improve-the-startup-time-of-wcf-client-applications-using-the-xmlserializer"></a><span data-ttu-id="b6e8c-102">如何：使用 XmlSerializer 改善 WCF 客户端应用程序的启动时间</span><span class="sxs-lookup"><span data-stu-id="b6e8c-102">How to: Improve the Startup Time of WCF Client Applications using the XmlSerializer</span></span>
<span data-ttu-id="b6e8c-103">如果服务和客户端应用程序使用可用 <xref:System.Xml.Serialization.XmlSerializer> 进行序列化的数据类型，则会在运行时生成并编译这些数据类型的序列化代码，从而导致启动性能降低。</span><span class="sxs-lookup"><span data-stu-id="b6e8c-103">Services and client applications that use data types that are serializable using the <xref:System.Xml.Serialization.XmlSerializer> generate and compile serialization code for those data types at runtime, which can result in slow start-up performance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b6e8c-104">预生成的序列化代码只能在客户端应用程序中使用，不能在服务中使用。</span><span class="sxs-lookup"><span data-stu-id="b6e8c-104">Pre-generated serialization code can only be used in client applications and not in services.</span></span>  
  
 <span data-ttu-id="b6e8c-105">[ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)可以通过从应用程序的已编译程序集生成必要的序列化代码提高这些应用程序的启动性能。</span><span class="sxs-lookup"><span data-stu-id="b6e8c-105">The [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) can improve start-up performance for these applications by generating the necessary serialization code from the compiled assemblies for the application.</span></span> <span data-ttu-id="b6e8c-106">Svcutil.exe 会为已编译的应用程序集的服务协定中使用的所有数据生成序列化代码，该代码可使用 <xref:System.Xml.Serialization.XmlSerializer> 进行序列化。</span><span class="sxs-lookup"><span data-stu-id="b6e8c-106">Svcutil.exe generates serialization code for all data types used in service contracts in the compiled application assembly that can be serialized using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="b6e8c-107">使用 <xref:System.Xml.Serialization.XmlSerializer> 的服务和操作协定用 <xref:System.ServiceModel.XmlSerializerFormatAttribute> 进行标记。</span><span class="sxs-lookup"><span data-stu-id="b6e8c-107">Service and operation contracts that use the <xref:System.Xml.Serialization.XmlSerializer> are marked with the <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span></span>  
  
### <a name="to-generate-xmlserializer-serialization-code"></a><span data-ttu-id="b6e8c-108">生成 XmlSerializer 序列化代码</span><span class="sxs-lookup"><span data-stu-id="b6e8c-108">To generate XmlSerializer serialization code</span></span>  
  
1. <span data-ttu-id="b6e8c-109">将服务或客户端代码编译为一个或多个程序集。</span><span class="sxs-lookup"><span data-stu-id="b6e8c-109">Compile your service or client code into one or more assemblies.</span></span>  
  
2. <span data-ttu-id="b6e8c-110">打开一个 SDK 命令提示符窗口。</span><span class="sxs-lookup"><span data-stu-id="b6e8c-110">Open an SDK command prompt.</span></span>  
  
3. <span data-ttu-id="b6e8c-111">在命令提示符处，使用下面的格式启动 Svcutil.exe 工具。</span><span class="sxs-lookup"><span data-stu-id="b6e8c-111">At the command prompt, launch the Svcutil.exe tool using the following format.</span></span>  
  
    ```  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     <span data-ttu-id="b6e8c-112">`assemblyPath` 参数指定包含服务协定类型的程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="b6e8c-112">The `assemblyPath` argument specifies the path to an assembly that contains service contract types.</span></span> <span data-ttu-id="b6e8c-113">Svcutil.exe 会为已编译的应用程序集的服务协定中使用的所有数据生成序列化代码，该代码可使用 <xref:System.Xml.Serialization.XmlSerializer> 进行序列化。</span><span class="sxs-lookup"><span data-stu-id="b6e8c-113">Svcutil.exe generates serialization code for all data types used in service contracts in the compiled application assembly that can be serialized using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span>  
  
     <span data-ttu-id="b6e8c-114">Svcutil.exe 只能生成 C# 序列化代码。</span><span class="sxs-lookup"><span data-stu-id="b6e8c-114">Svcutil.exe can only generate C# serialization code.</span></span> <span data-ttu-id="b6e8c-115">为每个输入程序集生成一个源代码文件。</span><span class="sxs-lookup"><span data-stu-id="b6e8c-115">One source code file is generated for each input assembly.</span></span> <span data-ttu-id="b6e8c-116">不能使用 **/language**开关更改所生成代码的语言。</span><span class="sxs-lookup"><span data-stu-id="b6e8c-116">You cannot use the **/language** switch to change the language of the generated code.</span></span>  
  
     <span data-ttu-id="b6e8c-117">若要指定从属程序集的路径，请使用 **/reference**选项。</span><span class="sxs-lookup"><span data-stu-id="b6e8c-117">To specify the path to dependent assemblies, use the **/reference** option.</span></span>  
  
4. <span data-ttu-id="b6e8c-118">通过使用下列选项之一使生成的序列化代码可供你的应用程序使用：</span><span class="sxs-lookup"><span data-stu-id="b6e8c-118">Make the generated serialization code available to your application by using one of the following options:</span></span>  
  
    1. <span data-ttu-id="b6e8c-119">生成的序列化代码编译为单独的程序集名称 [*原始程序集*]。Xmlserializers.dll (例如 MyApp.XmlSerializers.dll) 组成。</span><span class="sxs-lookup"><span data-stu-id="b6e8c-119">Compile the generated serialization code into a separate assembly with the name [*original assembly*].XmlSerializers.dll (for example, MyApp.XmlSerializers.dll).</span></span> <span data-ttu-id="b6e8c-120">您的应用程序必须能够加载该程序集，而该程序集必须使用与原始程序集相同的密钥进行签名。</span><span class="sxs-lookup"><span data-stu-id="b6e8c-120">Your application must be able to load the assembly, which must be signed with the same key as the original assembly.</span></span> <span data-ttu-id="b6e8c-121">如果您要重新编译原始程序集，则必须重新生成序列化程序集。</span><span class="sxs-lookup"><span data-stu-id="b6e8c-121">If you recompile the original assembly, you must regenerate the serialization assembly.</span></span>  
  
    2. <span data-ttu-id="b6e8c-122">将生成的序列化代码编译成单独的程序集，并在使用 <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> 的服务协定上使用 <xref:System.ServiceModel.XmlSerializerFormatAttribute>。</span><span class="sxs-lookup"><span data-stu-id="b6e8c-122">Compile the generated serialization code into a separate assembly and use the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> on the service contract that uses the <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span></span> <span data-ttu-id="b6e8c-123">将 <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> 或 <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> 属性设置为指向已编译的序列化程序集。</span><span class="sxs-lookup"><span data-stu-id="b6e8c-123">Set the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> or <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> properties to point to the compiled serialization assembly.</span></span>  
  
    3. <span data-ttu-id="b6e8c-124">将生成的序列化代码编译到您的应用程序集内并将 <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute><xref:System.ServiceModel.XmlSerializerFormatAttribute>添加到使用  的服务协定中。</span><span class="sxs-lookup"><span data-stu-id="b6e8c-124">Compile the generated serialization code into your application assembly and add the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute> to the service contract that uses the <xref:System.ServiceModel.XmlSerializerFormatAttribute>.</span></span> <span data-ttu-id="b6e8c-125">不要设置 <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> 或 <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="b6e8c-125">Do not set the <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.AssemblyName%2A> or <xref:System.Xml.Serialization.XmlSerializerAssemblyAttribute.CodeBase%2A> properties.</span></span> <span data-ttu-id="b6e8c-126">默认序列化程序集假定为当前程序集。</span><span class="sxs-lookup"><span data-stu-id="b6e8c-126">The default serialization assembly is assumed to be the current assembly.</span></span>  
  
### <a name="to-generate-xmlserializer-serialization-code-in-visual-studio"></a><span data-ttu-id="b6e8c-127">若要在 Visual Studio 中生成 XmlSerializer 序列化代码</span><span class="sxs-lookup"><span data-stu-id="b6e8c-127">To generate XmlSerializer serialization code in Visual Studio</span></span>  
  
1. <span data-ttu-id="b6e8c-128">在 Visual Studio 中创建的 WCF 服务和客户端项目。</span><span class="sxs-lookup"><span data-stu-id="b6e8c-128">Create the WCF service and client projects in Visual Studio.</span></span> <span data-ttu-id="b6e8c-129">然后，添加对客户端项目的服务引用。</span><span class="sxs-lookup"><span data-stu-id="b6e8c-129">Then, add a service reference to the client project.</span></span>  
  
2. <span data-ttu-id="b6e8c-130">添加<xref:System.ServiceModel.XmlSerializerFormatAttribute>到中的服务协定*reference.cs*下的客户端应用程序项目中的文件**serviceReference** -> **reference.svcmap**.</span><span class="sxs-lookup"><span data-stu-id="b6e8c-130">Add an <xref:System.ServiceModel.XmlSerializerFormatAttribute> to the service contract in the *reference.cs* file in the client app project under **serviceReference** -> **reference.svcmap**.</span></span> <span data-ttu-id="b6e8c-131">请注意，您需要显示所有文件中的**解决方案资源管理器**若要查看这些文件。</span><span class="sxs-lookup"><span data-stu-id="b6e8c-131">Note that you need to show all files in **Solution Explorer** to see these files.</span></span>  
  
3. <span data-ttu-id="b6e8c-132">生成客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="b6e8c-132">Build the client app.</span></span>  
  
4. <span data-ttu-id="b6e8c-133">使用[ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)若要创建预生成序列化程序 *.cs*文件使用命令：</span><span class="sxs-lookup"><span data-stu-id="b6e8c-133">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to create a pre-generated serializer *.cs* file by using the command:</span></span>  
  
    ```  
    svcutil.exe /t:xmlSerializer  <assemblyPath>*  
    ```  
  
     <span data-ttu-id="b6e8c-134">AssemblyPath 参数指定 WCF 客户端程序集的路径。</span><span class="sxs-lookup"><span data-stu-id="b6e8c-134">The assemblyPath argument specifies the path to the WCF client assembly.</span></span>  
  
     <span data-ttu-id="b6e8c-135">如：</span><span class="sxs-lookup"><span data-stu-id="b6e8c-135">Such as:</span></span>  
  
    ```  
    svcutil.exe /t:xmlSerializer wcfclient.exe  
    ```  
  
     <span data-ttu-id="b6e8c-136">*WCFClient.XmlSerializers.dll.cs*将生成文件。</span><span class="sxs-lookup"><span data-stu-id="b6e8c-136">The *WCFClient.XmlSerializers.dll.cs* file will be generated.</span></span>  
  
5. <span data-ttu-id="b6e8c-137">编译预生成的序列化程序集。</span><span class="sxs-lookup"><span data-stu-id="b6e8c-137">Compile the pre-generated serialization assembly.</span></span>  
  
     <span data-ttu-id="b6e8c-138">基于上一步中的示例，编译命令应为以下：</span><span class="sxs-lookup"><span data-stu-id="b6e8c-138">Based on the example in the previous step, the compile command would be the following:</span></span>  
  
    ```  
    csc /r:wcfclient.exe /out:WCFClient.XmlSerializers.dll /t:library WCFClient.XmlSerializers.dll.cs  
    ```  
  
     <span data-ttu-id="b6e8c-139">请确保生成*WCFClient.XmlSerializers.dll*中与客户端应用程序，这是相同的目录*WCFClient.exe*这种情况下。</span><span class="sxs-lookup"><span data-stu-id="b6e8c-139">Make sure the generated *WCFClient.XmlSerializers.dll* is in the same directory as the client app, which is *WCFClient.exe* in this case.</span></span>  
  
6. <span data-ttu-id="b6e8c-140">像往常一样运行客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="b6e8c-140">Run the client app as usual.</span></span> <span data-ttu-id="b6e8c-141">将使用预生成的序列化程序集。</span><span class="sxs-lookup"><span data-stu-id="b6e8c-141">The pre-generated serialization assembly will be used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6e8c-142">示例</span><span class="sxs-lookup"><span data-stu-id="b6e8c-142">Example</span></span>  
 <span data-ttu-id="b6e8c-143">下面的命令为 `XmlSerializer` 类型生成程序集中所有服务协定使用的序列化类型。</span><span class="sxs-lookup"><span data-stu-id="b6e8c-143">The following command generates serialization types for `XmlSerializer` types that any service contracts in the assembly use.</span></span>  
  
```  
svcutil /t:xmlserializer myContractLibrary.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="b6e8c-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="b6e8c-144">See also</span></span>

- [<span data-ttu-id="b6e8c-145">ServiceModel 元数据实用工具 (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="b6e8c-145">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)

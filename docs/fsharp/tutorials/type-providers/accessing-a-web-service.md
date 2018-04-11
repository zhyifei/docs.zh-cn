---
title: '演练-访问 Web 服务使用类型提供程序 （F #）'
description: '了解如何使用 F # 3.0 中提供的 Web 服务描述语言 (WSDL) 类型提供程序来访问 WSDL 服务。'
keywords: visual f#, f#, 函数编程
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 63374fa9-8fb8-43ac-bcb9-ef2290d9f851
ms.openlocfilehash: 2929198172a4e9f908daa64af19208e07859263f
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/10/2018
---
# <a name="walkthrough-accessing-a-web-service-by-using-type-providers"></a><span data-ttu-id="b61f3-104">演练：使用类型提供程序访问 Web 服务</span><span class="sxs-lookup"><span data-stu-id="b61f3-104">Walkthrough: Accessing a Web Service by Using Type Providers</span></span>

> [!NOTE]
<span data-ttu-id="b61f3-105">此指南专门针对 F # 3.0 编写，并将更新。</span><span class="sxs-lookup"><span data-stu-id="b61f3-105">This guide was written for F# 3.0 and will be updated.</span></span>  <span data-ttu-id="b61f3-106">请参阅 [FSharp.Data](https://fsharp.github.io/FSharp.Data/) 了解最新的跨平台类型提供程序。</span><span class="sxs-lookup"><span data-stu-id="b61f3-106">See [FSharp.Data](https://fsharp.github.io/FSharp.Data/) for up-to-date, cross-platform type providers.</span></span>

> [!NOTE]
<span data-ttu-id="b61f3-107">API 参考链接将转到 MSDN。</span><span class="sxs-lookup"><span data-stu-id="b61f3-107">The API reference links will take you to MSDN.</span></span>  <span data-ttu-id="b61f3-108">Docs.microsoft.com API 参考尚未完成。</span><span class="sxs-lookup"><span data-stu-id="b61f3-108">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="b61f3-109">本演练演示了如何使用 F # 3.0 来访问 WSDL 服务中提供的 Web 服务描述语言 (WSDL) 类型提供程序。</span><span class="sxs-lookup"><span data-stu-id="b61f3-109">This walkthrough shows you how to use the Web Services Description Language (WSDL) type provider that is available in F# 3.0 to access a WSDL service.</span></span> <span data-ttu-id="b61f3-110">在其他.NET 语言中，生成代码以调用 svcutil.exe 访问 web 服务通过将添加中的 web 引用，例如，C# 项目或若要获取 Visual Studio 来为您调用 svcutil.exe。</span><span class="sxs-lookup"><span data-stu-id="b61f3-110">In other .NET languages, you generate the code to access the web service by calling svcutil.exe, or by adding a web reference in, for example, a C# project to get Visual Studio to call svcutil.exe for you.</span></span> <span data-ttu-id="b61f3-111">在 F # 中，你可以使用附加选项的使用 WSDL 类型提供程序，因此只要你编写代码，以便创建 WsdlService 类型，类型必须生成并变为可用。</span><span class="sxs-lookup"><span data-stu-id="b61f3-111">In F#, you have the additional option of using the WSDL type provider, so as soon as you write the code that creates the WsdlService type, the types are generated and become available.</span></span> <span data-ttu-id="b61f3-112">此过程依赖于处于可用，在编写代码时服务。</span><span class="sxs-lookup"><span data-stu-id="b61f3-112">This process relies on the service being available when you are writing the code.</span></span>

<span data-ttu-id="b61f3-113">本演练阐释了以下任务。</span><span class="sxs-lookup"><span data-stu-id="b61f3-113">This walkthrough illustrates the following tasks.</span></span> <span data-ttu-id="b61f3-114">您必须完成它们按以下顺序才能成功完成演练：</span><span class="sxs-lookup"><span data-stu-id="b61f3-114">You must complete them in this order for the walkthrough to succeed:</span></span>


- <span data-ttu-id="b61f3-115">创建项目</span><span class="sxs-lookup"><span data-stu-id="b61f3-115">Creating the project</span></span>
<br />

- <span data-ttu-id="b61f3-116">配置类型提供程序</span><span class="sxs-lookup"><span data-stu-id="b61f3-116">Configuring the type provider</span></span>
<br />

- <span data-ttu-id="b61f3-117">调用 web 服务，并处理结果</span><span class="sxs-lookup"><span data-stu-id="b61f3-117">Calling the web service, and processing the results</span></span>
<br />


## <a name="creating-the-project"></a><span data-ttu-id="b61f3-118">创建项目</span><span class="sxs-lookup"><span data-stu-id="b61f3-118">Creating the project</span></span>
<span data-ttu-id="b61f3-119">在步骤中，你可以创建项目并添加相应的引用以使用 WSDL 类型提供程序。</span><span class="sxs-lookup"><span data-stu-id="b61f3-119">In the step, you create a project and add the appropriate references to use a WSDL type provider.</span></span>


#### <a name="to-create-and-set-up-an-f-project"></a><span data-ttu-id="b61f3-120">创建并设置 F# 项目</span><span class="sxs-lookup"><span data-stu-id="b61f3-120">To create and set up an F# project</span></span>

1. <span data-ttu-id="b61f3-121">打开一个新的 F # 控制台应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="b61f3-121">Open a new F# Console Application project.</span></span>
<br />

2. <span data-ttu-id="b61f3-122">在**解决方案资源管理器**，打开项目的快捷菜单**引用**节点，然后选择**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="b61f3-122">In **Solution Explorer**, open the shortcut menu for the project's **Reference** node, and then choose **Add Reference**.</span></span>
<br />

3. <span data-ttu-id="b61f3-123">在**程序集**区域中，选择**Framework**，然后在可用的程序集列表中，选择**System.Runtime.Serialization**和**System.ServiceModel**。</span><span class="sxs-lookup"><span data-stu-id="b61f3-123">In the **Assemblies** area, choose **Framework**, and then, in the list of available assemblies, choose **System.Runtime.Serialization** and **System.ServiceModel**.</span></span>
<br />

4. <span data-ttu-id="b61f3-124">在**程序集**区域中，选择**扩展**。</span><span class="sxs-lookup"><span data-stu-id="b61f3-124">In the **Assemblies** area, choose **Extensions**.</span></span>
<br />

5. <span data-ttu-id="b61f3-125">在可用的程序集列表中，选择**FSharp.Data.TypeProviders**，然后选择**确定**按钮以添加对这些程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="b61f3-125">In the list of available assemblies, choose **FSharp.Data.TypeProviders**, and then choose the **OK** button to add references to these assemblies.</span></span>
<br />

## <a name="configuring-the-type-provider"></a><span data-ttu-id="b61f3-126">配置类型提供程序</span><span class="sxs-lookup"><span data-stu-id="b61f3-126">Configuring the type provider</span></span>
<span data-ttu-id="b61f3-127">在此步骤中，你使用 WSDL 类型提供程序生成为 TerraServer web 服务的类型。</span><span class="sxs-lookup"><span data-stu-id="b61f3-127">In this step, you use the WSDL type provider to generate types for the TerraServer web service.</span></span>


#### <a name="to-configure-the-type-provider-and-generate-types"></a><span data-ttu-id="b61f3-128">配置类型提供程序和生成类型</span><span class="sxs-lookup"><span data-stu-id="b61f3-128">To configure the type provider and generate types</span></span>

1. <span data-ttu-id="b61f3-129">添加以下代码行以打开类型提供程序命名空间。</span><span class="sxs-lookup"><span data-stu-id="b61f3-129">Add the following line of code to open the type provider namespace.</span></span>
<br />

```fsharp
open System
open System.ServiceModel
open Microsoft.FSharp.Linq
open Microsoft.FSharp.Data.TypeProviders
```

2. <span data-ttu-id="b61f3-130">添加以下代码行以调用 web 服务的类型提供程序。</span><span class="sxs-lookup"><span data-stu-id="b61f3-130">Add the following line of code to invoke the type provider with a web service.</span></span> <span data-ttu-id="b61f3-131">在此示例中，使用 TerraServer web 服务。</span><span class="sxs-lookup"><span data-stu-id="b61f3-131">In this example, use the TerraServer web service.</span></span>
<br />

```fsharp
type TerraService = WsdlService<" HYPERLINK "https://terraserver-usa.com/TerraService2.asmx?WSDL" https://msrmaps.com/TerraService2.asmx?WSDL">
```

  <span data-ttu-id="b61f3-132">如果服务 URI 是拼写错误或者如果服务本身已关闭或不执行，红色波形曲线将出现在此代码行下。</span><span class="sxs-lookup"><span data-stu-id="b61f3-132">A red squiggle appears under this line of code if the service URI is misspelled or if the service itself is down or isn’t performing.</span></span> <span data-ttu-id="b61f3-133">如果您指向代码时，一条错误消息描述的问题。</span><span class="sxs-lookup"><span data-stu-id="b61f3-133">If you point to the code, an error message describes the problem.</span></span> <span data-ttu-id="b61f3-134">你可以查找中的相同信息**错误列表**窗口中或在**输出窗口**在生成后。</span><span class="sxs-lookup"><span data-stu-id="b61f3-134">You can find the same information in the **Error List** window or in the **Output Window** after you build.</span></span>
<br />  <span data-ttu-id="b61f3-135">有两种方法对于项目，使用 app.config 文件或在类型提供程序声明中使用的静态类型参数指定对于 WSDL 连接的配置设置。</span><span class="sxs-lookup"><span data-stu-id="b61f3-135">There are two ways to specify configuration settings for a WSDL connection, by using the app.config file for the project, or by using the static type parameters in the type provider declaration.</span></span> <span data-ttu-id="b61f3-136">你可以使用 svcutil.exe 生成相应的配置文件元素。</span><span class="sxs-lookup"><span data-stu-id="b61f3-136">You can use svcutil.exe to generate appropriate configuration file elements.</span></span> <span data-ttu-id="b61f3-137">有关使用 svcutil.exe 生成的 web 服务的配置信息的详细信息，请参阅[ServiceModel 元数据实用工具&#40;Svcutil.exe&#41;](https://msdn.microsoft.com/library/aa347733.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b61f3-137">For more information about using svcutil.exe to generate configuration information for a web service, see [ServiceModel Metadata Utility Tool &#40;Svcutil.exe&#41;](https://msdn.microsoft.com/library/aa347733.aspx).</span></span> <span data-ttu-id="b61f3-138">WSDL 类型提供程序的静态类型参数的完整说明，请参阅[WsdlService 类型提供程序](https://msdn.microsoft.com/visualfsharpdocs/conceptual/wsdlservice-type-provider-%5bfsharp%5d)。</span><span class="sxs-lookup"><span data-stu-id="b61f3-138">For a full description of the static type parameters for the WSDL type provider, see [WsdlService Type Provider](https://msdn.microsoft.com/visualfsharpdocs/conceptual/wsdlservice-type-provider-%5bfsharp%5d).</span></span>
<br />

## <a name="calling-the-web-service-and-processing-the-results"></a><span data-ttu-id="b61f3-139">调用 web 服务，并处理结果</span><span class="sxs-lookup"><span data-stu-id="b61f3-139">Calling the web service, and processing the results</span></span>
<span data-ttu-id="b61f3-140">每个 web 服务有其自己的一套被用作其方法调用参数的类型。</span><span class="sxs-lookup"><span data-stu-id="b61f3-140">Each web service has its own set of types that are used as parameters for its method calls.</span></span> <span data-ttu-id="b61f3-141">在此步骤中，您将准备这些参数，调用 web 方法，并处理它将返回的信息。</span><span class="sxs-lookup"><span data-stu-id="b61f3-141">In this step, you prepare these parameters, call a web method, and process the information that it returns.</span></span>


#### <a name="to-call-the-web-service-and-process-the-results"></a><span data-ttu-id="b61f3-142">若要调用 web 服务，以及如何处理结果</span><span class="sxs-lookup"><span data-stu-id="b61f3-142">To call the web service, and process the results</span></span>

1. <span data-ttu-id="b61f3-143">Web 服务可能会超时，或停止正常工作，因此你应在异常处理块中包含 web 服务调用。</span><span class="sxs-lookup"><span data-stu-id="b61f3-143">The web service might time out or stop functioning, so you should include the web service call in an exception handling block.</span></span> <span data-ttu-id="b61f3-144">编写下面的代码尝试从 web 服务获取数据。</span><span class="sxs-lookup"><span data-stu-id="b61f3-144">Write the following code to try to get data from the web service.</span></span>
<br />

```fsharp
try
  let terraClient = TerraService.GetTerraServiceSoap ()
  let myPlace = new TerraService.ServiceTypes.msrmaps.com.Place(City = "Redmond", State = "Washington", Country = "United States")
  let myLocation = terraClient.ConvertPlaceToLonLatPt(myPlace)
  printfn "Redmond Latitude: %f Longitude: %f" (myLocation.Lat) (myLocation.Lon)
with
| :? ServerTooBusyException as exn ->
  let innerMessage =
    match (exn.InnerException) with
    | null -> ""
    | innerExn -> innerExn.Message
  printfn "An exception occurred:\n %s\n %s" exn.Message innerMessage
| exn -> printfn "An exception occurred: %s" exn.Message
```

<span data-ttu-id="b61f3-145">请注意，你创建的数据类型所需的 web 服务，如**位置**和**位置**，如 WsdlService 下的嵌套的类型键入**TerraService**。</span><span class="sxs-lookup"><span data-stu-id="b61f3-145">Notice that you create the data types that are needed for the web service, such as **Place** and **Location**, as nested types under the WsdlService type **TerraService**.</span></span>
<br />


## <a name="see-also"></a><span data-ttu-id="b61f3-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b61f3-146">See Also</span></span>
[<span data-ttu-id="b61f3-147">WsdlService 类型提供程序</span><span class="sxs-lookup"><span data-stu-id="b61f3-147">WsdlService Type Provider</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/wsdlservice-type-provider-%5bfsharp%5d)

[<span data-ttu-id="b61f3-148">类型提供程序</span><span class="sxs-lookup"><span data-stu-id="b61f3-148">Type Providers</span></span>](index.md)

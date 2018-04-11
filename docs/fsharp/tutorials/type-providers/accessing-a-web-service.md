---
title: "演练-访问 Web 服务使用类型提供程序 （F #）"
description: "了解如何使用 F # 3.0 中提供的 Web 服务描述语言 (WSDL) 类型提供程序来访问 WSDL 服务。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 63374fa9-8fb8-43ac-bcb9-ef2290d9f851
ms.openlocfilehash: 2929198172a4e9f908daa64af19208e07859263f
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
---
# <a name="walkthrough-accessing-a-web-service-by-using-type-providers"></a>演练：使用类型提供程序访问 Web 服务

> [!NOTE]
此指南专门针对 F # 3.0 编写，并将更新。  请参阅 [FSharp.Data](https://fsharp.github.io/FSharp.Data/) 了解最新的跨平台类型提供程序。

> [!NOTE]
API 参考链接将转到 MSDN。  Docs.microsoft.com API 参考尚未完成。

本演练演示了如何使用 F # 3.0 来访问 WSDL 服务中提供的 Web 服务描述语言 (WSDL) 类型提供程序。 在其他.NET 语言中，生成代码以调用 svcutil.exe 访问 web 服务通过将添加中的 web 引用，例如，C# 项目或若要获取 Visual Studio 来为您调用 svcutil.exe。 在 F # 中，你可以使用附加选项的使用 WSDL 类型提供程序，因此只要你编写代码，以便创建 WsdlService 类型，类型必须生成并变为可用。 此过程依赖于处于可用，在编写代码时服务。

本演练阐释了以下任务。 您必须完成它们按以下顺序才能成功完成演练：


- 创建项目
<br />

- 配置类型提供程序
<br />

- 调用 web 服务，并处理结果
<br />


## <a name="creating-the-project"></a>创建项目
在步骤中，你可以创建项目并添加相应的引用以使用 WSDL 类型提供程序。


#### <a name="to-create-and-set-up-an-f-project"></a>创建并设置 F# 项目

1. 打开一个新的 F # 控制台应用程序项目。
<br />

2. 在**解决方案资源管理器**，打开项目的快捷菜单**引用**节点，然后选择**添加引用**。
<br />

3. 在**程序集**区域中，选择**Framework**，然后在可用的程序集列表中，选择**System.Runtime.Serialization**和**System.ServiceModel**。
<br />

4. 在**程序集**区域中，选择**扩展**。
<br />

5. 在可用的程序集列表中，选择**FSharp.Data.TypeProviders**，然后选择**确定**按钮以添加对这些程序集的引用。
<br />

## <a name="configuring-the-type-provider"></a>配置类型提供程序
在此步骤中，你使用 WSDL 类型提供程序生成为 TerraServer web 服务的类型。


#### <a name="to-configure-the-type-provider-and-generate-types"></a>配置类型提供程序和生成类型

1. 添加以下代码行以打开类型提供程序命名空间。
<br />

```fsharp
open System
open System.ServiceModel
open Microsoft.FSharp.Linq
open Microsoft.FSharp.Data.TypeProviders
```

2. 添加以下代码行以调用 web 服务的类型提供程序。 在此示例中，使用 TerraServer web 服务。
<br />

```fsharp
type TerraService = WsdlService<" HYPERLINK "https://terraserver-usa.com/TerraService2.asmx?WSDL" https://msrmaps.com/TerraService2.asmx?WSDL">
```

  如果服务 URI 是拼写错误或者如果服务本身已关闭或不执行，红色波形曲线将出现在此代码行下。 如果您指向代码时，一条错误消息描述的问题。 你可以查找中的相同信息**错误列表**窗口中或在**输出窗口**在生成后。
<br />  有两种方法对于项目，使用 app.config 文件或在类型提供程序声明中使用的静态类型参数指定对于 WSDL 连接的配置设置。 你可以使用 svcutil.exe 生成相应的配置文件元素。 有关使用 svcutil.exe 生成的 web 服务的配置信息的详细信息，请参阅[ServiceModel 元数据实用工具 &#40;Svcutil.exe &#41;](https://msdn.microsoft.com/library/aa347733.aspx). WSDL 类型提供程序的静态类型参数的完整说明，请参阅[WsdlService 类型提供程序](https://msdn.microsoft.com/visualfsharpdocs/conceptual/wsdlservice-type-provider-%5bfsharp%5d)。
<br />

## <a name="calling-the-web-service-and-processing-the-results"></a>调用 web 服务，并处理结果
每个 web 服务有其自己的一套被用作其方法调用参数的类型。 在此步骤中，您将准备这些参数，调用 web 方法，并处理它将返回的信息。


#### <a name="to-call-the-web-service-and-process-the-results"></a>若要调用 web 服务，以及如何处理结果

1. Web 服务可能会超时，或停止正常工作，因此你应在异常处理块中包含 web 服务调用。 编写下面的代码尝试从 web 服务获取数据。
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

请注意，你创建的数据类型所需的 web 服务，如**位置**和**位置**，如 WsdlService 下的嵌套的类型键入**TerraService**。
<br />


## <a name="see-also"></a>请参阅
[WsdlService 类型提供程序](https://msdn.microsoft.com/visualfsharpdocs/conceptual/wsdlservice-type-provider-%5bfsharp%5d)

[类型提供程序](index.md)

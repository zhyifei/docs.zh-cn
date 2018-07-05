---
title: Docker 中托管的微服务 - C#
description: 了解如何创建在 Docker 容器中运行的 ASP.NET Core 服务
ms.date: 06/08/2017
ms.assetid: 87e93838-a363-4813-b859-7356023d98ed
ms.openlocfilehash: 1f4b38243beb1210b1374bd701fac66b2fa72cc5
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106345"
---
# <a name="microservices-hosted-in-docker"></a>Docker 中托管的微服务

此教程将详细介绍在 Docker 容器中生成和部署 ASP.NET Core 微服务时必须完成的任务。 在此教程中，你将了解：

* 如何生成 ASP.NET Core 应用程序。
* 如何创建 Docker 开发环境。
* 如何根据现有映像生成 Docker 映像。
* 如何将服务部署到 Docker 容器中。

与此同时，你还将了解下面这些 C# 语言功能：

* 如何将 C# 对象转换成 JSON 有效负载。
* 如何生成不可变的数据传输对象。
* 如何处理传入的 HTTP 请求并生成 HTTP 响应。
* 如何使用可以为 null 的值类型。

你可以[查看或下载本主题的示例应用](https://github.com/dotnet/samples/tree/master/csharp/getting-started/WeatherMicroservice)。 有关下载说明，请参阅[示例和教程](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)。

## <a name="why-docker"></a>为什么要使用 Docker？

使用 Docker，可以轻松地创建标准计算机映像，从而在数据中心或公有云中托管服务。 使用 Docker，可以配置映像，并根据需要复制映像来扩展应用程序安装。

此教程中的所有代码适用于任何 .NET Core 环境。
附加 Docker 安装任务适用于 ASP.NET Core 应用程序。 

## <a name="prerequisites"></a>系统必备

必须将计算机设置为运行 .NET Core。 有关安装说明，请访问 [.NET Core](https://www.microsoft.com/net/core) 页。
可以在 Windows、Linux、macOS 或 Docker 容器中运行此应用程序。
必须安装常用的代码编辑器。 在以下说明中，我们使用的是开放源代码跨平台编辑器 [Visual Studio Code](https://code.visualstudio.com/)。 不过，你可以使用习惯使用的任意工具。

还必须安装 Docker 引擎。 请参阅 [Docker 安装页](http://www.docker.com/products/docker)，了解适用于自己的平台的说明。
可以在许多 Linux 发行版本、macOS 或 Windows 中安装 Docker。 上面引用的页面分部分提供了各个可安装的版本。

## <a name="create-the-application"></a>创建应用程序

现已安装所有工具，请在喜欢的 shell 中执行以下名称，在名为“WeatherMicroservice”的目录中新建 ASP.NET Core 应用程序：

```console
dotnet new web -o WeatherMicroservice
```

`dotnet` 命令可运行 .NET 开发所需的工具。 每个谓词执行一个不同的命令。

`dotnet new` 命令用于创建 .Net Core 项目。

`dotnet new` 命令后的 `-o WeatherMicroservice` 选项用于提供位置来创建 ASP.NET Core 应用程序。

对于此微服务，我们需要尽可能简单、轻型的 Web 应用程序，因此我们使用了“ASP.NET Core 空”模板，并指定其短名称为 `web`。

此模板将为你创建以下四个文件：

* Startup.cs 文件。 其中包含应用程序的基本内容。
* Program.cs 文件。 其中包含应用程序的入口点。
* WeatherMicroservice.csproj 文件。 这是应用程序的生成文件。
* Properties/launchSettings.json 文件。 其中包含 IDE 使用的调试设置。

现在可以运行模板生成的应用程序了：

```console
dotnet run
```

此命令将首先还原生成应用程序所需的依赖项，然后生成应用程序。

默认配置侦听的是 `http://localhost:5000`。 可以打开浏览器并转到相应页面，看到的是“Hello World!” 消息。

完成后，可以按 <kbd>Ctrl</kbd>+<kbd>C</kbd> 关闭应用程序。

### <a name="anatomy-of-an-aspnet-core-application"></a>ASP.NET Core 应用程序剖析

至此，已生成应用程序，让我们来看看此应用程序功能是如何实现的。 此时，生成的文件中有两个需要特别关注：WeatherMicroservice.csproj 和 Startup.cs。 

.csproj 文件包含项目相关信息。
最有趣的两个节点是 `<TargetFramework>` 和 `<PackageReference>`。

`<TargetFramework>` 节点指定将运行此应用程序的 .NET 版本。

使用每个 `<PackageReference>` 节点指定此应用程序所需的包。

此应用程序是在 Startup.cs 中实现。 此文件包含启动类。

ASP.NET Core 基础结构调用两种方法来配置并运行此应用程序。 `ConfigureServices` 方法描述了此应用程序所需的服务。 由于要生成的是精简的微服务，因此无需配置任何依赖项。 `Configure` 方法配置传入 HTTP 请求的处理程序。 模板生成简单的处理程序来响应所有关于文本“Hello World!”的请求。

## <a name="build-a-microservice"></a>生成微服务

要生成的服务将用于传递世界各地的天气预报。 在生产应用程序中，需要调用一些服务来检索天气数据。 在此示例中，我们将生成随机天气预报服务。 

需要执行以下许多任务，才能实现随机天气预报服务：

* 分析传入请求，读取经纬度。
* 生成一些随机预报数据。
* 将随机预报数据从 C# 对象转换成 JSON 数据包。
* 将响应头设置为指示服务发送回 JSON。
* 编写响应。

下面各部分将引导你逐一完成这些步骤。

### <a name="parsing-the-query-string"></a>分析查询字符串

首先要分析查询字符串。 此服务接受在以下形式的查询字符串中使用“lat”和“long”自变量：

```
http://localhost:5000/?lat=-35.55&long=-12.35
```

只需更改定义为启动类中 `app.Run` 的自变量的 lambda 表达式。

lambda 表达式中的自变量是请求的 `HttpContext`。 其属性之一是 `Request` 对象。 `Request` 对象具有 `Query` 属性，其中包含请求查询字符串中所有值的字典。 第一次添加的代码是为了查找经纬度值：

[!code-csharp[ReadQueryString](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ReadQueryString "read variables from the query string")]

`Query` 字典值属于 `StringValue` 类型。 此类型可以包含一系列字符串。 对于天气服务，每个值都是一个字符串。 正因如此，上面的代码调用 `FirstOrDefault()`。 

接下来，需要将字符串转换成双精度类型值。 用于将字符串转换成双精度类型值的方法是 `double.TryParse()`：

```csharp
bool TryParse(string s, out double result);
```

此方法利用 C# out 参数来指示能否将输入字符串转换成双精度类型值。 如果字符串确实是双精度类型值的有效表示形式，那么此方法会返回 true，并且 `result` 自变量中包含相应的值。 如果字符串不是双精度类型值的有效表示形式，则此方法返回 false。

能够使用返回*可以为 null 的双精度类型值*的*扩展方法*来调整此 API。 *可以为 null 的值类型*是某种值类型的类型表示形式，还可以保留缺少的值或 null 值。 可以为 null 的类型以类型声明中追加的 `?` 字符表示。 

虽然扩展方法被定义为静态方法，但可以在第一个参数中添加 `this` 修饰符，这样便能调用扩展方法，就像是相应类的成员方法一样。 只能在静态类中定义扩展方法。 下面定义了包含用于分析的扩展方法的类：

[!code-csharp[TryParseExtension](../../../samples/csharp/getting-started/WeatherMicroservice/Extensions.cs#TryParseExtension "try parse to a nullable")]

调用扩展方法前，将当前区域性更改为固定区域性：

[!code-csharp[SetCulture](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#SetCulture "set current culture to invariant")]

这可以确保应用程序在任意服务器上用相同的方式解析数字，而不管其默认区域性。

现在，可以使用此扩展方法将查询字符串自变量转换成双精度类型：

[!code-csharp[UseTryParse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#UseTryParse "Use the try parse extension method")]

为了能够轻松测试分析代码，请将响应更新为包含以下自变量值：

[!code-csharp[WriteResponse](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#WriteResponse "Write the output response")]

此时，可以运行 Web 应用程序，并检查分析代码是否有效。 在浏览器中向 Web 请求添加值，应该能够看到更新后的结果。

### <a name="build-a-random-weather-forecast"></a>生成随机天气预报

下一个任务是生成随机天气预报。 让我们从包含天气预报所需值的数据容器入手：

```csharp
public class WeatherReport
{
    private static readonly string[] PossibleConditions =
    {
        "Sunny",
        "Mostly Sunny",
        "Partly Sunny",
        "Partly Cloudy",
        "Mostly Cloudy",
        "Rain"
    };

    public int HighTemperatureFahrenheit { get; }
    public int LowTemperatureFahrenheit { get; }
    public int AverageWindSpeedMph { get; }
    public string Condition { get; }
}
```

接下来，生成用于随机设置这些值的构造函数。 此构造函数将经纬度值用作 `Random` 数生成器的源。 也就是说，同一地理位置的天气预报也是相同的。 如果更改经纬度自变量，将会生成不同的天气预报（因为源不同）。

[!code-csharp[WeatherReportConstructor](../../../samples/csharp/getting-started/WeatherMicroservice/WeatherReport.cs#WeatherReportConstructor "Weather Report Constructor")]

现在可以在响应方法中生成 5 天的天气预报：

```csharp
if (latitude.HasValue && longitude.HasValue)
{
    var forecast = new List<WeatherReport>();
    for (var days = 1; days <= 5; days++)
    {
        forecast.Add(new WeatherReport(latitude.Value, longitude.Value, days));
    }
}
```

### <a name="build-the-json-response"></a>生成 JSON 响应

服务器的最终代码任务是将 `WeatherReport` 列表转换为 JSON 文档并将其发送回客户端。 首先，我们要创建 JSON 文档。 将把 Newtonsoft JSON 序列化程序添加到依赖项列表中。 可以使用以下 `dotnet` 命令执行此操作：

```console
dotnet add package Newtonsoft.Json
```

然后，可以使用 `JsonConvert` 类将对象写入字符串：

[!code-csharp[ConvertToJson](../../../samples/csharp/getting-started/WeatherMicroservice/Startup.cs#ConvertToJSON "Convert objects to JSON")]

上面的代码将 forecast 对象（`WeatherForecast` 对象列表）转换成 JSON 文档。 构造响应文档后，将内容类型设置为 `application/json`，并编写字符串。

应用程序现在可以运行并返回随机天气预报。

## <a name="build-a-docker-image"></a>生成 Docker 映像

最后一项任务是在 Docker 中运行应用程序。 我们将创建一个 Docker 容器，用于运行表示此应用程序的 Docker 映像。

***Docker 映像***是定义应用程序运行环境的文件。

***Docker 容器***表示正在运行的 Docker 映像实例。

通过类推，可以将 *Docker 映像*视为*类*，将 *Docker 容器*视为对象或此类的实例。  

以下 Dockerfile 可供我们自行使用：

```
FROM microsoft/dotnet:2.1-sdk AS build
WORKDIR /app

# Copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# Copy everything else and build
COPY . ./
RUN dotnet publish -c Release -o out

# Build runtime image
FROM microsoft/dotnet:2.1-aspnetcore-runtime
WORKDIR /app
COPY --from=build /app/out .
ENTRYPOINT ["dotnet", "WeatherMicroservice.dll"]
```

我们先来介绍一下此文件的内容。

第一行指定用于生成应用程序的源映像：

```
FROM microsoft/dotnet:2.1-sdk AS build
```

通过 Docker，可以根据源模板配置计算机映像。 也就是说，开始时并不需要提供所有计算机参数，只需提供全部更改。 此处所说的更改包括我们的应用程序在内。

在此示例中，我们将使用 `dotnet` 映像的 `2.1-sdk` 版本。 这是创建有效 Docker 环境的最简单方式。 此映像包括 .NET Core 运行时和 .NET Core SDK。
这使得入门和生成更加轻松，但是创建的映像会更大，所以我们将使用此映像生成应用程序，使用另一个映像运行应用程序。

下面几行代码用于设置并生成应用程序：

```
WORKDIR /app

# Copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# Copy everything else and build
COPY . ./
RUN dotnet publish -c Release -o out
```

这会将当前目录中的项目文件复制到 Docker VM 中，并还原所有包。 使用 .NET CLI 意味着 Docker 映像必须包含 .NET Core SDK。 完成上述操作之后，应用程序的其余部分会得到复制，然后 `dotnet
publish` 命令会生成并打包应用程序。

最后，我们创建运行应用程序的第二个 Docker 映像：

```
# Build runtime image
FROM microsoft/dotnet:2.1-aspnetcore-runtime
WORKDIR /app
COPY --from=build /app/out .
ENTRYPOINT ["dotnet", "WeatherMicroservice.dll"]
```

此映像使用 `dotnet` 映像的 `2.1-aspnetcore-runtime` 版本，其中包含运行 ASP.NET Core 应用程序所需的全部内容，但是不包括 .NET Core SDK。 这意味着，此映像不能用于生成 .NET Core 应用程序，但它可以使最终映像变得更小。

为了实现此目的，我们将生成的应用程序从第一个映像复制到第二个。

`ENTRYPOINT` 命令通知 Docker 启动服务的命令。

## <a name="building-and-running-the-image-in-a-container"></a>在容器中生成并运行映像

让我们在 Docker 容器中生成映像并运行服务。 不是要将本地目录中的所有文件都复制到映像中， 而是要在容器中生成应用程序。 将创建 `.dockerignore` 文件来指定不要复制到映像中的目录。 你不想复制任何生成资产。 请在 `.dockerignore` 文件中指定生成和发布目录：

```
bin/*
obj/*
out/*
```

使用 `docker build` 命令生成映像。 从包含代码的目录运行以下命令。

```console
docker build -t weather-microservice .
```

此命令将根据 Dockerfile 中的所有信息生成容器映像。 `-t` 自变量提供此容器映像的标记或名称。 在上面的命令行中，Docker 容器的标记是 `weather-microservice`。 此命令完成后，就生成了一个可用于运行新服务的容器。 

运行以下命令，启动容器和服务：

```console
docker run -d -p 80:80 --name hello-docker weather-microservice
```

`-d` 选项表示运行从当前终端拆离出来的容器。 也就是说，终端中不会显示命令输出。 `-p` 选项指示服务和主机之间的端口映射。 即指应将端口 80 上的所有传入请求都转发到容器上的端口 80。 使用 80 与服务正在侦听的端口相匹配，这是生产应用程序的默认端口。 `--name` 自变量用于命名正在运行的容器。 此名称可方便与容器结合使用。

可以运行以下命令来确定映像能否正常运行：

```console
docker ps
```

如果容器能正常运行，那么正在运行的进程中就会有一行列出它来 （可能是唯一的。）

可以打开浏览器并转到 localhost，然后指定经纬度，从而测试服务：

```
http://localhost/?lat=35.5&long=40.75
```

## <a name="attaching-to-a-running-container"></a>附加到正在运行的容器

在命令窗口中运行服务时，可以查看针对各个请求打印输出的诊断信息。 如果容器是在拆离模式下运行，则看不到此类信息。 使用 Docker 附加命令，可以将窗口附加到正在运行的容器，以便查看日志信息。  在命令窗口中运行以下命令：

```console
docker attach --sig-proxy=false hello-docker
```

`--sig-proxy=false` 自变量表示 <kbd>Ctrl</kbd>+<kbd>C</kbd> 命令未发送到容器进程，而是停止运行 `docker attach` 命令。 最后的自变量是为 `docker run` 命令中的容器命名的名称。 

> [!NOTE]
> 还可以使用 Docker 分配的容器 ID 来引用任何容器。 如果没有在 `docker run` 中指定容器名称，则必须使用容器 ID。

打开浏览器并转到服务。 将可以在命令窗口中查看附加的正在运行的容器生成的诊断消息。

按 <kbd>Ctrl</kbd>+<kbd>C</kbd> 可停止附加进程。

使用完后，可以停止运行容器：

```console
docker stop hello-docker
```

容器和映像仍可供重启。  若要从计算机中删除容器，可以运行以下命令：

```console
docker rm hello-docker
```

若要从计算机中删除未使用的映像，可以运行以下命令：

```console
docker rmi weather-microservice
```

## <a name="conclusion"></a>结束语 

在此教程中，你生成了 ASP.NET Core 微服务，并添加了一些简单的功能。

此外，你还生成了此服务的 Docker 容器映像，并在计算机上运行了相应的容器。 最后，你还将终端窗口附加到了服务中，并查看服务生成的诊断消息。

与此同时，你还了解了多项 C# 语言功能的实际运用。

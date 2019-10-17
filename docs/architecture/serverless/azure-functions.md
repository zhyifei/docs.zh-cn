---
title: Azure Functions-无服务器应用
description: Azure 函数提供跨多种语言（C#、JavaScript、Java）和平台的无服务器功能，以提供事件驱动的即时缩放代码。
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 5e8187b3752a0f0d0bcf8e15f2ce440dc5a64e45
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522878"
---
# <a name="azure-functions"></a>Azure Functions

Azure 函数提供无服务器的计算体验。 函数由*触发器*调用（如访问 HTTP 终结点或计时器），并执行代码块或业务逻辑。 函数还支持连接到存储和队列等资源的专用*绑定*。

![Azure 函数徽标](./media/azure-functions-logo.png)

Azure Functions 框架有两个版本。 旧版本支持完整 .NET Framework，而新的运行时支持跨平台的 .NET Core 应用程序。 支持除 JavaScript C# 、 F#和 Java 之外的其他语言。 在门户中创建的函数提供丰富的脚本编写语法。 可以通过完全的平台支持和功能来部署作为独立项目创建的函数。

有关详细信息，请参阅[Azure Functions 文档](https://docs.microsoft.com/azure/azure-functions)。

## <a name="functions-v1-vs-v2"></a>函数 v1 与 v2

Azure Functions 运行时有两个版本：1.x 和2.x。 版本1.x 正式发布（GA）。 它通过门户或 Windows 计算机支持 .NET 开发，并使用 .NET Framework。 1.x 支持C#、JavaScript 和，并F#提供对 Python、PHP、TypeScript、Batch、Bash 和 PowerShell 的实验性支持。

[版本2.x 现已正式发布](https://azure.microsoft.com/blog/introducing-azure-functions-2-0/)。 它利用 .NET Core，并支持在 Windows、macOS 和 Linux 计算机上进行跨平台开发。 2.x 为 Java 添加一流的支持，但并不直接支持任何实验性语言。 版本2.x 使用新的绑定扩展性模型，该模型启用平台的第三方扩展、独立的绑定版本控制和更精简的执行环境。

> **在1.x 中存在一个已知问题，其中包含[绑定重定向支持](https://github.com/Azure/azure-functions-host/issues/992)。** 此问题特定于 .NET 开发。 对于依赖于运行时中包含的库不同版本的库，具有依赖项的项目会受到影响。 函数团队已致力于对问题进行具体的进度。 团队将在2.x 中处理绑定重定向，然后再将其公开上市。 此处提供了具有建议的修补程序和解决方法的官方团队声明： [Azure Functions 中的程序集解析](https://github.com/Azure/azure-functions-host/wiki/Assembly-Resolution-in-Azure-Functions)。

有关详细信息，请参阅[比较1.x 和](https://docs.microsoft.com/azure/azure-functions/functions-versions)2.x。

## <a name="programming-language-support"></a>编程语言支持

公开上市（GA）、预览或实验支持以下语言。

|语言      |1.x         |2.x      |
|--------------|------------|---------|
|**C#**        |上市          |预览  |
|**JavaScript**|上市          |预览  |
|**F#**        |上市          |         |
|**Java**      |            |预览  |
|**Python**    |实验|         |
|**PHP**       |实验|         |
|**TypeScript**|实验|         |
|**Batch**     |实验|         |
|**狂欢**      |实验|         |
|**PowerShell**|实验|         |

有关详细信息，请参阅[支持的语言](https://docs.microsoft.com/azure/azure-functions/supported-languages)。

## <a name="app-service-plans"></a>应用服务计划

函数由*应用服务计划*支持。 计划定义函数应用使用的资源。 你可以将计划分配给某个区域，确定将使用的虚拟机的大小和数量，并选择定价层。 对于真正无服务器方法，函数应用可以使用**消耗**计划。 消耗计划将根据负载自动缩放后端。

有关详细信息，请参阅[应用服务计划](https://docs.microsoft.com/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview)。

## <a name="create-your-first-function"></a>创建第一个函数

可以通过三种常用方法创建函数应用。

- 在门户中编写函数脚本。
- 使用 Azure 命令行接口（CLI）创建必要的资源。
- 使用最喜欢的 IDE 在本地生成函数并将其发布到 Azure。

有关在门户中创建脚本函数的详细信息，请参阅在[Azure 门户中创建第一个函数](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function)。

若要从 Azure CLI 生成，请参阅[使用 Azure CLI 创建第一个函数](https://docs.microsoft.com/azure/azure-functions/functions-create-first-azure-function-azure-cli)。

若要从 Visual Studio 创建函数，请参阅[使用 Visual Studio 创建第一个函数](https://docs.microsoft.com/azure/azure-functions/functions-create-your-first-function-visual-studio)。

## <a name="understand-triggers-and-bindings"></a>了解触发器和绑定

函数由*触发器*调用，只能有一个。 除了调用函数外，某些触发器还用作绑定。 除了触发器外，还可以定义多个绑定。 *绑定*提供了将数据连接到代码的声明性方式。 它们可以传入（输入）或接收数据（输出）。 触发器和绑定使函数易于使用。 绑定消除了手动创建数据库或文件系统连接的系统开销。 绑定所需的所有信息都包含在脚本中的特殊*函数 json*文件中，或在代码中用特性声明。

一些常见触发器包括：

- Blob 存储：在存储中上载或更改文件或文件夹时调用函数。
- HTTP：调用函数，如 REST API。
- Queue：在队列中存在项时调用函数。
- Timer：对定期节奏调用函数。

绑定示例包括：

- CosmosDB：轻松连接到数据库以加载或保存文件。
- 表存储：使用函数应用中的键/值存储。
- 队列存储：轻松地从队列中检索项，或在队列中放置新项。

下面的示例*函数 json*文件定义了触发器和绑定：

```json
{
  "bindings": [
    {
      "name": "myBlob",
      "type": "blobTrigger",
      "direction": "in",
      "path": "images/{name}",
      "connection": "AzureWebJobsStorage"
    },
    {
      "name": "$return",
      "type": "queue",
      "direction": "out",
      "queueName": "images",
      "connection": "AzureWebJobsStorage"
    }
  ],
  "disabled": false
}
```

在此示例中，该函数通过对 `images` 容器中的 blob 存储的更改触发。 传递文件的信息，因此触发器也充当绑定。 另一个绑定用于将信息放到名为 `images` 的队列中。

下面是该C#函数的脚本：

```csharp
public static string Run(Stream myBlob, string name, TraceWriter log)
{
    log.Info($"C# Blob trigger function Processed blob\n Name:{name} \n Size: {myBlob.Length} Bytes");
    return name;
}
```

该示例是一个简单的函数，该函数采用已修改或已上传到 blob 存储的文件的名称，并将其放在队列中供以后处理。

有关触发器和绑定的完整列表，请参阅[Azure Functions 触发器和绑定概念](https://docs.microsoft.com/azure/azure-functions/functions-triggers-bindings)。

## <a name="proxies"></a>代理

代理为应用程序提供重定向功能。 代理公开终结点，并将该终结点映射到另一个资源。 对于代理，你可以：

- 将传入请求重新路由到另一个终结点。
- 在传递请求之前修改传入请求。
- 修改或提供响应。

代理用于以下方案：

- 简化、缩短或更改 URL。
- 为多个后端服务提供一致的 API 前缀。
- 模拟响应正在开发的终结点。
- 提供对已知终结点的静态响应。
- 在移动或迁移后端时保持 API 终结点的一致性。

代理存储为 JSON 定义。 下面是一个示例：

```json
{
  "$schema": "http://json.schemastore.org/proxies",
  "proxies": {
    "Domain Redirect": {
      "matchCondition": {
        "route": "/{shortUrl}"
      },
      "backendUri": "http://%WEBSITE_HOSTNAME%/api/UrlRedirect/{shortUrl}"
    },
    "Root": {
      "matchCondition": {
        "route": "/"
      },
      "responseOverrides": {
        "response.statusCode": "301",
        "response.statusReason": "Moved Permanently",
        "response.headers.location": "https://docs.microsoft.com/"
      }
    }
  }
}
```

@No__t-0 代理使用缩短路由，并将其映射到较长的函数资源。 转换如下所示：

`https://--shorturl--/123` -> `https://--longurl--.azurewebsites.net/api/UrlRedirect/123`

@No__t-0 代理使用发送到根 URL （`https://--shorturl--/`）的任何内容，并将其重定向到文档站点。

视频[Azure：使用无服务器 Azure Functions 将你的应用引入到云中](https://channel9.msdn.com/events/Connect/2017/E102)。 在本地 SQL Server 上运行的 ASP.NET Core 应用程序将被迁移到 Azure 云。 代理用于帮助重构传统 Web API 项目，以使用函数。

有关代理的详细信息，请参阅[使用 Azure Functions 代理](https://docs.microsoft.com/azure/azure-functions/functions-proxies)。

>[!div class="step-by-step"]
>[上一页](azure-serverless-platform.md)
>[下一页](application-insights.md)

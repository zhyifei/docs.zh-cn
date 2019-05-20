---
title: 将模型部署到 Azure Functions
description: 使用 Azure Functions 通过 Internet 提供 ML.NET 情绪分析机器学习模型进行预测
ms.date: 05/03/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: 9e62d8826227aed07451387cc733d27094327f99
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645099"
---
# <a name="deploy-a-model-to-azure-functions"></a>将模型部署到 Azure Functions

了解如何通过 Azure Functions 无服务器环境部署预先训练的 ML.NET 机器学习模型，以便通过 HTTP 进行预测。

> [!NOTE]
> `PredictionEnginePool` 服务扩展目前处于预览状态。

## <a name="prerequisites"></a>系统必备

- 安装了“.NET Core 跨平台开发”工作负载和“Azure 开发”的 [Visual Studio 2017 15.6 或更高版本](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017)。
- [Azure Functions 工具](/azure/azure-functions/functions-develop-vs#check-your-tools-version)
- Powershell
- 预先定型的模型。 使用 [ML.NET 情绪分析教程](../tutorials/sentiment-analysis.md)生成自己的模型，或下载此[预先训练的情绪分析机器学习模型](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)

## <a name="create-azure-functions-project"></a>创建 Azure Functions 项目

1. 打开 Visual Studio 2017。 从菜单栏中选择“文件” > “新建” > “项目”。 在“新项目”对话框中，依次选择“Visual C#”节点和“云”节点。 然后，选择“Azure Functions”项目模板。 在“名称”文本框中，键入“SentimentAnalysisFunctionsApp”，再选择“确定”按钮。
1. 在“新项目”对话框中，打开项目选项上方的下拉列表，并选择“Azure Functions v2 (.NET Core)”。 然后，依次选择“Http 触发器”项目和“确定”按钮。
1. 在项目中创建“MLModels”目录，用于保存模型：

    在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新文件夹”。 键入“MLModels”，再按 Enter。

1. 安装“Microsoft.ML NuGet 包”：

    在“解决方案资源管理器”中，右键单击项目，然后选择“管理 NuGet 包”。 将“nuget.org”选择为“包源”，选择“浏览”选项卡并搜索“Microsoft.ML”，在列表中选择该包，然后选择“安装”按钮。 选择“预览更改”对话框上的“确定”按钮，如果你同意所列包的许可条款，则选择“接受许可”对话框上的“我接受”按钮。

1. 安装 **Microsoft.Extensions.ML NuGet 包**：

    在“解决方案资源管理器”中，右键单击项目，然后选择“管理 NuGet 包”。 选择“nuget.org”作为包源，然后选择“浏览”选项卡并搜索“Microsoft.Extensions.ML”，在列表中选择包，再选择“安装”按钮。 选择“预览更改”对话框上的“确定”按钮，如果你同意所列包的许可条款，则选择“接受许可”对话框上的“我接受”按钮。

## <a name="add-pre-trained-model-to-project"></a>将预先训练的模型添加到项目

1. 将预生成的模型复制到 MLModels 文件夹。
1. 在“解决方案资源管理器”中，右键单击预生成的模型文件，并选择“属性”。 在“高级”下，将“复制到输出目录”的值更改为“如果较新则复制”。

## <a name="create-azure-function-to-analyze-sentiment"></a>创建 Azure 函数用于分析情绪

创建情绪预测类。 向项目添加一个新类：

1. 在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新项”。

1. 在“添加新项”对话框中，选择“Azure 函数”，并将“名称”字段更改为“AnalyzeSentiment.cs”。 然后，选择“添加”按钮。

1. 在“新 Azure 函数”对话框中，选择“Http 触发器”。 然后，选择“确定”按钮。

    此时，AnalyzeSentiment.cs 文件在代码编辑器中打开。 将以下 `using` 语句添加到 *AnalyzeSentiment.cs* 的顶部：

    ```csharp
    using System;
    using System.IO;
    using System.Threading.Tasks;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Azure.WebJobs;
    using Microsoft.Azure.WebJobs.Extensions.Http;
    using Microsoft.AspNetCore.Http;
    using Microsoft.Extensions.Logging;
    using Newtonsoft.Json;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisFunctionsApp.DataModels;
    ```

    默认情况下，`AnalyzeSentiment` 类为 `static`。 确保从类定义中删除 `static` 关键字。

    ```csharp
    public class AnalyzeSentiment
    {
    
    }
    ```

## <a name="create-data-models"></a>创建数据模型

需要为输入数据和预测创建一些类。 向项目添加一个新类：

1. 在项目中创建“DataModels”目录，用于保存数据模型：在“解决方案资源管理器”中，右键单击项目，并依次选择“添加”>“新文件夹”。 键入“DataModels”，再按 Enter。
2. 在“解决方案资源管理器”中，右键单击“DataModels”目录，再依次选择“添加”>“新项”。
3. 在“添加新项”对话框中，选择“类”并将“名称”字段更改为“SentimentData.cs”。 然后，选择“添加”按钮。 

    “SentimentData.cs”文件随即在代码编辑器中打开。 将以下 using 语句添加到 SentimentData.cs 顶部：

    ```csharp
    using Microsoft.ML.Data;
    ```

    删除现有类定义，并将以下代码添加到 SentimentData.cs 文件：
    
    ```csharp
    public class SentimentData
    {
        [LoadColumn(0)]
        public string SentimentText;

        [LoadColumn(1)]
        [ColumnName("Label")]
        public bool Sentiment;
    }
    ```

4. 在“解决方案资源管理器”中，右键单击“DataModels”目录，再依次选择“添加”>“新项”。
5. 在“添加新项”对话框中，选择“类”，并将“名称”字段更改为“SentimentPrediction.cs”。 然后，选择“添加”按钮。 此时，SentimentPrediction.cs 文件在代码编辑器中打开。 将以下 using 语句添加到 SentimentPrediction.cs 顶部：

    ```csharp
    using Microsoft.ML.Data;
    ```

    删除现有类定义，并将以下代码添加到 SentimentPrediction.cs 文件：

    ```csharp
    public class SentimentPrediction : SentimentData
    {

        [ColumnName("PredictedLabel")]
        public bool Prediction { get; set; }

        public float Probability { get; set; }

        public float Score { get; set; }
    }
    ```

    `SentimentPrediction` 继承自 `SentimentData`，后者提供对 `SentimentText` 属性中原始数据以及模型生成的输出的访问。

## <a name="register-predictionenginepool-service"></a>注册 PredictionEnginePool 服务

若要进行单个预测，请使用 [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)。 若要在应用程序中使用 [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)，则必须在需要时创建它。 在这种情况下，可考虑的最佳做法是依赖项注入。

若要详细了解[依赖关系注入](https://en.wikipedia.org/wiki/Dependency_injection)，请单击下面的链接。

1. 在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新项”。
1. 在“添加新项”对话框中，选择“类”并将“名称”字段更改为“Startup.cs”。 然后，选择“添加”按钮。 

    此时，*Startup.cs* 文件在代码编辑器中打开。 将以下 using 语句添加到 *Startup.cs* 的顶部：

    ```csharp
    using Microsoft.Azure.WebJobs;
    using Microsoft.Azure.WebJobs.Hosting;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisFunctionsApp;
    using SentimentAnalysisFunctionsApp.DataModels;
    ```

    删除 using 语句下面的现有代码，并将以下代码添加到 *Startup.cs* 文件中：

    ```csharp
    [assembly: WebJobsStartup(typeof(Startup))]
    namespace SentimentAnalysisFunctionsApp
    {
        class Startup : IWebJobsStartup
        {
            public void Configure(IWebJobsBuilder builder)
            {
                builder.Services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
                    .FromFile("MLModels/sentiment_model.zip");
            }
        }
    }
    ```

概括地讲，此代码在应用程序请求时自动初始化对象和服务，你无需手动执行初始化。

> [!WARNING]
> [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) 不是线程安全型。 为了提高性能和线程安全性，请使用 `PredictionEnginePool` 服务，该服务可创建 `PredictionEngine` 对象的 [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) 供应用程序使用。 

## <a name="register-startup-as-an-azure-functions-extension"></a>将 Startup 注册为 Azure Functions 扩展

若要在应用程序中使用 `Startup`，需要将其注册为 Azure Functions 扩展。 在项目中创建名为 *extensions.json* 的新文件（如果尚不存在）。

1. 在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新项”。
1. 在“新建项目”对话框中，依次选择“Visual C#”节点和“Web”节点。 然后选择“Json 文件”选项。 在“名称”文本框中，键入“extensions.json”，然后选择“确定”按钮。

    此时，*extensions.json* 文件在代码编辑器中打开。 将以下内容添加到 *extensions.json*：
    
    ```json
    {
      "extensions": [
        {
          "name": "Startup",
          "typename": "SentimentAnalysisFunctionsApp.Startup, SentimentAnalysisFunctionsApp, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null"
        }
      ]
    }
    ```

1. 在解决方案资源管理器中，右键单击 *extensions.json* 文件，然后选择“属性”。 在“高级”下，将“复制到输出目录”的值更改为“如果较新则复制”。

## <a name="load-the-model-into-the-function"></a>将模型加载到函数中

在 *AnalyzeSentiment* 类中插入以下代码：

```csharp
private readonly PredictionEnginePool<SentimentData, SentimentPrediction> _predictionEnginePool;

// AnalyzeSentiment class constructor
public AnalyzeSentiment(PredictionEnginePool<SentimentData, SentimentPrediction> predictionEnginePool)
{
    _predictionEnginePool = predictionEnginePool;
}
```

此代码通过将 `PredictionEnginePool` 传递给函数的构造函数（通过依赖项注入获得）来分配它。

## <a name="use-the-model-to-make-predictions"></a>使用模型进行预测

将 AnalyzeSentiment 类中 Run 方法的现有实现替换为以下代码：

```csharp
[FunctionName("AnalyzeSentiment")]
public async Task<IActionResult> Run(
[HttpTrigger(AuthorizationLevel.Function, "post", Route = null)] HttpRequest req,
ILogger log)
{
    log.LogInformation("C# HTTP trigger function processed a request.");

    //Parse HTTP Request Body
    string requestBody = await new StreamReader(req.Body).ReadToEndAsync();
    SentimentData data = JsonConvert.DeserializeObject<SentimentData>(requestBody);
    
    //Make Prediction
    SentimentPrediction prediction = _predictionEnginePool.Predict(data);

    //Convert prediction to string
    string sentiment = Convert.ToBoolean(prediction.Prediction) ? "Positive" : "Negative";

    //Return Prediction
    return (ActionResult)new OkObjectResult(sentiment);
}
```

执行 `Run` 方法时，来自 HTTP 请求的传入数据被反序列化并用作 `PredictionEnginePool` 的输入。 随后调用 `Predict` 方法生成预测并将结果返回给用户。 

## <a name="test-locally"></a>在本地测试

至此，已完成所有设置，是时候测试应用程序了：

1. 运行此应用程序
1. 打开 PowerShell，并在提示符中输入代码（其中，PORT 是应用程序运行所在的端口）。 端口通常是 7071。

    ```powershell
    Invoke-RestMethod "http://localhost:<PORT>/api/AnalyzeSentiment" -Method Post -Body (@{SentimentText="This is a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    如果成功，输出文本应如下所示：
    
    ```powershell
    Negative
    ```

祝贺你！ 你已成功使用 Azure Functions 通过 Internet 提供模型进行预测。

## <a name="next-steps"></a>后续步骤

- [部署到 Azure](/azure/azure-functions/functions-develop-vs#publish-to-azure)

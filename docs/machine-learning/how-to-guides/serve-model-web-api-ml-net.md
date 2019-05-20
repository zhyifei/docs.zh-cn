---
title: 在 ASP.NET Core Web API 中部署模型
description: 使用 ASP.NET Core Web API 通过 Internet 提供 ML.NET 情绪分析机器学习模型
ms.date: 05/03/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to
ms.openlocfilehash: f8b8f74f752aeb243d4a2987929bd28ddc5f7d5a
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641079"
---
# <a name="deploy-a-model-in-an-aspnet-core-web-api"></a>在 ASP.NET Core Web API 中部署模型

了解如何使用 ASP.NET Core Web API 在 Web 上提供预先训练的 ML.NET 机器学习模型。 通过 Web API 提供模型可实现通过标准 HTTP 方法进行预测。

> [!NOTE]
> `PredictionEnginePool` 服务扩展目前处于预览状态。

## <a name="prerequisites"></a>系统必备

- 安装了“.NET Core 跨平台开发”工作负载的 [Visual Studio 2017 15.6 或更高版本](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017)。
- PowerShell。
- 预先定型的模型。 使用 [ML.NET 情绪分析教程](../tutorials/sentiment-analysis.md)生成自己的模型，或下载此[预先训练的情绪分析机器学习模型](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)

## <a name="create-aspnet-core-web-api-project"></a>创建 ASP.NET Core Web API 项目

1. 打开 Visual Studio 2017。 从菜单栏中依次选择“文件”>“新建”>“项目”。 在“新项目”对话框中，依次选择“Visual C#”节点和“Web”节点。 然后，选择“ASP.NET Core Web 应用程序”项目模板。 在“名称”文本框中，键入“SentimentAnalysisWebAPI”，再选择“确定”按钮。

1. 在显示不同类型 ASP.NET Core 项目的窗口中，依次选择“API”和“确定”按钮。

1. 在项目中创建“MLModels”目录，用于保存预生成的机器学习模型文件：

    在“解决方案资源管理器”中，右键单击项目，并依次选择“添加”>“新文件夹”。 键入“MLModels”，再按 Enter。

1. 安装“Microsoft.ML NuGet 包”：

    在“解决方案资源管理器”中，右键单击项目，然后选择“管理 NuGet 包”。 选择“nuget.org”作为“包源”，选择“浏览”选项卡并搜索“Microsoft.ML”，再依次选择列表中的相应包和“安装”按钮。 选择“预览更改”对话框中的“确定”按钮；如果同意所列包的许可条款，请选择“接受许可”对话框中的“我接受”按钮。

1. 安装 **Microsoft.Extensions.ML Nuget 包**：

    在“解决方案资源管理器”中，右键单击项目，然后选择“管理 NuGet 包”。 选择“nuget.org”作为包源，然后选择“浏览”选项卡并搜索“Microsoft.Extensions.ML”，在列表中选择包，再选择“安装”按钮。 选择“预览更改”对话框中的“确定”按钮；如果同意所列包的许可条款，请选择“接受许可”对话框中的“我接受”按钮。

### <a name="add-model-to-aspnet-core-web-api-project"></a>将模型添加到 ASP.NET Core Web API 项目

1. 将预生成的模型复制到 MLModels 目录
1. 在“解决方案资源管理器”中，右键单击模型 zip 文件，并选择“属性”。 在“高级”下，将“复制到输出目录”的值更改为“如果较新则复制”。

## <a name="create-data-models"></a>创建数据模型

需要为输入数据和预测创建一些类。 向项目添加一个新类：

1. 在项目中创建“DataModels”目录，用于保存数据模型：

    在“解决方案资源管理器”中，右键单击项目，并依次选择“添加”>“新文件夹”。 键入“DataModels”，再按 Enter。

2. 在“解决方案资源管理器”中，右键单击“DataModels”目录，再依次选择“添加”>“新项”。
3. 在“添加新项”对话框中，选择“类”并将“名称”字段更改为“SentimentData.cs”。 然后，选择“添加”按钮。 “SentimentData.cs”文件随即在代码编辑器中打开。 将以下 using 语句添加到 SentimentData.cs 顶部：

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

    `SentimentPrediction` 继承自 `SentimentData`。 这样可以更轻松地查看 `SentimentText` 属性中的原始数据以及模型生成的输出。 

## <a name="register-predictionenginepool-for-use-in-the-application"></a>注册 PredictionEnginePool 用于应用程序

若要进行单个预测，请使用 [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)。 若要在应用程序中使用 [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)，则必须在需要时创建它。 在这种情况下，可考虑的最佳做法是依赖项注入。

如果想要了解 [ASP.NET Core 中的依赖项注入](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1)，以下链接提供详细信息。

1. 打开 Startup.cs 类，并将以下 using 语句添加到文件顶部：

    ```csharp
    using Microsoft.AspNetCore.Builder;
    using Microsoft.AspNetCore.Hosting;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.Configuration;
    using Microsoft.Extensions.DependencyInjection;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

2. 将以下代码添加到 *ConfigureServices* 方法中：

    ```csharp
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddMvc().SetCompatibilityVersion(CompatibilityVersion.Version_2_1);
        services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
            .FromFile("MLModels/sentiment_model.zip");
    }
    ```

概括地讲，此代码在应用程序请求时自动初始化对象和服务，你无需手动执行初始化。

> [!WARNING]
> [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) 不是线程安全型。 为了提高性能和线程安全性，请使用 `PredictionEnginePool` 服务，该服务可创建 `PredictionEngine` 对象的 [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) 供应用程序使用。 阅读以下博客文章，了解有关[在 ASP.NET Core 中创建和使用 `PredictionEngine` 对象池](https://devblogs.microsoft.com/cesardelatorre/how-to-optimize-and-run-ml-net-models-on-scalable-asp-net-core-webapis-or-web-apps/)的详细信息。  

## <a name="create-predict-controller"></a>创建预测控制器

若要处理传入的 HTTP 请求，请创建控制器。

1. 在“解决方案资源管理器”中，右键单击“Controllers”目录，再依次选择“添加”>“控制器”。
1. 在“添加新项”对话框中，依次选择“空 API 控制器”和“添加”。
1. 在提示窗口中，将“控制器名称”字段更改为“PredictController.cs”。 然后，选择“添加”按钮。 此时，PredictController.cs 文件在代码编辑器中打开。 将以下 using 语句添加到 PredictController.cs 顶部：

    ```csharp
    using System;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

    删除现有类定义，并将以下代码添加到 PredictController.cs 文件：
    
    ```csharp
    public class PredictController : ControllerBase
    {
        private readonly PredictionEnginePool<SentimentData, SentimentPrediction> _predictionEnginePool;

        public PredictController(PredictionEnginePool<SentimentData,SentimentPrediction> predictionEnginePool)
        {
            _predictionEnginePool = predictionEnginePool;
        }

        [HttpPost]
        public ActionResult<string> Post([FromBody] SentimentData input)
        {
            if(!ModelState.IsValid)
            {
                return BadRequest();
            }

            SentimentPrediction prediction = _predictionEnginePool.Predict(input);

            string sentiment = Convert.ToBoolean(prediction.Prediction) ? "Positive" : "Negative";

            return Ok(sentiment);
        }
    }
    ```

此代码通过将 `PredictionEnginePool` 传递给控制器的构造函数（通过依赖项注入获得）来分配它。 然后，`Predict` 控制器的 `Post` 方法使用 `PredictionEnginePool` 进行预测，并在成功时将结果返回给用户。

## <a name="test-web-api-locally"></a>在本地测试 Web API

完成所有设置后，是时候测试应用程序了。

1. 运行该应用程序。
1. 打开 Powershell，并输入以下代码（其中，PORT 是应用程序正在侦听的端口）。

    ```powershell
    Invoke-RestMethod "https://localhost:<PORT>/api/predict" -Method Post -Body (@{Text="This was a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    如果成功，输出文本应如下所示：
    
    ```powershell
    Negative
    ```

祝贺你！ 已成功提供模型用于使用 ASP.NET Core Web API 通过 Internet 进行预测。

## <a name="next-steps"></a>后续步骤

- [部署到 Azure](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs?view=aspnetcore-2.1#deploy-the-app-to-azure)

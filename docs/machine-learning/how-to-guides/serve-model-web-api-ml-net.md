---
title: 使用 ASP.NET Core Web API 提供机器学习模型
description: 使用 ASP.NET Core Web API 通过 Internet 提供 ML.NET 情绪分析机器学习模型
ms.date: 03/05/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 07b751caff8ef0ca9a23bed68ddf88feb7b5ae4f
ms.sourcegitcommit: 69bf8b719d4c289eec7b45336d0b933dd7927841
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2019
ms.locfileid: "57856697"
---
# <a name="how-to-serve-machine-learning-model-through-aspnet-core-web-api"></a><span data-ttu-id="3b233-103">操作说明：通过 ASP.NET Core Web API 提供机器学习模型</span><span class="sxs-lookup"><span data-stu-id="3b233-103">How-To: Serve Machine Learning Model Through ASP.NET Core Web API</span></span>

<span data-ttu-id="3b233-104">本操作说明介绍了如何使用 ASP.NET Core Web API 向 Web 提供预生成的 ML.NET 机器学习模型。</span><span class="sxs-lookup"><span data-stu-id="3b233-104">This how-to shows how to serve a pre-built ML.NET machine learning model to the web using an ASP.NET Core Web API.</span></span> <span data-ttu-id="3b233-105">这样一来，用户可以通过标准 HTTP 方法将 API 用于预测目的。</span><span class="sxs-lookup"><span data-stu-id="3b233-105">By doing so it allows for users to access the API for prediction purposes via standard HTTP methods.</span></span>

> [!NOTE]
> <span data-ttu-id="3b233-106">本主题引用 ML.NET（目前处于预览状态），且材料可能会更改。</span><span class="sxs-lookup"><span data-stu-id="3b233-106">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="3b233-107">有关详细信息，请访问 [ML.NET 简介](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)。</span><span class="sxs-lookup"><span data-stu-id="3b233-107">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="3b233-108">此操作说明和相关示例目前使用的是 ML.NET 版本 0.10。</span><span class="sxs-lookup"><span data-stu-id="3b233-108">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="3b233-109">有关详细信息，请参阅 [dotnet/machinelearning GitHub 存储库](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)上的发行说明。</span><span class="sxs-lookup"><span data-stu-id="3b233-109">For more information, see the release notes at the [dotnet/machinelearning github repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3b233-110">系统必备</span><span class="sxs-lookup"><span data-stu-id="3b233-110">Prerequisites</span></span>

- <span data-ttu-id="3b233-111">安装了“.NET Core 跨平台开发”工作负载的 [Visual Studio 2017 15.6 或更高版本](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)。</span><span class="sxs-lookup"><span data-stu-id="3b233-111">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>
- <span data-ttu-id="3b233-112">PowerShell。</span><span class="sxs-lookup"><span data-stu-id="3b233-112">Powershell.</span></span>
- <span data-ttu-id="3b233-113">预先定型的模型。</span><span class="sxs-lookup"><span data-stu-id="3b233-113">Pre-trained model.</span></span>
    - <span data-ttu-id="3b233-114">根据 [ML.NET 情绪分析教程](../tutorials/sentiment-analysis.md)生成你自己的模型。</span><span class="sxs-lookup"><span data-stu-id="3b233-114">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model.</span></span>
    - <span data-ttu-id="3b233-115">下载此[预先定型的情绪分析机器学习模型](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span><span class="sxs-lookup"><span data-stu-id="3b233-115">Download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-aspnet-core-web-api-project"></a><span data-ttu-id="3b233-116">创建 ASP.NET Core Web API 项目</span><span class="sxs-lookup"><span data-stu-id="3b233-116">Create ASP.NET Core Web API Project</span></span>

1. <span data-ttu-id="3b233-117">打开 Visual Studio 2017。</span><span class="sxs-lookup"><span data-stu-id="3b233-117">Open Visual Studio 2017.</span></span> <span data-ttu-id="3b233-118">从菜单栏中依次选择“文件”>“新建”>“项目”。</span><span class="sxs-lookup"><span data-stu-id="3b233-118">Select **File > New > Project** from the menu bar.</span></span> <span data-ttu-id="3b233-119">在“新项目”对话框中，依次选择“Visual C#”节点和“Web”节点。</span><span class="sxs-lookup"><span data-stu-id="3b233-119">In the New Project dialog, select the **Visual C#** node followed by the **Web** node.</span></span> <span data-ttu-id="3b233-120">然后，选择“ASP.NET Core Web 应用程序”项目模板。</span><span class="sxs-lookup"><span data-stu-id="3b233-120">Then select the **ASP.NET Core Web Application** project template.</span></span> <span data-ttu-id="3b233-121">在“名称”文本框中，键入“SentimentAnalysisWebAPI”，再选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="3b233-121">In the **Name** text box, type "SentimentAnalysisWebAPI" and then select the **OK** button.</span></span>
1. <span data-ttu-id="3b233-122">在显示不同类型 ASP.NET Core 项目的窗口中，依次选择“API”和“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="3b233-122">In the window that displays the different types of ASP.NET Core Projects, select **API** and the select the **OK** button.</span></span>
1. <span data-ttu-id="3b233-123">在项目中创建“MLModels”目录，用于保存预生成的机器学习模型文件：</span><span class="sxs-lookup"><span data-stu-id="3b233-123">Create a directory named *MLModels* in your project to save your pre-built machine learning model files:</span></span>

    <span data-ttu-id="3b233-124">在“解决方案资源管理器”中，右键单击项目，并依次选择“添加”>“新文件夹”。</span><span class="sxs-lookup"><span data-stu-id="3b233-124">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="3b233-125">键入“MLModels”，再按 Enter。</span><span class="sxs-lookup"><span data-stu-id="3b233-125">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="3b233-126">安装“Microsoft.ML NuGet 包”：</span><span class="sxs-lookup"><span data-stu-id="3b233-126">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="3b233-127">在“解决方案资源管理器”中，右键单击项目，然后选择“管理 NuGet 包”。</span><span class="sxs-lookup"><span data-stu-id="3b233-127">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="3b233-128">选择“nuget.org”作为“包源”，选择“浏览”选项卡并搜索“Microsoft.ML”，再依次选择列表中的相应包和“安装”按钮。</span><span class="sxs-lookup"><span data-stu-id="3b233-128">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the Install button.</span></span> <span data-ttu-id="3b233-129">选择“预览更改”对话框中的“确定”按钮；如果同意所列包的许可条款，请选择“接受许可”对话框中的“我接受”按钮。</span><span class="sxs-lookup"><span data-stu-id="3b233-129">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="add-model-to-aspnet-core-web-api-project"></a><span data-ttu-id="3b233-130">将模型添加到 ASP.NET Core Web API 项目</span><span class="sxs-lookup"><span data-stu-id="3b233-130">Add Model to ASP.NET Core Web API Project</span></span>

1. <span data-ttu-id="3b233-131">将预生成的模型复制到 MLModels 目录</span><span class="sxs-lookup"><span data-stu-id="3b233-131">Copy your pre-built model to the *MLModels* directory</span></span>
1. <span data-ttu-id="3b233-132">在“解决方案资源管理器”中，右键单击模型 zip 文件，并选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="3b233-132">In Solution Explorer, right-click the model zip file and select Properties.</span></span> <span data-ttu-id="3b233-133">在“高级”下，将“复制到输出目录”的值更改为“如果较新则复制”。</span><span class="sxs-lookup"><span data-stu-id="3b233-133">Under Advanced, change the value of Copy to Output Directory to Copy if newer.</span></span>

## <a name="build-data-models"></a><span data-ttu-id="3b233-134">生成数据模型</span><span class="sxs-lookup"><span data-stu-id="3b233-134">Build Data Models</span></span>

<span data-ttu-id="3b233-135">需要为输入数据和预测创建一些类。</span><span class="sxs-lookup"><span data-stu-id="3b233-135">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="3b233-136">向项目添加一个新类：</span><span class="sxs-lookup"><span data-stu-id="3b233-136">Add a new class to your project:</span></span>

1. <span data-ttu-id="3b233-137">在项目中创建“DataModels”目录，用于保存数据模型：</span><span class="sxs-lookup"><span data-stu-id="3b233-137">Create a directory named *DataModels* in your project to save your data models:</span></span>

    <span data-ttu-id="3b233-138">在“解决方案资源管理器”中，右键单击项目，并依次选择“添加”>“新文件夹”。</span><span class="sxs-lookup"><span data-stu-id="3b233-138">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="3b233-139">键入“DataModels”，再按 Enter。</span><span class="sxs-lookup"><span data-stu-id="3b233-139">Type "DataModels" and hit **Enter**.</span></span>

2. <span data-ttu-id="3b233-140">在“解决方案资源管理器”中，右键单击“DataModels”目录，再依次选择“添加”>“新项”。</span><span class="sxs-lookup"><span data-stu-id="3b233-140">In Solution Explorer, right-click the *DataModels* directory, and then select Add > New Item.</span></span>
3. <span data-ttu-id="3b233-141">在“添加新项”对话框中，选择“类”并将“名称”字段更改为“SentimentData.cs”。</span><span class="sxs-lookup"><span data-stu-id="3b233-141">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="3b233-142">然后，选择“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="3b233-142">Then, select the **Add** button.</span></span> <span data-ttu-id="3b233-143">“SentimentData.cs”文件随即在代码编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="3b233-143">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="3b233-144">将以下 using 语句添加到 SentimentData.cs 顶部：</span><span class="sxs-lookup"><span data-stu-id="3b233-144">Add the following using statement to the top of *SentimentData.cs*:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.ML.Data;
```

<span data-ttu-id="3b233-145">删除现有类定义，并将以下代码添加到 SentimentData.cs 文件：</span><span class="sxs-lookup"><span data-stu-id="3b233-145">Remove the existing class definition and add the following code to the **SentimentData.cs** file:</span></span>

```csharp
public class SentimentData
{
    [LoadColumn(0)]
    public bool Label { get; set; }
    [LoadColumn(1)]
    public string Text { get; set; }   
}
```

4. <span data-ttu-id="3b233-146">在“解决方案资源管理器”中，右键单击“DataModels”目录，再依次选择“添加”>“新项”。</span><span class="sxs-lookup"><span data-stu-id="3b233-146">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="3b233-147">在“添加新项”对话框中，选择“类”，并将“名称”字段更改为“SentimentPrediction.cs”。</span><span class="sxs-lookup"><span data-stu-id="3b233-147">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="3b233-148">然后，选择“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="3b233-148">Then, select the Add button.</span></span> <span data-ttu-id="3b233-149">此时，SentimentPrediction.cs 文件在代码编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="3b233-149">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="3b233-150">将以下 using 语句添加到 SentimentPrediction.cs 顶部：</span><span class="sxs-lookup"><span data-stu-id="3b233-150">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.ML.Data;
```

<span data-ttu-id="3b233-151">删除现有类定义，并将以下代码添加到 SentimentPrediction.cs 文件：</span><span class="sxs-lookup"><span data-stu-id="3b233-151">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

```csharp
public class SentimentPrediction
{
    [ColumnName("PredictedLabel")]
    public bool Prediction { get; set; }
}
```

## <a name="create-prediction-service"></a><span data-ttu-id="3b233-152">创建预测服务</span><span class="sxs-lookup"><span data-stu-id="3b233-152">Create Prediction Service</span></span>

<span data-ttu-id="3b233-153">若要在整个应用程序中整理和重用预测逻辑，请创建预测服务。</span><span class="sxs-lookup"><span data-stu-id="3b233-153">To organize and re-use the prediction logic throughout the entire application, create a prediction service.</span></span>

1. <span data-ttu-id="3b233-154">在项目中创建“Services”目录，用于保留供应用程序使用的服务：</span><span class="sxs-lookup"><span data-stu-id="3b233-154">Create a directory named *Services* in your project to hold services to be used by the application:</span></span>

    <span data-ttu-id="3b233-155">在“解决方案资源管理器”中，右键单击项目，并依次选择“添加”>“新文件夹”。</span><span class="sxs-lookup"><span data-stu-id="3b233-155">In Solution Explorer, right-click on your project and select **Add > New Folder**.</span></span> <span data-ttu-id="3b233-156">键入“Services”，再按 Enter。</span><span class="sxs-lookup"><span data-stu-id="3b233-156">Type "Services" and hit **Enter**.</span></span>

1. <span data-ttu-id="3b233-157">在“解决方案资源管理器”中，右键单击“Services”目录，再依次选择“添加”>“新项”。</span><span class="sxs-lookup"><span data-stu-id="3b233-157">In Solution Explorer, right-click the *Services* directory, and then select **Add > New Item**.</span></span>
1. <span data-ttu-id="3b233-158">在“添加新项”对话框中，选择“类”，并将“名称”字段更改为“PredictionService.cs”。</span><span class="sxs-lookup"><span data-stu-id="3b233-158">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *PredictionService.cs*.</span></span> <span data-ttu-id="3b233-159">然后，选择“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="3b233-159">Then, select the **Add** button.</span></span> <span data-ttu-id="3b233-160">此时，PredictionService.cs 文件在代码编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="3b233-160">The *PredictionService.cs* file opens in the code editor.</span></span> <span data-ttu-id="3b233-161">将以下 using 语句添加到 PredictionService.cs 顶部：</span><span class="sxs-lookup"><span data-stu-id="3b233-161">Add the following using statement to the top of *PredictionService.cs*:</span></span>

```csharp
using System;
using System.IO;
using System.Collections.Generic;
using System.Linq;
using System.Threading.Tasks;
using Microsoft.ML;
using Microsoft.ML.Core.Data;
using SentimentAnalysisWebAPI.DataModels;
```

<span data-ttu-id="3b233-162">删除现有类定义，并将以下代码添加到 PredictionService.cs 文件：</span><span class="sxs-lookup"><span data-stu-id="3b233-162">Remove the existing class definition and add the following code to the *PredictionService.cs* file:</span></span>

```csharp
public class PredictionService
{
    private readonly PredictionEngine<SentimentData, SentimentPrediction> _predictionEngine;
    public PredictionService(PredictionEngine<SentimentData,SentimentPrediction> predictionEngine)
    {
        _predictionEngine = predictionEngine;
    }

    public string Predict(SentimentData input)
    {
        // Make a prediction
        SentimentPrediction prediction = _predictionEngine.Predict(input);

        //If prediction is true then it is toxic. If it is false, the it is not.
        string isToxic = Convert.ToBoolean(prediction.Prediction) ? "Toxic" : "Not Toxic";

        return isToxic;

    }
}
```

## <a name="register-predictions-service-for-use-in-application"></a><span data-ttu-id="3b233-163">注册预测服务以供在应用程序中使用</span><span class="sxs-lookup"><span data-stu-id="3b233-163">Register Predictions Service for Use in Application</span></span>

<span data-ttu-id="3b233-164">必须在每次需要使用预测服务时创建它，才能在应用程序中使用预测服务。</span><span class="sxs-lookup"><span data-stu-id="3b233-164">To use the prediction service in your application you will have to create it every time it is needed.</span></span> <span data-ttu-id="3b233-165">在这种情况下，建议的最佳做法是 ASP.NET Core 依赖关系注入。</span><span class="sxs-lookup"><span data-stu-id="3b233-165">In that case, a best practice to consider is ASP.NET Core dependency injection.</span></span>

<span data-ttu-id="3b233-166">若要详细了解[依赖关系注入](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1)，请单击下面的链接。</span><span class="sxs-lookup"><span data-stu-id="3b233-166">The following link provides more information if you want to learn about [dependency injection](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).</span></span>

1. <span data-ttu-id="3b233-167">打开 Startup.cs 类，并将以下 using 语句添加到文件顶部：</span><span class="sxs-lookup"><span data-stu-id="3b233-167">Open the *Startup.cs* class and add the following using statement to the top of the file:</span></span>

```csharp
using System.IO;
using Microsoft.AspNetCore.Builder;
using Microsoft.AspNetCore.Hosting;
using Microsoft.AspNetCore.Mvc;
using Microsoft.Extensions.Configuration;
using Microsoft.Extensions.DependencyInjection;
using Microsoft.ML;
using Microsoft.ML.Core.Data;
using SentimentAnalysisWebAPI.DataModels;
using SentimentAnalysisWebAPI.Services;
```

1. <span data-ttu-id="3b233-168">将以下代码行添加到 ConfigureServices 方法：</span><span class="sxs-lookup"><span data-stu-id="3b233-168">Add the following lines of code to the *ConfigureServices* method:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddMvc().SetCompatibilityVersion(CompatibilityVersion.Version_2_1);

    services.AddSingleton<MLContext>();
    services.AddSingleton<PredictionEngine<SentimentData, SentimentPrediction>>((ctx) =>
    {
        MLContext mlContext = ctx.GetRequiredService<MLContext>();
        string modelFilePathName = "MLModels/sentiment_model.zip";

        //Load model from file
        ITransformer model;
        using (var stream = File.OpenRead(modelFilePathName))
        {
            model = mlContext.Model.Load(stream);
        }

        // Return prediction engine
        return model.CreatePredictionEngine<SentimentData, SentimentPrediction>(mlContext);
    });
    services.AddSingleton<PredictionService>();
}
```

<span data-ttu-id="3b233-169">概括地讲，此代码在应用程序请求时自动初始化对象和服务，你无需手动执行初始化。</span><span class="sxs-lookup"><span data-stu-id="3b233-169">At a high level, this code initializes the objects and services automatically when requested by the application instead of having to manually do it.</span></span>

## <a name="create-predict-controller"></a><span data-ttu-id="3b233-170">创建预测控制器</span><span class="sxs-lookup"><span data-stu-id="3b233-170">Create Predict Controller</span></span>

<span data-ttu-id="3b233-171">必须创建控制器，才能处理传入 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="3b233-171">To process your incoming HTTP requests, you need to create a controller.</span></span>

1. <span data-ttu-id="3b233-172">在“解决方案资源管理器”中，右键单击“Controllers”目录，再依次选择“添加”>“控制器”。</span><span class="sxs-lookup"><span data-stu-id="3b233-172">In Solution Explorer, right-click the *Controllers* directory, and then select **Add > Controller**.</span></span>
1. <span data-ttu-id="3b233-173">在“添加新项”对话框中，依次选择“空 API 控制器”和“添加”。</span><span class="sxs-lookup"><span data-stu-id="3b233-173">In the **Add New Item** dialog box, select **API Controller Empty** and select **Add**.</span></span>
1. <span data-ttu-id="3b233-174">在提示窗口中，将“控制器名称”字段更改为“PredictController.cs”。</span><span class="sxs-lookup"><span data-stu-id="3b233-174">In the prompt change the **Controller Name** field to *PredictController.cs*.</span></span> <span data-ttu-id="3b233-175">然后，选择“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="3b233-175">Then, select the Add button.</span></span> <span data-ttu-id="3b233-176">此时，PredictController.cs 文件在代码编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="3b233-176">The *PredictController.cs* file opens in the code editor.</span></span> <span data-ttu-id="3b233-177">将以下 using 语句添加到 PredictController.cs 顶部：</span><span class="sxs-lookup"><span data-stu-id="3b233-177">Add the following using statement to the top of *PredictController.cs*:</span></span>

```csharp
using Microsoft.AspNetCore.Mvc;
using SentimentAnalysisWebAPI.DataModels;
using SentimentAnalysisWebAPI.Services;
```

<span data-ttu-id="3b233-178">删除现有类定义，并将以下代码添加到 PredictController.cs 文件：</span><span class="sxs-lookup"><span data-stu-id="3b233-178">Remove the existing class definition and add the following code to the *PredictController.cs* file:</span></span>

```csharp
public class PredictController : ControllerBase
{

    private readonly PredictionService _predictionService;

    public PredictController(PredictionService predictionService)
    {
        _predictionService = predictionService; //Define prediction service
    }

    [HttpPost]
    public ActionResult<string> Post([FromBody]SentimentData input)
    {
        if(!ModelState.IsValid)
        {
            return BadRequest();
        }
        return Ok(_predictionService.Predict(input));
    }

}
```

<span data-ttu-id="3b233-179">这是在将预测服务传递给通过依赖关系注入获取的控制器构造函数，从而分配预测服务。</span><span class="sxs-lookup"><span data-stu-id="3b233-179">This is assigning the Prediction service by passing it to the controller's constructor which you get via dependency injection.</span></span> <span data-ttu-id="3b233-180">然后，在此控制器的 POST 方法中，使用预测服务进行预测；如果成功，它会将结果返回给用户。</span><span class="sxs-lookup"><span data-stu-id="3b233-180">Then, in the POST method of this controller the Prediction service is being used to make predictions and return the results back to the user if successful.</span></span>

## <a name="test-web-api-locally"></a><span data-ttu-id="3b233-181">本地测试 Web API</span><span class="sxs-lookup"><span data-stu-id="3b233-181">Test Web API Locally</span></span>

<span data-ttu-id="3b233-182">完成所有设置后，是时候测试应用程序了。</span><span class="sxs-lookup"><span data-stu-id="3b233-182">Once everything is set up, it's time to test the application.</span></span>

1. <span data-ttu-id="3b233-183">运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="3b233-183">Run the application.</span></span>
1. <span data-ttu-id="3b233-184">打开 Powershell，并输入以下代码（其中，PORT 是应用程序正在侦听的端口）。</span><span class="sxs-lookup"><span data-stu-id="3b233-184">Open Powershell and enter the following code where PORT is the port your application is listening on.</span></span>

```powershell
Invoke-RestMethod "https://localhost:<PORT>/api/predict" -Method Post -Body (@{Text="This is a very rude movie"} | ConvertTo-Json) -ContentType "application/json"
```

<span data-ttu-id="3b233-185">如果成功，输出文本应如下所示：</span><span class="sxs-lookup"><span data-stu-id="3b233-185">If successful, the output should look similar to the text below:</span></span>

```powershell
Toxic
```

<span data-ttu-id="3b233-186">祝贺你！</span><span class="sxs-lookup"><span data-stu-id="3b233-186">Congratulations!</span></span> <span data-ttu-id="3b233-187">你已成功使用 ASP.NET Core API 通过 Internet 提供模型进行预测。</span><span class="sxs-lookup"><span data-stu-id="3b233-187">You have successfully served your model to make predictions over the internet using an ASP.NET Core API.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3b233-188">后续步骤</span><span class="sxs-lookup"><span data-stu-id="3b233-188">Next Steps</span></span>

- [<span data-ttu-id="3b233-189">部署到 Azure</span><span class="sxs-lookup"><span data-stu-id="3b233-189">Deploy to Azure</span></span>](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs?view=aspnetcore-2.1#deploy-the-app-to-azure)
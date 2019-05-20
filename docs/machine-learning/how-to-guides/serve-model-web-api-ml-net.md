---
title: 在 ASP.NET Core Web API 中部署模型
description: 使用 ASP.NET Core Web API 通过 Internet 提供 ML.NET 情绪分析机器学习模型
ms.date: 05/03/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to
ms.openlocfilehash: c78e58dbec6b2ba3065fc46c4d4fd65abdcd37cd
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063482"
---
# <a name="deploy-a-model-in-an-aspnet-core-web-api"></a><span data-ttu-id="3fa3b-103">在 ASP.NET Core Web API 中部署模型</span><span class="sxs-lookup"><span data-stu-id="3fa3b-103">Deploy a model in an ASP.NET Core Web API</span></span>

<span data-ttu-id="3fa3b-104">了解如何使用 ASP.NET Core Web API 在 Web 上提供预先训练的 ML.NET 机器学习模型。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-104">Learn how to serve a pre-trained ML.NET machine learning model on the web using an ASP.NET Core Web API.</span></span> <span data-ttu-id="3fa3b-105">通过 Web API 提供模型可实现通过标准 HTTP 方法进行预测。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-105">Serving a model over a web API enables predictions via standard HTTP methods.</span></span>

> [!NOTE]
> <span data-ttu-id="3fa3b-106">`PredictionEnginePool` 服务扩展目前处于预览状态。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-106">`PredictionEnginePool` service extension is currently in preview.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3fa3b-107">系统必备</span><span class="sxs-lookup"><span data-stu-id="3fa3b-107">Prerequisites</span></span>

- <span data-ttu-id="3fa3b-108">安装了“.NET Core 跨平台开发”工作负载的 [Visual Studio 2017 15.6 或更高版本](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017)。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-108">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>
- <span data-ttu-id="3fa3b-109">PowerShell。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-109">Powershell.</span></span>
- <span data-ttu-id="3fa3b-110">预先定型的模型。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-110">Pre-trained model.</span></span> <span data-ttu-id="3fa3b-111">使用 [ML.NET 情绪分析教程](../tutorials/sentiment-analysis.md)生成自己的模型，或下载此[预先训练的情绪分析机器学习模型](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span><span class="sxs-lookup"><span data-stu-id="3fa3b-111">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model or download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-aspnet-core-web-api-project"></a><span data-ttu-id="3fa3b-112">创建 ASP.NET Core Web API 项目</span><span class="sxs-lookup"><span data-stu-id="3fa3b-112">Create ASP.NET Core Web API project</span></span>

1. <span data-ttu-id="3fa3b-113">打开 Visual Studio 2017。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-113">Open Visual Studio 2017.</span></span> <span data-ttu-id="3fa3b-114">从菜单栏中依次选择“文件”>“新建”>“项目”。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-114">Select **File > New > Project** from the menu bar.</span></span> <span data-ttu-id="3fa3b-115">在“新项目”对话框中，依次选择“Visual C#”节点和“Web”节点。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-115">In the New Project dialog, select the **Visual C#** node followed by the **Web** node.</span></span> <span data-ttu-id="3fa3b-116">然后，选择“ASP.NET Core Web 应用程序”项目模板。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-116">Then select the **ASP.NET Core Web Application** project template.</span></span> <span data-ttu-id="3fa3b-117">在“名称”文本框中，键入“SentimentAnalysisWebAPI”，再选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-117">In the **Name** text box, type "SentimentAnalysisWebAPI" and then select the **OK** button.</span></span>

1. <span data-ttu-id="3fa3b-118">在显示不同类型 ASP.NET Core 项目的窗口中，依次选择“API”和“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-118">In the window that displays the different types of ASP.NET Core Projects, select **API** and the select the **OK** button.</span></span>

1. <span data-ttu-id="3fa3b-119">在项目中创建“MLModels”目录，用于保存预生成的机器学习模型文件：</span><span class="sxs-lookup"><span data-stu-id="3fa3b-119">Create a directory named *MLModels* in your project to save your pre-built machine learning model files:</span></span>

    <span data-ttu-id="3fa3b-120">在“解决方案资源管理器”中，右键单击项目，并依次选择“添加”>“新文件夹”。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-120">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="3fa3b-121">键入“MLModels”，再按 Enter。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-121">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="3fa3b-122">安装“Microsoft.ML NuGet 包”：</span><span class="sxs-lookup"><span data-stu-id="3fa3b-122">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="3fa3b-123">在“解决方案资源管理器”中，右键单击项目，然后选择“管理 NuGet 包”。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-123">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="3fa3b-124">选择“nuget.org”作为“包源”，选择“浏览”选项卡并搜索“Microsoft.ML”，再依次选择列表中的相应包和“安装”按钮。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-124">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the Install button.</span></span> <span data-ttu-id="3fa3b-125">选择“预览更改”对话框中的“确定”按钮；如果同意所列包的许可条款，请选择“接受许可”对话框中的“我接受”按钮。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-125">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="3fa3b-126">安装 **Microsoft.Extensions.ML Nuget 包**：</span><span class="sxs-lookup"><span data-stu-id="3fa3b-126">Install the **Microsoft.Extensions.ML Nuget Package**:</span></span>

    <span data-ttu-id="3fa3b-127">在“解决方案资源管理器”中，右键单击项目，然后选择“管理 NuGet 包”。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-127">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="3fa3b-128">选择“nuget.org”作为包源，然后选择“浏览”选项卡并搜索“Microsoft.Extensions.ML”，在列表中选择包，再选择“安装”按钮。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-128">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.Extensions.ML**, select that package in the list, and select the Install button.</span></span> <span data-ttu-id="3fa3b-129">选择“预览更改”对话框中的“确定”按钮；如果同意所列包的许可条款，请选择“接受许可”对话框中的“我接受”按钮。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-129">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="add-model-to-aspnet-core-web-api-project"></a><span data-ttu-id="3fa3b-130">将模型添加到 ASP.NET Core Web API 项目</span><span class="sxs-lookup"><span data-stu-id="3fa3b-130">Add model to ASP.NET Core Web API project</span></span>

1. <span data-ttu-id="3fa3b-131">将预生成的模型复制到 MLModels 目录</span><span class="sxs-lookup"><span data-stu-id="3fa3b-131">Copy your pre-built model to the *MLModels* directory</span></span>
1. <span data-ttu-id="3fa3b-132">在“解决方案资源管理器”中，右键单击模型 zip 文件，并选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-132">In Solution Explorer, right-click the model zip file and select Properties.</span></span> <span data-ttu-id="3fa3b-133">在“高级”下，将“复制到输出目录”的值更改为“如果较新则复制”。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-133">Under Advanced, change the value of Copy to Output Directory to Copy if newer.</span></span>

## <a name="create-data-models"></a><span data-ttu-id="3fa3b-134">创建数据模型</span><span class="sxs-lookup"><span data-stu-id="3fa3b-134">Create data models</span></span>

<span data-ttu-id="3fa3b-135">需要为输入数据和预测创建一些类。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-135">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="3fa3b-136">向项目添加一个新类：</span><span class="sxs-lookup"><span data-stu-id="3fa3b-136">Add a new class to your project:</span></span>

1. <span data-ttu-id="3fa3b-137">在项目中创建“DataModels”目录，用于保存数据模型：</span><span class="sxs-lookup"><span data-stu-id="3fa3b-137">Create a directory named *DataModels* in your project to save your data models:</span></span>

    <span data-ttu-id="3fa3b-138">在“解决方案资源管理器”中，右键单击项目，并依次选择“添加”>“新文件夹”。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-138">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="3fa3b-139">键入“DataModels”，再按 Enter。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-139">Type "DataModels" and hit **Enter**.</span></span>

2. <span data-ttu-id="3fa3b-140">在“解决方案资源管理器”中，右键单击“DataModels”目录，再依次选择“添加”>“新项”。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-140">In Solution Explorer, right-click the *DataModels* directory, and then select Add > New Item.</span></span>
3. <span data-ttu-id="3fa3b-141">在“添加新项”对话框中，选择“类”并将“名称”字段更改为“SentimentData.cs”。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-141">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="3fa3b-142">然后，选择“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-142">Then, select the **Add** button.</span></span> <span data-ttu-id="3fa3b-143">“SentimentData.cs”文件随即在代码编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-143">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="3fa3b-144">将以下 using 语句添加到 SentimentData.cs 顶部：</span><span class="sxs-lookup"><span data-stu-id="3fa3b-144">Add the following using statement to the top of *SentimentData.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```
    
    <span data-ttu-id="3fa3b-145">删除现有类定义，并将以下代码添加到 SentimentData.cs 文件：</span><span class="sxs-lookup"><span data-stu-id="3fa3b-145">Remove the existing class definition and add the following code to the **SentimentData.cs** file:</span></span>
    
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

4. <span data-ttu-id="3fa3b-146">在“解决方案资源管理器”中，右键单击“DataModels”目录，再依次选择“添加”>“新项”。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-146">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="3fa3b-147">在“添加新项”对话框中，选择“类”，并将“名称”字段更改为“SentimentPrediction.cs”。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-147">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="3fa3b-148">然后，选择“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-148">Then, select the Add button.</span></span> <span data-ttu-id="3fa3b-149">此时，SentimentPrediction.cs 文件在代码编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-149">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="3fa3b-150">将以下 using 语句添加到 SentimentPrediction.cs 顶部：</span><span class="sxs-lookup"><span data-stu-id="3fa3b-150">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```
    
    <span data-ttu-id="3fa3b-151">删除现有类定义，并将以下代码添加到 SentimentPrediction.cs 文件：</span><span class="sxs-lookup"><span data-stu-id="3fa3b-151">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>
    
    ```csharp
    public class SentimentPrediction : SentimentData
    {

        [ColumnName("PredictedLabel")]
        public bool Prediction { get; set; }

        public float Probability { get; set; }

        public float Score { get; set; }
    }
    ```

    <span data-ttu-id="3fa3b-152">`SentimentPrediction` 继承自 `SentimentData`。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-152">`SentimentPrediction` inherits from `SentimentData`.</span></span> <span data-ttu-id="3fa3b-153">这样可以更轻松地查看 `SentimentText` 属性中的原始数据以及模型生成的输出。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-153">This makes it easier to see the original data in the `SentimentText` property along with the output generated by the model.</span></span> 

## <a name="register-predictionenginepool-for-use-in-the-application"></a><span data-ttu-id="3fa3b-154">注册 PredictionEnginePool 用于应用程序</span><span class="sxs-lookup"><span data-stu-id="3fa3b-154">Register PredictionEnginePool for use in the application</span></span>

<span data-ttu-id="3fa3b-155">若要进行单个预测，请使用 [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-155">To make a single prediction, use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span></span> <span data-ttu-id="3fa3b-156">若要在应用程序中使用 [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)，则必须在需要时创建它。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-156">In order to use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) in your application you must create it when it's needed.</span></span> <span data-ttu-id="3fa3b-157">在这种情况下，可考虑的最佳做法是依赖项注入。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-157">In that case, a best practice to consider is dependency injection.</span></span>

<span data-ttu-id="3fa3b-158">如果想要了解 [ASP.NET Core 中的依赖项注入](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1)，以下链接提供详细信息。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-158">The following link provides more information if you want to learn about [dependency injection in ASP.NET Core](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).</span></span>

1. <span data-ttu-id="3fa3b-159">打开 Startup.cs 类，并将以下 using 语句添加到文件顶部：</span><span class="sxs-lookup"><span data-stu-id="3fa3b-159">Open the *Startup.cs* class and add the following using statement to the top of the file:</span></span>

    ```csharp
    using Microsoft.AspNetCore.Builder;
    using Microsoft.AspNetCore.Hosting;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.Configuration;
    using Microsoft.Extensions.DependencyInjection;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

2. <span data-ttu-id="3fa3b-160">将以下代码添加到 *ConfigureServices* 方法中：</span><span class="sxs-lookup"><span data-stu-id="3fa3b-160">Add the following code to the *ConfigureServices* method:</span></span>

    ```csharp
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddMvc().SetCompatibilityVersion(CompatibilityVersion.Version_2_1);
        services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
            .FromFile("MLModels/sentiment_model.zip");
    }
    ```

<span data-ttu-id="3fa3b-161">概括地讲，此代码在应用程序请求时自动初始化对象和服务，你无需手动执行初始化。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-161">At a high level, this code initializes the objects and services automatically when requested by the application instead of having to manually do it.</span></span>

> [!WARNING]
> <span data-ttu-id="3fa3b-162">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) 不是线程安全型。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-162">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="3fa3b-163">为了提高性能和线程安全性，请使用 `PredictionEnginePool` 服务，该服务可创建 `PredictionEngine` 对象的 [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) 供应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-163">For improved performance and thread safety, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of `PredictionEngine` objects for application use.</span></span> <span data-ttu-id="3fa3b-164">阅读以下博客文章，了解有关[在 ASP.NET Core 中创建和使用 `PredictionEngine` 对象池](https://devblogs.microsoft.com/cesardelatorre/how-to-optimize-and-run-ml-net-models-on-scalable-asp-net-core-webapis-or-web-apps/)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-164">Read the following blog post to learn more about [creating and using `PredictionEngine` object pools in ASP.NET Core](https://devblogs.microsoft.com/cesardelatorre/how-to-optimize-and-run-ml-net-models-on-scalable-asp-net-core-webapis-or-web-apps/).</span></span>  

## <a name="create-predict-controller"></a><span data-ttu-id="3fa3b-165">创建预测控制器</span><span class="sxs-lookup"><span data-stu-id="3fa3b-165">Create Predict controller</span></span>

<span data-ttu-id="3fa3b-166">若要处理传入的 HTTP 请求，请创建控制器。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-166">To process your incoming HTTP requests, create a controller.</span></span>

1. <span data-ttu-id="3fa3b-167">在“解决方案资源管理器”中，右键单击“Controllers”目录，再依次选择“添加”>“控制器”。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-167">In Solution Explorer, right-click the *Controllers* directory, and then select **Add > Controller**.</span></span>
1. <span data-ttu-id="3fa3b-168">在“添加新项”对话框中，依次选择“空 API 控制器”和“添加”。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-168">In the **Add New Item** dialog box, select **API Controller Empty** and select **Add**.</span></span>
1. <span data-ttu-id="3fa3b-169">在提示窗口中，将“控制器名称”字段更改为“PredictController.cs”。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-169">In the prompt change the **Controller Name** field to *PredictController.cs*.</span></span> <span data-ttu-id="3fa3b-170">然后，选择“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-170">Then, select the Add button.</span></span> <span data-ttu-id="3fa3b-171">此时，PredictController.cs 文件在代码编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-171">The *PredictController.cs* file opens in the code editor.</span></span> <span data-ttu-id="3fa3b-172">将以下 using 语句添加到 PredictController.cs 顶部：</span><span class="sxs-lookup"><span data-stu-id="3fa3b-172">Add the following using statement to the top of *PredictController.cs*:</span></span>

    ```csharp
    using System;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

    <span data-ttu-id="3fa3b-173">删除现有类定义，并将以下代码添加到 PredictController.cs 文件：</span><span class="sxs-lookup"><span data-stu-id="3fa3b-173">Remove the existing class definition and add the following code to the *PredictController.cs* file:</span></span>
    
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

<span data-ttu-id="3fa3b-174">此代码通过将 `PredictionEnginePool` 传递给控制器的构造函数（通过依赖项注入获得）来分配它。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-174">This code assigns the `PredictionEnginePool` by passing it to the controller's constructor which you get via dependency injection.</span></span> <span data-ttu-id="3fa3b-175">然后，`Predict` 控制器的 `Post` 方法使用 `PredictionEnginePool` 进行预测，并在成功时将结果返回给用户。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-175">Then, the `Predict` controller's `Post` method uses the `PredictionEnginePool` to make predictions and return the results back to the user if successful.</span></span>

## <a name="test-web-api-locally"></a><span data-ttu-id="3fa3b-176">在本地测试 Web API</span><span class="sxs-lookup"><span data-stu-id="3fa3b-176">Test web API locally</span></span>

<span data-ttu-id="3fa3b-177">完成所有设置后，是时候测试应用程序了。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-177">Once everything is set up, it's time to test the application.</span></span>

1. <span data-ttu-id="3fa3b-178">运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-178">Run the application.</span></span>
1. <span data-ttu-id="3fa3b-179">打开 Powershell，并输入以下代码（其中，PORT 是应用程序正在侦听的端口）。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-179">Open Powershell and enter the following code where PORT is the port your application is listening on.</span></span>

    ```powershell
    Invoke-RestMethod "https://localhost:<PORT>/api/predict" -Method Post -Body (@{Text="This was a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    <span data-ttu-id="3fa3b-180">如果成功，输出文本应如下所示：</span><span class="sxs-lookup"><span data-stu-id="3fa3b-180">If successful, the output should look similar to the text below:</span></span>
    
    ```powershell
    Negative
    ```

<span data-ttu-id="3fa3b-181">祝贺你！</span><span class="sxs-lookup"><span data-stu-id="3fa3b-181">Congratulations!</span></span> <span data-ttu-id="3fa3b-182">已成功提供模型用于使用 ASP.NET Core Web API 通过 Internet 进行预测。</span><span class="sxs-lookup"><span data-stu-id="3fa3b-182">You have successfully served your model to make predictions over the internet using an ASP.NET Core Web API.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3fa3b-183">后续步骤</span><span class="sxs-lookup"><span data-stu-id="3fa3b-183">Next Steps</span></span>

- [<span data-ttu-id="3fa3b-184">部署到 Azure</span><span class="sxs-lookup"><span data-stu-id="3fa3b-184">Deploy to Azure</span></span>](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs?view=aspnetcore-2.1#deploy-the-app-to-azure)

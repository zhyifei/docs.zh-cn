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
# <a name="deploy-a-model-to-azure-functions"></a><span data-ttu-id="9523e-103">将模型部署到 Azure Functions</span><span class="sxs-lookup"><span data-stu-id="9523e-103">Deploy a model to Azure Functions</span></span>

<span data-ttu-id="9523e-104">了解如何通过 Azure Functions 无服务器环境部署预先训练的 ML.NET 机器学习模型，以便通过 HTTP 进行预测。</span><span class="sxs-lookup"><span data-stu-id="9523e-104">Learn how to deploy a pre-trained ML.NET machine learning model for predictions over HTTP through an Azure Functions serverless environment.</span></span>

> [!NOTE]
> <span data-ttu-id="9523e-105">`PredictionEnginePool` 服务扩展目前处于预览状态。</span><span class="sxs-lookup"><span data-stu-id="9523e-105">`PredictionEnginePool` service extension is currently in preview.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9523e-106">系统必备</span><span class="sxs-lookup"><span data-stu-id="9523e-106">Prerequisites</span></span>

- <span data-ttu-id="9523e-107">安装了“.NET Core 跨平台开发”工作负载和“Azure 开发”的 [Visual Studio 2017 15.6 或更高版本](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017)。</span><span class="sxs-lookup"><span data-stu-id="9523e-107">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload and "Azure development" installed.</span></span>
- [<span data-ttu-id="9523e-108">Azure Functions 工具</span><span class="sxs-lookup"><span data-stu-id="9523e-108">Azure Functions Tools</span></span>](/azure/azure-functions/functions-develop-vs#check-your-tools-version)
- <span data-ttu-id="9523e-109">Powershell</span><span class="sxs-lookup"><span data-stu-id="9523e-109">Powershell</span></span>
- <span data-ttu-id="9523e-110">预先定型的模型。</span><span class="sxs-lookup"><span data-stu-id="9523e-110">Pre-trained model.</span></span> <span data-ttu-id="9523e-111">使用 [ML.NET 情绪分析教程](../tutorials/sentiment-analysis.md)生成自己的模型，或下载此[预先训练的情绪分析机器学习模型](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span><span class="sxs-lookup"><span data-stu-id="9523e-111">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model or download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-azure-functions-project"></a><span data-ttu-id="9523e-112">创建 Azure Functions 项目</span><span class="sxs-lookup"><span data-stu-id="9523e-112">Create Azure Functions project</span></span>

1. <span data-ttu-id="9523e-113">打开 Visual Studio 2017。</span><span class="sxs-lookup"><span data-stu-id="9523e-113">Open Visual Studio 2017.</span></span> <span data-ttu-id="9523e-114">从菜单栏中选择“文件” > “新建” > “项目”。</span><span class="sxs-lookup"><span data-stu-id="9523e-114">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="9523e-115">在“新项目”对话框中，依次选择“Visual C#”节点和“云”节点。</span><span class="sxs-lookup"><span data-stu-id="9523e-115">In the **New Project** dialog, select the **Visual C#** node followed by the **Cloud** node.</span></span> <span data-ttu-id="9523e-116">然后，选择“Azure Functions”项目模板。</span><span class="sxs-lookup"><span data-stu-id="9523e-116">Then select the **Azure Functions** project template.</span></span> <span data-ttu-id="9523e-117">在“名称”文本框中，键入“SentimentAnalysisFunctionsApp”，再选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="9523e-117">In the **Name** text box, type "SentimentAnalysisFunctionsApp" and then select the **OK** button.</span></span>
1. <span data-ttu-id="9523e-118">在“新项目”对话框中，打开项目选项上方的下拉列表，并选择“Azure Functions v2 (.NET Core)”。</span><span class="sxs-lookup"><span data-stu-id="9523e-118">In the **New Project** dialog, open the dropdown above the project options and select **Azure Functions v2 (.NET Core)**.</span></span> <span data-ttu-id="9523e-119">然后，依次选择“Http 触发器”项目和“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="9523e-119">Then, select the **Http trigger** project and then select the **OK** button.</span></span>
1. <span data-ttu-id="9523e-120">在项目中创建“MLModels”目录，用于保存模型：</span><span class="sxs-lookup"><span data-stu-id="9523e-120">Create a directory named *MLModels* in your project to save your model:</span></span>

    <span data-ttu-id="9523e-121">在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新文件夹”。</span><span class="sxs-lookup"><span data-stu-id="9523e-121">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="9523e-122">键入“MLModels”，再按 Enter。</span><span class="sxs-lookup"><span data-stu-id="9523e-122">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="9523e-123">安装“Microsoft.ML NuGet 包”：</span><span class="sxs-lookup"><span data-stu-id="9523e-123">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="9523e-124">在“解决方案资源管理器”中，右键单击项目，然后选择“管理 NuGet 包”。</span><span class="sxs-lookup"><span data-stu-id="9523e-124">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="9523e-125">将“nuget.org”选择为“包源”，选择“浏览”选项卡并搜索“Microsoft.ML”，在列表中选择该包，然后选择“安装”按钮。</span><span class="sxs-lookup"><span data-stu-id="9523e-125">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="9523e-126">选择“预览更改”对话框上的“确定”按钮，如果你同意所列包的许可条款，则选择“接受许可”对话框上的“我接受”按钮。</span><span class="sxs-lookup"><span data-stu-id="9523e-126">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="9523e-127">安装 **Microsoft.Extensions.ML NuGet 包**：</span><span class="sxs-lookup"><span data-stu-id="9523e-127">Install the **Microsoft.Extensions.ML NuGet Package**:</span></span>

    <span data-ttu-id="9523e-128">在“解决方案资源管理器”中，右键单击项目，然后选择“管理 NuGet 包”。</span><span class="sxs-lookup"><span data-stu-id="9523e-128">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="9523e-129">选择“nuget.org”作为包源，然后选择“浏览”选项卡并搜索“Microsoft.Extensions.ML”，在列表中选择包，再选择“安装”按钮。</span><span class="sxs-lookup"><span data-stu-id="9523e-129">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.Extensions.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="9523e-130">选择“预览更改”对话框上的“确定”按钮，如果你同意所列包的许可条款，则选择“接受许可”对话框上的“我接受”按钮。</span><span class="sxs-lookup"><span data-stu-id="9523e-130">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="add-pre-trained-model-to-project"></a><span data-ttu-id="9523e-131">将预先训练的模型添加到项目</span><span class="sxs-lookup"><span data-stu-id="9523e-131">Add pre-trained model to project</span></span>

1. <span data-ttu-id="9523e-132">将预生成的模型复制到 MLModels 文件夹。</span><span class="sxs-lookup"><span data-stu-id="9523e-132">Copy your pre-built model to the *MLModels* folder.</span></span>
1. <span data-ttu-id="9523e-133">在“解决方案资源管理器”中，右键单击预生成的模型文件，并选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="9523e-133">In Solution Explorer, right-click your pre-built model file and select **Properties**.</span></span> <span data-ttu-id="9523e-134">在“高级”下，将“复制到输出目录”的值更改为“如果较新则复制”。</span><span class="sxs-lookup"><span data-stu-id="9523e-134">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

## <a name="create-azure-function-to-analyze-sentiment"></a><span data-ttu-id="9523e-135">创建 Azure 函数用于分析情绪</span><span class="sxs-lookup"><span data-stu-id="9523e-135">Create Azure Function to analyze sentiment</span></span>

<span data-ttu-id="9523e-136">创建情绪预测类。</span><span class="sxs-lookup"><span data-stu-id="9523e-136">Create a class to predict sentiment.</span></span> <span data-ttu-id="9523e-137">向项目添加一个新类：</span><span class="sxs-lookup"><span data-stu-id="9523e-137">Add a new class to your project:</span></span>

1. <span data-ttu-id="9523e-138">在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新项”。</span><span class="sxs-lookup"><span data-stu-id="9523e-138">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="9523e-139">在“添加新项”对话框中，选择“Azure 函数”，并将“名称”字段更改为“AnalyzeSentiment.cs”。</span><span class="sxs-lookup"><span data-stu-id="9523e-139">In the **Add New Item** dialog box, select **Azure Function** and change the **Name** field to *AnalyzeSentiment.cs*.</span></span> <span data-ttu-id="9523e-140">然后，选择“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="9523e-140">Then, select the **Add** button.</span></span>

1. <span data-ttu-id="9523e-141">在“新 Azure 函数”对话框中，选择“Http 触发器”。</span><span class="sxs-lookup"><span data-stu-id="9523e-141">In the **New Azure Function** dialog box, select **Http Trigger**.</span></span> <span data-ttu-id="9523e-142">然后，选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="9523e-142">Then, select the **OK** button.</span></span>

    <span data-ttu-id="9523e-143">此时，AnalyzeSentiment.cs 文件在代码编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="9523e-143">The *AnalyzeSentiment.cs* file opens in the code editor.</span></span> <span data-ttu-id="9523e-144">将以下 `using` 语句添加到 *AnalyzeSentiment.cs* 的顶部：</span><span class="sxs-lookup"><span data-stu-id="9523e-144">Add the following `using` statement to the top of *AnalyzeSentiment.cs*:</span></span>

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

    <span data-ttu-id="9523e-145">默认情况下，`AnalyzeSentiment` 类为 `static`。</span><span class="sxs-lookup"><span data-stu-id="9523e-145">By default, the `AnalyzeSentiment` class is `static`.</span></span> <span data-ttu-id="9523e-146">确保从类定义中删除 `static` 关键字。</span><span class="sxs-lookup"><span data-stu-id="9523e-146">Make sure to remove the `static` keyword from the class definition.</span></span>

    ```csharp
    public class AnalyzeSentiment
    {
    
    }
    ```

## <a name="create-data-models"></a><span data-ttu-id="9523e-147">创建数据模型</span><span class="sxs-lookup"><span data-stu-id="9523e-147">Create data models</span></span>

<span data-ttu-id="9523e-148">需要为输入数据和预测创建一些类。</span><span class="sxs-lookup"><span data-stu-id="9523e-148">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="9523e-149">向项目添加一个新类：</span><span class="sxs-lookup"><span data-stu-id="9523e-149">Add a new class to your project:</span></span>

1. <span data-ttu-id="9523e-150">在项目中创建“DataModels”目录，用于保存数据模型：在“解决方案资源管理器”中，右键单击项目，并依次选择“添加”>“新文件夹”。</span><span class="sxs-lookup"><span data-stu-id="9523e-150">Create a directory named *DataModels* in your project to save your data models: In Solution Explorer, right-click on your project and select **Add > New Folder**.</span></span> <span data-ttu-id="9523e-151">键入“DataModels”，再按 Enter。</span><span class="sxs-lookup"><span data-stu-id="9523e-151">Type "DataModels" and hit Enter.</span></span>
2. <span data-ttu-id="9523e-152">在“解决方案资源管理器”中，右键单击“DataModels”目录，再依次选择“添加”>“新项”。</span><span class="sxs-lookup"><span data-stu-id="9523e-152">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
3. <span data-ttu-id="9523e-153">在“添加新项”对话框中，选择“类”并将“名称”字段更改为“SentimentData.cs”。</span><span class="sxs-lookup"><span data-stu-id="9523e-153">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="9523e-154">然后，选择“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="9523e-154">Then, select the **Add** button.</span></span> 

    <span data-ttu-id="9523e-155">“SentimentData.cs”文件随即在代码编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="9523e-155">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="9523e-156">将以下 using 语句添加到 SentimentData.cs 顶部：</span><span class="sxs-lookup"><span data-stu-id="9523e-156">Add the following using statement to the top of *SentimentData.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```

    <span data-ttu-id="9523e-157">删除现有类定义，并将以下代码添加到 SentimentData.cs 文件：</span><span class="sxs-lookup"><span data-stu-id="9523e-157">Remove the existing class definition and add the following code to the *SentimentData.cs* file:</span></span>
    
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

4. <span data-ttu-id="9523e-158">在“解决方案资源管理器”中，右键单击“DataModels”目录，再依次选择“添加”>“新项”。</span><span class="sxs-lookup"><span data-stu-id="9523e-158">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="9523e-159">在“添加新项”对话框中，选择“类”，并将“名称”字段更改为“SentimentPrediction.cs”。</span><span class="sxs-lookup"><span data-stu-id="9523e-159">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="9523e-160">然后，选择“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="9523e-160">Then, select the **Add** button.</span></span> <span data-ttu-id="9523e-161">此时，SentimentPrediction.cs 文件在代码编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="9523e-161">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="9523e-162">将以下 using 语句添加到 SentimentPrediction.cs 顶部：</span><span class="sxs-lookup"><span data-stu-id="9523e-162">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```

    <span data-ttu-id="9523e-163">删除现有类定义，并将以下代码添加到 SentimentPrediction.cs 文件：</span><span class="sxs-lookup"><span data-stu-id="9523e-163">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

    ```csharp
    public class SentimentPrediction : SentimentData
    {

        [ColumnName("PredictedLabel")]
        public bool Prediction { get; set; }

        public float Probability { get; set; }

        public float Score { get; set; }
    }
    ```

    <span data-ttu-id="9523e-164">`SentimentPrediction` 继承自 `SentimentData`，后者提供对 `SentimentText` 属性中原始数据以及模型生成的输出的访问。</span><span class="sxs-lookup"><span data-stu-id="9523e-164">`SentimentPrediction` inherits from `SentimentData` which provides access to the original data in the `SentimentText` property as well as the output generated by the model.</span></span>

## <a name="register-predictionenginepool-service"></a><span data-ttu-id="9523e-165">注册 PredictionEnginePool 服务</span><span class="sxs-lookup"><span data-stu-id="9523e-165">Register PredictionEnginePool service</span></span>

<span data-ttu-id="9523e-166">若要进行单个预测，请使用 [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)。</span><span class="sxs-lookup"><span data-stu-id="9523e-166">To make a single prediction, use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span></span> <span data-ttu-id="9523e-167">若要在应用程序中使用 [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)，则必须在需要时创建它。</span><span class="sxs-lookup"><span data-stu-id="9523e-167">In order to use [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) in your application you must create it when it's needed.</span></span> <span data-ttu-id="9523e-168">在这种情况下，可考虑的最佳做法是依赖项注入。</span><span class="sxs-lookup"><span data-stu-id="9523e-168">In that case, a best practice to consider is dependency injection.</span></span>

<span data-ttu-id="9523e-169">若要详细了解[依赖关系注入](https://en.wikipedia.org/wiki/Dependency_injection)，请单击下面的链接。</span><span class="sxs-lookup"><span data-stu-id="9523e-169">The following link provides more information if you want to learn about [dependency injection](https://en.wikipedia.org/wiki/Dependency_injection).</span></span>

1. <span data-ttu-id="9523e-170">在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新项”。</span><span class="sxs-lookup"><span data-stu-id="9523e-170">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="9523e-171">在“添加新项”对话框中，选择“类”并将“名称”字段更改为“Startup.cs”。</span><span class="sxs-lookup"><span data-stu-id="9523e-171">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *Startup.cs*.</span></span> <span data-ttu-id="9523e-172">然后，选择“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="9523e-172">Then, select the **Add** button.</span></span> 

    <span data-ttu-id="9523e-173">此时，*Startup.cs* 文件在代码编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="9523e-173">The *Startup.cs* file opens in the code editor.</span></span> <span data-ttu-id="9523e-174">将以下 using 语句添加到 *Startup.cs* 的顶部：</span><span class="sxs-lookup"><span data-stu-id="9523e-174">Add the following using statement to the top of *Startup.cs*:</span></span>

    ```csharp
    using Microsoft.Azure.WebJobs;
    using Microsoft.Azure.WebJobs.Hosting;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisFunctionsApp;
    using SentimentAnalysisFunctionsApp.DataModels;
    ```

    <span data-ttu-id="9523e-175">删除 using 语句下面的现有代码，并将以下代码添加到 *Startup.cs* 文件中：</span><span class="sxs-lookup"><span data-stu-id="9523e-175">Remove the existing code below the using statements and add the following code to the *Startup.cs* file:</span></span>

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

<span data-ttu-id="9523e-176">概括地讲，此代码在应用程序请求时自动初始化对象和服务，你无需手动执行初始化。</span><span class="sxs-lookup"><span data-stu-id="9523e-176">At a high level, this code initializes the objects and services automatically when requested by the application instead of having to manually do it.</span></span>

> [!WARNING]
> <span data-ttu-id="9523e-177">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) 不是线程安全型。</span><span class="sxs-lookup"><span data-stu-id="9523e-177">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="9523e-178">为了提高性能和线程安全性，请使用 `PredictionEnginePool` 服务，该服务可创建 `PredictionEngine` 对象的 [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) 供应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="9523e-178">For improved performance and thread safety, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of `PredictionEngine` objects for application use.</span></span> 

## <a name="register-startup-as-an-azure-functions-extension"></a><span data-ttu-id="9523e-179">将 Startup 注册为 Azure Functions 扩展</span><span class="sxs-lookup"><span data-stu-id="9523e-179">Register Startup as an Azure Functions extension</span></span>

<span data-ttu-id="9523e-180">若要在应用程序中使用 `Startup`，需要将其注册为 Azure Functions 扩展。</span><span class="sxs-lookup"><span data-stu-id="9523e-180">In order to use `Startup` in your application, you need to register it as an Azure Functions extension.</span></span> <span data-ttu-id="9523e-181">在项目中创建名为 *extensions.json* 的新文件（如果尚不存在）。</span><span class="sxs-lookup"><span data-stu-id="9523e-181">Create a new file called *extensions.json* in your project if one does not already exist.</span></span>

1. <span data-ttu-id="9523e-182">在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新项”。</span><span class="sxs-lookup"><span data-stu-id="9523e-182">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="9523e-183">在“新建项目”对话框中，依次选择“Visual C#”节点和“Web”节点。</span><span class="sxs-lookup"><span data-stu-id="9523e-183">In the **New Item** dialog, select the **Visual C#** node followed by the **Web** node.</span></span> <span data-ttu-id="9523e-184">然后选择“Json 文件”选项。</span><span class="sxs-lookup"><span data-stu-id="9523e-184">Then select the **Json File** option.</span></span> <span data-ttu-id="9523e-185">在“名称”文本框中，键入“extensions.json”，然后选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="9523e-185">In the **Name** text box, type "extensions.json" and then select the **OK** button.</span></span>

    <span data-ttu-id="9523e-186">此时，*extensions.json* 文件在代码编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="9523e-186">The *extensions.json* file opens in the code editor.</span></span> <span data-ttu-id="9523e-187">将以下内容添加到 *extensions.json*：</span><span class="sxs-lookup"><span data-stu-id="9523e-187">Add the following content to *extensions.json*:</span></span>
    
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

1. <span data-ttu-id="9523e-188">在解决方案资源管理器中，右键单击 *extensions.json* 文件，然后选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="9523e-188">In Solution Explorer, right-click your *extensions.json* file and select **Properties**.</span></span> <span data-ttu-id="9523e-189">在“高级”下，将“复制到输出目录”的值更改为“如果较新则复制”。</span><span class="sxs-lookup"><span data-stu-id="9523e-189">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

## <a name="load-the-model-into-the-function"></a><span data-ttu-id="9523e-190">将模型加载到函数中</span><span class="sxs-lookup"><span data-stu-id="9523e-190">Load the model into the function</span></span>

<span data-ttu-id="9523e-191">在 *AnalyzeSentiment* 类中插入以下代码：</span><span class="sxs-lookup"><span data-stu-id="9523e-191">Insert the following code inside the *AnalyzeSentiment* class:</span></span>

```csharp
private readonly PredictionEnginePool<SentimentData, SentimentPrediction> _predictionEnginePool;

// AnalyzeSentiment class constructor
public AnalyzeSentiment(PredictionEnginePool<SentimentData, SentimentPrediction> predictionEnginePool)
{
    _predictionEnginePool = predictionEnginePool;
}
```

<span data-ttu-id="9523e-192">此代码通过将 `PredictionEnginePool` 传递给函数的构造函数（通过依赖项注入获得）来分配它。</span><span class="sxs-lookup"><span data-stu-id="9523e-192">This code assigns the `PredictionEnginePool` by passing it to the function's constructor which you get via dependency injection.</span></span>

## <a name="use-the-model-to-make-predictions"></a><span data-ttu-id="9523e-193">使用模型进行预测</span><span class="sxs-lookup"><span data-stu-id="9523e-193">Use the model to make predictions</span></span>

<span data-ttu-id="9523e-194">将 AnalyzeSentiment 类中 Run 方法的现有实现替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="9523e-194">Replace the existing implementation of *Run* method in *AnalyzeSentiment* class with the following code:</span></span>

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

<span data-ttu-id="9523e-195">执行 `Run` 方法时，来自 HTTP 请求的传入数据被反序列化并用作 `PredictionEnginePool` 的输入。</span><span class="sxs-lookup"><span data-stu-id="9523e-195">When the `Run` method executes, the incoming data from the HTTP request is deserialized and used as input for the `PredictionEnginePool`.</span></span> <span data-ttu-id="9523e-196">随后调用 `Predict` 方法生成预测并将结果返回给用户。</span><span class="sxs-lookup"><span data-stu-id="9523e-196">The `Predict` method is then called to generate a prediction and return the result to the user.</span></span> 

## <a name="test-locally"></a><span data-ttu-id="9523e-197">在本地测试</span><span class="sxs-lookup"><span data-stu-id="9523e-197">Test locally</span></span>

<span data-ttu-id="9523e-198">至此，已完成所有设置，是时候测试应用程序了：</span><span class="sxs-lookup"><span data-stu-id="9523e-198">Now that everything is set up, it's time to test the application:</span></span>

1. <span data-ttu-id="9523e-199">运行此应用程序</span><span class="sxs-lookup"><span data-stu-id="9523e-199">Run the application</span></span>
1. <span data-ttu-id="9523e-200">打开 PowerShell，并在提示符中输入代码（其中，PORT 是应用程序运行所在的端口）。</span><span class="sxs-lookup"><span data-stu-id="9523e-200">Open PowerShell and enter the code into the prompt where PORT is the port your application is running on.</span></span> <span data-ttu-id="9523e-201">端口通常是 7071。</span><span class="sxs-lookup"><span data-stu-id="9523e-201">Typically the port is 7071.</span></span>

    ```powershell
    Invoke-RestMethod "http://localhost:<PORT>/api/AnalyzeSentiment" -Method Post -Body (@{SentimentText="This is a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    <span data-ttu-id="9523e-202">如果成功，输出文本应如下所示：</span><span class="sxs-lookup"><span data-stu-id="9523e-202">If successful, the output should look similar to the text below:</span></span>
    
    ```powershell
    Negative
    ```

<span data-ttu-id="9523e-203">祝贺你！</span><span class="sxs-lookup"><span data-stu-id="9523e-203">Congratulations!</span></span> <span data-ttu-id="9523e-204">你已成功使用 Azure Functions 通过 Internet 提供模型进行预测。</span><span class="sxs-lookup"><span data-stu-id="9523e-204">You have successfully served your model to make predictions over the internet using an Azure Function.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9523e-205">后续步骤</span><span class="sxs-lookup"><span data-stu-id="9523e-205">Next Steps</span></span>

- [<span data-ttu-id="9523e-206">部署到 Azure</span><span class="sxs-lookup"><span data-stu-id="9523e-206">Deploy to Azure</span></span>](/azure/azure-functions/functions-develop-vs#publish-to-azure)

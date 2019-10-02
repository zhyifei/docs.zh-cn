---
title: 在 ASP.NET Core Web API 中部署模型
description: 使用 ASP.NET Core Web API 通过 Internet 提供 ML.NET 情绪分析机器学习模型
ms.date: 09/11/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc,how-to
ms.openlocfilehash: 1173315bbc88797ce0c6d0fcc9597896f14889ac
ms.sourcegitcommit: 8b8dd14dde727026fd0b6ead1ec1df2e9d747a48
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2019
ms.locfileid: "71332694"
---
# <a name="deploy-a-model-in-an-aspnet-core-web-api"></a><span data-ttu-id="2ed5c-103">在 ASP.NET Core Web API 中部署模型</span><span class="sxs-lookup"><span data-stu-id="2ed5c-103">Deploy a model in an ASP.NET Core Web API</span></span>

<span data-ttu-id="2ed5c-104">了解如何使用 ASP.NET Core Web API 在 Web 上提供预先训练的 ML.NET 机器学习模型。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-104">Learn how to serve a pre-trained ML.NET machine learning model on the web using an ASP.NET Core Web API.</span></span> <span data-ttu-id="2ed5c-105">通过 Web API 提供模型可实现通过标准 HTTP 方法进行预测。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-105">Serving a model over a web API enables predictions via standard HTTP methods.</span></span>

> [!NOTE]
> <span data-ttu-id="2ed5c-106">`PredictionEnginePool` 服务扩展目前处于预览状态。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-106">`PredictionEnginePool` service extension is currently in preview.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2ed5c-107">系统必备</span><span class="sxs-lookup"><span data-stu-id="2ed5c-107">Prerequisites</span></span>

- <span data-ttu-id="2ed5c-108">安装了“.NET Core 跨平台开发”工作负载的 [Visual Studio 2017 15.6 或更高版本](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017)。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-108">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>
- <span data-ttu-id="2ed5c-109">PowerShell。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-109">Powershell.</span></span>
- <span data-ttu-id="2ed5c-110">预先定型的模型。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-110">Pre-trained model.</span></span> <span data-ttu-id="2ed5c-111">使用 [ML.NET 情绪分析教程](../tutorials/sentiment-analysis.md)生成自己的模型，或下载此[预先训练的情绪分析机器学习模型](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span><span class="sxs-lookup"><span data-stu-id="2ed5c-111">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model or download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-aspnet-core-web-api-project"></a><span data-ttu-id="2ed5c-112">创建 ASP.NET Core Web API 项目</span><span class="sxs-lookup"><span data-stu-id="2ed5c-112">Create ASP.NET Core Web API project</span></span>

1. <span data-ttu-id="2ed5c-113">打开 Visual Studio 2017。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-113">Open Visual Studio 2017.</span></span> <span data-ttu-id="2ed5c-114">从菜单栏中依次选择“文件”>“新建”>“项目”  。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-114">Select **File > New > Project** from the menu bar.</span></span> <span data-ttu-id="2ed5c-115">在“新项目”对话框中，依次选择“Visual C#”  节点和“Web”  节点。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-115">In the New Project dialog, select the **Visual C#** node followed by the **Web** node.</span></span> <span data-ttu-id="2ed5c-116">然后，选择“ASP.NET Core Web 应用程序”  项目模板。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-116">Then select the **ASP.NET Core Web Application** project template.</span></span> <span data-ttu-id="2ed5c-117">在“名称”  文本框中，键入“SentimentAnalysisWebAPI”，再选择“确定”  按钮。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-117">In the **Name** text box, type "SentimentAnalysisWebAPI" and then select the **OK** button.</span></span>

1. <span data-ttu-id="2ed5c-118">在显示不同类型 ASP.NET Core 项目的窗口中，依次选择“API”  和“确定”  按钮。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-118">In the window that displays the different types of ASP.NET Core Projects, select **API** and the select the **OK** button.</span></span>

1. <span data-ttu-id="2ed5c-119">在项目中创建“MLModels”  目录，用于保存预生成的机器学习模型文件：</span><span class="sxs-lookup"><span data-stu-id="2ed5c-119">Create a directory named *MLModels* in your project to save your pre-built machine learning model files:</span></span>

    <span data-ttu-id="2ed5c-120">在“解决方案资源管理器”中，右键单击项目，并依次选择“添加”>“新文件夹”。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-120">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="2ed5c-121">键入“MLModels”，再按 Enter。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-121">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="2ed5c-122">安装“Microsoft.ML NuGet 包”  ：</span><span class="sxs-lookup"><span data-stu-id="2ed5c-122">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="2ed5c-123">在“解决方案资源管理器”中，右键单击项目，然后选择“管理 NuGet 包”  。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-123">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="2ed5c-124">选择“nuget.org”作为“包源”，选择“浏览”选项卡并搜索“Microsoft.ML”  ，再依次选择列表中的相应包和“安装”按钮。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-124">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the Install button.</span></span> <span data-ttu-id="2ed5c-125">选择“预览更改”  对话框中的“确定”  按钮；如果同意所列包的许可条款，请选择“接受许可”对话框中的“我接受”  按钮。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-125">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>

1. <span data-ttu-id="2ed5c-126">安装 **Microsoft.Extensions.ML Nuget 包**：</span><span class="sxs-lookup"><span data-stu-id="2ed5c-126">Install the **Microsoft.Extensions.ML Nuget Package**:</span></span>

    <span data-ttu-id="2ed5c-127">在“解决方案资源管理器”中，右键单击项目，然后选择“管理 NuGet 包”  。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-127">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="2ed5c-128">选择“nuget.org”作为包源，然后选择“浏览”选项卡并搜索“Microsoft.Extensions.ML”，在列表中选择包，再选择“安装”按钮  。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-128">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.Extensions.ML**, select that package in the list, and select the Install button.</span></span> <span data-ttu-id="2ed5c-129">选择“预览更改”  对话框中的“确定”  按钮；如果同意所列包的许可条款，请选择“接受许可”对话框中的“我接受”  按钮。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-129">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the License Acceptance dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="add-model-to-aspnet-core-web-api-project"></a><span data-ttu-id="2ed5c-130">将模型添加到 ASP.NET Core Web API 项目</span><span class="sxs-lookup"><span data-stu-id="2ed5c-130">Add model to ASP.NET Core Web API project</span></span>

1. <span data-ttu-id="2ed5c-131">将预生成的模型复制到 MLModels  目录</span><span class="sxs-lookup"><span data-stu-id="2ed5c-131">Copy your pre-built model to the *MLModels* directory</span></span>
1. <span data-ttu-id="2ed5c-132">在“解决方案资源管理器”中，右键单击模型 zip 文件，并选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-132">In Solution Explorer, right-click the model zip file and select Properties.</span></span> <span data-ttu-id="2ed5c-133">在“高级”下，将“复制到输出目录”的值更改为“如果较新则复制”。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-133">Under Advanced, change the value of Copy to Output Directory to Copy if newer.</span></span>

## <a name="create-data-models"></a><span data-ttu-id="2ed5c-134">创建数据模型</span><span class="sxs-lookup"><span data-stu-id="2ed5c-134">Create data models</span></span>

<span data-ttu-id="2ed5c-135">需要为输入数据和预测创建一些类。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-135">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="2ed5c-136">向项目添加一个新类：</span><span class="sxs-lookup"><span data-stu-id="2ed5c-136">Add a new class to your project:</span></span>

1. <span data-ttu-id="2ed5c-137">在项目中创建“DataModels”  目录，用于保存数据模型：</span><span class="sxs-lookup"><span data-stu-id="2ed5c-137">Create a directory named *DataModels* in your project to save your data models:</span></span>

    <span data-ttu-id="2ed5c-138">在“解决方案资源管理器”中，右键单击项目，并依次选择“添加”>“新文件夹”。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-138">In Solution Explorer, right-click on your project and select Add > New Folder.</span></span> <span data-ttu-id="2ed5c-139">键入“DataModels”，再按 Enter  。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-139">Type "DataModels" and hit **Enter**.</span></span>

2. <span data-ttu-id="2ed5c-140">在“解决方案资源管理器”中，右键单击“DataModels”  目录，再依次选择“添加”>“新项”。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-140">In Solution Explorer, right-click the *DataModels* directory, and then select Add > New Item.</span></span>
3. <span data-ttu-id="2ed5c-141">在“添加新项”  对话框中，选择“类”  并将“名称”  字段更改为“SentimentData.cs”  。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-141">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="2ed5c-142">然后，选择“添加”  按钮。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-142">Then, select the **Add** button.</span></span> <span data-ttu-id="2ed5c-143">“SentimentData.cs”  文件随即在代码编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-143">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="2ed5c-144">将以下 using 语句添加到 SentimentData.cs  顶部：</span><span class="sxs-lookup"><span data-stu-id="2ed5c-144">Add the following using statement to the top of *SentimentData.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```
    
    <span data-ttu-id="2ed5c-145">删除现有类定义，并将以下代码添加到 SentimentData.cs  文件：</span><span class="sxs-lookup"><span data-stu-id="2ed5c-145">Remove the existing class definition and add the following code to the **SentimentData.cs** file:</span></span>
    
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

4. <span data-ttu-id="2ed5c-146">在“解决方案资源管理器”中，右键单击“DataModels”  目录，再依次选择“添加”>“新项”  。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-146">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="2ed5c-147">在“添加新项”  对话框中，选择“类”  ，并将“名称”  字段更改为“SentimentPrediction.cs”  。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-147">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="2ed5c-148">然后，选择“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-148">Then, select the Add button.</span></span> <span data-ttu-id="2ed5c-149">此时，SentimentPrediction.cs  文件在代码编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-149">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="2ed5c-150">将以下 using 语句添加到 SentimentPrediction.cs  顶部：</span><span class="sxs-lookup"><span data-stu-id="2ed5c-150">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

    ```csharp
    using Microsoft.ML.Data;
    ```
    
    <span data-ttu-id="2ed5c-151">删除现有类定义，并将以下代码添加到 SentimentPrediction.cs  文件：</span><span class="sxs-lookup"><span data-stu-id="2ed5c-151">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>
    
    ```csharp
    public class SentimentPrediction : SentimentData
    {

        [ColumnName("PredictedLabel")]
        public bool Prediction { get; set; }

        public float Probability { get; set; }

        public float Score { get; set; }
    }
    ```

    <span data-ttu-id="2ed5c-152">`SentimentPrediction` 继承自 `SentimentData`。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-152">`SentimentPrediction` inherits from `SentimentData`.</span></span> <span data-ttu-id="2ed5c-153">这样可以更轻松地查看 `SentimentText` 属性中的原始数据以及模型生成的输出。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-153">This makes it easier to see the original data in the `SentimentText` property along with the output generated by the model.</span></span> 

## <a name="register-predictionenginepool-for-use-in-the-application"></a><span data-ttu-id="2ed5c-154">注册 PredictionEnginePool 用于应用程序</span><span class="sxs-lookup"><span data-stu-id="2ed5c-154">Register PredictionEnginePool for use in the application</span></span>

<span data-ttu-id="2ed5c-155">若要进行单一预测，必须创建 [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-155">To make a single prediction, you have to create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602).</span></span> <span data-ttu-id="2ed5c-156">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) 不是线程安全型。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-156">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="2ed5c-157">此外，必须在应用程序中的每一处所需位置创建它的实例。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-157">Additionally, you have to create an instance of it everywhere it is needed within your application.</span></span> <span data-ttu-id="2ed5c-158">随着应用程序的增长，此过程可能会变得难以管理。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-158">As your application grows, this process can become unmanageable.</span></span> <span data-ttu-id="2ed5c-159">为了提高性能和线程安全，请使用依赖项注入和 `PredictionEnginePool` 服务的组合，这将创建一个在整个应用程序中使用的 [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) 对象的 [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601)。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-159">For improved performance and thread safety, use a combination of dependency injection and the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span>

<span data-ttu-id="2ed5c-160">如果想要详细了解 [ASP.NET Core 中的依赖项注入](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1)，以下链接提供详细信息。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-160">The following link provides more information if you want to learn more about [dependency injection in ASP.NET Core](https://docs.microsoft.com/aspnet/core/fundamentals/dependency-injection?view=aspnetcore-2.1).</span></span>

1. <span data-ttu-id="2ed5c-161">打开 Startup.cs  类，并将以下 using 语句添加到文件顶部：</span><span class="sxs-lookup"><span data-stu-id="2ed5c-161">Open the *Startup.cs* class and add the following using statement to the top of the file:</span></span>

    ```csharp
    using Microsoft.AspNetCore.Builder;
    using Microsoft.AspNetCore.Hosting;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.Configuration;
    using Microsoft.Extensions.DependencyInjection;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

2. <span data-ttu-id="2ed5c-162">将以下代码添加到 *ConfigureServices* 方法中：</span><span class="sxs-lookup"><span data-stu-id="2ed5c-162">Add the following code to the *ConfigureServices* method:</span></span>

    ```csharp
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddMvc().SetCompatibilityVersion(CompatibilityVersion.Version_2_1);
        services.AddPredictionEnginePool<SentimentData, SentimentPrediction>()
            .FromFile(modelName: "SentimentAnalysisModel", filePath:"MLModels/sentiment_model.zip", watchForChanges: true);
    }
    ```

<span data-ttu-id="2ed5c-163">概括地讲，此代码在应用程序请求时自动初始化对象和服务以供稍后使用，你无需手动执行初始化。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-163">At a high level, this code initializes the objects and services automatically for later use when requested by the application instead of having to manually do it.</span></span> 

<span data-ttu-id="2ed5c-164">机器学习模型不是静态的。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-164">Machine learning models are not static.</span></span> <span data-ttu-id="2ed5c-165">随着新的训练数据变得可用，模型将重新训练并重新部署。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-165">As new training data becomes available, the model is retrained and redeployed.</span></span> <span data-ttu-id="2ed5c-166">在应用程序中获取模型的最新版本的一种方法是重新部署整个应用程序。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-166">One way to get the latest version of the model into your application is to redeploy the entire application.</span></span> <span data-ttu-id="2ed5c-167">但这会导致应用程序关闭。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-167">However, this introduces application downtime.</span></span> <span data-ttu-id="2ed5c-168">`PredictionEnginePool` 服务提供了一种机制，用于在不使应用程序关闭的情况下重新加载已更新的模型。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-168">The `PredictionEnginePool` service provides a mechanism to reload an updated model without taking your application down.</span></span> 

<span data-ttu-id="2ed5c-169">将 `watchForChanges` 参数设置为 `true`，`PredictionEnginePool` 则启动 [`FileSystemWatcher`](xref:System.IO.FileSystemWatcher)，它侦听文件系统更改通知并在文件发生更改时引发事件。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-169">Set the `watchForChanges` parameter to `true`, and the `PredictionEnginePool` starts a [`FileSystemWatcher`](xref:System.IO.FileSystemWatcher) that listens to the file system change notifications and raises events when there is a change to the file.</span></span> <span data-ttu-id="2ed5c-170">这会提示 `PredictionEnginePool` 会自动重新加载模型。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-170">This prompts the `PredictionEnginePool` to automatically reload the model.</span></span>

<span data-ttu-id="2ed5c-171">模型由 `modelName` 参数标识，因此更改时可以重新加载每个应用程序的多个模型。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-171">The model is identified by the `modelName` parameter so that more than one model per application can be reloaded upon change.</span></span> 

<span data-ttu-id="2ed5c-172">或者，如果使用远程存储的模型，则可以使用 `FromUri` 方法。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-172">Alternatively, you can use the `FromUri` method when working with models stored remotely.</span></span> <span data-ttu-id="2ed5c-173">`FromUri` 会轮询远程位置以获取更改，而不是监视文件更改事件。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-173">Rather than watching for file changed events, `FromUri` polls the remote location for changes.</span></span> <span data-ttu-id="2ed5c-174">轮询间隔默认为 5 分钟。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-174">The polling interval defaults to 5 minutes.</span></span> <span data-ttu-id="2ed5c-175">你可以根据应用程序的要求，增加或减少轮询间隔。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-175">You can increase or decrease the polling interval based on your application's requirements.</span></span>

## <a name="create-predict-controller"></a><span data-ttu-id="2ed5c-176">创建预测控制器</span><span class="sxs-lookup"><span data-stu-id="2ed5c-176">Create Predict controller</span></span>

<span data-ttu-id="2ed5c-177">若要处理传入的 HTTP 请求，请创建控制器。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-177">To process your incoming HTTP requests, create a controller.</span></span>

1. <span data-ttu-id="2ed5c-178">在“解决方案资源管理器”中，右键单击“Controllers”  目录，再依次选择“添加”>“控制器”  。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-178">In Solution Explorer, right-click the *Controllers* directory, and then select **Add > Controller**.</span></span>
1. <span data-ttu-id="2ed5c-179">在“添加新项”  对话框中，依次选择“空 API 控制器”  和“添加”  。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-179">In the **Add New Item** dialog box, select **API Controller Empty** and select **Add**.</span></span>
1. <span data-ttu-id="2ed5c-180">在提示窗口中，将“控制器名称”  字段更改为“PredictController.cs”  。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-180">In the prompt change the **Controller Name** field to *PredictController.cs*.</span></span> <span data-ttu-id="2ed5c-181">然后，选择“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-181">Then, select the Add button.</span></span> <span data-ttu-id="2ed5c-182">此时，PredictController.cs  文件在代码编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-182">The *PredictController.cs* file opens in the code editor.</span></span> <span data-ttu-id="2ed5c-183">将以下 using 语句添加到 PredictController.cs  顶部：</span><span class="sxs-lookup"><span data-stu-id="2ed5c-183">Add the following using statement to the top of *PredictController.cs*:</span></span>

    ```csharp
    using System;
    using Microsoft.AspNetCore.Mvc;
    using Microsoft.Extensions.ML;
    using SentimentAnalysisWebAPI.DataModels;
    ```

    <span data-ttu-id="2ed5c-184">删除现有类定义，并将以下代码添加到 PredictController.cs  文件：</span><span class="sxs-lookup"><span data-stu-id="2ed5c-184">Remove the existing class definition and add the following code to the *PredictController.cs* file:</span></span>
    
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

            SentimentPrediction prediction = _predictionEnginePool.Predict(modelName: "SentimentAnalysisModel", example: input);

            string sentiment = Convert.ToBoolean(prediction.Prediction) ? "Positive" : "Negative";

            return Ok(sentiment);
        }
    }
    ```

<span data-ttu-id="2ed5c-185">此代码通过将 `PredictionEnginePool` 传递给控制器的构造函数（通过依赖项注入获得）来分配它。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-185">This code assigns the `PredictionEnginePool` by passing it to the controller's constructor which you get via dependency injection.</span></span> <span data-ttu-id="2ed5c-186">然后，`Predict` 控制器的 `Post` 方法使用 `PredictionEnginePool`，来通过在 `Startup` 类中注册的 `SentimentAnalysisModel` 进行预测，并在成功时将结果返回给用户。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-186">Then, the `Predict` controller's `Post` method uses the `PredictionEnginePool` to make predictions using the `SentimentAnalysisModel` registered in the `Startup` class and returns the results back to the user if successful.</span></span>

## <a name="test-web-api-locally"></a><span data-ttu-id="2ed5c-187">在本地测试 Web API</span><span class="sxs-lookup"><span data-stu-id="2ed5c-187">Test web API locally</span></span>

<span data-ttu-id="2ed5c-188">完成所有设置后，是时候测试应用程序了。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-188">Once everything is set up, it's time to test the application.</span></span>

1. <span data-ttu-id="2ed5c-189">运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-189">Run the application.</span></span>
1. <span data-ttu-id="2ed5c-190">打开 Powershell，并输入以下代码（其中，PORT 是应用程序正在侦听的端口）。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-190">Open Powershell and enter the following code where PORT is the port your application is listening on.</span></span>

    ```powershell
    Invoke-RestMethod "https://localhost:<PORT>/api/predict" -Method Post -Body (@{SentimentText="This was a very bad steak"} | ConvertTo-Json) -ContentType "application/json"
    ```

    <span data-ttu-id="2ed5c-191">如果成功，输出文本应如下所示：</span><span class="sxs-lookup"><span data-stu-id="2ed5c-191">If successful, the output should look similar to the text below:</span></span>
    
    ```powershell
    Negative
    ```

<span data-ttu-id="2ed5c-192">祝贺你！</span><span class="sxs-lookup"><span data-stu-id="2ed5c-192">Congratulations!</span></span> <span data-ttu-id="2ed5c-193">已成功提供模型用于使用 ASP.NET Core Web API 通过 Internet 进行预测。</span><span class="sxs-lookup"><span data-stu-id="2ed5c-193">You have successfully served your model to make predictions over the internet using an ASP.NET Core Web API.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2ed5c-194">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2ed5c-194">Next Steps</span></span>

- [<span data-ttu-id="2ed5c-195">部署到 Azure</span><span class="sxs-lookup"><span data-stu-id="2ed5c-195">Deploy to Azure</span></span>](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs#deploy-the-app-to-azure)

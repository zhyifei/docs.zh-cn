---
title: 将 ML.NET 模型部署到 Azure Functions
description: 使用 Azure Functions 通过 Internet 提供 ML.NET 情绪分析机器学习模型进行预测
ms.date: 03/08/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 4681b37da64097dd8e537b4c956917277ecff96b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59330631"
---
# <a name="how-to-use-mlnet-model-in-azure-functions"></a><span data-ttu-id="bf3ed-103">操作说明：在 Azure Functions 中使用 ML.NET 模型</span><span class="sxs-lookup"><span data-stu-id="bf3ed-103">How-To: Use ML.NET Model in Azure Functions</span></span>

<span data-ttu-id="bf3ed-104">本操作说明介绍了如何在无服务器环境（如 Azure Functions）中通过 Internet 使用预生成的 ML.NET 机器学习模型进行各个预测。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-104">This how-to shows how individual predictions can be made using a pre-built ML.NET machine learning model through the internet in a serverless environment such as Azure Functions.</span></span>

> [!NOTE]
> <span data-ttu-id="bf3ed-105">本主题引用 ML.NET（目前处于预览状态），且材料可能会更改。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-105">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="bf3ed-106">有关详细信息，请访问 [ML.NET 简介](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-106">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="bf3ed-107">此操作说明和相关示例目前使用的是 ML.NET 版本 0.10。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-107">This how-to and related sample are currently using **ML.NET version 0.10**.</span></span> <span data-ttu-id="bf3ed-108">有关详细信息，请参阅 [dotnet/machinelearning GitHub 存储库](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)上的发行说明。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-108">For more information, see the release notes at the [dotnet/machinelearning github repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bf3ed-109">系统必备</span><span class="sxs-lookup"><span data-stu-id="bf3ed-109">Prerequisites</span></span>

- <span data-ttu-id="bf3ed-110">安装了“.NET Core 跨平台开发”工作负载和“Azure 开发”的 [Visual Studio 2017 15.6 或更高版本](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017)。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-110">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload and "Azure development" installed.</span></span> 
- [<span data-ttu-id="bf3ed-111">Azure Functions 工具</span><span class="sxs-lookup"><span data-stu-id="bf3ed-111">Azure Functions Tools</span></span>](/azure/azure-functions/functions-develop-vs#check-your-tools-version)
- <span data-ttu-id="bf3ed-112">Powershell</span><span class="sxs-lookup"><span data-stu-id="bf3ed-112">Powershell</span></span>
- <span data-ttu-id="bf3ed-113">预先定型的模型。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-113">Pre-trained model.</span></span> 
    - <span data-ttu-id="bf3ed-114">根据 [ML.NET 情绪分析教程](../tutorials/sentiment-analysis.md)生成你自己的模型。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-114">Use the [ML.NET Sentiment Analysis tutorial](../tutorials/sentiment-analysis.md) to build your own model.</span></span>
    - <span data-ttu-id="bf3ed-115">下载此[预先定型的情绪分析机器学习模型](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span><span class="sxs-lookup"><span data-stu-id="bf3ed-115">Download this [pre-trained sentiment analysis machine learning model](https://github.com/dotnet/samples/blob/master/machine-learning/models/sentimentanalysis/sentiment_model.zip)</span></span>

## <a name="create-azure-functions-project"></a><span data-ttu-id="bf3ed-116">创建 Azure Functions 项目</span><span class="sxs-lookup"><span data-stu-id="bf3ed-116">Create Azure Functions Project</span></span>

1. <span data-ttu-id="bf3ed-117">打开 Visual Studio 2017。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-117">Open Visual Studio 2017.</span></span> <span data-ttu-id="bf3ed-118">从菜单栏中选择“文件” > “新建” > “项目”。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-118">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="bf3ed-119">在“新项目”对话框中，依次选择“Visual C#”节点和“云”节点。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-119">In the **New Project** dialog, select the **Visual C#** node followed by the **Cloud** node.</span></span> <span data-ttu-id="bf3ed-120">然后，选择“Azure Functions”项目模板。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-120">Then select the **Azure Functions** project template.</span></span> <span data-ttu-id="bf3ed-121">在“名称”文本框中，键入“SentimentAnalysisFunctionsApp”，再选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-121">In the **Name** text box, type "SentimentAnalysisFunctionsApp" and then select the **OK** button.</span></span>
1. <span data-ttu-id="bf3ed-122">在“新项目”对话框中，打开项目选项上方的下拉列表，并选择“Azure Functions v2 (.NET Core)”。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-122">In the **New Project** dialog, open the dropdown above the project options and select **Azure Functions v2 (.NET Core)**.</span></span> <span data-ttu-id="bf3ed-123">然后，依次选择“Http 触发器”项目和“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-123">Then, select the **Http trigger** project and then select the **OK** button.</span></span>
1. <span data-ttu-id="bf3ed-124">在项目中创建“MLModels”目录，用于保存模型：</span><span class="sxs-lookup"><span data-stu-id="bf3ed-124">Create a directory named *MLModels* in your project to save your model:</span></span>

    <span data-ttu-id="bf3ed-125">在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新文件夹”。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-125">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="bf3ed-126">键入“MLModels”，再按 Enter。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-126">Type "MLModels" and hit Enter.</span></span>

1. <span data-ttu-id="bf3ed-127">安装“Microsoft.ML NuGet 包”：</span><span class="sxs-lookup"><span data-stu-id="bf3ed-127">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="bf3ed-128">在“解决方案资源管理器”中，右键单击项目，然后选择“管理 NuGet 包”。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-128">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="bf3ed-129">将“nuget.org”选择为“包源”，选择“浏览”选项卡并搜索“Microsoft.ML”，在列表中选择该包，然后选择“安装”按钮。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-129">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="bf3ed-130">选择“预览更改”对话框上的“确定”按钮，如果你同意所列包的许可条款，则选择“接受许可”对话框上的“我接受”按钮。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-130">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="add-pre-built-model-to-project"></a><span data-ttu-id="bf3ed-131">将预生成的模型添加到项目</span><span class="sxs-lookup"><span data-stu-id="bf3ed-131">Add Pre-built Model To Project</span></span>

1. <span data-ttu-id="bf3ed-132">将预生成的模型复制到 MLModels 文件夹。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-132">Copy your pre-built model to the *MLModels* folder.</span></span>
1. <span data-ttu-id="bf3ed-133">在“解决方案资源管理器”中，右键单击预生成的模型文件，并选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-133">In Solution Explorer, right-click your pre-built model file and select **Properties**.</span></span> <span data-ttu-id="bf3ed-134">在“高级”下，将“复制到输出目录”的值更改为“如果较新则复制”。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-134">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

## <a name="create-function-to-analyze-sentiment"></a><span data-ttu-id="bf3ed-135">创建情绪分析函数</span><span class="sxs-lookup"><span data-stu-id="bf3ed-135">Create Function to Analyze Sentiment</span></span>

<span data-ttu-id="bf3ed-136">创建情绪预测类。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-136">Create a class to predict sentiment.</span></span> <span data-ttu-id="bf3ed-137">向项目添加一个新类：</span><span class="sxs-lookup"><span data-stu-id="bf3ed-137">Add a new class to your project:</span></span>

1. <span data-ttu-id="bf3ed-138">在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新项”。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-138">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="bf3ed-139">在“添加新项”对话框中，选择“Azure 函数”，并将“名称”字段更改为“AnalyzeSentiment.cs”。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-139">In the **Add New Item** dialog box, select **Azure Function** and change the **Name** field to *AnalyzeSentiment.cs*.</span></span> <span data-ttu-id="bf3ed-140">然后，选择“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-140">Then, select the **Add** button.</span></span>

1. <span data-ttu-id="bf3ed-141">在“新 Azure 函数”对话框中，选择“Http 触发器”。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-141">In the **New Azure Function** dialog box, select **Http Trigger**.</span></span> <span data-ttu-id="bf3ed-142">然后，选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-142">Then, select the **OK** button.</span></span>

    <span data-ttu-id="bf3ed-143">此时，AnalyzeSentiment.cs 文件在代码编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-143">The *AnalyzeSentiment.cs* file opens in the code editor.</span></span> <span data-ttu-id="bf3ed-144">将下面的 `using` 语句添加到 GitHubIssueData.cs 的顶部：</span><span class="sxs-lookup"><span data-stu-id="bf3ed-144">Add the following `using` statement to the top of *GitHubIssueData.cs*:</span></span>

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
using Microsoft.ML;
using Microsoft.ML.Core.Data;
using Microsoft.ML.Data;
using MLNETServerless.DataModels;
```

### <a name="create-data-models"></a><span data-ttu-id="bf3ed-145">创建数据模型</span><span class="sxs-lookup"><span data-stu-id="bf3ed-145">Create Data Models</span></span>

<span data-ttu-id="bf3ed-146">需要为输入数据和预测创建一些类。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-146">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="bf3ed-147">向项目添加一个新类：</span><span class="sxs-lookup"><span data-stu-id="bf3ed-147">Add a new class to your project:</span></span>

1. <span data-ttu-id="bf3ed-148">在项目中创建“DataModels”目录，用于保存数据模型：在“解决方案资源管理器”中，右键单击项目，并依次选择“添加”>“新文件夹”。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-148">Create a directory named *DataModels* in your project to save your data models: In Solution Explorer, right-click on your project and select **Add > New Folder**.</span></span> <span data-ttu-id="bf3ed-149">键入“DataModels”，再按 Enter。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-149">Type "DataModels" and hit Enter.</span></span>
2. <span data-ttu-id="bf3ed-150">在“解决方案资源管理器”中，右键单击“DataModels”目录，再依次选择“添加”>“新项”。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-150">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
3. <span data-ttu-id="bf3ed-151">在“添加新项”对话框中，选择“类”并将“名称”字段更改为“SentimentData.cs”。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-151">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="bf3ed-152">然后，选择“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-152">Then, select the **Add** button.</span></span> <span data-ttu-id="bf3ed-153">“SentimentData.cs”文件随即在代码编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-153">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="bf3ed-154">将以下 using 语句添加到 SentimentData.cs 顶部：</span><span class="sxs-lookup"><span data-stu-id="bf3ed-154">Add the following using statement to the top of *SentimentData.cs*:</span></span>

```csharp
using Microsoft.ML.Data;
```

<span data-ttu-id="bf3ed-155">删除现有类定义，并将以下代码添加到 SentimentData.cs 文件：</span><span class="sxs-lookup"><span data-stu-id="bf3ed-155">Remove the existing class definition and add the following code to the SentimentData.cs file:</span></span>

```csharp
public class SentimentData
{
    [LoadColumn(0)]
    public bool Label { get; set; }
    [LoadColumn(1)]
    public string Text { get; set; }
}
```

4. <span data-ttu-id="bf3ed-156">在“解决方案资源管理器”中，右键单击“DataModels”目录，再依次选择“添加”>“新项”。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-156">In Solution Explorer, right-click the *DataModels* directory, and then select **Add > New Item**.</span></span>
5. <span data-ttu-id="bf3ed-157">在“添加新项”对话框中，选择“类”，并将“名称”字段更改为“SentimentPrediction.cs”。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-157">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentPrediction.cs*.</span></span> <span data-ttu-id="bf3ed-158">然后，选择“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-158">Then, select the **Add** button.</span></span> <span data-ttu-id="bf3ed-159">此时，SentimentPrediction.cs 文件在代码编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-159">The *SentimentPrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="bf3ed-160">将以下 using 语句添加到 SentimentPrediction.cs 顶部：</span><span class="sxs-lookup"><span data-stu-id="bf3ed-160">Add the following using statement to the top of *SentimentPrediction.cs*:</span></span>

```csharp
using Microsoft.ML.Data;
```

<span data-ttu-id="bf3ed-161">删除现有类定义，并将以下代码添加到 SentimentPrediction.cs 文件：</span><span class="sxs-lookup"><span data-stu-id="bf3ed-161">Remove the existing class definition and add the following code to the *SentimentPrediction.cs* file:</span></span>

```csharp
public class SentimentPrediction
{
    [ColumnName("PredictedLabel")]
    public bool Prediction { get; set; }
}
```

### <a name="add-prediction-logic"></a><span data-ttu-id="bf3ed-162">添加预测逻辑</span><span class="sxs-lookup"><span data-stu-id="bf3ed-162">Add Prediction Logic</span></span>

<span data-ttu-id="bf3ed-163">将 AnalyzeSentiment 类中 Run 方法的现有实现替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="bf3ed-163">Replace the existing implementation of *Run* method in *AnalyzeSentiment* class with the following code:</span></span>

```csharp
    public static async Task<IActionResult> Run(
        [HttpTrigger(AuthorizationLevel.Function,"post", Route = null)] HttpRequest req,
        ILogger log)
    {
        log.LogInformation("C# HTTP trigger function processed a request.");

        //Create Context
        MLContext mlContext = new MLContext();

        //Load Model
        using (var fs = File.OpenRead("MLModels/sentiment_model.zip"))
        {
            model = mlContext.Model.Load(fs);
        }

        //Parse HTTP Request Body
        string requestBody = await new StreamReader(req.Body).ReadToEndAsync();
        SentimentData data = JsonConvert.DeserializeObject<SentimentData>(requestBody);

        //Create Prediction Engine
        PredictionEngine<SentimentData, SentimentPrediction> predictionEngine = model.CreatePredictionEngine<SentimentData, SentimentPrediction>(mlContext);

        //Make Prediction
        SentimentPrediction prediction = predictionEngine.Predict(data);

        //Convert prediction to string
        string isToxic = Convert.ToBoolean(prediction.Prediction) ? "Toxic" : "Not Toxic";

        //Return Prediction
        return (ActionResult)new OkObjectResult(isToxic);
    }
}
```

## <a name="test-locally"></a><span data-ttu-id="bf3ed-164">本地测试</span><span class="sxs-lookup"><span data-stu-id="bf3ed-164">Test Locally</span></span>

<span data-ttu-id="bf3ed-165">至此，已完成所有设置，是时候测试应用程序了：</span><span class="sxs-lookup"><span data-stu-id="bf3ed-165">Now that everything is set up, it's time to test the application:</span></span>

1. <span data-ttu-id="bf3ed-166">运行此应用程序</span><span class="sxs-lookup"><span data-stu-id="bf3ed-166">Run the application</span></span>
1. <span data-ttu-id="bf3ed-167">打开 PowerShell，并在提示符中输入代码（其中，PORT 是应用程序运行所在的端口）。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-167">Open PowerShell and enter the code into the prompt where PORT is the port your application is running on.</span></span> <span data-ttu-id="bf3ed-168">端口通常是 7071。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-168">Typically the port is 7071.</span></span> 

```powershell
Invoke-RestMethod "http://localhost:<PORT>/api/AnalyzeSentiment" -Method Post -Body (@{Text="This is a very rude movie"} | ConvertTo-Json) -ContentType "application/json"
```

<span data-ttu-id="bf3ed-169">如果成功，输出文本应如下所示：</span><span class="sxs-lookup"><span data-stu-id="bf3ed-169">If successful, the output should look similar to the text below:</span></span>

```powershell
Toxic
```

<span data-ttu-id="bf3ed-170">祝贺你！</span><span class="sxs-lookup"><span data-stu-id="bf3ed-170">Congratulations!</span></span> <span data-ttu-id="bf3ed-171">你已成功使用 Azure Functions 通过 Internet 提供模型进行预测。</span><span class="sxs-lookup"><span data-stu-id="bf3ed-171">You have successfully served your model to make predictions over the internet using an Azure Function.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bf3ed-172">后续步骤</span><span class="sxs-lookup"><span data-stu-id="bf3ed-172">Next Steps</span></span>

- [<span data-ttu-id="bf3ed-173">部署到 Azure</span><span class="sxs-lookup"><span data-stu-id="bf3ed-173">Deploy to Azure</span></span>](/azure/azure-functions/functions-develop-vs#publish-to-azure)
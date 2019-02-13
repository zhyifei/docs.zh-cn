---
title: 在情绪分析二元分类方案中使用 ML.NET
description: 了解如何在二元分类方案中使用 ML.NET，以了解如何使用情绪预测来采取相应措施。
ms.date: 01/15/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 47cf9deb9452d15aee8cf4c1ebc5e3d0f1aa10ae
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627990"
---
# <a name="tutorial-use-mlnet-in-a-sentiment-analysis-binary-classification-scenario"></a><span data-ttu-id="2183a-103">教程：在情绪分析二元分类方案中使用 ML.NET</span><span class="sxs-lookup"><span data-stu-id="2183a-103">Tutorial: Use ML.NET in a sentiment analysis binary classification scenario</span></span>

> [!NOTE]
> <span data-ttu-id="2183a-104">本主题引用 ML.NET（目前处于预览状态），且材料可能会更改。</span><span class="sxs-lookup"><span data-stu-id="2183a-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="2183a-105">有关详细信息，请访问 [ML.NET 简介](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)。</span><span class="sxs-lookup"><span data-stu-id="2183a-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="2183a-106">此示例教程通过在 Visual Studio 2017 中使用 C# 的 .NET Core 控制台应用程序，演示如何使用 ML.NET 创建情绪分类器。</span><span class="sxs-lookup"><span data-stu-id="2183a-106">This sample tutorial illustrates using ML.NET to create a sentiment classifier via a .NET Core console application using C# in Visual Studio 2017.</span></span>

<span data-ttu-id="2183a-107">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="2183a-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="2183a-108">了解问题</span><span class="sxs-lookup"><span data-stu-id="2183a-108">Understand the problem</span></span>
> * <span data-ttu-id="2183a-109">选择适当的机器学习任务</span><span class="sxs-lookup"><span data-stu-id="2183a-109">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="2183a-110">准备数据</span><span class="sxs-lookup"><span data-stu-id="2183a-110">Prepare your data</span></span>
> * <span data-ttu-id="2183a-111">创建学习管道</span><span class="sxs-lookup"><span data-stu-id="2183a-111">Create the learning pipeline</span></span>
> * <span data-ttu-id="2183a-112">加载分类器</span><span class="sxs-lookup"><span data-stu-id="2183a-112">Load a classifier</span></span>
> * <span data-ttu-id="2183a-113">定型模型</span><span class="sxs-lookup"><span data-stu-id="2183a-113">Train the model</span></span>
> * <span data-ttu-id="2183a-114">使用不同数据集评估模型</span><span class="sxs-lookup"><span data-stu-id="2183a-114">Evaluate the model with a different dataset</span></span>
> * <span data-ttu-id="2183a-115">使用模型预测单个测试数据结果实例</span><span class="sxs-lookup"><span data-stu-id="2183a-115">Predict a single instance of test data outcome with the model</span></span>
> * <span data-ttu-id="2183a-116">使用加载模型预测测试数据结果</span><span class="sxs-lookup"><span data-stu-id="2183a-116">Predict the test data outcomes with a loaded model</span></span>

## <a name="sentiment-analysis-sample-overview"></a><span data-ttu-id="2183a-117">情绪分析示例概述</span><span class="sxs-lookup"><span data-stu-id="2183a-117">Sentiment analysis sample overview</span></span>

<span data-ttu-id="2183a-118">该示例是使用 ML.NET 定型模型的控制台应用，以将情绪分类和预测为正面或负面。</span><span class="sxs-lookup"><span data-stu-id="2183a-118">The sample is a console app that uses ML.NET to train a model that classifies and predicts sentiment as either positive or negative.</span></span> <span data-ttu-id="2183a-119">它还使用第二个数据集对模型进行评估，以进行质量分析。</span><span class="sxs-lookup"><span data-stu-id="2183a-119">It also evaluates the model with a second dataset for quality analysis.</span></span> <span data-ttu-id="2183a-120">情绪数据集来自 WikiDetox 项目。</span><span class="sxs-lookup"><span data-stu-id="2183a-120">The sentiment datasets are from the WikiDetox project.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2183a-121">系统必备</span><span class="sxs-lookup"><span data-stu-id="2183a-121">Prerequisites</span></span>

* <span data-ttu-id="2183a-122">安装了“.NET Core 跨平台开发”工作负载的 [Visual Studio 2017 15.6 或更高版本](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)。</span><span class="sxs-lookup"><span data-stu-id="2183a-122">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* <span data-ttu-id="2183a-123">[Wikipedia detox 行数据制表符分隔文件 (wikiPedia-detox-250-line-data.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv)。</span><span class="sxs-lookup"><span data-stu-id="2183a-123">The [Wikipedia detox line data tab separated file (wikiPedia-detox-250-line-data.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv).</span></span>
* <span data-ttu-id="2183a-124">[Wikipedia detox 行测试制表符分隔文件 (wikipedia-detox-250-line-test.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv)。</span><span class="sxs-lookup"><span data-stu-id="2183a-124">The [Wikipedia detox line test tab separated file (wikipedia-detox-250-line-test.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv).</span></span>

## <a name="machine-learning-workflow"></a><span data-ttu-id="2183a-125">机器学习工作流</span><span class="sxs-lookup"><span data-stu-id="2183a-125">Machine learning workflow</span></span>

<span data-ttu-id="2183a-126">本教程后面介绍了机器学习工作流，使该过程能够有序地进行。</span><span class="sxs-lookup"><span data-stu-id="2183a-126">This tutorial follows a machine learning workflow that enables the process to move in an orderly fashion.</span></span>

<span data-ttu-id="2183a-127">工作流阶段如下所示：</span><span class="sxs-lookup"><span data-stu-id="2183a-127">The workflow phases are as follows:</span></span>

1. <span data-ttu-id="2183a-128">**了解问题**</span><span class="sxs-lookup"><span data-stu-id="2183a-128">**Understand the problem**</span></span>
2. <span data-ttu-id="2183a-129">**准备数据**</span><span class="sxs-lookup"><span data-stu-id="2183a-129">**Prepare your data**</span></span>
   * <span data-ttu-id="2183a-130">**加载数据**</span><span class="sxs-lookup"><span data-stu-id="2183a-130">**Load the data**</span></span>
   * <span data-ttu-id="2183a-131">**提取功能（转换数据）**</span><span class="sxs-lookup"><span data-stu-id="2183a-131">**Extract features (Transform your data)**</span></span>
3. <span data-ttu-id="2183a-132">**生成并定型**</span><span class="sxs-lookup"><span data-stu-id="2183a-132">**Build and train**</span></span> 
   * <span data-ttu-id="2183a-133">**定型模型**</span><span class="sxs-lookup"><span data-stu-id="2183a-133">**Train the model**</span></span>
   * <span data-ttu-id="2183a-134">**评估模型**</span><span class="sxs-lookup"><span data-stu-id="2183a-134">**Evaluate the model**</span></span>
4. <span data-ttu-id="2183a-135">**运行**</span><span class="sxs-lookup"><span data-stu-id="2183a-135">**Run**</span></span>
   * <span data-ttu-id="2183a-136">**模型使用**</span><span class="sxs-lookup"><span data-stu-id="2183a-136">**Model consumption**</span></span>

### <a name="understand-the-problem"></a><span data-ttu-id="2183a-137">了解问题</span><span class="sxs-lookup"><span data-stu-id="2183a-137">Understand the problem</span></span>

<span data-ttu-id="2183a-138">首先需要了解问题，因此可以将其分解为能够支持构建和定型模型的几个部分。</span><span class="sxs-lookup"><span data-stu-id="2183a-138">You first need to understand the problem, so you can break it down to parts that can support building and training the model.</span></span> <span data-ttu-id="2183a-139">分解问题可以预测和评估结果。</span><span class="sxs-lookup"><span data-stu-id="2183a-139">Breaking the problem down allows you to predict and evaluate the results.</span></span>

<span data-ttu-id="2183a-140">本教程中的问题是了解传入网站评论情绪以采取相应的措施。</span><span class="sxs-lookup"><span data-stu-id="2183a-140">The problem for this tutorial is to understand incoming website comment sentiment to take the appropriate action.</span></span>

<span data-ttu-id="2183a-141">可以将问题分解为你想要对模型进行定型的数据的情绪文本和情绪值，以及可以评估和以操作状态使用的预期情绪值。</span><span class="sxs-lookup"><span data-stu-id="2183a-141">You can break down the problem to the sentiment text and sentiment value for the data you want to train the model with, and a predicted sentiment value that you can evaluate and then use operationally.</span></span>

<span data-ttu-id="2183a-142">然后，需要确定情绪，这将帮助你进行机器学习任务选择。</span><span class="sxs-lookup"><span data-stu-id="2183a-142">You then need to **determine** the sentiment, which helps you with the machine learning task selection.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="2183a-143">选择适当的机器学习任务</span><span class="sxs-lookup"><span data-stu-id="2183a-143">Select the appropriate machine learning task</span></span>

<span data-ttu-id="2183a-144">通过此问题，你将了解以下情况：</span><span class="sxs-lookup"><span data-stu-id="2183a-144">With this problem, you know the following facts:</span></span>

<span data-ttu-id="2183a-145">定型数据：网站评论可以是负面 (1) 或正面 (0)（情绪）。</span><span class="sxs-lookup"><span data-stu-id="2183a-145">Training data: website comments can be toxic (1) or not toxic (0) (**sentiment**).</span></span>
<span data-ttu-id="2183a-146">预测新网站评论的情绪，负面或正面，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="2183a-146">Predict the **sentiment** of a new website comment, either toxic or not toxic, such as in the following examples:</span></span>

* <span data-ttu-id="2183a-147">请避免向 Wikipedia 添加无意义的内容。</span><span class="sxs-lookup"><span data-stu-id="2183a-147">Please refrain from adding nonsense to Wikipedia.</span></span>
* <span data-ttu-id="2183a-148">他是最棒的，且文章应如此表述。</span><span class="sxs-lookup"><span data-stu-id="2183a-148">He is the best, and the article should say that.</span></span>

<span data-ttu-id="2183a-149">分类机器学习任务最适合此方案。</span><span class="sxs-lookup"><span data-stu-id="2183a-149">The classification machine learning task is best suited for this scenario.</span></span>

### <a name="about-the-classification-task"></a><span data-ttu-id="2183a-150">有关分类任务</span><span class="sxs-lookup"><span data-stu-id="2183a-150">About the classification task</span></span>

<span data-ttu-id="2183a-151">分类是一项机器学习任务，它使用数据来确定某个项或数据行的类别、类型或类。</span><span class="sxs-lookup"><span data-stu-id="2183a-151">Classification is a machine learning task that uses data to **determine** the category, type, or class of an item or row of data.</span></span> <span data-ttu-id="2183a-152">例如，可以使用分类：</span><span class="sxs-lookup"><span data-stu-id="2183a-152">For example, you can use classification to:</span></span>

* <span data-ttu-id="2183a-153">识别情绪为正面还是负面。</span><span class="sxs-lookup"><span data-stu-id="2183a-153">Identify sentiment as positive or negative.</span></span>
* <span data-ttu-id="2183a-154">将电子邮件分类为垃圾邮件或正常邮件。</span><span class="sxs-lookup"><span data-stu-id="2183a-154">Classify email as spam, junk, or good.</span></span>
* <span data-ttu-id="2183a-155">确定患者的实验室样本是否癌变。</span><span class="sxs-lookup"><span data-stu-id="2183a-155">Determine whether a patient's lab sample is cancerous.</span></span>
* <span data-ttu-id="2183a-156">根据客户对销售活动的反应倾向对客户进行分类。</span><span class="sxs-lookup"><span data-stu-id="2183a-156">Categorize customers by their propensity to respond to a sales campaign.</span></span>

<span data-ttu-id="2183a-157">分类任务通常为以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="2183a-157">Classification tasks are frequently one of the following types:</span></span>

* <span data-ttu-id="2183a-158">二元：A 或 B。</span><span class="sxs-lookup"><span data-stu-id="2183a-158">Binary: either A or B.</span></span>
* <span data-ttu-id="2183a-159">多类：可以通过使用单个模型来预测多个类别。</span><span class="sxs-lookup"><span data-stu-id="2183a-159">Multiclass: multiple categories that can be predicted by using a single model.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="2183a-160">创建控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="2183a-160">Create a console application</span></span>

1. <span data-ttu-id="2183a-161">打开 Visual Studio 2017。</span><span class="sxs-lookup"><span data-stu-id="2183a-161">Open Visual Studio 2017.</span></span> <span data-ttu-id="2183a-162">从菜单栏中选择“文件” > “新建” > “项目”。</span><span class="sxs-lookup"><span data-stu-id="2183a-162">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="2183a-163">在“新项目”对话框中，依次选择“Visual C#”和“.NET Core”节点。</span><span class="sxs-lookup"><span data-stu-id="2183a-163">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="2183a-164">然后，选择“控制台应用程序(.NET Core)”项目模板。</span><span class="sxs-lookup"><span data-stu-id="2183a-164">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="2183a-165">在“名称”文本框中，键入“SentimentAnalysis”，然后选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="2183a-165">In the **Name** text box, type "SentimentAnalysis" and then select the **OK** button.</span></span>

2. <span data-ttu-id="2183a-166">在项目中创建一个名为“数据”的目录来保存数据集文件：</span><span class="sxs-lookup"><span data-stu-id="2183a-166">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="2183a-167">在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新文件夹”。</span><span class="sxs-lookup"><span data-stu-id="2183a-167">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="2183a-168">键入“Data”，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="2183a-168">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="2183a-169">安装“Microsoft.ML NuGet 包”：</span><span class="sxs-lookup"><span data-stu-id="2183a-169">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="2183a-170">在“解决方案资源管理器”中，右键单击项目，然后选择“管理 NuGet 包”。</span><span class="sxs-lookup"><span data-stu-id="2183a-170">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="2183a-171">将“nuget.org”选择为“包源”，选择“浏览”选项卡并搜索“Microsoft.ML”，在列表中选择该包，然后选择“安装”按钮。</span><span class="sxs-lookup"><span data-stu-id="2183a-171">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="2183a-172">选择“预览更改”对话框上的“确定”按钮，如果你同意所列包的许可条款，则选择“接受许可”对话框上的“我接受”按钮。</span><span class="sxs-lookup"><span data-stu-id="2183a-172">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="2183a-173">准备数据</span><span class="sxs-lookup"><span data-stu-id="2183a-173">Prepare your data</span></span>

1. <span data-ttu-id="2183a-174">下载 [WikiPedia detox-250-line-data.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv) 和 [wikipedia-detox-250-line-test.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv) 数据集并将它们保存到先前创建的“Data”文件夹。</span><span class="sxs-lookup"><span data-stu-id="2183a-174">Download the [WikiPedia detox-250-line-data.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv) and the [wikipedia-detox-250-line-test.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv) data sets and save them to the *Data* folder previously created.</span></span> <span data-ttu-id="2183a-175">第一个数据集定型机器学习模型，第二个数据集可用来评估模型的准确度。</span><span class="sxs-lookup"><span data-stu-id="2183a-175">The first dataset trains the machine learning model and the second can be used to evaluate how accurate your model is.</span></span>

2. <span data-ttu-id="2183a-176">在“解决方案资源管理器”中，右键单击每个 \*.tsv 文件，然后选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="2183a-176">In Solution Explorer, right-click each of the \*.tsv files and select **Properties**.</span></span> <span data-ttu-id="2183a-177">在“高级”下，将“复制到输出目录”的值更改为“如果较新则复制”。</span><span class="sxs-lookup"><span data-stu-id="2183a-177">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="2183a-178">创建类和定义路径</span><span class="sxs-lookup"><span data-stu-id="2183a-178">Create classes and define paths</span></span>

<span data-ttu-id="2183a-179">将以下附加的 `using` 语句添加到“Program.cs”文件顶部：</span><span class="sxs-lookup"><span data-stu-id="2183a-179">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#1 "Add necessary usings")]

<span data-ttu-id="2183a-180">需要创建三个全局字段，来保存最近下载的文件路径和 `TextLoader` 的全局变量：</span><span class="sxs-lookup"><span data-stu-id="2183a-180">You need to create three global fields to hold the paths to the recently downloaded files, and a global variable for the `TextLoader`:</span></span>

* <span data-ttu-id="2183a-181">`_trainDataPath` 具有用于定型模型的数据集路径。</span><span class="sxs-lookup"><span data-stu-id="2183a-181">`_trainDataPath` has the path to the dataset used to train the model.</span></span>
* <span data-ttu-id="2183a-182">`_testDataPath` 具有用于评估模型的数据集路径。</span><span class="sxs-lookup"><span data-stu-id="2183a-182">`_testDataPath` has the path to the dataset used to evaluate the model.</span></span>
* <span data-ttu-id="2183a-183">`_modelPath` 具有在其中保存定型模型的路径。</span><span class="sxs-lookup"><span data-stu-id="2183a-183">`_modelPath` has the path where the trained model is saved.</span></span>
* <span data-ttu-id="2183a-184">`_textLoader` 是用于加载和转换数据集的 <xref:Microsoft.ML.Data.TextLoader>。</span><span class="sxs-lookup"><span data-stu-id="2183a-184">`_textLoader` is the <xref:Microsoft.ML.Data.TextLoader> used to load and transform the datasets.</span></span>

<span data-ttu-id="2183a-185">将以下代码添加到 `Main` 方法上方的行中，以指定这些路径和 `_textLoader` 变量：</span><span class="sxs-lookup"><span data-stu-id="2183a-185">Add the following code to the line right above the `Main` method to specify those paths and the `_textLoader` variable:</span></span>

[!code-csharp[Declare global variables](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#2 "Declare global variables")]

<span data-ttu-id="2183a-186">需要为输入数据和预测创建一些类。</span><span class="sxs-lookup"><span data-stu-id="2183a-186">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="2183a-187">向项目添加一个新类：</span><span class="sxs-lookup"><span data-stu-id="2183a-187">Add a new class to your project:</span></span>

1. <span data-ttu-id="2183a-188">在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新项”。</span><span class="sxs-lookup"><span data-stu-id="2183a-188">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="2183a-189">在“添加新项”对话框中，选择“类”并将“名称”字段更改为“SentimentData.cs”。</span><span class="sxs-lookup"><span data-stu-id="2183a-189">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="2183a-190">然后，选择“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="2183a-190">Then, select the **Add** button.</span></span>

    <span data-ttu-id="2183a-191">“SentimentData.cs”文件随即在代码编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="2183a-191">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="2183a-192">将下面的 `using` 语句添加到 SentimentData.cs 的顶部：</span><span class="sxs-lookup"><span data-stu-id="2183a-192">Add the following `using` statement to the top of *SentimentData.cs*:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#1 "Add necessary usings")]

<span data-ttu-id="2183a-193">删除现有类定义并向“SentimentData.cs”文件添加以下代码，其中有两个类 `SentimentData` 和 `SentimentPrediction`：</span><span class="sxs-lookup"><span data-stu-id="2183a-193">Remove the existing class definition and add the following code, which has two classes `SentimentData` and `SentimentPrediction`, to the *SentimentData.cs* file:</span></span>

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#2 "Declare data record types")]

<span data-ttu-id="2183a-194">`SentimentData` 是输入数据集类，且具有带正或负情绪值的 `float` (`Sentiment`) 和评论字符串 (`SentimentText`)。</span><span class="sxs-lookup"><span data-stu-id="2183a-194">`SentimentData` is the input dataset class and has a `float` (`Sentiment`) that has a value for sentiment of either positive or negative, and a string for the comment (`SentimentText`).</span></span> <span data-ttu-id="2183a-195">这两个字段均有随附的 `Column` 属性。</span><span class="sxs-lookup"><span data-stu-id="2183a-195">Both fields have `Column` attributes attached to them.</span></span> <span data-ttu-id="2183a-196">此属性描述数据文件中每个字段的顺序，以及哪个是 `Label` 字段。</span><span class="sxs-lookup"><span data-stu-id="2183a-196">This attribute describes the order of each field in the data file, and which is the `Label` field.</span></span> <span data-ttu-id="2183a-197">`SentimentPrediction` 是在定型模型后用于预测的类。</span><span class="sxs-lookup"><span data-stu-id="2183a-197">`SentimentPrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="2183a-198">它有一个布尔值 (`Sentiment`) 和一个 `PredictedLabel` `ColumnName` 属性。</span><span class="sxs-lookup"><span data-stu-id="2183a-198">It has a single boolean (`Sentiment`) and a `PredictedLabel` `ColumnName` attribute.</span></span> <span data-ttu-id="2183a-199">`Label` 用于创建和定型模型，并且与第二个数据集结合使用来评估模型。</span><span class="sxs-lookup"><span data-stu-id="2183a-199">The `Label` is used to create and train the model, and it's also used with a second dataset to evaluate the model.</span></span> <span data-ttu-id="2183a-200">`PredictedLabel` 在预测和评估过程中使用。</span><span class="sxs-lookup"><span data-stu-id="2183a-200">The `PredictedLabel` is used during prediction and evaluation.</span></span> <span data-ttu-id="2183a-201">对于计算，将使用带定型数据的输入、预测值和模型。</span><span class="sxs-lookup"><span data-stu-id="2183a-201">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="2183a-202">使用 ML.NET 构建模型时，首先要创建一个 `MLContext`。</span><span class="sxs-lookup"><span data-stu-id="2183a-202">When building a model with ML.NET you start by creating an `MLContext`.</span></span> <span data-ttu-id="2183a-203">这在概念上相当于在实体框架中使用 `DbContext`。</span><span class="sxs-lookup"><span data-stu-id="2183a-203">This is comparable conceptually to using `DbContext` in Entity Framework.</span></span> <span data-ttu-id="2183a-204">该环境为 ML 作业提供一个上下文，可以用于异常情况跟踪和日志记录。</span><span class="sxs-lookup"><span data-stu-id="2183a-204">The environment provides a context for your ML job that can be used for exception tracking and logging.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="2183a-205">在 Main 中初始化变量</span><span class="sxs-lookup"><span data-stu-id="2183a-205">Initialize variables in Main</span></span>

<span data-ttu-id="2183a-206">创建一个名为 `mlContext` 的变量并将其初始化为 `MLContext` 的新实例。</span><span class="sxs-lookup"><span data-stu-id="2183a-206">Create a variable called `mlContext` and initialize it with a new instance of `MLContext`.</span></span>  <span data-ttu-id="2183a-207">用下面 `Main` 方法中的代码替换 `Console.WriteLine("Hello World!")` 行：</span><span class="sxs-lookup"><span data-stu-id="2183a-207">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#3 "Create the ML Context")]

<span data-ttu-id="2183a-208">下一步，为设置数据加载，请初始化 `_textLoader` 全局变量以便重用它。</span><span class="sxs-lookup"><span data-stu-id="2183a-208">Next, to setup for data loading initialize the `_textLoader` global variable in order to reuse it.</span></span>  <span data-ttu-id="2183a-209">请注意，将使用 `TextReader`。</span><span class="sxs-lookup"><span data-stu-id="2183a-209">Notice that you're using a `TextReader`.</span></span> <span data-ttu-id="2183a-210">当使用 `TextReader` 创建 `TextLoader` 时，请传入需要的上下文和启用自定义的 <xref:Microsoft.ML.Data.TextLoader.Arguments> 类。</span><span class="sxs-lookup"><span data-stu-id="2183a-210">When you create a `TextLoader` using a `TextReader`, you pass in the context needed and the <xref:Microsoft.ML.Data.TextLoader.Arguments> class which enables customization.</span></span>

 <span data-ttu-id="2183a-211">通过将包含所有列名及其类型的 <xref:Microsoft.ML.Data.TextLoader.Column> 对象数组传递给加载程序来指定数据模式。</span><span class="sxs-lookup"><span data-stu-id="2183a-211">Specify the data schema by passing an array of <xref:Microsoft.ML.Data.TextLoader.Column> objects to the loader containing all the column names and their types.</span></span> <span data-ttu-id="2183a-212">以前在创建 `SentimentData` 类时定义了数据模式。</span><span class="sxs-lookup"><span data-stu-id="2183a-212">You defined the data schema previously when you created our `SentimentData` class.</span></span> <span data-ttu-id="2183a-213">对于我们的架构，第一列 (Label) 是 <xref:System.Boolean>（预测），第二列 (SentimentText) 是文本/字符串类型功能，用于预测情绪。</span><span class="sxs-lookup"><span data-stu-id="2183a-213">For our schema, the first column (Label) is a <xref:System.Boolean> (the prediction) and the second column (SentimentText) is the feature of type text/string used for predicting the sentiment.</span></span>
<span data-ttu-id="2183a-214">`TextReader` 类返回完全初始化的 <xref:Microsoft.ML.Data.TextLoader></span><span class="sxs-lookup"><span data-stu-id="2183a-214">The `TextReader` class returns a fully initialized <xref:Microsoft.ML.Data.TextLoader></span></span>  

<span data-ttu-id="2183a-215">若要初始化 `_textLoader` 全局变量以将其重复用于所需的数据集，请在 `mlContext` 初始化后添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="2183a-215">To initialize the `_textLoader` global variable in order to reuse it for the needed datasets, add the following code after the  `mlContext` initialization:</span></span>

[!code-csharp[initTextReader](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#4 "Initialize the TextReader")]

<span data-ttu-id="2183a-216">将以下代码作为下一行代码添加到 `Main` 方法中：</span><span class="sxs-lookup"><span data-stu-id="2183a-216">Add the following as the next line of code in the `Main` method:</span></span>

[!code-csharp[Train](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#5 "Train your model")]

<span data-ttu-id="2183a-217">`Train` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="2183a-217">The `Train` method executes the following tasks:</span></span>

* <span data-ttu-id="2183a-218">加载数据。</span><span class="sxs-lookup"><span data-stu-id="2183a-218">Loads the data.</span></span>
* <span data-ttu-id="2183a-219">提取并转换数据。</span><span class="sxs-lookup"><span data-stu-id="2183a-219">Extracts and transforms the data.</span></span>
* <span data-ttu-id="2183a-220">定型模型。</span><span class="sxs-lookup"><span data-stu-id="2183a-220">Trains the model.</span></span>
* <span data-ttu-id="2183a-221">根据测试数据预测情绪。</span><span class="sxs-lookup"><span data-stu-id="2183a-221">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="2183a-222">返回模型。</span><span class="sxs-lookup"><span data-stu-id="2183a-222">Returns the model.</span></span>

<span data-ttu-id="2183a-223">使用下面的代码紧随 `Main` 方法后创建 `Train` 方法：</span><span class="sxs-lookup"><span data-stu-id="2183a-223">Create the `Train` method, just after the `Main` method, using the following code:</span></span>

```csharp
 public static ITransformer Train(MLContext mlContext, string dataPath)
{

}
```

<span data-ttu-id="2183a-224">请注意，两个参数传递给 Train 方法；`MLContext` 用于上下文 (`mlContext`)，<xref:System.String> 用于数据集路径 (`dataPath`)。</span><span class="sxs-lookup"><span data-stu-id="2183a-224">Notice that two parameters are passed into the Train method; a `MLContext` for the context (`mlContext`), and a <xref:System.String> for the dataset path (`dataPath`).</span></span> <span data-ttu-id="2183a-225">将多次使用该方法进行定型和测试。</span><span class="sxs-lookup"><span data-stu-id="2183a-225">You're going to use this method more than once for training and testing.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="2183a-226">加载数据</span><span class="sxs-lookup"><span data-stu-id="2183a-226">Load the data</span></span>

<span data-ttu-id="2183a-227">将使用带有 `dataPath` 参数的 `_textLoader` 全局变量加载数据。</span><span class="sxs-lookup"><span data-stu-id="2183a-227">You'll load the data using the `_textLoader` global variable with the `dataPath` parameter.</span></span> <span data-ttu-id="2183a-228">它将返回 <xref:Microsoft.ML.Data.IDataView>。</span><span class="sxs-lookup"><span data-stu-id="2183a-228">It returns a <xref:Microsoft.ML.Data.IDataView>.</span></span> <span data-ttu-id="2183a-229">作为 `Transforms` 的输入和输出，`DataView` 是基本的数据管道类型，与 `LINQ` 中的 `IEnumerable` 类似。</span><span class="sxs-lookup"><span data-stu-id="2183a-229">As the input and output of `Transforms`, a `DataView` is the fundamental data pipeline type, comparable to `IEnumerable` for `LINQ`.</span></span>

<span data-ttu-id="2183a-230">在 ML.NET 中，数据类似于 SQL 视图。</span><span class="sxs-lookup"><span data-stu-id="2183a-230">In ML.NET, data is similar to a SQL view.</span></span> <span data-ttu-id="2183a-231">它是异源数据，会延迟计算并进行架构化。</span><span class="sxs-lookup"><span data-stu-id="2183a-231">It is lazily evaluated, schematized, and heterogenous.</span></span> <span data-ttu-id="2183a-232">该对象是管道的第一部分，并加载数据。</span><span class="sxs-lookup"><span data-stu-id="2183a-232">The object is the first part of the pipeline, and loads the data.</span></span> <span data-ttu-id="2183a-233">对于本教程，它会加载具有注释和相应正面或负面情绪的数据集。</span><span class="sxs-lookup"><span data-stu-id="2183a-233">For this tutorial, it loads a dataset with comments and corresponding toxic or non toxic sentiment.</span></span> <span data-ttu-id="2183a-234">这用于创建模型并对其进行定型。</span><span class="sxs-lookup"><span data-stu-id="2183a-234">This is used to create the model, and train it.</span></span>

 <span data-ttu-id="2183a-235">将以下代码添加为 `Train` 方法的首行：</span><span class="sxs-lookup"><span data-stu-id="2183a-235">Add the following code as the first line of the `Train` method:</span></span>

[!code-csharp[LoadTrainData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#6 "loading training dataset")]

## <a name="extract-and-transform-the-data"></a><span data-ttu-id="2183a-236">提取和转换数据</span><span class="sxs-lookup"><span data-stu-id="2183a-236">Extract and transform the data</span></span>

<span data-ttu-id="2183a-237">预处理和清除数据任务至关重要，需要首先执行才能将数据集有效地用于机器学习。</span><span class="sxs-lookup"><span data-stu-id="2183a-237">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span> <span data-ttu-id="2183a-238">原始数据通常嘈杂不可靠，并且可能缺少值。</span><span class="sxs-lookup"><span data-stu-id="2183a-238">Raw data is often noisy and unreliable, and may be missing values.</span></span> <span data-ttu-id="2183a-239">在没有这些建模任务的情况下使用数据会产生误导性结果。</span><span class="sxs-lookup"><span data-stu-id="2183a-239">Using data without these modeling tasks can produce misleading results.</span></span>

<span data-ttu-id="2183a-240">ML.NET 的转换管道撰写一组自定义转换，在定型或测试数据之前将其应用到数据。</span><span class="sxs-lookup"><span data-stu-id="2183a-240">ML.NET's transform pipelines compose a custom set of transforms that are applied to your data before training or testing.</span></span> <span data-ttu-id="2183a-241">转换的主要目的是为了[特征化](../resources/glossary.md#feature-engineering)数据。</span><span class="sxs-lookup"><span data-stu-id="2183a-241">The transforms' primary purpose is data [featurization](../resources/glossary.md#feature-engineering).</span></span> <span data-ttu-id="2183a-242">机器学习算法理解[特征化](../resources/glossary.md#feature)数据，因此下一步是将文本数据转换为 ML 算法识别的格式。</span><span class="sxs-lookup"><span data-stu-id="2183a-242">Machine learning algorithms understand [featurized](../resources/glossary.md#feature) data, so the next step is to transform our textual data into a format that our ML algorithms recognize.</span></span> <span data-ttu-id="2183a-243">该格式是[数值向量](../resources/glossary.md#numerical-feature-vector)。</span><span class="sxs-lookup"><span data-stu-id="2183a-243">That format is a [numeric vector](../resources/glossary.md#numerical-feature-vector).</span></span>

<span data-ttu-id="2183a-244">下一步，调用将文本列 (`SentimentText`) 列特征化为机器学习算法使用的名为 `Features` 的数值向量的 `mlContext.Transforms.Text.FeaturizeText`。</span><span class="sxs-lookup"><span data-stu-id="2183a-244">Next, call `mlContext.Transforms.Text.FeaturizeText` which featurizes the text column (`SentimentText`) column into a numeric vector called `Features` used by the machine learning algorithm.</span></span> <span data-ttu-id="2183a-245">此为包装器调用，它返回实际上是管道的 <xref:Microsoft.ML.Data.EstimatorChain%601>。</span><span class="sxs-lookup"><span data-stu-id="2183a-245">This is a wrapper call that returns an <xref:Microsoft.ML.Data.EstimatorChain%601> that will effectively be a pipeline.</span></span> <span data-ttu-id="2183a-246">命名此 `pipeline`，因为你将把定型程序附加到 `EstimatorChain`。</span><span class="sxs-lookup"><span data-stu-id="2183a-246">Name this `pipeline` as you will then append the trainer to the `EstimatorChain`.</span></span> <span data-ttu-id="2183a-247">将此添加为下一个代码行：</span><span class="sxs-lookup"><span data-stu-id="2183a-247">Add this as the next line of code:</span></span>

[!code-csharp[TextFeaturizingEstimator](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#7 "Add a TextFeaturizingEstimator")]

<span data-ttu-id="2183a-248">这是预处理/特征化步骤。</span><span class="sxs-lookup"><span data-stu-id="2183a-248">This is the preprocessing/featurization step.</span></span> <span data-ttu-id="2183a-249">使用 ML.NET 中可用的其他组件可以在使用模型时生成更佳结果。</span><span class="sxs-lookup"><span data-stu-id="2183a-249">Using additional components available in ML.NET can enable better results with your model.</span></span>

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="2183a-250">选择学习算法</span><span class="sxs-lookup"><span data-stu-id="2183a-250">Choose a learning algorithm</span></span>

<span data-ttu-id="2183a-251">若要添加定型程序，调用返回 <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryClassificationTrainer> 对象的 `mlContext.Transforms.Text.FeaturizeText` 包装器方法。</span><span class="sxs-lookup"><span data-stu-id="2183a-251">To add the trainer, call the `mlContext.Transforms.Text.FeaturizeText` wrapper method which returns a <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryClassificationTrainer> object.</span></span> <span data-ttu-id="2183a-252">这是一个将在此管道中使用的决策树学习器。</span><span class="sxs-lookup"><span data-stu-id="2183a-252">This is a decision tree learner you'll use in this pipeline.</span></span> <span data-ttu-id="2183a-253">`FastTreeBinaryClassificationTrainer` 追加到 `pipeline` 并接受特征化的 `SentimentText` (`Features`) 和 `Label` 输入参数，以便从历史数据中学习。</span><span class="sxs-lookup"><span data-stu-id="2183a-253">The `FastTreeBinaryClassificationTrainer` is appended to the `pipeline` and accepts the featurized `SentimentText` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span>

<span data-ttu-id="2183a-254">将以下代码添加到 `Train` 方法中：</span><span class="sxs-lookup"><span data-stu-id="2183a-254">Add the following code to the `Train` method:</span></span>

[!code-csharp[FastTreeBinaryClassificationTrainer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#8 "Add a FastTreeBinaryClassificationTrainer")]

## <a name="train-the-model"></a><span data-ttu-id="2183a-255">定型模型</span><span class="sxs-lookup"><span data-stu-id="2183a-255">Train the model</span></span>

<span data-ttu-id="2183a-256">根据已加载和转换的数据集定型模型 <xref:Microsoft.ML.Data.TransformerChain%601>。</span><span class="sxs-lookup"><span data-stu-id="2183a-256">You train the model, <xref:Microsoft.ML.Data.TransformerChain%601>, based on the dataset that has been loaded and transformed.</span></span> <span data-ttu-id="2183a-257">一旦定义了估算器，将使用 <xref:Microsoft.ML.Data.EstimatorChain`1.Fit*> 定型模型，同时提供已经加载的定型数据。</span><span class="sxs-lookup"><span data-stu-id="2183a-257">Once the estimator has been defined, you train your model using the <xref:Microsoft.ML.Data.EstimatorChain`1.Fit*> while providing the already loaded training data.</span></span> <span data-ttu-id="2183a-258">这将返回要用于预测的模型。</span><span class="sxs-lookup"><span data-stu-id="2183a-258">This returns a model to use for predictions.</span></span> <span data-ttu-id="2183a-259">`pipeline.Fit()` 定型管道，并返回基于传入的 `DataView` 的 `Transformer`。</span><span class="sxs-lookup"><span data-stu-id="2183a-259">`pipeline.Fit()` trains the pipeline and returns a `Transformer` based on the `DataView` passed in.</span></span> <span data-ttu-id="2183a-260">在发生这种情况之前不会执行此试验。</span><span class="sxs-lookup"><span data-stu-id="2183a-260">The experiment is not executed until this happens.</span></span>

<span data-ttu-id="2183a-261">将以下代码添加到 `Train` 方法中：</span><span class="sxs-lookup"><span data-stu-id="2183a-261">Add the following code to the `Train` method:</span></span>

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#9 "Train the model")]

### <a name="save-and-return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="2183a-262">保存并返回定型模型以用于评估</span><span class="sxs-lookup"><span data-stu-id="2183a-262">Save and Return the model trained to use for evaluation</span></span>

<span data-ttu-id="2183a-263">此时，你具有可以集成到任何现有或新 .NET 应用程序的 <xref:Microsoft.ML.Data.TransformerChain%601> 类型模型。</span><span class="sxs-lookup"><span data-stu-id="2183a-263">At this point, you have a model of type <xref:Microsoft.ML.Data.TransformerChain%601> that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="2183a-264">在 `Train` 方法末尾返回模型。</span><span class="sxs-lookup"><span data-stu-id="2183a-264">Return the model at the end of the `Train` method.</span></span>

[!code-csharp[ReturnModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#10 "Return the model")]

## <a name="evaluate-the-model"></a><span data-ttu-id="2183a-265">评估模型</span><span class="sxs-lookup"><span data-stu-id="2183a-265">Evaluate the model</span></span>

<span data-ttu-id="2183a-266">你已经创建和定型模型，现在需要使用不同的数据集对其进行评估以保证质量和进行验证。</span><span class="sxs-lookup"><span data-stu-id="2183a-266">Now that you've created and trained the model, you need to evaluate it with a different dataset for quality assurance and validation.</span></span> <span data-ttu-id="2183a-267">在 `Evaluate` 方法中，将传入在 `Train` 中创建的模型以进行评估。</span><span class="sxs-lookup"><span data-stu-id="2183a-267">In the `Evaluate` method, the model created in `Train` is passed in to be evaluated.</span></span> <span data-ttu-id="2183a-268">紧随 `Train` 后创建 `Evaluate` 方法，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="2183a-268">Create the `Evaluate` method, just after `Train`, as in the following code:</span></span>

```csharp
public static void Evaluate(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="2183a-269">`Evaluate` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="2183a-269">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="2183a-270">加载测试数据集。</span><span class="sxs-lookup"><span data-stu-id="2183a-270">Loads the test dataset.</span></span>
* <span data-ttu-id="2183a-271">创建二进制计算器。</span><span class="sxs-lookup"><span data-stu-id="2183a-271">Creates the binary evaluator.</span></span>
* <span data-ttu-id="2183a-272">评估模型并创建指标。</span><span class="sxs-lookup"><span data-stu-id="2183a-272">Evaluates the model and create metrics.</span></span>
* <span data-ttu-id="2183a-273">显示指标。</span><span class="sxs-lookup"><span data-stu-id="2183a-273">Displays the metrics.</span></span>

<span data-ttu-id="2183a-274">使用下面的代码，在 `Train` 方法调用的正下方，从 `Main` 方法中添加对新方法的调用：</span><span class="sxs-lookup"><span data-stu-id="2183a-274">Add a call to the new method from the `Main` method, right under the `Train` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#11 "Call the Evaluate method")]

<span data-ttu-id="2183a-275">将使用前面初始化的带有 `_testDataPath` 全局字段的 `_textLoader` 全局变量来加载测试数据集。</span><span class="sxs-lookup"><span data-stu-id="2183a-275">You'll load the test dataset using the previously initialized  `_textLoader` global variable with the `_testDataPath` global field.</span></span> <span data-ttu-id="2183a-276">可以将此数据集作为质量检查来评估模型。</span><span class="sxs-lookup"><span data-stu-id="2183a-276">You can evaluate the model using this dataset as a quality check.</span></span> <span data-ttu-id="2183a-277">将以下代码添加到 `Evaluate` 方法中：</span><span class="sxs-lookup"><span data-stu-id="2183a-277">Add the following code to the `Evaluate` method:</span></span>

[!code-csharp[LoadTestDataset](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#12 "Load the test dataset")]

<span data-ttu-id="2183a-278">接下来，将使用机器学习 `model` 参数（转换器）来输入特性，并返回预测。</span><span class="sxs-lookup"><span data-stu-id="2183a-278">Next, you'll use the machine learning `model` parameter (a transformer) to input the features and return predictions.</span></span> <span data-ttu-id="2183a-279">将以下代码作为下一行添加到 `Evaluate` 方法中：</span><span class="sxs-lookup"><span data-stu-id="2183a-279">Add the following code to the `Evaluate` method as the next line:</span></span>

[!code-csharp[PredictWithTransformer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#13 "Predict using the Transformer")]

<span data-ttu-id="2183a-280">`BinaryClassificationContext.Evaluate` 方法使用指定数据集计算 `PredictionModel` 的质量指标。</span><span class="sxs-lookup"><span data-stu-id="2183a-280">The `BinaryClassificationContext.Evaluate` method computes the quality metrics for the `PredictionModel` using the specified dataset.</span></span> <span data-ttu-id="2183a-281">它返回 `BinaryClassificationEvaluator.CalibratedResult` 对象，其中包含由二元分类计算器计算出的总体指标。</span><span class="sxs-lookup"><span data-stu-id="2183a-281">It returns a `BinaryClassificationEvaluator.CalibratedResult` object contains the overall metrics computed by binary classification evaluators.</span></span> <span data-ttu-id="2183a-282">若要显示这些指标来确定模型质量，需要先获取指标。</span><span class="sxs-lookup"><span data-stu-id="2183a-282">To display these to determine the quality of the model, you need to get the metrics first.</span></span> <span data-ttu-id="2183a-283">将以下代码作为下一行添加到 `Evaluate` 方法中：</span><span class="sxs-lookup"><span data-stu-id="2183a-283">Add the following code as the next line in the `Evaluate` method:</span></span>

[!code-csharp[ComputeMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#14 "Compute Metrics")]

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="2183a-284">显示用于模型验证的指标</span><span class="sxs-lookup"><span data-stu-id="2183a-284">Displaying the metrics for model validation</span></span>

<span data-ttu-id="2183a-285">使用下面的代码显示指标、共享结果，然后处理它们：</span><span class="sxs-lookup"><span data-stu-id="2183a-285">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#15 "Display selected metrics")]

<span data-ttu-id="2183a-286">若要在返回之前将模型保存到 .zip 文件，请添加以下代码作为 `Evaluate` 中的下一行来调用 `SaveModelAsFile` 方法：</span><span class="sxs-lookup"><span data-stu-id="2183a-286">To save your model to a .zip file before returning, add the following code to call the `SaveModelAsFile` method as the next line in `Evaluate`:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#23 "Save the model")]

## <a name="save-the-model-as-azip-file"></a><span data-ttu-id="2183a-287">将模型保存为 .zip 文件</span><span class="sxs-lookup"><span data-stu-id="2183a-287">Save the model as a.zip file</span></span>

<span data-ttu-id="2183a-288">使用下面的代码紧随 `Evaluate` 方法后创建 `SaveModelAsFile` 方法：</span><span class="sxs-lookup"><span data-stu-id="2183a-288">Create the `SaveModelAsFile` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="2183a-289">`SaveModelAsFile` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="2183a-289">The `SaveModelAsFile` method executes the following tasks:</span></span>

* <span data-ttu-id="2183a-290">将模型保存为 .zip 文件。</span><span class="sxs-lookup"><span data-stu-id="2183a-290">Saves the model as a .zip file.</span></span>

<span data-ttu-id="2183a-291">接下来，创建一个方法来保存模型，以便它可以在其他应用程序中重用和使用。</span><span class="sxs-lookup"><span data-stu-id="2183a-291">Next, create a method to save the model so that it can be reused and consumed in other applications.</span></span> <span data-ttu-id="2183a-292">`ITransformer` 有一个在 `_modelPath` 全局字段中采用的 <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> 方法和一个 <xref:System.IO.Stream> 方法。</span><span class="sxs-lookup"><span data-stu-id="2183a-292">The `ITransformer` has a <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> method that takes in the `_modelPath` global field, and a <xref:System.IO.Stream>.</span></span> <span data-ttu-id="2183a-293">要将其保存为 zip 文件，将在调用 `SaveTo` 方法之前立即创建 `FileStream`。</span><span class="sxs-lookup"><span data-stu-id="2183a-293">To save this as a zip file, you'll create the `FileStream` immediately before calling the `SaveTo` method.</span></span> <span data-ttu-id="2183a-294">将以下代码作为下一行添加到 `SaveModelAsFile` 方法中：</span><span class="sxs-lookup"><span data-stu-id="2183a-294">Add the following code to the `SaveModelAsFile` method as the next line:</span></span>

[!code-csharp[SaveToMethod](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#24 "Add the SaveTo Method")]

<span data-ttu-id="2183a-295">还可以使用以下代码通过使用 `_modelPath` 编写控制台消息来显示文件的写入位置：</span><span class="sxs-lookup"><span data-stu-id="2183a-295">You could also display where the file was written by writing a console message with the `_modelPath`, using the following code:</span></span>

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="predict-the-test-data-outcome-with-the-model-and-a-single-comment"></a><span data-ttu-id="2183a-296">使用模型和单个注释预测测试数据结果</span><span class="sxs-lookup"><span data-stu-id="2183a-296">Predict the test data outcome with the model and a single comment</span></span>

<span data-ttu-id="2183a-297">使用下面的代码紧随 `Evaluate` 方法后创建 `Predict` 方法：</span><span class="sxs-lookup"><span data-stu-id="2183a-297">Create the `Predict` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void Predict(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="2183a-298">`Predict` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="2183a-298">The `Predict` method executes the following tasks:</span></span>

* <span data-ttu-id="2183a-299">创建测试数据的单个注释。</span><span class="sxs-lookup"><span data-stu-id="2183a-299">Creates a single comment of test data.</span></span>
* <span data-ttu-id="2183a-300">根据测试数据预测情绪。</span><span class="sxs-lookup"><span data-stu-id="2183a-300">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="2183a-301">结合测试数据和预测进行报告。</span><span class="sxs-lookup"><span data-stu-id="2183a-301">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="2183a-302">显示预测结果。</span><span class="sxs-lookup"><span data-stu-id="2183a-302">Displays the predicted results.</span></span>

<span data-ttu-id="2183a-303">使用下面的代码，在 `Evaluate` 方法调用的正下方，从 `Main` 方法中添加对新方法的调用：</span><span class="sxs-lookup"><span data-stu-id="2183a-303">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallPredict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#16 "Call the Predict method")]

<span data-ttu-id="2183a-304">虽然 `model` 是对多行数据进行操作的 `transformer`，但是一个非常常见的生产场景是，需要对单个示例进行预测。</span><span class="sxs-lookup"><span data-stu-id="2183a-304">While the `model` is a `transformer` that operates on many rows of data, a very common production scenario is a need for predictions on individual examples.</span></span> <span data-ttu-id="2183a-305"><xref:Microsoft.ML.PredictionEngine%602> 是从 `CreatePredictionEngine` 方法返回的包装器。</span><span class="sxs-lookup"><span data-stu-id="2183a-305">The <xref:Microsoft.ML.PredictionEngine%602> is a wrapper that is returned from the `CreatePredictionEngine` method.</span></span> <span data-ttu-id="2183a-306">让我们添加以下代码来创建 `PredictionEngine`，作为 `Predict` 方法中的第一行：</span><span class="sxs-lookup"><span data-stu-id="2183a-306">Let's add the following code to create the `PredictionEngine` as the first line in the `Predict` Method:</span></span>

[!code-csharp[CreatePredictionFunction](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#17 "Create the PredictionFunction")]
  
<span data-ttu-id="2183a-307">通过创建一个 `SentimentData` 实例，在 `Predict` 方法中添加一个注释来测试定型模型的预测：</span><span class="sxs-lookup"><span data-stu-id="2183a-307">Add a comment to test the trained model's prediction in the `Predict` method by creating an instance of `SentimentData`:</span></span>

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#18 "Create test data for single prediction")]

 <span data-ttu-id="2183a-308">可以使用它来预测单个注释数据实例的正面或负面情绪。</span><span class="sxs-lookup"><span data-stu-id="2183a-308">You can use that to predict the Toxic or Non Toxic sentiment of a single instance of the comment data.</span></span> <span data-ttu-id="2183a-309">要获得预测，请对数据使用 <xref:Microsoft.ML.PredictionEngine%602.Predict%2A>。</span><span class="sxs-lookup"><span data-stu-id="2183a-309">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="2183a-310">请注意，输入数据是一个字符串，且模型包含特征化。</span><span class="sxs-lookup"><span data-stu-id="2183a-310">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="2183a-311">管道在定型和预测期间同步。</span><span class="sxs-lookup"><span data-stu-id="2183a-311">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="2183a-312">不必专门为预测编写预处理/特征化代码，并且相同 API 负责批处理和一次性预测。</span><span class="sxs-lookup"><span data-stu-id="2183a-312">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#19 "Create a prediction of sentiment")]

### <a name="model-operationalization-prediction"></a><span data-ttu-id="2183a-313">模型操作化：预测</span><span class="sxs-lookup"><span data-stu-id="2183a-313">Model operationalization: prediction</span></span>

<span data-ttu-id="2183a-314">显示 `SentimentText` 和相应的情绪预测以便共享结果，并采取相应措施。</span><span class="sxs-lookup"><span data-stu-id="2183a-314">Display `SentimentText` and corresponding sentiment prediction in order to share the results and act on them accordingly.</span></span> <span data-ttu-id="2183a-315">这称为操作化，使用返回的数据作为操作策略的一部分。</span><span class="sxs-lookup"><span data-stu-id="2183a-315">This is called operationalization, using the returned data as part of the operational policies.</span></span> <span data-ttu-id="2183a-316">使用以下 <xref:System.Console.WriteLine?displayProperty=nameWithType> 代码创建结果显示：</span><span class="sxs-lookup"><span data-stu-id="2183a-316">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputPrediction](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#20 "Display prediction output")]

## <a name="predict-the-test-data-outcomes-with-the-saved-model"></a><span data-ttu-id="2183a-317">使用保存的模型预测测试数据结果</span><span class="sxs-lookup"><span data-stu-id="2183a-317">Predict the test data outcomes with the saved model</span></span>

<span data-ttu-id="2183a-318">使用下面的代码在 `SaveModelAsFile` 方法前创建 `PredictWithModelLoadedFromFile` 方法：</span><span class="sxs-lookup"><span data-stu-id="2183a-318">Create the `PredictWithModelLoadedFromFile` method, just before the `SaveModelAsFile` method, using the following code:</span></span>

```csharp
public static void PredictWithModelLoadedFromFile(MLContext mlContext)
{

}
```

<span data-ttu-id="2183a-319">`PredictWithModelLoadedFromFile` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="2183a-319">The `PredictWithModelLoadedFromFile` method executes the following tasks:</span></span>

* <span data-ttu-id="2183a-320">创建批处理测试数据。</span><span class="sxs-lookup"><span data-stu-id="2183a-320">Creates batch test data.</span></span>
* <span data-ttu-id="2183a-321">根据测试数据预测情绪。</span><span class="sxs-lookup"><span data-stu-id="2183a-321">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="2183a-322">结合测试数据和预测进行报告。</span><span class="sxs-lookup"><span data-stu-id="2183a-322">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="2183a-323">显示预测结果。</span><span class="sxs-lookup"><span data-stu-id="2183a-323">Displays the predicted results.</span></span>

<span data-ttu-id="2183a-324">使用下面的代码，在 `Predict` 方法调用的正下方，从 `Main` 方法中添加对新方法的调用：</span><span class="sxs-lookup"><span data-stu-id="2183a-324">Add a call to the new method from the `Main` method, right under the `Predict` method call, using the following code:</span></span>

[!code-csharp[CallPredictModelLoaded](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#25 "Call the PredictWithModelLoadedFromFile method")]

<span data-ttu-id="2183a-325">添加一些评论，以测试 `PredictWithModelLoadedFromFile` 方法中的定型模型预测：</span><span class="sxs-lookup"><span data-stu-id="2183a-325">Add some comments to test the trained model's predictions in the `PredictWithModelLoadedFromFile` method:</span></span>

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#26 "Create test data for predictions")]

<span data-ttu-id="2183a-326">加载模型</span><span class="sxs-lookup"><span data-stu-id="2183a-326">Load the model</span></span>

[!code-csharp[LoadTheModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#27 "Load the model")]

<span data-ttu-id="2183a-327">现在你有一个模型，可以使用它来预测使用 <xref:Microsoft.ML.Core.Data.ITransformer.Transform(Microsoft.ML.Data.IDataView)> 方法的评论数据的正面或负面情绪。</span><span class="sxs-lookup"><span data-stu-id="2183a-327">Now that you have a model, you can use that to predict the Toxic or Non Toxic sentiment of the comment data using the <xref:Microsoft.ML.Core.Data.ITransformer.Transform(Microsoft.ML.Data.IDataView)> method.</span></span> <span data-ttu-id="2183a-328">要获得预测，请使用新数据上的 `Predict`。</span><span class="sxs-lookup"><span data-stu-id="2183a-328">To get a prediction, use `Predict` on new data.</span></span> <span data-ttu-id="2183a-329">请注意，输入数据是一个字符串，且模型包含特征化。</span><span class="sxs-lookup"><span data-stu-id="2183a-329">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="2183a-330">管道在定型和预测期间同步。</span><span class="sxs-lookup"><span data-stu-id="2183a-330">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="2183a-331">不必专门为预测编写预处理/特征化代码，并且相同 API 负责批处理和一次性预测。</span><span class="sxs-lookup"><span data-stu-id="2183a-331">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span> <span data-ttu-id="2183a-332">在用于预测的 `PredictWithModelLoadedFromFile` 方法中添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="2183a-332">Add the following code to the `PredictWithModelLoadedFromFile` method for the predictions:</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#28 "Create predictions of sentiments")]

### <a name="model-operationalization-prediction"></a><span data-ttu-id="2183a-333">模型操作化：预测</span><span class="sxs-lookup"><span data-stu-id="2183a-333">Model operationalization: prediction</span></span>

<span data-ttu-id="2183a-334">显示 `SentimentText` 和相应的情绪预测以便共享结果，并采取相应措施。</span><span class="sxs-lookup"><span data-stu-id="2183a-334">Display `SentimentText` and corresponding sentiment prediction in order to share the results and act on them accordingly.</span></span> <span data-ttu-id="2183a-335">这称为操作化，使用返回的数据作为操作策略的一部分。</span><span class="sxs-lookup"><span data-stu-id="2183a-335">This is called operationalization, using the returned data as part of the operational policies.</span></span> <span data-ttu-id="2183a-336">使用以下 <xref:System.Console.WriteLine?displayProperty=nameWithType> 代码创建结果标头：</span><span class="sxs-lookup"><span data-stu-id="2183a-336">Create a header for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputHeaders](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#29 "Display prediction outputs")]

<span data-ttu-id="2183a-337">在显示预测结果之前，将情绪和预测结合在一起以查看原始评论及其预测情绪。</span><span class="sxs-lookup"><span data-stu-id="2183a-337">Before displaying the predicted results, combine the sentiment and prediction together to see the original comment with its predicted sentiment.</span></span> <span data-ttu-id="2183a-338">下面的代码使用 <xref:System.Linq.Enumerable.Zip%2A> 方法来实现此目的，因此请在下一步添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="2183a-338">The following code uses the <xref:System.Linq.Enumerable.Zip%2A> method to make that happen, so add that code next:</span></span>

[!code-csharp[BuildTuples](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#30 "Build the pairs of sentiment data and predictions")]

<span data-ttu-id="2183a-339">将 `SentimentText` 和 `Sentiment` 合并到一个类后，现在可以使用 <xref:System.Console.WriteLine?displayProperty=nameWithType> 方法来显示结果：</span><span class="sxs-lookup"><span data-stu-id="2183a-339">Now that you've combined the `SentimentText` and `Sentiment` into a class, you can display the results using the <xref:System.Console.WriteLine?displayProperty=nameWithType> method:</span></span>

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#31 "Display the predictions")]

<span data-ttu-id="2183a-340">因为推测的元组元素名称是 C# 7.1 中的新功能，且项目的默认语言版本为 C# 7.0，你需要将语言版本更改为 C# 7.1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="2183a-340">Because inferred tuple element names are a new feature in C# 7.1 and the default language version of the project is C# 7.0, you need to change the language version to C# 7.1 or higher.</span></span>
<span data-ttu-id="2183a-341">要完成此操作，右键单击“解决方案资源管理器”中的项目节点，然后选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="2183a-341">To do that, right-click on the project node in **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="2183a-342">选择**生成**选项卡并选择**高级**按钮。</span><span class="sxs-lookup"><span data-stu-id="2183a-342">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="2183a-343">在下拉列表中，选择“C# 7.1”（或更高版本）。</span><span class="sxs-lookup"><span data-stu-id="2183a-343">In the dropdown, select  **C# 7.1** (or a higher version).</span></span> <span data-ttu-id="2183a-344">选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="2183a-344">Select the **OK** button.</span></span>

## <a name="results"></a><span data-ttu-id="2183a-345">结果</span><span class="sxs-lookup"><span data-stu-id="2183a-345">Results</span></span>

<span data-ttu-id="2183a-346">结果应如下所示。</span><span class="sxs-lookup"><span data-stu-id="2183a-346">Your results should be similar to the following.</span></span> <span data-ttu-id="2183a-347">管道处理期间，会显示消息。</span><span class="sxs-lookup"><span data-stu-id="2183a-347">As the pipeline processes, it displays messages.</span></span> <span data-ttu-id="2183a-348">你可能会看到警告或处理消息。</span><span class="sxs-lookup"><span data-stu-id="2183a-348">You may see warnings, or processing messages.</span></span> <span data-ttu-id="2183a-349">为清楚起见，已经从下面的结果中删除这些内容。</span><span class="sxs-lookup"><span data-stu-id="2183a-349">These have been removed from the following results for clarity.</span></span>

```console
Model quality metrics evaluation
--------------------------------
Accuracy: 94.44%
Auc: 98.77%
F1Score: 94.74%
=============== End of model evaluation ===============

=============== Prediction Test of model with a single sample and test dataset ===============

Sentiment: This is a very rude movie | Prediction: Toxic | Probability: 0.5297049
=============== End of Predictions ===============

=============== New iteration of Model ===============
=============== Create and Train the Model ===============
=============== End of training ===============


The model is saved to: C:\Tutorial\SentimentAnalysis\bin\Debug\netcoreapp2.0\Data\Model.zip

=============== Prediction Test of loaded model with a multiple sample ===============

Sentiment: This is a very rude movie | Prediction: Toxic | Probability: 0.4585565
Sentiment: He is the best, and the article should say that. | Prediction: Not Toxic | Probability: 0.9924279

```

<span data-ttu-id="2183a-350">祝贺你！</span><span class="sxs-lookup"><span data-stu-id="2183a-350">Congratulations!</span></span> <span data-ttu-id="2183a-351">现在，你已成功生成用于分类和预测消息情绪的机器学习模型。</span><span class="sxs-lookup"><span data-stu-id="2183a-351">You've now successfully built a machine learning model for classifying and predicting messages sentiment.</span></span> <span data-ttu-id="2183a-352">可以在 [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) 存储库中找到本教程的源代码。</span><span class="sxs-lookup"><span data-stu-id="2183a-352">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2183a-353">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2183a-353">Next steps</span></span>

<span data-ttu-id="2183a-354">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="2183a-354">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="2183a-355">了解问题</span><span class="sxs-lookup"><span data-stu-id="2183a-355">Understand the problem</span></span>
> * <span data-ttu-id="2183a-356">选择适当的机器学习任务</span><span class="sxs-lookup"><span data-stu-id="2183a-356">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="2183a-357">准备数据</span><span class="sxs-lookup"><span data-stu-id="2183a-357">Prepare your data</span></span>
> * <span data-ttu-id="2183a-358">创建学习管道</span><span class="sxs-lookup"><span data-stu-id="2183a-358">Create the learning pipeline</span></span>
> * <span data-ttu-id="2183a-359">加载分类器</span><span class="sxs-lookup"><span data-stu-id="2183a-359">Load a classifier</span></span>
> * <span data-ttu-id="2183a-360">定型模型</span><span class="sxs-lookup"><span data-stu-id="2183a-360">Train the model</span></span>
> * <span data-ttu-id="2183a-361">使用不同数据集评估模型</span><span class="sxs-lookup"><span data-stu-id="2183a-361">Evaluate the model with a different dataset</span></span>
> * <span data-ttu-id="2183a-362">使用模型预测测试数据结果</span><span class="sxs-lookup"><span data-stu-id="2183a-362">Predict the test data outcomes with the model</span></span>

<span data-ttu-id="2183a-363">进入下一教程了解详细信息</span><span class="sxs-lookup"><span data-stu-id="2183a-363">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="2183a-364">问题分类</span><span class="sxs-lookup"><span data-stu-id="2183a-364">Issue Classification</span></span>](github-issue-classification.md)

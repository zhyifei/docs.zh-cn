---
title: 在情绪分析二元分类方案中使用 ML.NET
description: 了解如何在二元分类方案中使用 ML.NET，以了解如何使用情绪预测来采取相应措施。
ms.date: 06/04/2018
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: dec44bf114472e19fdac131e0af6c13854957fe3
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43864769"
---
# <a name="tutorial-use-mlnet-in-a-sentiment-analysis-binary-classification-scenario"></a><span data-ttu-id="5ec8e-103">教程：在情绪分析二元分类方案中使用 ML.NET</span><span class="sxs-lookup"><span data-stu-id="5ec8e-103">Tutorial: Use ML.NET in a sentiment analysis binary classification scenario</span></span>

> [!NOTE]
> <span data-ttu-id="5ec8e-104">本主题引用 ML.NET（目前处于预览状态），且材料可能会更改。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="5ec8e-105">有关详细信息，请访问 [ML.NET 简介](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="5ec8e-106">此示例教程通过在 Visual Studio 2017 中使用 C# 的 .NET Core 控制台应用程序，演示如何使用 ML.NET 创建情绪分类器。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-106">This sample tutorial illustrates using ML.NET to create a sentiment classifier via a .NET Core console application using C# in Visual Studio 2017.</span></span>

<span data-ttu-id="5ec8e-107">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="5ec8e-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="5ec8e-108">了解问题</span><span class="sxs-lookup"><span data-stu-id="5ec8e-108">Understand the problem</span></span>
> * <span data-ttu-id="5ec8e-109">选择适当的机器学习任务</span><span class="sxs-lookup"><span data-stu-id="5ec8e-109">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="5ec8e-110">准备数据</span><span class="sxs-lookup"><span data-stu-id="5ec8e-110">Prepare your data</span></span>
> * <span data-ttu-id="5ec8e-111">创建学习管道</span><span class="sxs-lookup"><span data-stu-id="5ec8e-111">Create the learning pipeline</span></span>
> * <span data-ttu-id="5ec8e-112">加载分类器</span><span class="sxs-lookup"><span data-stu-id="5ec8e-112">Load a classifier</span></span>
> * <span data-ttu-id="5ec8e-113">定型模型</span><span class="sxs-lookup"><span data-stu-id="5ec8e-113">Train the model</span></span>
> * <span data-ttu-id="5ec8e-114">使用不同数据集评估模型</span><span class="sxs-lookup"><span data-stu-id="5ec8e-114">Evaluate the model with a different dataset</span></span>
> * <span data-ttu-id="5ec8e-115">使用模型预测测试数据结果</span><span class="sxs-lookup"><span data-stu-id="5ec8e-115">Predict the test data outcomes with the model</span></span>

## <a name="sentiment-analysis-sample-overview"></a><span data-ttu-id="5ec8e-116">情绪分析示例概述</span><span class="sxs-lookup"><span data-stu-id="5ec8e-116">Sentiment analysis sample overview</span></span>

<span data-ttu-id="5ec8e-117">该示例是使用 ML.NET 定型模型的控制台应用，以将情绪分类和预测为正面或负面。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-117">The sample is a console app that uses ML.NET to train a model that classifies and predicts sentiment as either positive or negative.</span></span> <span data-ttu-id="5ec8e-118">它还使用第二个数据集对模型进行评估，以进行质量分析。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-118">It also evaluates the model with a second dataset for quality analysis.</span></span> <span data-ttu-id="5ec8e-119">情绪数据集来自 WikiDetox 项目。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-119">The sentiment datasets are from the WikiDetox project.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5ec8e-120">系统必备</span><span class="sxs-lookup"><span data-stu-id="5ec8e-120">Prerequisites</span></span>

* <span data-ttu-id="5ec8e-121">安装了“.NET Core 跨平台开发”工作负载的 [Visual Studio 2017 15.6 或更高版本](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-121">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* <span data-ttu-id="5ec8e-122">[Wikipedia detox 行数据制表符分隔文件 (wikiPedia-detox-250-line-data.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv)。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-122">The [Wikipedia detox line data tab separated file (wikiPedia-detox-250-line-data.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv).</span></span>
* <span data-ttu-id="5ec8e-123">[Wikipedia detox 行测试制表符分隔文件 (wikipedia-detox-250-line-test.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv)。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-123">The [Wikipedia detox line test tab separated file (wikipedia-detox-250-line-test.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv).</span></span>

## <a name="machine-learning-workflow"></a><span data-ttu-id="5ec8e-124">机器学习工作流</span><span class="sxs-lookup"><span data-stu-id="5ec8e-124">Machine learning workflow</span></span>

<span data-ttu-id="5ec8e-125">本教程后面介绍了机器学习工作流，使该过程能够有序地进行。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-125">This tutorial follows a machine learning workflow that enables the process to move in an orderly fashion.</span></span>

<span data-ttu-id="5ec8e-126">工作流阶段如下所示：</span><span class="sxs-lookup"><span data-stu-id="5ec8e-126">The workflow phases are as follows:</span></span>

1. <span data-ttu-id="5ec8e-127">**了解问题**</span><span class="sxs-lookup"><span data-stu-id="5ec8e-127">**Understand the problem**</span></span>
2. <span data-ttu-id="5ec8e-128">**引入数据**</span><span class="sxs-lookup"><span data-stu-id="5ec8e-128">**Ingest the data**</span></span>
3. <span data-ttu-id="5ec8e-129">**数据预处理和特征工程**</span><span class="sxs-lookup"><span data-stu-id="5ec8e-129">**Data preprocess and feature engineering**</span></span>
4. <span data-ttu-id="5ec8e-130">**定型和预测模型**</span><span class="sxs-lookup"><span data-stu-id="5ec8e-130">**Train and predict the model**</span></span>
5. <span data-ttu-id="5ec8e-131">**评估模型**</span><span class="sxs-lookup"><span data-stu-id="5ec8e-131">**Evaluate the model**</span></span>
6. <span data-ttu-id="5ec8e-132">**模型操作化**</span><span class="sxs-lookup"><span data-stu-id="5ec8e-132">**Model operationalization**</span></span>

### <a name="understand-the-problem"></a><span data-ttu-id="5ec8e-133">了解问题</span><span class="sxs-lookup"><span data-stu-id="5ec8e-133">Understand the problem</span></span>

<span data-ttu-id="5ec8e-134">首先需要了解问题，因此可以将其分解为能够支持构建和定型模型的几个部分。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-134">You first need to understand the problem, so you can break it down to parts that can support building and training the model.</span></span> <span data-ttu-id="5ec8e-135">分解问题以预测和评估结果。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-135">Breaking the problem down you to predict and evaluate the results.</span></span>

<span data-ttu-id="5ec8e-136">本教程中的问题是了解传入网站评论情绪以采取相应的措施。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-136">The problem for this tutorial is to understand incoming website comment sentiment to take the appropriate action.</span></span>

<span data-ttu-id="5ec8e-137">可以将问题分解为你想要对模型进行定型的数据的情绪文本和情绪值，以及可以评估和以操作状态使用的预期情绪值。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-137">You can break down the problem to the sentiment text and sentiment value for the data you want to train the model with, and a predicted sentiment value that you can evaluate and then use operationally.</span></span>

<span data-ttu-id="5ec8e-138">然后，需要确定情绪，这将帮助你进行机器学习任务选择。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-138">You then need to **determine** the sentiment, which helps you with the machine learning task selection.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="5ec8e-139">选择适当的机器学习任务</span><span class="sxs-lookup"><span data-stu-id="5ec8e-139">Select the appropriate machine learning task</span></span>

<span data-ttu-id="5ec8e-140">通过此问题，你将了解以下情况：</span><span class="sxs-lookup"><span data-stu-id="5ec8e-140">With this problem, you know the following facts:</span></span>

<span data-ttu-id="5ec8e-141">定型数据：网站评论可以是正面或负面（情绪）。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-141">Training data: website comments can be positive or negative (**sentiment**).</span></span>
<span data-ttu-id="5ec8e-142">预测新网站评论的情绪，正面或负面，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="5ec8e-142">Predict the **sentiment** of a new website comment, either positive or negative, such as in the following examples:</span></span>

* <span data-ttu-id="5ec8e-143">请避免向 Wikipedia 添加无意义的内容。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-143">Please refrain from adding nonsense to Wikipedia.</span></span>
* <span data-ttu-id="5ec8e-144">他是最棒的，且文章应如此表述。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-144">He is the best, and the article should say that.</span></span>

<span data-ttu-id="5ec8e-145">分类机器学习任务最适合此方案。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-145">The classification machine learning task is best suited for this scenario.</span></span>

### <a name="about-the-classification-task"></a><span data-ttu-id="5ec8e-146">有关分类任务</span><span class="sxs-lookup"><span data-stu-id="5ec8e-146">About the classification task</span></span>

<span data-ttu-id="5ec8e-147">分类是一项机器学习任务，它使用数据来确定某个项或数据行的类别、类型或类。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-147">Classification is a machine learning task that uses data to **determine** the category, type, or class of an item or row of data.</span></span> <span data-ttu-id="5ec8e-148">例如，可以使用分类：</span><span class="sxs-lookup"><span data-stu-id="5ec8e-148">For example, you can use classification to:</span></span>

* <span data-ttu-id="5ec8e-149">识别情绪为正面还是负面。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-149">Identify sentiment as positive or negative.</span></span>
* <span data-ttu-id="5ec8e-150">将电子邮件分类为垃圾邮件或正常邮件。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-150">Classify email as spam, junk, or good.</span></span>
* <span data-ttu-id="5ec8e-151">确定患者的实验室样本是否癌变。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-151">Determine whether a patient's lab sample is cancerous.</span></span>
* <span data-ttu-id="5ec8e-152">根据客户对销售活动的反应倾向对客户进行分类。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-152">Categorize customers by their propensity to respond to a sales campaign.</span></span>

<span data-ttu-id="5ec8e-153">分类任务通常为以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="5ec8e-153">Classification tasks are frequently one of the following types:</span></span>

* <span data-ttu-id="5ec8e-154">二元：A 或 B。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-154">Binary: either A or B.</span></span>
* <span data-ttu-id="5ec8e-155">多类：可以通过使用单个模型来预测多个类别。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-155">Multiclass: multiple categories that can be predicted by using a single model.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="5ec8e-156">创建控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="5ec8e-156">Create a console application</span></span>

1. <span data-ttu-id="5ec8e-157">打开 Visual Studio 2017。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-157">Open Visual Studio 2017.</span></span> <span data-ttu-id="5ec8e-158">从菜单栏中选择“文件” > “新建” > “项目”。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-158">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="5ec8e-159">在“新项目”对话框中，依次选择“Visual C#”和“.NET Core”节点。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-159">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="5ec8e-160">然后，选择“控制台应用程序(.NET Core)”项目模板。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-160">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="5ec8e-161">在“名称”文本框中，键入“SentimentAnalysis”，然后选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-161">In the **Name** text box, type "SentimentAnalysis" and then select the **OK** button.</span></span>

2. <span data-ttu-id="5ec8e-162">在项目中创建一个名为“数据”的目录来保存数据集文件：</span><span class="sxs-lookup"><span data-stu-id="5ec8e-162">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="5ec8e-163">在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新文件夹”。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-163">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="5ec8e-164">键入“数据”，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-164">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="5ec8e-165">安装“Microsoft.ML NuGet 包”：</span><span class="sxs-lookup"><span data-stu-id="5ec8e-165">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="5ec8e-166">在“解决方案资源管理器”中，右键单击项目，然后选择“管理 NuGet 包”。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-166">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="5ec8e-167">将“nuget.org”选择为“包源”，选择“浏览”选项卡并搜索“Microsoft.ML”，在列表中选择该包，然后选择“安装”按钮。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-167">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="5ec8e-168">选择“预览更改”对话框上的“确定”按钮，如果你同意所列包的许可条款，则选择“接受许可”对话框上的“我接受”按钮。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-168">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="5ec8e-169">准备数据</span><span class="sxs-lookup"><span data-stu-id="5ec8e-169">Prepare your data</span></span>

1. <span data-ttu-id="5ec8e-170">下载 [WikiPedia detox-250-line-data.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv) 和 [wikipedia-detox-250-line-test.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv) 数据集并将它们保存到先前创建的“数据”文件夹。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-170">Download the [WikiPedia detox-250-line-data.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv) and the [wikipedia-detox-250-line-test.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv) data sets and save them to the *Data* folder previously created.</span></span> <span data-ttu-id="5ec8e-171">第一个数据集定型机器学习模型，第二个数据集可用来评估模型的准确度。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-171">The first dataset trains the machine learning model and the second can be used to evaluate how accurate your model is.</span></span>

2. <span data-ttu-id="5ec8e-172">在“解决方案资源管理器”中，右键单击每个 \*.tsv 文件，然后选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-172">In Solution Explorer, right-click each of the \*.tsv files and select **Properties**.</span></span> <span data-ttu-id="5ec8e-173">在“高级”下，将“复制到输出目录”的值更改为“如果较新则复制”。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-173">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="5ec8e-174">创建类和定义路径</span><span class="sxs-lookup"><span data-stu-id="5ec8e-174">Create classes and define paths</span></span>

<span data-ttu-id="5ec8e-175">将以下附加的 `using` 语句添加到“Program.cs”文件顶部：</span><span class="sxs-lookup"><span data-stu-id="5ec8e-175">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#1 "Add necessary usings")]

<span data-ttu-id="5ec8e-176">需要创建三个全局字段，来保存最近下载的文件的路径：</span><span class="sxs-lookup"><span data-stu-id="5ec8e-176">You need to create three global fields to hold the paths to the recently downloaded files:</span></span>

* <span data-ttu-id="5ec8e-177">`_dataPath` 具有用于定型模型的数据集路径。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-177">`_dataPath` has the path to the dataset used to train the model.</span></span>
* <span data-ttu-id="5ec8e-178">`_testDataPath` 具有用于评估模型的数据集路径。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-178">`_testDataPath` has the path to the dataset used to evaluate the model.</span></span>
* <span data-ttu-id="5ec8e-179">`_modelPath` 具有在其中保存定型模型的路径。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-179">`_modelPath` has the path where the trained model is saved.</span></span>

<span data-ttu-id="5ec8e-180">将以下代码添加到 `Main` 方法上方的行中，以指定这些路径：</span><span class="sxs-lookup"><span data-stu-id="5ec8e-180">Add the following code to the line right above the `Main` method to specify those paths:</span></span>

[!code-csharp[Declare file variables](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#2 "Declare variables to store data files")]

<span data-ttu-id="5ec8e-181">需要为输入数据和预测创建一些类。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-181">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="5ec8e-182">向项目添加一个新类：</span><span class="sxs-lookup"><span data-stu-id="5ec8e-182">Add a new class to your project:</span></span>

1. <span data-ttu-id="5ec8e-183">在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新项”。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-183">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="5ec8e-184">在“添加新项”对话框中，选择“类”并将“名称”字段更改为“SentimentData.cs”。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-184">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="5ec8e-185">然后，选择“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-185">Then, select the **Add** button.</span></span>

    <span data-ttu-id="5ec8e-186">“SentimentData.cs”文件随即在代码编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-186">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="5ec8e-187">将下面的 `using` 语句添加到 SentimentData.cs 的顶部：</span><span class="sxs-lookup"><span data-stu-id="5ec8e-187">Add the following `using` statement to the top of *SentimentData.cs*:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#1 "Add necessary usings")]

<span data-ttu-id="5ec8e-188">删除现有类定义并向“SentimentData.cs”文件添加以下代码，其中有两个类 `SentimentData` 和 `SentimentPrediction`：</span><span class="sxs-lookup"><span data-stu-id="5ec8e-188">Remove the existing class definition and add the following code, which has two classes `SentimentData` and `SentimentPrediction`, to the *SentimentData.cs* file:</span></span>

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#2 "Declare data record types")]

<span data-ttu-id="5ec8e-189">`SentimentData` 是输入数据集类，且具有带正或负情绪值的 `float` (`Sentiment`) 和评论字符串 (`SentimentText`)。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-189">`SentimentData` is the input dataset class and has a `float` (`Sentiment`) that has a value for sentiment of either positive or negative, and a string for the comment (`SentimentText`).</span></span> <span data-ttu-id="5ec8e-190">这两个字段均有随附的 `Column` 属性。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-190">Both fields have `Column` attributes attached to them.</span></span> <span data-ttu-id="5ec8e-191">此属性描述数据文件中每个字段的顺序，以及哪个是 `Label` 字段。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-191">This attribute describes the order of each field in the data file, and which is the `Label` field.</span></span> <span data-ttu-id="5ec8e-192">`SentimentPrediction` 是在定型模型后用于预测的类。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-192">`SentimentPrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="5ec8e-193">它有一个布尔值 (`Sentiment`) 和一个 `PredictedLabel` `ColumnName` 属性。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-193">It has a single boolean (`Sentiment`) and a `PredictedLabel` `ColumnName` attribute.</span></span> <span data-ttu-id="5ec8e-194">`Label` 用于创建和定型模型，并且与第二个数据集结合使用来评估模型。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-194">The `Label` is used to create and train the model, and it's also used with a second dataset to evaluate the model.</span></span> <span data-ttu-id="5ec8e-195">`PredictedLabel` 在预测和评估过程中使用。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-195">The `PredictedLabel` is used during prediction and evaluation.</span></span> <span data-ttu-id="5ec8e-196">对于计算，将使用带定型数据的输入、预测值和模型。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-196">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="5ec8e-197">在“Program.cs”文件中，通过将 `void` 替换为 `async Task` 来更改 `Main` 方法签名，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="5ec8e-197">In the *Program.cs* file, change the `Main` method signature by replacing `void` with `async Task`, as in the following example:</span></span>

```csharp
static async Task Main(string[] args) 
{

}
```

<span data-ttu-id="5ec8e-198">将 `async` 添加到带有 <xref:System.Threading.Tasks.Task> 返回类型的 `Main`，因为稍后你会将模型保存到一个 zip 文件，且该过程需要等待，直到此外部任务完成。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-198">You add `async` to `Main` with a <xref:System.Threading.Tasks.Task> return type because you're saving the model to a zip file later, and the program needs to wait until that external task completes.</span></span>

> [!NOTE]
> <span data-ttu-id="5ec8e-199">*异步 Main* 方法使你能够在 `Main` 方法中使用 `await` 关键字。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-199">An *async main* method enables you to use `await` in your `Main` method.</span></span> <span data-ttu-id="5ec8e-200">有关详细信息，请参阅 C# 编程指南中的[异步 Main](../../../docs/csharp/programming-guide/main-and-command-args/index.md) 主题。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-200">For more information, see the [async main](../../../docs/csharp/programming-guide/main-and-command-args/index.md) topic in the C# programming guide.</span></span>

<span data-ttu-id="5ec8e-201">用下面 `Main` 方法中的代码替换 `Console.WriteLine("Hello World!")` 行：</span><span class="sxs-lookup"><span data-stu-id="5ec8e-201">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[Train](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#3 "Train your model")]

<span data-ttu-id="5ec8e-202">`Train` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="5ec8e-202">The `Train` method executes the following tasks:</span></span>

* <span data-ttu-id="5ec8e-203">加载或引入数据。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-203">Loads or ingests the data.</span></span>
* <span data-ttu-id="5ec8e-204">预处理和特征化数据。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-204">Preprocesses and featurizes the data.</span></span>
* <span data-ttu-id="5ec8e-205">定型模型。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-205">Trains the model.</span></span>
* <span data-ttu-id="5ec8e-206">根据测试数据预测情绪。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-206">Predicts sentiment based on test data.</span></span>

<span data-ttu-id="5ec8e-207">使用下面的代码紧随 `Main` 方法后创建 `Train` 方法：</span><span class="sxs-lookup"><span data-stu-id="5ec8e-207">Create the `Train` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static async Task<PredictionModel<SentimentData, SentimentPrediction>> Train()
{

}
```

## <a name="ingest-the-data"></a><span data-ttu-id="5ec8e-208">引入数据</span><span class="sxs-lookup"><span data-stu-id="5ec8e-208">Ingest the data</span></span>

<span data-ttu-id="5ec8e-209">初始化 <xref:Microsoft.ML.LearningPipeline> 的新实例以包含数据加载、数据处理/特征化和模型。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-209">Initialize a new instance of <xref:Microsoft.ML.LearningPipeline> that will include the data loading, data processing/featurization, and model.</span></span> <span data-ttu-id="5ec8e-210">将以下代码添加为 `Train` 方法的首行：</span><span class="sxs-lookup"><span data-stu-id="5ec8e-210">Add the following code as the first line of the `Train` method:</span></span>

[!code-csharp[LearningPipeline](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#5 "Create a learning pipeline")]

<span data-ttu-id="5ec8e-211"><xref:Microsoft.ML.Data.TextLoader> 对象是管道的第一部分，并加载定型文件数据。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-211">The <xref:Microsoft.ML.Data.TextLoader> object is the first part of the pipeline, and loads the training file data.</span></span>

[!code-csharp[TextLoader](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#6 "Add a text loader to the pipeline")]

## <a name="data-preprocess-and-feature-engineering"></a><span data-ttu-id="5ec8e-212">数据预处理和特征工程</span><span class="sxs-lookup"><span data-stu-id="5ec8e-212">Data preprocess and feature engineering</span></span>

<span data-ttu-id="5ec8e-213">预处理和清除数据任务至关重要，需要首先执行才能将数据集有效地用于机器学习。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-213">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span> <span data-ttu-id="5ec8e-214">原始数据通常嘈杂不可靠，并且可能缺少值。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-214">Raw data is often noisy and unreliable, and may be missing values.</span></span> <span data-ttu-id="5ec8e-215">在没有这些建模任务的情况下使用数据会产生误导性结果。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-215">Using data without these modeling tasks can produce misleading results.</span></span> <span data-ttu-id="5ec8e-216">可以通过 ML.NET 的转换管道撰写一组自定义转换，在定型或测试数据之前将其应用到数据。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-216">ML.NET's transform pipelines allow you to compose a custom set of transforms that are applied to your data before training or testing.</span></span> <span data-ttu-id="5ec8e-217">转换的主要目的是为了特征化数据。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-217">The transforms' primary purpose is for data featurization.</span></span> <span data-ttu-id="5ec8e-218">转换管道的优点是，在转换管道定义之后，保存管道以将其应用于测试数据。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-218">A transform pipeline's advantage is that after transform pipeline definition, save the pipeline to apply it to test data.</span></span>

<span data-ttu-id="5ec8e-219">应用 <xref:Microsoft.ML.Transforms.TextFeaturizer> 将 `SentimentText` 列转换为机器学习算法使用的名为 `Features` 的[数值向量](../resources/glossary.md#numerical-feature-vector)。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-219">Apply a <xref:Microsoft.ML.Transforms.TextFeaturizer> to convert the `SentimentText` column into a [numeric vector](../resources/glossary.md#numerical-feature-vector) called `Features` used by the machine learning algorithm.</span></span> <span data-ttu-id="5ec8e-220">这是预处理/特征化步骤。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-220">This is the preprocessing/featurization step.</span></span> <span data-ttu-id="5ec8e-221">使用 ML.NET 中可用的其他组件可以在使用模型时生成更佳结果。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-221">Using additional components available in ML.NET can enable better results with your model.</span></span> <span data-ttu-id="5ec8e-222">将 `TextFeaturizer` 添加到管道作为下一行代码：</span><span class="sxs-lookup"><span data-stu-id="5ec8e-222">Add `TextFeaturizer` to the pipeline as the next line of code:</span></span>

[!code-csharp[TextFeaturizer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#7 "Add a TextFeaturizer to the pipeline")]

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="5ec8e-223">选择学习算法</span><span class="sxs-lookup"><span data-stu-id="5ec8e-223">Choose a learning algorithm</span></span>

<span data-ttu-id="5ec8e-224"><xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier> 对象是一个将在此管道中使用的决策树学习器。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-224">The <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier> object is a decision tree learner you'll use in this pipeline.</span></span> <span data-ttu-id="5ec8e-225">与特征化步骤类似，尝试使用 ML.NET 中提供的其他学习器和更改其参数会导致不同结果。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-225">Similar to the featurization step, trying out different learners available in ML.NET and changing their parameters leads to different results.</span></span> <span data-ttu-id="5ec8e-226">对于优化，可以设置[超参数](../resources/glossary.md#hyperparameter)，如 <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.NumTrees>、<xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.NumLeaves> 和 <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.MinDocumentsInLeafs>。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-226">For tuning, you can set [hyperparameters](../resources/glossary.md#hyperparameter) like <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.NumTrees>, <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.NumLeaves>, and <xref:Microsoft.ML.Trainers.FastTreeBinaryClassifier.MinDocumentsInLeafs>.</span></span> <span data-ttu-id="5ec8e-227">这些超参数是在任何影响模型的情况下设置的，并且特定于模型。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-227">These hyperparameters are set before anything affects the model and are model-specific.</span></span> <span data-ttu-id="5ec8e-228">它们用于优化决策树的性能，因此较大的值可以会对性能产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-228">They're used to tune the decision tree for performance, so larger values can negatively impact performance.</span></span>

<span data-ttu-id="5ec8e-229">将以下代码添加到 `Train` 方法：</span><span class="sxs-lookup"><span data-stu-id="5ec8e-229">Add the following code to the `Train` method:</span></span>

[!code-csharp[BinaryClassifier](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#8 "Add a fast binary tree classifier")]

## <a name="train-the-model"></a><span data-ttu-id="5ec8e-230">定型模型</span><span class="sxs-lookup"><span data-stu-id="5ec8e-230">Train the model</span></span>

<span data-ttu-id="5ec8e-231">根据已加载和转换的数据集定型模型 <xref:Microsoft.ML.PredictionModel%602>。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-231">You train the model, <xref:Microsoft.ML.PredictionModel%602>, based on the dataset that has been loaded and transformed.</span></span> <span data-ttu-id="5ec8e-232">`pipeline.Train<SentimentData, SentimentPrediction>()` 定型管道（加载数据、定型特征化程序和学习器）。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-232">`pipeline.Train<SentimentData, SentimentPrediction>()` trains the pipeline (loads the data, trains the featurizer and learner).</span></span> <span data-ttu-id="5ec8e-233">在发生这种情况之前不会执行此试验。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-233">The experiment is not executed until this happens.</span></span>

<span data-ttu-id="5ec8e-234">将以下代码添加到 `Train` 方法：</span><span class="sxs-lookup"><span data-stu-id="5ec8e-234">Add the following code to the `Train` method:</span></span>

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#9 "Train the model")]

### <a name="save-and-return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="5ec8e-235">保存并返回定型模型以用于评估</span><span class="sxs-lookup"><span data-stu-id="5ec8e-235">Save and Return the model trained to use for evaluation</span></span>

<span data-ttu-id="5ec8e-236">此时，你具有可以集成到任何现有或新 .NET 应用程序的模型。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-236">At this point, you have a model that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="5ec8e-237">若要在返回之前将模型保存到 .zip 文件，请将下面的代码添加到 `Train` 中的下一行：</span><span class="sxs-lookup"><span data-stu-id="5ec8e-237">To save your model to a .zip file before returning, add the following code to the next line in `Train`:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#10 "Save the model")]

<span data-ttu-id="5ec8e-238">在 `Train` 方法末尾返回模型。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-238">Return the model at the end of the `Train` method.</span></span>

[!code-csharp[ReturnModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#11 "Return the model")]

## <a name="evaluate-the-model"></a><span data-ttu-id="5ec8e-239">评估模型</span><span class="sxs-lookup"><span data-stu-id="5ec8e-239">Evaluate the model</span></span>

<span data-ttu-id="5ec8e-240">你已经创建和定型模型，现在需要使用不同的数据集对其进行评估以保证质量和进行验证。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-240">Now that you've created and trained the model, you need to evaluate it with a different dataset for quality assurance and validation.</span></span> <span data-ttu-id="5ec8e-241">在 `Evaluate` 方法中，将传入在 `Train` 中创建的模型以进行评估。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-241">In the `Evaluate` method, the model created in `Train` is passed in to be evaluated.</span></span> <span data-ttu-id="5ec8e-242">紧随 `Train` 后创建 `Evaluate` 方法，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="5ec8e-242">Create the `Evaluate` method, just after `Train`, as in the following code:</span></span>

```csharp
public static void Evaluate(PredictionModel<SentimentData, SentimentPrediction> model)
{

}
```

<span data-ttu-id="5ec8e-243">`Evaluate` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="5ec8e-243">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="5ec8e-244">加载测试数据集。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-244">Loads the test dataset.</span></span>
* <span data-ttu-id="5ec8e-245">创建二进制计算器。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-245">Creates the binary evaluator.</span></span>
* <span data-ttu-id="5ec8e-246">评估模型并创建指标。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-246">Evaluates the model and create metrics.</span></span>
* <span data-ttu-id="5ec8e-247">显示指标。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-247">Displays the metrics.</span></span>

<span data-ttu-id="5ec8e-248">使用下面的代码，在 `Train` 方法调用的正下方，从 `Main` 方法中添加对新方法的调用：</span><span class="sxs-lookup"><span data-stu-id="5ec8e-248">Add a call to the new method from the `Main` method, right under the `Train` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#12 "Call the Evaluate method")]

<span data-ttu-id="5ec8e-249"><xref:Microsoft.ML.Data.TextLoader> 类使用相同的架构加载新的测试数据集。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-249">The <xref:Microsoft.ML.Data.TextLoader> class loads the new test dataset with the same schema.</span></span> <span data-ttu-id="5ec8e-250">可以将此数据集作为质量检查来评估模型。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-250">You can evaluate the model using this dataset as a quality check.</span></span> <span data-ttu-id="5ec8e-251">将以下代码添加到 `Evaluate` 方法：</span><span class="sxs-lookup"><span data-stu-id="5ec8e-251">Add the following code to the `Evaluate` method:</span></span>

[!code-csharp[LoadText](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#13 "Load the test dataset")]

<span data-ttu-id="5ec8e-252"><xref:Microsoft.ML.Models.BinaryClassificationEvaluator> 对象使用指定数据集计算 `PredictionModel` 的质量指标。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-252">The <xref:Microsoft.ML.Models.BinaryClassificationEvaluator> object computes the quality metrics for the `PredictionModel` using the specified dataset.</span></span> <span data-ttu-id="5ec8e-253">要查看这些指标，使用以下代码将计算器添加为 `Evaluate` 方法中的下一行：</span><span class="sxs-lookup"><span data-stu-id="5ec8e-253">To see those metrics, add the evaluator as the next line in the `Evaluate` method, with the following code:</span></span>

[!code-csharp[BinaryEvaluator](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#14 "Create the binary evaluator")]

<span data-ttu-id="5ec8e-254"><xref:Microsoft.ML.Models.BinaryClassificationMetrics> 包含由二元分类计算器计算出的总体指标。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-254">The <xref:Microsoft.ML.Models.BinaryClassificationMetrics> contains the overall metrics computed by binary classification evaluators.</span></span> <span data-ttu-id="5ec8e-255">若要显示这些指标来确定模型质量，需要先获取指标。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-255">To display these to determine the quality of the model, you need to get the metrics first.</span></span> <span data-ttu-id="5ec8e-256">添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="5ec8e-256">Add the following code:</span></span>

[!code-csharp[CreateMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#15 "Evaluate the model and create metrics")]

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="5ec8e-257">显示用于模型验证的指标</span><span class="sxs-lookup"><span data-stu-id="5ec8e-257">Displaying the metrics for model validation</span></span>

<span data-ttu-id="5ec8e-258">使用下面的代码显示指标、共享结果，然后处理它们：</span><span class="sxs-lookup"><span data-stu-id="5ec8e-258">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#16 "Display selected metrics")]

## <a name="predict-the-test-data-outcomes-with-the-model"></a><span data-ttu-id="5ec8e-259">使用模型预测测试数据结果</span><span class="sxs-lookup"><span data-stu-id="5ec8e-259">Predict the test data outcomes with the model</span></span>

<span data-ttu-id="5ec8e-260">使用下面的代码紧随 `Evaluate` 方法后创建 `Predict` 方法：</span><span class="sxs-lookup"><span data-stu-id="5ec8e-260">Create the `Predict` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
public static void Predict(PredictionModel<SentimentData, SentimentPrediction> model)
{

}
```

<span data-ttu-id="5ec8e-261">`Predict` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="5ec8e-261">The `Predict` method executes the following tasks:</span></span>

* <span data-ttu-id="5ec8e-262">创建测试数据。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-262">Creates test data.</span></span>
* <span data-ttu-id="5ec8e-263">根据测试数据预测情绪。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-263">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="5ec8e-264">结合测试数据和预测进行报告。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-264">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="5ec8e-265">显示预测结果。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-265">Displays the predicted results.</span></span>

<span data-ttu-id="5ec8e-266">使用下面的代码，在 `Evaluate` 方法调用的正下方，从 `Main` 方法中添加对新方法的调用：</span><span class="sxs-lookup"><span data-stu-id="5ec8e-266">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#17 "Call the Predict method")]

<span data-ttu-id="5ec8e-267">添加一些评论，以测试 `Predict` 方法中的定型模型预测：</span><span class="sxs-lookup"><span data-stu-id="5ec8e-267">Add some comments to test the trained model's predictions in the `Predict` method:</span></span>

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#18 "Create test data for predictions")]

<span data-ttu-id="5ec8e-268">现在你有一个模型，可以使用它来预测使用 <xref:Microsoft.ML.PredictionModel.Predict%2A?displayProperty=nameWithType> 方法的评论数据的正面或负面情绪。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-268">Now that you have a model, you can use that to predict the positive or negative sentiment of the comment data using the <xref:Microsoft.ML.PredictionModel.Predict%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="5ec8e-269">要获得预测，请使用新数据上的 `Predict`。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-269">To get a prediction, use `Predict` on new data.</span></span> <span data-ttu-id="5ec8e-270">请注意，输入数据是一个字符串，且模型包含特征化。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-270">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="5ec8e-271">管道在定型和预测期间同步。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-271">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="5ec8e-272">不必专门为预测编写预处理/特征化代码，并且相同 API 负责批处理和一次性预测。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-272">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#19 "Create predictions of sentiments")]

### <a name="model-operationalization-prediction"></a><span data-ttu-id="5ec8e-273">模型操作化：预测</span><span class="sxs-lookup"><span data-stu-id="5ec8e-273">Model operationalization: prediction</span></span>

<span data-ttu-id="5ec8e-274">显示 `SentimentText` 和相应的情绪预测以便共享结果，并采取相应措施。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-274">Display `SentimentText` and corresponding sentiment prediction in order to share the results and act on them accordingly.</span></span> <span data-ttu-id="5ec8e-275">这称为操作化，使用返回的数据作为操作策略的一部分。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-275">This is called operationalization, using the returned data as part of the operational policies.</span></span> <span data-ttu-id="5ec8e-276">使用以下 <xref:System.Console.WriteLine?displayProperty=nameWithType> 代码创建结果标头：</span><span class="sxs-lookup"><span data-stu-id="5ec8e-276">Create a header for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputHeaders](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#20 "Display prediction outputs")]

<span data-ttu-id="5ec8e-277">在显示预测结果之前，将情绪和预测结合在一起以查看原始评论及其预测情绪。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-277">Before displaying the predicted results, combine the sentiment and prediction together to see the original comment with its predicted sentiment.</span></span> <span data-ttu-id="5ec8e-278">下面的代码使用 <xref:System.Linq.Enumerable.Zip%2A> 方法来实现此目的，因此请在下一步添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="5ec8e-278">The following code uses the <xref:System.Linq.Enumerable.Zip%2A> method to make that happen, so add that code next:</span></span>

[!code-csharp[BuildTuples](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#21 "Build the pairs of sentiment data and predictions")]

<span data-ttu-id="5ec8e-279">将 `SentimentText` 和 `Sentiment` 合并到一个类后，现在可以使用 <xref:System.Console.WriteLine?displayProperty=nameWithType> 方法来显示结果：</span><span class="sxs-lookup"><span data-stu-id="5ec8e-279">Now that you've combined the `SentimentText` and `Sentiment` into a class, you can display the results using the <xref:System.Console.WriteLine?displayProperty=nameWithType> method:</span></span>

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#22 "Display the predictions")]

<span data-ttu-id="5ec8e-280">因为推测的元组元素名称是 C# 7.1 中的新功能，且项目的默认语言版本为 C# 7.0，你需要将语言版本更改为 C# 7.1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-280">Because inferred tuple element names are a new feature in C# 7.1 and the default language version of the project is C# 7.0, you need to change the language version to C# 7.1 or higher.</span></span>
<span data-ttu-id="5ec8e-281">要完成此操作，右键单击“解决方案资源管理器”中的项目节点，然后选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-281">To do that, right-click on the project node in **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="5ec8e-282">选择**生成**选项卡并选择**高级**按钮。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-282">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="5ec8e-283">在下拉列表中，选择“C# 7.1”（或更高版本）。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-283">In the dropdown, select  **C# 7.1** (or a higher version).</span></span> <span data-ttu-id="5ec8e-284">选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-284">Select the **OK** button.</span></span>

## <a name="results"></a><span data-ttu-id="5ec8e-285">结果</span><span class="sxs-lookup"><span data-stu-id="5ec8e-285">Results</span></span>

<span data-ttu-id="5ec8e-286">结果应如下所示。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-286">Your results should be similar to the following.</span></span> <span data-ttu-id="5ec8e-287">管道处理期间，会显示消息。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-287">As the pipeline processes, it displays messages.</span></span> <span data-ttu-id="5ec8e-288">你可能会看到警告或处理消息。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-288">You may see warnings, or processing messages.</span></span> <span data-ttu-id="5ec8e-289">为清楚起见，已经从下面的结果中删除这些内容。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-289">These have been removed from the following results for clarity.</span></span>

```

PredictionModel quality metrics evaluation
------------------------------------------
Accuracy: 66.67%
Auc: 94.44%
F1Score: 75.00%

Sentiment Predictions
---------------------
Sentiment: Please refrain from adding nonsense to Wikipedia. | Prediction: Negative
Sentiment: He is the best, and the article should say that. | Prediction: Positive

```

<span data-ttu-id="5ec8e-290">祝贺你！</span><span class="sxs-lookup"><span data-stu-id="5ec8e-290">Congratulations!</span></span> <span data-ttu-id="5ec8e-291">现在，你已成功生成用于分类和预测消息情绪的机器学习模型。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-291">You've now successfully built a machine learning model for classifying and predicting messages sentiment.</span></span> <span data-ttu-id="5ec8e-292">可以在 [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) 存储库中找到本教程的源代码。</span><span class="sxs-lookup"><span data-stu-id="5ec8e-292">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5ec8e-293">后续步骤</span><span class="sxs-lookup"><span data-stu-id="5ec8e-293">Next steps</span></span>

<span data-ttu-id="5ec8e-294">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="5ec8e-294">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="5ec8e-295">了解问题</span><span class="sxs-lookup"><span data-stu-id="5ec8e-295">Understand the problem</span></span>
> * <span data-ttu-id="5ec8e-296">选择适当的机器学习任务</span><span class="sxs-lookup"><span data-stu-id="5ec8e-296">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="5ec8e-297">准备数据</span><span class="sxs-lookup"><span data-stu-id="5ec8e-297">Prepare your data</span></span>
> * <span data-ttu-id="5ec8e-298">创建学习管道</span><span class="sxs-lookup"><span data-stu-id="5ec8e-298">Create the learning pipeline</span></span>
> * <span data-ttu-id="5ec8e-299">加载分类器</span><span class="sxs-lookup"><span data-stu-id="5ec8e-299">Load a classifier</span></span>
> * <span data-ttu-id="5ec8e-300">定型模型</span><span class="sxs-lookup"><span data-stu-id="5ec8e-300">Train the model</span></span>
> * <span data-ttu-id="5ec8e-301">使用不同数据集评估模型</span><span class="sxs-lookup"><span data-stu-id="5ec8e-301">Evaluate the model with a different dataset</span></span>
> * <span data-ttu-id="5ec8e-302">使用模型预测测试数据结果</span><span class="sxs-lookup"><span data-stu-id="5ec8e-302">Predict the test data outcomes with the model</span></span>

<span data-ttu-id="5ec8e-303">进入下一教程了解详细信息</span><span class="sxs-lookup"><span data-stu-id="5ec8e-303">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="5ec8e-304">出租车费预测器</span><span class="sxs-lookup"><span data-stu-id="5ec8e-304">Taxi Fare Predictor</span></span>](taxi-fare.md)

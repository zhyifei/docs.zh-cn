---
title: 在 GitHub 问题多类分类方案中使用 ML.NET
description: 了解如何在多类分类方案中使用 ML.NET 对 GitHub 问题进行分类，将其分配到给定区域。
ms.date: 01/24/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 6f01357906fd4398f68dadfb35dbce816f4302c0
ms.sourcegitcommit: d9a0071d0fd490ae006c816f78a563b9946e269a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/25/2019
ms.locfileid: "55066193"
---
# <a name="tutorial-use-mlnet-in-a-multiclass-classification-scenario-to-classify-github-issues"></a><span data-ttu-id="182a8-103">教程：在多类分类场景中使用 ML.NET 对 GitHub 问题进行分类。</span><span class="sxs-lookup"><span data-stu-id="182a8-103">Tutorial: Use ML.NET in a multiclass classification scenario to classify GitHub issues.</span></span>

<span data-ttu-id="182a8-104">此示例教程通过在 Visual Studio 2017 中使用 C# 的 .NET Core 控制台应用程序，演示如何使用 ML.NET 创建 GitHub 问题分类器。</span><span class="sxs-lookup"><span data-stu-id="182a8-104">This sample tutorial illustrates using ML.NET to create a GitHub issue classifier via a .NET Core console application using C# in Visual Studio 2017.</span></span>

<span data-ttu-id="182a8-105">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="182a8-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="182a8-106">了解问题</span><span class="sxs-lookup"><span data-stu-id="182a8-106">Understand the problem</span></span>
> * <span data-ttu-id="182a8-107">选择适当的机器学习任务</span><span class="sxs-lookup"><span data-stu-id="182a8-107">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="182a8-108">准备数据</span><span class="sxs-lookup"><span data-stu-id="182a8-108">Prepare your data</span></span>
> * <span data-ttu-id="182a8-109">创建学习管道</span><span class="sxs-lookup"><span data-stu-id="182a8-109">Create the learning pipeline</span></span>
> * <span data-ttu-id="182a8-110">加载分类器</span><span class="sxs-lookup"><span data-stu-id="182a8-110">Load a classifier</span></span>
> * <span data-ttu-id="182a8-111">定型模型</span><span class="sxs-lookup"><span data-stu-id="182a8-111">Train the model</span></span>
> * <span data-ttu-id="182a8-112">使用不同数据集评估模型</span><span class="sxs-lookup"><span data-stu-id="182a8-112">Evaluate the model with a different dataset</span></span>
> * <span data-ttu-id="182a8-113">使用模型预测单个测试数据结果实例</span><span class="sxs-lookup"><span data-stu-id="182a8-113">Predict a single instance of test data outcome with the model</span></span>
> * <span data-ttu-id="182a8-114">使用加载模型预测测试数据结果</span><span class="sxs-lookup"><span data-stu-id="182a8-114">Predict the test data outcomes with a loaded model</span></span>

> [!NOTE]
> <span data-ttu-id="182a8-115">本主题引用 ML.NET（目前处于预览状态），且材料可能会更改。</span><span class="sxs-lookup"><span data-stu-id="182a8-115">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="182a8-116">有关详细信息，请访问 [ML.NET 简介](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)。</span><span class="sxs-lookup"><span data-stu-id="182a8-116">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

## <a name="github-issue-sample-overview"></a><span data-ttu-id="182a8-117">GitHub 问题示例概述</span><span class="sxs-lookup"><span data-stu-id="182a8-117">GitHub issue sample overview</span></span>

<span data-ttu-id="182a8-118">该示例是使用 ML.NET 来定型模型的控制台应用，该模型对 GitHub 问题的 Area 标签进行分类和预测。</span><span class="sxs-lookup"><span data-stu-id="182a8-118">The sample is a console app that uses ML.NET to train a model that classifies and predicts the Area label for a GitHub issue.</span></span> <span data-ttu-id="182a8-119">它还使用第二个数据集对模型进行评估，以进行质量分析。</span><span class="sxs-lookup"><span data-stu-id="182a8-119">It also evaluates the model with a second dataset for quality analysis.</span></span> <span data-ttu-id="182a8-120">问题数据集来自 dotnet/corefx GitHub 存储库。</span><span class="sxs-lookup"><span data-stu-id="182a8-120">The issue datasets are from the dotnet/corefx GitHub repo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="182a8-121">系统必备</span><span class="sxs-lookup"><span data-stu-id="182a8-121">Prerequisites</span></span>

* <span data-ttu-id="182a8-122">安装了“.NET Core 跨平台开发”工作负载的 [Visual Studio 2017 15.6 或更高版本](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)。</span><span class="sxs-lookup"><span data-stu-id="182a8-122">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* <span data-ttu-id="182a8-123">[Github 问题制表符分隔文件 (issues_train.tsv)](https://github.com/dotnet/samples/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv)。</span><span class="sxs-lookup"><span data-stu-id="182a8-123">The [Github issues tab separated file (issues_train.tsv)](https://github.com/dotnet/samples/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv).</span></span>
* <span data-ttu-id="182a8-124">[Github 问题测试制表符分隔文件 (issues_test.tsv)](https://github.com/dotnet/samples/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv)。</span><span class="sxs-lookup"><span data-stu-id="182a8-124">The [Github issues test tab separated file (issues_test.tsv)](https://github.com/dotnet/samples/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv).</span></span>

## <a name="machine-learning-workflow"></a><span data-ttu-id="182a8-125">机器学习工作流</span><span class="sxs-lookup"><span data-stu-id="182a8-125">Machine learning workflow</span></span>

<span data-ttu-id="182a8-126">本教程后面介绍了机器学习工作流，使该过程能够有序地进行。</span><span class="sxs-lookup"><span data-stu-id="182a8-126">This tutorial follows a machine learning workflow that enables the process to move in an orderly fashion.</span></span>

<span data-ttu-id="182a8-127">工作流阶段如下所示：</span><span class="sxs-lookup"><span data-stu-id="182a8-127">The workflow phases are as follows:</span></span>

1. <span data-ttu-id="182a8-128">**了解问题**</span><span class="sxs-lookup"><span data-stu-id="182a8-128">**Understand the problem**</span></span>
2. <span data-ttu-id="182a8-129">**准备数据**</span><span class="sxs-lookup"><span data-stu-id="182a8-129">**Prepare your data**</span></span>
   * <span data-ttu-id="182a8-130">**加载数据**</span><span class="sxs-lookup"><span data-stu-id="182a8-130">**Load the data**</span></span>
   * <span data-ttu-id="182a8-131">**提取功能（转换数据）**</span><span class="sxs-lookup"><span data-stu-id="182a8-131">**Extract features (Transform your data)**</span></span>
3. <span data-ttu-id="182a8-132">**生成并定型**</span><span class="sxs-lookup"><span data-stu-id="182a8-132">**Build and train**</span></span> 
   * <span data-ttu-id="182a8-133">**定型模型**</span><span class="sxs-lookup"><span data-stu-id="182a8-133">**Train the model**</span></span>
   * <span data-ttu-id="182a8-134">**评估模型**</span><span class="sxs-lookup"><span data-stu-id="182a8-134">**Evaluate the model**</span></span>
4. <span data-ttu-id="182a8-135">**运行**</span><span class="sxs-lookup"><span data-stu-id="182a8-135">**Run**</span></span>
   * <span data-ttu-id="182a8-136">**模型使用**</span><span class="sxs-lookup"><span data-stu-id="182a8-136">**Model consumption**</span></span>

### <a name="understand-the-problem"></a><span data-ttu-id="182a8-137">了解问题</span><span class="sxs-lookup"><span data-stu-id="182a8-137">Understand the problem</span></span>

<span data-ttu-id="182a8-138">首先需要了解问题，因此可以将其分解为能够支持构建和定型模型的几个部分。</span><span class="sxs-lookup"><span data-stu-id="182a8-138">You first need to understand the problem, so you can break it down to parts that can support building and training the model.</span></span> <span data-ttu-id="182a8-139">通过分解问题，可以预测和评估结果。</span><span class="sxs-lookup"><span data-stu-id="182a8-139">Breaking  down the problem allows you to predict and evaluate the results.</span></span>

<span data-ttu-id="182a8-140">本教程旨在探讨传入的 GitHub 问题属于哪个区域，目的是对其进行正确标记，从而确定优先级和进行计划安排。</span><span class="sxs-lookup"><span data-stu-id="182a8-140">The problem for this tutorial is to understand what area incoming GitHub issues belong to in order to label them correctly for prioritization and scheduling.</span></span>

<span data-ttu-id="182a8-141">可以将问题分解为以下内容：</span><span class="sxs-lookup"><span data-stu-id="182a8-141">You can break down the problem to the following:</span></span>

* <span data-ttu-id="182a8-142">问题标题文本</span><span class="sxs-lookup"><span data-stu-id="182a8-142">the issue title text</span></span>
* <span data-ttu-id="182a8-143">问题说明文本</span><span class="sxs-lookup"><span data-stu-id="182a8-143">the issue description text</span></span>
* <span data-ttu-id="182a8-144">模型定型数据的区域值</span><span class="sxs-lookup"><span data-stu-id="182a8-144">an area value for the model training data</span></span>
* <span data-ttu-id="182a8-145">一个可评估的预测区域值，评估后可在实际操作中使用该值</span><span class="sxs-lookup"><span data-stu-id="182a8-145">a predicted area value that you can evaluate and then use operationally</span></span>

<span data-ttu-id="182a8-146">然后，需要确定区域，并借助此操作选择机器学习任务。</span><span class="sxs-lookup"><span data-stu-id="182a8-146">You then need to **determine** the area, which helps you with the machine learning task selection.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="182a8-147">选择适当的机器学习任务</span><span class="sxs-lookup"><span data-stu-id="182a8-147">Select the appropriate machine learning task</span></span>

<span data-ttu-id="182a8-148">通过此问题，你将了解以下情况：</span><span class="sxs-lookup"><span data-stu-id="182a8-148">With this problem, you know the following facts:</span></span>

<span data-ttu-id="182a8-149">定型数据：</span><span class="sxs-lookup"><span data-stu-id="182a8-149">Training data:</span></span>

<span data-ttu-id="182a8-150">可以在几个区域（区域）中标记 GitHub 问题，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="182a8-150">GitHub issues can be labeled in several areas (**Area**) as in the following examples:</span></span>

* <span data-ttu-id="182a8-151">area-System.Numerics</span><span class="sxs-lookup"><span data-stu-id="182a8-151">area-System.Numerics</span></span>
* <span data-ttu-id="182a8-152">area-System.Xml</span><span class="sxs-lookup"><span data-stu-id="182a8-152">area-System.Xml</span></span>
* <span data-ttu-id="182a8-153">area-Infrastructure</span><span class="sxs-lookup"><span data-stu-id="182a8-153">area-Infrastructure</span></span>
* <span data-ttu-id="182a8-154">area-System.Linq</span><span class="sxs-lookup"><span data-stu-id="182a8-154">area-System.Linq</span></span>
* <span data-ttu-id="182a8-155">area-System.IO</span><span class="sxs-lookup"><span data-stu-id="182a8-155">area-System.IO</span></span>

<span data-ttu-id="182a8-156">预测新 GitHub 问题的“区域”，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="182a8-156">Predict the **Area** of a new GitHub Issue such as in the following examples:</span></span>

* <span data-ttu-id="182a8-157">Contract.Assert vs Debug.Assert</span><span class="sxs-lookup"><span data-stu-id="182a8-157">Contract.Assert vs Debug.Assert</span></span>
* <span data-ttu-id="182a8-158">Make fields readonly in System.Xml</span><span class="sxs-lookup"><span data-stu-id="182a8-158">Make fields readonly in System.Xml</span></span>

<span data-ttu-id="182a8-159">分类机器学习任务最适合此方案。</span><span class="sxs-lookup"><span data-stu-id="182a8-159">The classification machine learning task is best suited for this scenario.</span></span>

### <a name="about-the-classification-task"></a><span data-ttu-id="182a8-160">有关分类任务</span><span class="sxs-lookup"><span data-stu-id="182a8-160">About the classification task</span></span>

<span data-ttu-id="182a8-161">分类是一项机器学习任务，它使用数据来确定某个项或数据行的类别、类型或类。</span><span class="sxs-lookup"><span data-stu-id="182a8-161">Classification is a machine learning task that uses data to **determine** the category, type, or class of an item or row of data.</span></span> <span data-ttu-id="182a8-162">例如，可以使用分类：</span><span class="sxs-lookup"><span data-stu-id="182a8-162">For example, you can use classification to:</span></span>

* <span data-ttu-id="182a8-163">识别情绪为正面还是负面。</span><span class="sxs-lookup"><span data-stu-id="182a8-163">Identify sentiment as positive or negative.</span></span>
* <span data-ttu-id="182a8-164">将电子邮件分类为垃圾邮件或正常邮件。</span><span class="sxs-lookup"><span data-stu-id="182a8-164">Classify email as spam, junk, or good.</span></span>
* <span data-ttu-id="182a8-165">确定患者的实验室样本是否癌变。</span><span class="sxs-lookup"><span data-stu-id="182a8-165">Determine whether a patient's lab sample is cancerous.</span></span>
* <span data-ttu-id="182a8-166">根据客户对销售活动的反应倾向对客户进行分类。</span><span class="sxs-lookup"><span data-stu-id="182a8-166">Categorize customers by their propensity to respond to a sales campaign.</span></span>

<span data-ttu-id="182a8-167">分类任务通常为以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="182a8-167">Classification tasks are frequently one of the following types:</span></span>

* <span data-ttu-id="182a8-168">二元：A 或 B。</span><span class="sxs-lookup"><span data-stu-id="182a8-168">Binary: either A or B.</span></span>
* <span data-ttu-id="182a8-169">多类：可以通过使用单个模型来预测多个类别。</span><span class="sxs-lookup"><span data-stu-id="182a8-169">Multiclass: multiple categories that can be predicted by using a single model.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="182a8-170">创建控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="182a8-170">Create a console application</span></span>

### <a name="create-a-project"></a><span data-ttu-id="182a8-171">创建项目</span><span class="sxs-lookup"><span data-stu-id="182a8-171">Create a project</span></span>

1. <span data-ttu-id="182a8-172">打开 Visual Studio 2017。</span><span class="sxs-lookup"><span data-stu-id="182a8-172">Open Visual Studio 2017.</span></span> <span data-ttu-id="182a8-173">从菜单栏中选择“文件” > “新建” > “项目”。</span><span class="sxs-lookup"><span data-stu-id="182a8-173">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="182a8-174">在“新项目”对话框中，依次选择“Visual C#”和“.NET Core”节点。</span><span class="sxs-lookup"><span data-stu-id="182a8-174">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="182a8-175">然后，选择“控制台应用程序(.NET Core)”项目模板。</span><span class="sxs-lookup"><span data-stu-id="182a8-175">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="182a8-176">在“名称”文本框中，键入“SentimentAnalysis”，然后选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="182a8-176">In the **Name** text box, type "SentimentAnalysis" and then select the **OK** button.</span></span>

2. <span data-ttu-id="182a8-177">在项目中创建一个名为“数据”的目录来保存数据集文件：</span><span class="sxs-lookup"><span data-stu-id="182a8-177">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="182a8-178">在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新文件夹”。</span><span class="sxs-lookup"><span data-stu-id="182a8-178">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="182a8-179">键入“Data”，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="182a8-179">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="182a8-180">安装“Microsoft.ML NuGet 包”：</span><span class="sxs-lookup"><span data-stu-id="182a8-180">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="182a8-181">在“解决方案资源管理器”中，右键单击项目，然后选择“管理 NuGet 包”。</span><span class="sxs-lookup"><span data-stu-id="182a8-181">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="182a8-182">将“nuget.org”选择为“包源”，选择“浏览”选项卡并搜索“Microsoft.ML”，在列表中选择该包，然后选择“安装”按钮。</span><span class="sxs-lookup"><span data-stu-id="182a8-182">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="182a8-183">选择“预览更改”对话框上的“确定”按钮，如果你同意所列包的许可条款，则选择“接受许可”对话框上的“我接受”按钮。</span><span class="sxs-lookup"><span data-stu-id="182a8-183">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="182a8-184">准备数据</span><span class="sxs-lookup"><span data-stu-id="182a8-184">Prepare your data</span></span>

1. <span data-ttu-id="182a8-185">下载 [issues_train.tsv](https://github.com/dotnet/samples/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv) 和 [issues_test.tsv](https://github.com/dotnet/samples/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv) 数据集，并将它们保存到先前创建的“数据”文件夹。</span><span class="sxs-lookup"><span data-stu-id="182a8-185">Download the [issues_train.tsv](https://github.com/dotnet/samples/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv) and the [issues_test.tsv](https://github.com/dotnet/samples/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv) data sets and save them to the *Data* folder previously created.</span></span> <span data-ttu-id="182a8-186">第一个数据集定型机器学习模型，第二个数据集可用来评估模型的准确度。</span><span class="sxs-lookup"><span data-stu-id="182a8-186">The first dataset trains the machine learning model and the second can be used to evaluate how accurate your model is.</span></span>

2. <span data-ttu-id="182a8-187">在“解决方案资源管理器”中，右键单击每个 \*.tsv 文件，然后选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="182a8-187">In Solution Explorer, right-click each of the \*.tsv files and select **Properties**.</span></span> <span data-ttu-id="182a8-188">在“高级”下，将“复制到输出目录”的值更改为“如果较新则复制”。</span><span class="sxs-lookup"><span data-stu-id="182a8-188">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="182a8-189">创建类和定义路径</span><span class="sxs-lookup"><span data-stu-id="182a8-189">Create classes and define paths</span></span>

<span data-ttu-id="182a8-190">将以下附加的 `using` 语句添加到“Program.cs”文件顶部：</span><span class="sxs-lookup"><span data-stu-id="182a8-190">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddUsings)]

<span data-ttu-id="182a8-191">需要创建三个全局字段，来保存最近下载的文件路径和 `TextLoader` 的全局变量：</span><span class="sxs-lookup"><span data-stu-id="182a8-191">You need to create three global fields to hold the paths to the recently downloaded files, and a global variable for the `TextLoader`:</span></span>

* <span data-ttu-id="182a8-192">`_trainDataPath` 具有用于定型模型的数据集路径。</span><span class="sxs-lookup"><span data-stu-id="182a8-192">`_trainDataPath` has the path to the dataset used to train the model.</span></span>
* <span data-ttu-id="182a8-193">`_testDataPath` 具有用于评估模型的数据集路径。</span><span class="sxs-lookup"><span data-stu-id="182a8-193">`_testDataPath` has the path to the dataset used to evaluate the model.</span></span>
* <span data-ttu-id="182a8-194">`_modelPath` 具有在其中保存定型模型的路径。</span><span class="sxs-lookup"><span data-stu-id="182a8-194">`_modelPath` has the path where the trained model is saved.</span></span>
* <span data-ttu-id="182a8-195">`_mlContext` 是用于提供处理上下文的 <xref:Microsoft.ML.MLContext>。</span><span class="sxs-lookup"><span data-stu-id="182a8-195">`_mlContext` is the <xref:Microsoft.ML.MLContext> that provides processing context.</span></span>
* <span data-ttu-id="182a8-196">`_trainingDataView` 是用于处理定型数据集的 <xref:Microsoft.ML.Data.IDataView>。</span><span class="sxs-lookup"><span data-stu-id="182a8-196">`_trainingDataView` is the <xref:Microsoft.ML.Data.IDataView> used to process the training dataset.</span></span>
* <span data-ttu-id="182a8-197">`_predEngine` 是用于单个预测的 <xref:Microsoft.ML.PredictionEngine%602>。</span><span class="sxs-lookup"><span data-stu-id="182a8-197">`_predEngine` is the <xref:Microsoft.ML.PredictionEngine%602> used for single predictions.</span></span>
* <span data-ttu-id="182a8-198">`_reader` 是用于加载和转换数据集的 <xref:Microsoft.ML.Data.TextLoader>。</span><span class="sxs-lookup"><span data-stu-id="182a8-198">`_reader` is the <xref:Microsoft.ML.Data.TextLoader> used to load and transform the datasets.</span></span>

<span data-ttu-id="182a8-199">将以下代码添加到 `Main` 方法正上方的行中以指定这些路径和其他变量：</span><span class="sxs-lookup"><span data-stu-id="182a8-199">Add the following code to the line right above the `Main` method to specify those paths and the other variables:</span></span>

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DeclareGlobalVariables)]

<span data-ttu-id="182a8-200">需要为输入数据和预测创建一些类。</span><span class="sxs-lookup"><span data-stu-id="182a8-200">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="182a8-201">向项目添加一个新类：</span><span class="sxs-lookup"><span data-stu-id="182a8-201">Add a new class to your project:</span></span>

1. <span data-ttu-id="182a8-202">在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新项”。</span><span class="sxs-lookup"><span data-stu-id="182a8-202">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="182a8-203">在“添加新项”对话框中，选择“类”并将“名称”字段更改为“GitHubIssueData.cs”。</span><span class="sxs-lookup"><span data-stu-id="182a8-203">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *GitHubIssueData.cs*.</span></span> <span data-ttu-id="182a8-204">然后，选择“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="182a8-204">Then, select the **Add** button.</span></span>

    <span data-ttu-id="182a8-205">“GitHubIssueData.cs”文件随即在代码编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="182a8-205">The *GitHubIssueData.cs* file opens in the code editor.</span></span> <span data-ttu-id="182a8-206">将下面的 `using` 语句添加到 GitHubIssueData.cs 的顶部：</span><span class="sxs-lookup"><span data-stu-id="182a8-206">Add the following `using` statement to the top of *GitHubIssueData.cs*:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/GitHubIssueClassification/GitHubIssueData.cs#AddUsings)]

<span data-ttu-id="182a8-207">删除现有类定义并向“GitHubIssueData.cs”文件添加以下代码，其中有两个类 `GitHubIssue` 和 `IssuePrediction`：</span><span class="sxs-lookup"><span data-stu-id="182a8-207">Remove the existing class definition and add the following code, which has two classes `GitHubIssue` and `IssuePrediction`, to the *GitHubIssueData.cs* file:</span></span>

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/GitHubIssueClassification/GitHubIssueData.cs#DeclareTypes)]

<span data-ttu-id="182a8-208">`GitHubIssue` 是输入数据集类，具有以下 <xref:System.String> 字段：</span><span class="sxs-lookup"><span data-stu-id="182a8-208">`GitHubIssue` is the input dataset class and has the following <xref:System.String> fields:</span></span>

* <span data-ttu-id="182a8-209">`ID` 包含 GitHub 问题 ID 的值</span><span class="sxs-lookup"><span data-stu-id="182a8-209">`ID` contains a value for the GitHub issue ID</span></span>
* <span data-ttu-id="182a8-210">`Area` 包含 `Area` 标签的值</span><span class="sxs-lookup"><span data-stu-id="182a8-210">`Area` contains a value for the `Area` label</span></span>
* <span data-ttu-id="182a8-211">`Title` 包含 GitHub 问题标题</span><span class="sxs-lookup"><span data-stu-id="182a8-211">`Title` contains the GitHub issue title</span></span>
* <span data-ttu-id="182a8-212">`Description` 包含 GitHub 问题说明</span><span class="sxs-lookup"><span data-stu-id="182a8-212">`Description` contains the GitHub issue description</span></span>

<span data-ttu-id="182a8-213">`IssuePrediction` 是在定型模型后用于预测的类。</span><span class="sxs-lookup"><span data-stu-id="182a8-213">`IssuePrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="182a8-214">它有一个 `string` (`Area`) 和一个 `PredictedLabel` `ColumnName` 属性。</span><span class="sxs-lookup"><span data-stu-id="182a8-214">It has a single `string` (`Area`) and a `PredictedLabel` `ColumnName` attribute.</span></span> <span data-ttu-id="182a8-215">`Label` 用于创建和定型模型，并且与第二个数据集结合使用来评估模型。</span><span class="sxs-lookup"><span data-stu-id="182a8-215">The `Label` is used to create and train the model, and it's also used with a second dataset to evaluate the model.</span></span> <span data-ttu-id="182a8-216">`PredictedLabel` 在预测和评估过程中使用。</span><span class="sxs-lookup"><span data-stu-id="182a8-216">The `PredictedLabel` is used during prediction and evaluation.</span></span> <span data-ttu-id="182a8-217">对于计算，将使用带定型数据的输入、预测值和模型。</span><span class="sxs-lookup"><span data-stu-id="182a8-217">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="182a8-218">使用 ML.NET 构建模型时，首先要创建一个 <xref:Microsoft.ML.MLContext>。</span><span class="sxs-lookup"><span data-stu-id="182a8-218">When building a model with ML.NET, you start by creating an <xref:Microsoft.ML.MLContext>.</span></span> <span data-ttu-id="182a8-219">这在概念上相当于在实体框架中使用 `DbContext`。</span><span class="sxs-lookup"><span data-stu-id="182a8-219">This is comparable conceptually to using `DbContext` in Entity Framework.</span></span> <span data-ttu-id="182a8-220">该环境为 ML 作业提供一个上下文，可以用于异常情况跟踪和日志记录。</span><span class="sxs-lookup"><span data-stu-id="182a8-220">The environment provides a context for your ML job that can be used for exception tracking and logging.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="182a8-221">在 Main 中初始化变量</span><span class="sxs-lookup"><span data-stu-id="182a8-221">Initialize variables in Main</span></span>

<span data-ttu-id="182a8-222">使用具有随机种子 (`seed: 0`) 的新实例 `MLContext` 初始化 `_mlContext` 全局变量，以获得跨多个定型的可重复/确定性结果。</span><span class="sxs-lookup"><span data-stu-id="182a8-222">Initialize the `_mlContext` global variable  with a new instance of `MLContext` with a random seed (`seed: 0`) for repeatable/deterministic results across multiple trainings.</span></span>  <span data-ttu-id="182a8-223">用下面 `Main` 方法中的代码替换 `Console.WriteLine("Hello World!")` 行：</span><span class="sxs-lookup"><span data-stu-id="182a8-223">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreateMLContext)]

## <a name="load-the-data"></a><span data-ttu-id="182a8-224">加载数据</span><span class="sxs-lookup"><span data-stu-id="182a8-224">Load the data</span></span>

<span data-ttu-id="182a8-225">接下来，初始化 `_trainingDataView` <xref:Microsoft.ML.Data.IDataView> 全局变量并使用 `_trainDataPath` 参数加载数据。</span><span class="sxs-lookup"><span data-stu-id="182a8-225">Next, initialize the `_trainingDataView` <xref:Microsoft.ML.Data.IDataView> global variable and load the data with the `_trainDataPath` parameter.</span></span>

 <span data-ttu-id="182a8-226">作为 `Transforms` 的输入和输出，`DataView` 是基本的数据管道类型，与 `LINQ` 中的 `IEnumerable` 类似。</span><span class="sxs-lookup"><span data-stu-id="182a8-226">As the input and output of `Transforms`, a `DataView` is the fundamental data pipeline type, comparable to `IEnumerable` for `LINQ`.</span></span>

<span data-ttu-id="182a8-227">在 ML.NET 中，数据类似于 `SQL view`。</span><span class="sxs-lookup"><span data-stu-id="182a8-227">In ML.NET, data is similar to a `SQL view`.</span></span> <span data-ttu-id="182a8-228">它是异源数据，会延迟计算并进行架构化。</span><span class="sxs-lookup"><span data-stu-id="182a8-228">It is lazily evaluated, schematized, and heterogenous.</span></span> <span data-ttu-id="182a8-229">该对象是管道的第一部分，并加载数据。</span><span class="sxs-lookup"><span data-stu-id="182a8-229">The object is the first part of the pipeline, and loads the data.</span></span> <span data-ttu-id="182a8-230">在本教程中，它会加载一个包含问题标题、说明和相应区域 GitHub 标签的数据集。</span><span class="sxs-lookup"><span data-stu-id="182a8-230">For this tutorial, it loads a dataset with issue titles, descriptions, and corresponding area GitHub label.</span></span> <span data-ttu-id="182a8-231">`DataView` 用于创建和定型模型。</span><span class="sxs-lookup"><span data-stu-id="182a8-231">The `DataView` is used to create and train the model.</span></span>

<span data-ttu-id="182a8-232">由于先前创建的 `GitHubIssue` 数据模型类型与数据集架构相匹配，因此可以将初始化、映射和数据集加载合并到一行代码中。</span><span class="sxs-lookup"><span data-stu-id="182a8-232">Since your previously created `GitHubIssue` data model type matches the dataset schema, you can combine the initialization, mapping, and dataset loading into one line of code.</span></span>

<span data-ttu-id="182a8-233">该行的第一部分 (`CreateTextReader<GitHubIssue>(hasHeader: true)`) 通过从 `GitHubIssue` 数据模型类型推断数据集架构并使用数据集标头，来创建 <xref:Microsoft.ML.Data.TextLoader>。</span><span class="sxs-lookup"><span data-stu-id="182a8-233">The first part of the line (`CreateTextReader<GitHubIssue>(hasHeader: true)`) creates a <xref:Microsoft.ML.Data.TextLoader> by inferencing the dataset schema from the `GitHubIssue` data model type and using the dataset header.</span></span>

<span data-ttu-id="182a8-234">之前在创建 `GitHubIssue` 类时定义了数据模式。</span><span class="sxs-lookup"><span data-stu-id="182a8-234">You defined the data schema previously when you created the `GitHubIssue` class.</span></span> <span data-ttu-id="182a8-235">对于架构：</span><span class="sxs-lookup"><span data-stu-id="182a8-235">For your schema:</span></span>

* <span data-ttu-id="182a8-236">第一列 `ID`（GitHub 问题 ID）</span><span class="sxs-lookup"><span data-stu-id="182a8-236">the first column `ID` (GitHub Issue ID)</span></span>
* <span data-ttu-id="182a8-237">第二列 `Area`（定型预测）</span><span class="sxs-lookup"><span data-stu-id="182a8-237">the second column `Area` (the prediction for training)</span></span>
* <span data-ttu-id="182a8-238">第三列 `Title`（GitHub 问题标题）是用于预测 `Area` 的第一个[特征](../resources/glossary.md##feature)</span><span class="sxs-lookup"><span data-stu-id="182a8-238">the third column `Title` (GitHub issue title) is the first [feature](../resources/glossary.md##feature)  used for predicting the `Area`</span></span>
* <span data-ttu-id="182a8-239">第四列 `Description` 是用于预测 `Area` 的第二个特征</span><span class="sxs-lookup"><span data-stu-id="182a8-239">the fourth column  `Description` is the second feature used for predicting the `Area`</span></span>

<span data-ttu-id="182a8-240">该行的第二部分 (`.Read(_trainDataPath)`) 使用 <xref:Microsoft.ML.Data.TextLoader.Read%2A> 方法将 `_trainDataPath` 的定型文本文件加载到 `IDataView` (`_trainingDataView`) 全局变量中。</span><span class="sxs-lookup"><span data-stu-id="182a8-240">The second part of the line  (`.Read(_trainDataPath)`) uses <xref:Microsoft.ML.Data.TextLoader.Read%2A> method to load the training text file using `_trainDataPath` into the `IDataView` (`_trainingDataView`) global variable.</span></span>  

<span data-ttu-id="182a8-241">要初始化并加载 `_trainingDataView` 全局变量以将其用于管道，请在 `mlContext` 初始化后添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="182a8-241">To initialize and load the `_trainingDataView` global variable in order to use it for the pipeline, add the following code after the  `mlContext` initialization:</span></span>

[!code-csharp[LoadTrainData](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadTrainData)]


<span data-ttu-id="182a8-242">将以下代码作为下一行代码添加到 `Main` 方法中：</span><span class="sxs-lookup"><span data-stu-id="182a8-242">Add the following as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallProcessData](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallProcessData)]

<span data-ttu-id="182a8-243">`ProcessData` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="182a8-243">The `ProcessData` method executes the following tasks:</span></span>

* <span data-ttu-id="182a8-244">提取并转换数据。</span><span class="sxs-lookup"><span data-stu-id="182a8-244">Extracts and transforms the data.</span></span>
* <span data-ttu-id="182a8-245">返回处理管道。</span><span class="sxs-lookup"><span data-stu-id="182a8-245">Returns the processing pipeline.</span></span>

<span data-ttu-id="182a8-246">使用下面的代码紧随 `Main` 方法后创建 `ProcessData` 方法：</span><span class="sxs-lookup"><span data-stu-id="182a8-246">Create the `ProcessData` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static EstimatorChain<ITransformer> ProcessData()
{

}
```

## <a name="extract-and-transform-the-data"></a><span data-ttu-id="182a8-247">提取和转换数据</span><span class="sxs-lookup"><span data-stu-id="182a8-247">Extract and transform the data</span></span>

<span data-ttu-id="182a8-248">预处理和清除数据任务至关重要，需要首先执行才能将数据集有效地用于机器学习。</span><span class="sxs-lookup"><span data-stu-id="182a8-248">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span> <span data-ttu-id="182a8-249">原始数据通常嘈杂不可靠，并且可能缺少值。</span><span class="sxs-lookup"><span data-stu-id="182a8-249">Raw data is often noisy and unreliable, and may be missing values.</span></span> <span data-ttu-id="182a8-250">在没有这些建模任务的情况下使用数据会产生误导性结果。</span><span class="sxs-lookup"><span data-stu-id="182a8-250">Using data without these modeling tasks can produce misleading results.</span></span>

<span data-ttu-id="182a8-251">ML.NET 的转换管道撰写一组自定义转换，在定型或测试数据之前将其应用到数据。</span><span class="sxs-lookup"><span data-stu-id="182a8-251">ML.NET's transform pipelines compose a custom set of transforms that are applied to your data before training or testing.</span></span> <span data-ttu-id="182a8-252">转换的主要目的是为了[特征化](../resources/glossary.md#feature-engineering)数据。</span><span class="sxs-lookup"><span data-stu-id="182a8-252">The transforms' primary purpose is data [featurization](../resources/glossary.md#feature-engineering).</span></span> <span data-ttu-id="182a8-253">机器学习算法理解[特征化](../resources/glossary.md#feature)数据，因此下一步是将文本数据转换为 ML 算法识别的格式。</span><span class="sxs-lookup"><span data-stu-id="182a8-253">Machine learning algorithms understand [featurized](../resources/glossary.md#feature) data, so the next step is to transform our textual data into a format that our ML algorithms recognize.</span></span> <span data-ttu-id="182a8-254">该格式是[数值向量](../resources/glossary.md#numerical-feature-vector)。</span><span class="sxs-lookup"><span data-stu-id="182a8-254">That format is a [numeric vector](../resources/glossary.md#numerical-feature-vector).</span></span>

<span data-ttu-id="182a8-255">在后续步骤中，按 `GitHubIssue` 类中定义的名称引用列。</span><span class="sxs-lookup"><span data-stu-id="182a8-255">In the next steps, we refer to the columns by the names defined in the `GitHubIssue` class.</span></span>

<span data-ttu-id="182a8-256">定型和评估模型时，默认情况下，将“标签”列中的值视为要预测的正确值。</span><span class="sxs-lookup"><span data-stu-id="182a8-256">When the model is trained and evaluated, by default, the values in the **Label** column are considered as correct values to be predicted.</span></span> <span data-ttu-id="182a8-257">由于要预测 `GitHubIssue` 的区域 GitHub 标签，所以将 `Area` 列复制到“标签”列。</span><span class="sxs-lookup"><span data-stu-id="182a8-257">As we want to predict the Area GitHub label for a `GitHubIssue`, copy the `Area` column into the **Label** column.</span></span> <span data-ttu-id="182a8-258">为此，请使用 `MLContext.Transforms.Conversion.MapValueToKey`，它是 <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A> 转换类的包装器。</span><span class="sxs-lookup"><span data-stu-id="182a8-258">To do that, use the `MLContext.Transforms.Conversion.MapValueToKey`, which is a wrapper for the <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A> transformation class.</span></span>  <span data-ttu-id="182a8-259">`MapValueToKey` 返回实际上是管道的 <xref:Microsoft.ML.Data.EstimatorChain%601>。</span><span class="sxs-lookup"><span data-stu-id="182a8-259">The `MapValueToKey` returns an <xref:Microsoft.ML.Data.EstimatorChain%601> that will effectively be a pipeline.</span></span> <span data-ttu-id="182a8-260">命名此 `pipeline`，因为你将把定型程序附加到 `EstimatorChain`。</span><span class="sxs-lookup"><span data-stu-id="182a8-260">Name this `pipeline` as you will then append the trainer to the `EstimatorChain`.</span></span> <span data-ttu-id="182a8-261">将此添加为下一个代码行：</span><span class="sxs-lookup"><span data-stu-id="182a8-261">Add this as the next line of code:</span></span>

[!code-csharp[MapValueToKey](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#MapValueToKey)]

<span data-ttu-id="182a8-262">为模型定型的算法需要“数字”特征，因此下一步是调用 `mlContext.Transforms.Text.FeaturizeText`，它将文本（`Title` 和 `Description`）列特征化为分别称为 `TitleFeaturized` 和 `DescriptionFeaturized` 的数字向量。</span><span class="sxs-lookup"><span data-stu-id="182a8-262">The algorithm that trains the model requires **numeric** features, so you have Next, call `mlContext.Transforms.Text.FeaturizeText` which featurizes the text (`Title` and `Description`) columns into a numeric vector for each called `TitleFeaturized` and `DescriptionFeaturized`.</span></span> <span data-ttu-id="182a8-263">特征化将不同的数字键值分配给每列的不同值，供机器学习算法使用。</span><span class="sxs-lookup"><span data-stu-id="182a8-263">Featurizing assigns different numeric key values to the different values in each of the columns and is used by the machine learning algorithm.</span></span>
<span data-ttu-id="182a8-264">使用以下代码将两列的特征化附加到管道：</span><span class="sxs-lookup"><span data-stu-id="182a8-264">Append the featurization for both columns to the pipeline with the following code:</span></span>

[!code-csharp[FeaturizeText](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#FeaturizeText)]

<span data-ttu-id="182a8-265">数据准备最后一步使用 `Concatenate` 转换类将所有功能列合并到“功能”列。</span><span class="sxs-lookup"><span data-stu-id="182a8-265">The last step in data preparation combines all of the feature columns into the **Features** column using the `Concatenate` transformation class.</span></span> <span data-ttu-id="182a8-266">默认情况下，学习算法仅处理“特征”列的特征。</span><span class="sxs-lookup"><span data-stu-id="182a8-266">By default, a learning algorithm processes only features from the **Features** column.</span></span> <span data-ttu-id="182a8-267">使用以下代码将此转换附加到管道：</span><span class="sxs-lookup"><span data-stu-id="182a8-267">Append this transformation to the pipeline with the following code:</span></span>

[!code-csharp[Concatenate](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Concatenate)]

 <span data-ttu-id="182a8-268">接下来，附加一个 <xref:Microsoft.ML.Data.EstimatorChain`1.AppendCacheCheckpoint%2A> 来缓存数据视图，以便在使用缓存多次循环访问数据时获得更好的性能，如下面的代码所示</span><span class="sxs-lookup"><span data-stu-id="182a8-268">Next, append a <xref:Microsoft.ML.Data.EstimatorChain`1.AppendCacheCheckpoint%2A> to cache the DataView so when you iterate over the data multiple times using the cache might get better performance, as with the following code</span></span>

[!code-csharp[AppendCache](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AppendCache)]

<span data-ttu-id="182a8-269">在 `ProcessData` 方法的末尾返回管道。</span><span class="sxs-lookup"><span data-stu-id="182a8-269">Return the pipeline at the end of the `ProcessData` method.</span></span>

[!code-csharp[ReturnPipeline](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#ReturnPipeline)]

<span data-ttu-id="182a8-270">此步骤处理预处理/特征化。</span><span class="sxs-lookup"><span data-stu-id="182a8-270">This step handles preprocessing/featurization.</span></span> <span data-ttu-id="182a8-271">使用 ML.NET 中可用的其他组件可以在使用模型时生成更佳结果。</span><span class="sxs-lookup"><span data-stu-id="182a8-271">Using additional components available in ML.NET can enable better results with your model.</span></span>

## <a name="build-and-train-the-model"></a><span data-ttu-id="182a8-272">生成和定型模型</span><span class="sxs-lookup"><span data-stu-id="182a8-272">Build and train the model</span></span>

<span data-ttu-id="182a8-273">将以下调用添加到 `BuildAndTrainModel` 方法作为 `Main` 方法的下一行代码：</span><span class="sxs-lookup"><span data-stu-id="182a8-273">Add the following call to the `BuildAndTrainModel`method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallBuildAndTrainModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallBuildAndTrainModel)]

<span data-ttu-id="182a8-274">`BuildAndTrainModel` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="182a8-274">The `BuildAndTrainModel` method executes the following tasks:</span></span>

* <span data-ttu-id="182a8-275">创建定型算法类。</span><span class="sxs-lookup"><span data-stu-id="182a8-275">Creates the training algorithm class.</span></span>
* <span data-ttu-id="182a8-276">定型模型。</span><span class="sxs-lookup"><span data-stu-id="182a8-276">Trains the model.</span></span>
* <span data-ttu-id="182a8-277">根据定型数据预测区域。</span><span class="sxs-lookup"><span data-stu-id="182a8-277">Predicts area based on training data.</span></span>
* <span data-ttu-id="182a8-278">将模型保存到 `.zip` 文件。</span><span class="sxs-lookup"><span data-stu-id="182a8-278">Saves the model to a `.zip` file.</span></span>
* <span data-ttu-id="182a8-279">返回模型。</span><span class="sxs-lookup"><span data-stu-id="182a8-279">Returns the model.</span></span>

<span data-ttu-id="182a8-280">使用下面的代码紧随 `Main` 方法后创建 `BuildAndTrainModel` 方法：</span><span class="sxs-lookup"><span data-stu-id="182a8-280">Create the `BuildAndTrainModel` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static void BuildAndTrainModel()
{

}
```

<span data-ttu-id="182a8-281">请注意，两个参数传递到 BuildAndTrainModel 方法；用于定性数据集 (`trainingDataView`) 的 `IDataView`，用于 ProcessData (`pipeline`) 中创建的处理管道的 <xref:Microsoft.ML.Data.EstimatorChain%601>。</span><span class="sxs-lookup"><span data-stu-id="182a8-281">Notice that two parameters are passed into the BuildAndTrainModel method; an `IDataView` for the training dataset (`trainingDataView`), and a <xref:Microsoft.ML.Data.EstimatorChain%601> for the processing pipeline created in ProcessData (`pipeline`).</span></span>

 <span data-ttu-id="182a8-282">将以下代码添加为 `BuildAndTrainModel` 方法的首行：</span><span class="sxs-lookup"><span data-stu-id="182a8-282">Add the following code as the first line of the `BuildAndTrainModel` method:</span></span>

### <a name="choose-a-trainer-algorithm"></a><span data-ttu-id="182a8-283">选择定型程序算法</span><span class="sxs-lookup"><span data-stu-id="182a8-283">Choose a trainer algorithm</span></span>

<span data-ttu-id="182a8-284">若要添加定型程序算法，请调用返回 <xref:Microsoft.ML.Trainers.SdcaMultiClassTrainer> 对象的 `mlContext.Transforms.Text.FeaturizeText` 包装器方法。</span><span class="sxs-lookup"><span data-stu-id="182a8-284">To add the trainer algorithm, call the `mlContext.Transforms.Text.FeaturizeText` wrapper method which returns a <xref:Microsoft.ML.Trainers.SdcaMultiClassTrainer> object.</span></span> <span data-ttu-id="182a8-285">这是一个将在此管道中使用的决策树学习器。</span><span class="sxs-lookup"><span data-stu-id="182a8-285">This is a decision tree learner you'll use in this pipeline.</span></span> <span data-ttu-id="182a8-286">`SdcaMultiClassTrainer` 追加到 `pipeline` 并接受特征化的 `Title` 和 `Description` (`Features`) 以及 `Label` 输入参数，以便从历史数据中学习。</span><span class="sxs-lookup"><span data-stu-id="182a8-286">The `SdcaMultiClassTrainer` is appended to the `pipeline` and accepts the featurized `Title` and `Description` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span>

<span data-ttu-id="182a8-287">将以下代码添加到 `BuildAndTrainModel` 方法中：</span><span class="sxs-lookup"><span data-stu-id="182a8-287">Add the following code to the `BuildAndTrainModel` method:</span></span>

[!code-csharp[SdcaMultiClassTrainer](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#SdcaMultiClassTrainer)]

<span data-ttu-id="182a8-288">现已创建了一个定型程序算法，可将其附加到 `pipeline`。</span><span class="sxs-lookup"><span data-stu-id="182a8-288">Now that you've created a trainer algorithm, append it to the `pipeline`.</span></span> <span data-ttu-id="182a8-289">还需要将标签映射到值以返回其原始可读状态。</span><span class="sxs-lookup"><span data-stu-id="182a8-289">You also need to map the label to the value to return to its original readable state.</span></span> <span data-ttu-id="182a8-290">使用以下代码执行这两个操作：</span><span class="sxs-lookup"><span data-stu-id="182a8-290">Do both of those actions with the following code:</span></span>

[!code-csharp[AddTrainer](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddTrainer)]

### <a name="train-the-model"></a><span data-ttu-id="182a8-291">定型模型</span><span class="sxs-lookup"><span data-stu-id="182a8-291">Train the model</span></span>

<span data-ttu-id="182a8-292">根据已加载和转换的数据集定型模型 <xref:Microsoft.ML.Data.TransformerChain%601>。</span><span class="sxs-lookup"><span data-stu-id="182a8-292">You train the model, <xref:Microsoft.ML.Data.TransformerChain%601>, based on the dataset that has been loaded and transformed.</span></span> <span data-ttu-id="182a8-293">一旦定义了估算器，将使用 <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> 定型模型，同时提供已经加载的定型数据。</span><span class="sxs-lookup"><span data-stu-id="182a8-293">Once the estimator has been defined, you train your model using the <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> while providing the already loaded training data.</span></span> <span data-ttu-id="182a8-294">这将返回要用于预测的模型。</span><span class="sxs-lookup"><span data-stu-id="182a8-294">This returns a model to use for predictions.</span></span> <span data-ttu-id="182a8-295">`trainingPipeline.Fit()` 定型管道，并返回基于传入的 `DataView` 的 `Transformer`。</span><span class="sxs-lookup"><span data-stu-id="182a8-295">`trainingPipeline.Fit()` trains the pipeline and returns a `Transformer` based on the `DataView` passed in.</span></span> <span data-ttu-id="182a8-296">在发生这种情况之前不会执行此试验。</span><span class="sxs-lookup"><span data-stu-id="182a8-296">The experiment is not executed until this happens.</span></span>

<span data-ttu-id="182a8-297">将以下代码添加到 `BuildAndTrainModel` 方法中：</span><span class="sxs-lookup"><span data-stu-id="182a8-297">Add the following code to the `BuildAndTrainModel` method:</span></span>

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#TrainModel)]

<span data-ttu-id="182a8-298">虽然 `model` 是对多行数据进行操作的 `transformer`，但是一个非常常见的生产场景是，需要对单个示例进行预测。</span><span class="sxs-lookup"><span data-stu-id="182a8-298">While the `model` is a `transformer` that operates on many rows of data, a very common production scenario is a need for predictions on individual examples.</span></span> <span data-ttu-id="182a8-299"><xref:Microsoft.ML.PredictionEngine%602> 是从 `CreatePredictionEngine` 方法返回的包装器。</span><span class="sxs-lookup"><span data-stu-id="182a8-299">The <xref:Microsoft.ML.PredictionEngine%602> is a wrapper that is returned from the `CreatePredictionEngine` method.</span></span> <span data-ttu-id="182a8-300">让我们添加以下代码来创建 `PredictionEngine`，作为 `BuildAndTrainModel` 方法中的下一行：</span><span class="sxs-lookup"><span data-stu-id="182a8-300">Let's add the following code to create the `PredictionEngine` as the next line in the `BuildAndTrainModel` Method:</span></span>

[!code-csharp[CreatePredictionEngine](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine)]

<span data-ttu-id="182a8-301">通过创建一个 `GitHubIssue` 实例，在 `Predict` 方法中添加一个 GitHub 问题来测试定型模型的预测：</span><span class="sxs-lookup"><span data-stu-id="182a8-301">Add a GitHub issue to test the trained model's prediction in the `Predict` method by creating an instance of `GitHubIssue`:</span></span>

[!code-csharp[CreateTestIssue1](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreateTestIssue1)]

<span data-ttu-id="182a8-302">可以使用它来预测问题数据的单个实例的 `Area` 标签。</span><span class="sxs-lookup"><span data-stu-id="182a8-302">You can use that to predict the `Area` label of a single instance of the issue data.</span></span> <span data-ttu-id="182a8-303">要获得预测，请对数据使用 <xref:Microsoft.ML.PredictionEngine%602.Predict%2A>。</span><span class="sxs-lookup"><span data-stu-id="182a8-303">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="182a8-304">请注意，输入数据是一个字符串，且模型包含特征化。</span><span class="sxs-lookup"><span data-stu-id="182a8-304">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="182a8-305">管道在定型和预测期间同步。</span><span class="sxs-lookup"><span data-stu-id="182a8-305">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="182a8-306">不必专门为预测编写预处理/特征化代码，并且相同 API 负责批处理和一次性预测。</span><span class="sxs-lookup"><span data-stu-id="182a8-306">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Predict)]

### <a name="model-operationalization-prediction"></a><span data-ttu-id="182a8-307">模型操作化：预测</span><span class="sxs-lookup"><span data-stu-id="182a8-307">Model operationalization: prediction</span></span>

<span data-ttu-id="182a8-308">显示 `GitHubIssue` 和相应的 `Area` 标签预测以便共享结果，并采取相应措施。</span><span class="sxs-lookup"><span data-stu-id="182a8-308">Display `GitHubIssue` and corresponding `Area` label prediction in order to share the results and act on them accordingly.</span></span> <span data-ttu-id="182a8-309">这称为操作化，使用返回的数据作为操作策略的一部分。</span><span class="sxs-lookup"><span data-stu-id="182a8-309">This is called operationalization, using the returned data as part of the operational policies.</span></span> <span data-ttu-id="182a8-310">使用以下 <xref:System.Console.WriteLine?displayProperty=nameWithType> 代码创建结果显示：</span><span class="sxs-lookup"><span data-stu-id="182a8-310">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputPrediction](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#OutputPrediction)]

### <a name="save-and-return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="182a8-311">保存并返回定型模型以用于评估</span><span class="sxs-lookup"><span data-stu-id="182a8-311">Save and return the model trained to use for evaluation</span></span>

<span data-ttu-id="182a8-312">此时，你具有可以集成到任何现有或新 .NET 应用程序的 <xref:Microsoft.ML.Data.TransformerChain%601> 类型模型。</span><span class="sxs-lookup"><span data-stu-id="182a8-312">At this point, you have a model of type <xref:Microsoft.ML.Data.TransformerChain%601> that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="182a8-313">要将已定型的模型保存为 .zip 文件，请添加以下代码作为 `BuildAndTrainModel` 中的下一行来调用 `SaveModelAsFile` 方法：</span><span class="sxs-lookup"><span data-stu-id="182a8-313">To save your trained model to a .zip file, add the following code to call the `SaveModelAsFile` method as the next line in `BuildAndTrainModel`:</span></span>

[!code-csharp[CallSaveModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallSaveModel)]

<span data-ttu-id="182a8-314">在 `BuildAndTrainModel` 方法末尾返回模型。</span><span class="sxs-lookup"><span data-stu-id="182a8-314">Return the model at the end of the `BuildAndTrainModel` method.</span></span>

[!code-csharp[ReturnModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#ReturnModel)]

## <a name="save-the-model-as-azip-file"></a><span data-ttu-id="182a8-315">将模型保存为 .zip 文件</span><span class="sxs-lookup"><span data-stu-id="182a8-315">Save the model as a.zip file</span></span>

<span data-ttu-id="182a8-316">使用下面的代码紧随 `BuildAndTrainModel` 方法后创建 `SaveModelAsFile` 方法：</span><span class="sxs-lookup"><span data-stu-id="182a8-316">Create the `SaveModelAsFile` method, just after the `BuildAndTrainModel` method, using the following code:</span></span>

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="182a8-317">`SaveModelAsFile` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="182a8-317">The `SaveModelAsFile` method executes the following tasks:</span></span>

* <span data-ttu-id="182a8-318">将模型保存为 .zip 文件。</span><span class="sxs-lookup"><span data-stu-id="182a8-318">Saves the model as a .zip file.</span></span>

<span data-ttu-id="182a8-319">接下来，创建一个方法来保存模型，以便它可以在其他应用程序中重用和使用。</span><span class="sxs-lookup"><span data-stu-id="182a8-319">Next, create a method to save the model so that it can be reused and consumed in other applications.</span></span> <span data-ttu-id="182a8-320">`ITransformer` 有一个在 `_modelPath` 全局字段中采用的 <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> 方法和一个 <xref:System.IO.Stream> 方法。</span><span class="sxs-lookup"><span data-stu-id="182a8-320">The `ITransformer` has a <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> method that takes in the `_modelPath` global field, and a <xref:System.IO.Stream>.</span></span> <span data-ttu-id="182a8-321">要将其保存为 zip 文件，将在调用 `SaveTo` 方法之前立即创建 `FileStream`。</span><span class="sxs-lookup"><span data-stu-id="182a8-321">To save this as a zip file, you'll create the `FileStream` immediately before calling the `SaveTo` method.</span></span> <span data-ttu-id="182a8-322">将以下代码作为下一行添加到 `SaveModelAsFile` 方法中：</span><span class="sxs-lookup"><span data-stu-id="182a8-322">Add the following code to the `SaveModelAsFile` method as the next line:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#SaveModel)]

<span data-ttu-id="182a8-323">还可以使用以下代码通过使用 `_modelPath` 编写控制台消息来显示文件的写入位置：</span><span class="sxs-lookup"><span data-stu-id="182a8-323">You could also display where the file was written by writing a console message with the `_modelPath`, using the following code:</span></span>

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="evaluate-the-model"></a><span data-ttu-id="182a8-324">评估模型</span><span class="sxs-lookup"><span data-stu-id="182a8-324">Evaluate the model</span></span>

<span data-ttu-id="182a8-325">你已经创建和定型模型，现在需要使用不同的数据集对其进行评估以保证质量和进行验证。</span><span class="sxs-lookup"><span data-stu-id="182a8-325">Now that you've created and trained the model, you need to evaluate it with a different dataset for quality assurance and validation.</span></span> <span data-ttu-id="182a8-326">在 `Evaluate` 方法中，将传入在 `BuildAndTrainModel` 中创建的模型以进行评估。</span><span class="sxs-lookup"><span data-stu-id="182a8-326">In the `Evaluate` method, the model created in `BuildAndTrainModel` is passed in to be evaluated.</span></span> <span data-ttu-id="182a8-327">紧随 `BuildAndTrainModel` 后创建 `Evaluate` 方法，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="182a8-327">Create the `Evaluate` method, just after `BuildAndTrainModel`, as in the following code:</span></span>

```csharp
public static void Evaluate()
{

}
```

<span data-ttu-id="182a8-328">`Evaluate` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="182a8-328">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="182a8-329">加载测试数据集。</span><span class="sxs-lookup"><span data-stu-id="182a8-329">Loads the test dataset.</span></span>
* <span data-ttu-id="182a8-330">创建多类评估程序。</span><span class="sxs-lookup"><span data-stu-id="182a8-330">Creates the multiclass evaluator.</span></span>
* <span data-ttu-id="182a8-331">评估模型并创建指标。</span><span class="sxs-lookup"><span data-stu-id="182a8-331">Evaluates the model and create metrics.</span></span>
* <span data-ttu-id="182a8-332">显示指标。</span><span class="sxs-lookup"><span data-stu-id="182a8-332">Displays the metrics.</span></span>

<span data-ttu-id="182a8-333">使用下面的代码，在 `BuildAndTrainModel` 方法调用的正下方，从 `Main` 方法中添加对新方法的调用：</span><span class="sxs-lookup"><span data-stu-id="182a8-333">Add a call to the new method from the `Main` method, right under the `BuildAndTrainModel` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallEvaluate)]

<span data-ttu-id="182a8-334">如同之前使用定型数据集执行的操作，可以将初始化、映射和测试数据集加载合并到一行代码中。</span><span class="sxs-lookup"><span data-stu-id="182a8-334">As you did previously with the training dataset, you can combine the initialization, mapping, and test dataset loading into one line of code.</span></span> <span data-ttu-id="182a8-335">可以将此数据集作为质量检查来评估模型。</span><span class="sxs-lookup"><span data-stu-id="182a8-335">You can evaluate the model using this dataset as a quality check.</span></span> <span data-ttu-id="182a8-336">将以下代码添加到 `Evaluate` 方法中：</span><span class="sxs-lookup"><span data-stu-id="182a8-336">Add the following code to the `Evaluate` method:</span></span>

[!code-csharp[LoadTestDataset](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadTestDataset)]

<span data-ttu-id="182a8-337">`MulticlassClassificationContext.Evaluate` 是 <xref:Microsoft.ML.MulticlassClassificationContext.Evaluate%2A> 方法的包装器，它使用指定数据集计算模型的质量指标。</span><span class="sxs-lookup"><span data-stu-id="182a8-337">The `MulticlassClassificationContext.Evaluate` is a wrapper for the <xref:Microsoft.ML.MulticlassClassificationContext.Evaluate%2A> method that computes the quality metrics for the model using the specified dataset.</span></span> <span data-ttu-id="182a8-338">它返回 <xref:Microsoft.ML.Data.MultiClassClassifierMetrics> 对象，其中包含由多类分类计算器计算出的总体指标。</span><span class="sxs-lookup"><span data-stu-id="182a8-338">It returns a <xref:Microsoft.ML.Data.MultiClassClassifierMetrics> object that contains the overall metrics computed by multiclass classification evaluators.</span></span>
<span data-ttu-id="182a8-339">若要显示这些指标来确定模型质量，需要先获取指标。</span><span class="sxs-lookup"><span data-stu-id="182a8-339">To display these to determine the quality of the model, you need to get the metrics first.</span></span>
<span data-ttu-id="182a8-340">请注意使用机器学习 `_trainedModel` 全局变量（转换器）的 `Transform` 方法来输入要素和返回预测。</span><span class="sxs-lookup"><span data-stu-id="182a8-340">Notice the use of the `Transform` method of the machine learning `_trainedModel` global variable (a transformer) to input the features and return predictions.</span></span> <span data-ttu-id="182a8-341">将以下代码作为下一行添加到 `Evaluate` 方法中：</span><span class="sxs-lookup"><span data-stu-id="182a8-341">Add the following code to the `Evaluate` method as the next line:</span></span>

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Evaluate)]

<span data-ttu-id="182a8-342">针对多类分类评估以下指标：</span><span class="sxs-lookup"><span data-stu-id="182a8-342">The following metrics are evaluated for multiclass classification:</span></span>

* <span data-ttu-id="182a8-343">微观准确性 - 每个“样本-类”对准确性指标的贡献度相同。</span><span class="sxs-lookup"><span data-stu-id="182a8-343">Micro Accuracy - Every sample-class pair contributes equally to the accuracy metric.</span></span>  <span data-ttu-id="182a8-344">通常会希望微观准确性尽可能接近 1。</span><span class="sxs-lookup"><span data-stu-id="182a8-344">You want Micro Accuracy to be as close to 1 as possible.</span></span>

* <span data-ttu-id="182a8-345">宏观准确性 - 每个类对准确性指标的贡献度相同。</span><span class="sxs-lookup"><span data-stu-id="182a8-345">Macro Accuracy - Every class contributes equally to the accuracy metric.</span></span> <span data-ttu-id="182a8-346">占比较小的类与占比较大的类拥有同等的权重。</span><span class="sxs-lookup"><span data-stu-id="182a8-346">Minority classes are given equal weight as the larger classes.</span></span> <span data-ttu-id="182a8-347">通常会希望宏准确性尽可能接近 1。</span><span class="sxs-lookup"><span data-stu-id="182a8-347">You want Macro Accuracy to be as close to 1 as possible.</span></span>

* <span data-ttu-id="182a8-348">对数损失 - 请参阅[对数损失](../resources/glossary.md#log-loss)。</span><span class="sxs-lookup"><span data-stu-id="182a8-348">Log-loss - see [Log Loss](../resources/glossary.md#log-loss).</span></span> <span data-ttu-id="182a8-349">通常会希望对数损失尽可能接近 0。</span><span class="sxs-lookup"><span data-stu-id="182a8-349">You want Log-loss to be as close to zero as possible.</span></span>

* <span data-ttu-id="182a8-350">对数损失减小 - 取值范围为 [-inf，100]，其中 100 表示非常精准的预测结果，0 表示准确性一般的预测。</span><span class="sxs-lookup"><span data-stu-id="182a8-350">Log-loss reduction - Ranges from [-inf, 100], where 100 is perfect predictions and 0 indicates mean predictions.</span></span> <span data-ttu-id="182a8-351">通常会希望数损失减少尽可能接近零。</span><span class="sxs-lookup"><span data-stu-id="182a8-351">You want Log-loss reduction to be as close to zero as possible.</span></span>

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="182a8-352">显示用于模型验证的指标</span><span class="sxs-lookup"><span data-stu-id="182a8-352">Displaying the metrics for model validation</span></span>

<span data-ttu-id="182a8-353">使用下面的代码显示指标、共享结果，然后处理它们：</span><span class="sxs-lookup"><span data-stu-id="182a8-353">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DisplayMetrics)]

## <a name="predict-the-test-data-outcome-with-the-saved-model"></a><span data-ttu-id="182a8-354">使用保存的模型预测测试数据结果</span><span class="sxs-lookup"><span data-stu-id="182a8-354">Predict the test data outcome with the saved model</span></span>

<span data-ttu-id="182a8-355">使用下面的代码，在 `Evaluate` 方法调用的正下方，从 `Main` 方法中添加对新方法的调用：</span><span class="sxs-lookup"><span data-stu-id="182a8-355">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallPredictIssue](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallPredictIssue)]

<span data-ttu-id="182a8-356">使用下面的代码紧随 `Evaluate` 方法后创建 `PredictIssue` 方法：</span><span class="sxs-lookup"><span data-stu-id="182a8-356">Create the `PredictIssue` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void PredictIssue()
{

}
```

<span data-ttu-id="182a8-357">`PredictIssue` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="182a8-357">The `PredictIssue` method executes the following tasks:</span></span>

* <span data-ttu-id="182a8-358">创建测试数据的单个问题。</span><span class="sxs-lookup"><span data-stu-id="182a8-358">Creates a single issue of test data.</span></span>
* <span data-ttu-id="182a8-359">根据测试数据预测区域。</span><span class="sxs-lookup"><span data-stu-id="182a8-359">Predicts Area based on test data.</span></span>
* <span data-ttu-id="182a8-360">结合测试数据和预测进行报告。</span><span class="sxs-lookup"><span data-stu-id="182a8-360">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="182a8-361">显示预测结果。</span><span class="sxs-lookup"><span data-stu-id="182a8-361">Displays the predicted results.</span></span>

<span data-ttu-id="182a8-362">首先，使用以下代码加载先前保存的模型：</span><span class="sxs-lookup"><span data-stu-id="182a8-362">First, load the model that you saved previously with the following code:</span></span>

[!code-csharp[LoadModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadModel)]

<span data-ttu-id="182a8-363">通过创建一个 `GitHubIssue` 实例，在 `Predict` 方法中添加一个 GitHub 问题来测试定型模型的预测：</span><span class="sxs-lookup"><span data-stu-id="182a8-363">Add a GitHub issue to test the trained model's prediction in the `Predict` method by creating an instance of `GitHubIssue`:</span></span>

[!code-csharp[AddTestIssue](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddTestIssue)]

[!code-csharp[CreatePredictionEngine](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine)]
  
<span data-ttu-id="182a8-364">现在已有一个模型，可以使用它来预测 GitHub 问题数据的单个实例的区域 GitHub 标签。</span><span class="sxs-lookup"><span data-stu-id="182a8-364">Now that you have a model, you can use that to predict the Area GitHub label of a single instance of the GitHub issue data.</span></span> <span data-ttu-id="182a8-365">要获得预测，请对数据使用 <xref:Microsoft.ML.PredictionEngine%602.Predict%2A>。</span><span class="sxs-lookup"><span data-stu-id="182a8-365">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="182a8-366">请注意，输入数据是一个字符串，且模型包含特征化。</span><span class="sxs-lookup"><span data-stu-id="182a8-366">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="182a8-367">管道在定型和预测期间同步。</span><span class="sxs-lookup"><span data-stu-id="182a8-367">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="182a8-368">不必专门为预测编写预处理/特征化代码，并且相同 API 负责批处理和一次性预测。</span><span class="sxs-lookup"><span data-stu-id="182a8-368">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span> <span data-ttu-id="182a8-369">在用于预测的 `PredictIssue` 方法中添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="182a8-369">Add the following code to the `PredictIssue` method for the predictions:</span></span>

[!code-csharp[PredictIssue](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine)]

### <a name="model-operationalization-prediction"></a><span data-ttu-id="182a8-370">模型操作化：预测</span><span class="sxs-lookup"><span data-stu-id="182a8-370">Model operationalization: prediction</span></span>

<span data-ttu-id="182a8-371">显示 `Area` 以便对问题进行分类并对其进行相应操作。</span><span class="sxs-lookup"><span data-stu-id="182a8-371">Display `Area` in order to categorize the issue and act on it accordingly.</span></span> <span data-ttu-id="182a8-372">这称为操作化，使用返回的数据作为操作策略的一部分。</span><span class="sxs-lookup"><span data-stu-id="182a8-372">This is called operationalization, using the returned data as part of the operational policies.</span></span> <span data-ttu-id="182a8-373">使用以下 <xref:System.Console.WriteLine?displayProperty=nameWithType> 代码创建结果显示：</span><span class="sxs-lookup"><span data-stu-id="182a8-373">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[DisplayResults](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DisplayResults)]

## <a name="results"></a><span data-ttu-id="182a8-374">结果</span><span class="sxs-lookup"><span data-stu-id="182a8-374">Results</span></span>

<span data-ttu-id="182a8-375">结果应如下所示。</span><span class="sxs-lookup"><span data-stu-id="182a8-375">Your results should be similar to the following.</span></span> <span data-ttu-id="182a8-376">管道处理期间，会显示消息。</span><span class="sxs-lookup"><span data-stu-id="182a8-376">As the pipeline processes, it displays messages.</span></span> <span data-ttu-id="182a8-377">你可能会看到警告或处理消息。</span><span class="sxs-lookup"><span data-stu-id="182a8-377">You may see warnings, or processing messages.</span></span> <span data-ttu-id="182a8-378">为清楚起见，已经从下面的结果中删除这些内容。</span><span class="sxs-lookup"><span data-stu-id="182a8-378">These have been removed from the following results for clarity.</span></span>

```console
=============== Single Prediction just-trained-model - Result: area-System.Net ===============
The model is saved to C:\Users\johalex\dotnet-samples\samples\machine-learning\tutorials\GitHubIssueClassification\bin\Debug\netcoreapp2.0\..\..\..\Models\model.zip
*************************************************************************************************************
*       Metrics for Multi-class Classification model - Test Data
*------------------------------------------------------------------------------------------------------------
*       MicroAccuracy:    0.74
*       MacroAccuracy:    0.687
*       LogLoss:          .932
*       LogLossReduction: 63.852
*************************************************************************************************************
=============== Single Prediction - Result: area-System.Data ===============
```

<span data-ttu-id="182a8-379">祝贺你！</span><span class="sxs-lookup"><span data-stu-id="182a8-379">Congratulations!</span></span> <span data-ttu-id="182a8-380">现在，已成功生成用于为 GitHub 问题分类和预测区域标签的机器学习模型。</span><span class="sxs-lookup"><span data-stu-id="182a8-380">You've now successfully built a machine learning model for classifying and predicting an Area label for a GitHub issue.</span></span> <span data-ttu-id="182a8-381">可以在 [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) 存储库中找到本教程的源代码。</span><span class="sxs-lookup"><span data-stu-id="182a8-381">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="182a8-382">后续步骤</span><span class="sxs-lookup"><span data-stu-id="182a8-382">Next steps</span></span>

<span data-ttu-id="182a8-383">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="182a8-383">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="182a8-384">了解问题</span><span class="sxs-lookup"><span data-stu-id="182a8-384">Understand the problem</span></span>
> * <span data-ttu-id="182a8-385">选择适当的机器学习任务</span><span class="sxs-lookup"><span data-stu-id="182a8-385">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="182a8-386">准备数据</span><span class="sxs-lookup"><span data-stu-id="182a8-386">Prepare your data</span></span>
> * <span data-ttu-id="182a8-387">创建学习管道</span><span class="sxs-lookup"><span data-stu-id="182a8-387">Create the learning pipeline</span></span>
> * <span data-ttu-id="182a8-388">加载分类器</span><span class="sxs-lookup"><span data-stu-id="182a8-388">Load a classifier</span></span>
> * <span data-ttu-id="182a8-389">定型模型</span><span class="sxs-lookup"><span data-stu-id="182a8-389">Train the model</span></span>
> * <span data-ttu-id="182a8-390">使用不同数据集评估模型</span><span class="sxs-lookup"><span data-stu-id="182a8-390">Evaluate the model with a different dataset</span></span>
> * <span data-ttu-id="182a8-391">使用模型预测测试数据结果</span><span class="sxs-lookup"><span data-stu-id="182a8-391">Predict the test data outcomes with the model</span></span>

<span data-ttu-id="182a8-392">进入下一教程了解详细信息</span><span class="sxs-lookup"><span data-stu-id="182a8-392">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="182a8-393">出租车费预测器</span><span class="sxs-lookup"><span data-stu-id="182a8-393">Taxi Fare Predictor</span></span>](taxi-fare.md)

---
title: 在 GitHub 问题多类分类方案中使用 ML.NET
description: 了解如何在多类分类方案中使用 ML.NET 对 GitHub 问题进行分类，将其分配到给定区域。
ms.date: 03/12/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 1031ac8a592c968e22745de4be966392733597dd
ms.sourcegitcommit: 16aefeb2d265e69c0d80967580365fabf0c5d39a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/18/2019
ms.locfileid: "57846306"
---
# <a name="tutorial-use-mlnet-in-a-multiclass-classification-scenario-to-classify-github-issues"></a><span data-ttu-id="27a89-103">教程：在多类分类场景中使用 ML.NET 对 GitHub 问题进行分类</span><span class="sxs-lookup"><span data-stu-id="27a89-103">Tutorial: Use ML.NET in a multiclass classification scenario to classify GitHub issues</span></span>

<span data-ttu-id="27a89-104">此示例教程通过在 Visual Studio 2017 中使用 C# 的 .NET Core 控制台应用程序，演示如何使用 ML.NET 创建 GitHub 问题分类器。</span><span class="sxs-lookup"><span data-stu-id="27a89-104">This sample tutorial illustrates using ML.NET to create a GitHub issue classifier via a .NET Core console application using C# in Visual Studio 2017.</span></span>

<span data-ttu-id="27a89-105">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="27a89-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="27a89-106">了解问题</span><span class="sxs-lookup"><span data-stu-id="27a89-106">Understand the problem</span></span>
> * <span data-ttu-id="27a89-107">选择适当的机器学习算法</span><span class="sxs-lookup"><span data-stu-id="27a89-107">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="27a89-108">准备数据</span><span class="sxs-lookup"><span data-stu-id="27a89-108">Prepare your data</span></span>
> * <span data-ttu-id="27a89-109">转换数据</span><span class="sxs-lookup"><span data-stu-id="27a89-109">Transform the data</span></span>
> * <span data-ttu-id="27a89-110">定型模型</span><span class="sxs-lookup"><span data-stu-id="27a89-110">Train the model</span></span>
> * <span data-ttu-id="27a89-111">评估模型</span><span class="sxs-lookup"><span data-stu-id="27a89-111">Evaluate the model</span></span>
> * <span data-ttu-id="27a89-112">使用训练的模型预测</span><span class="sxs-lookup"><span data-stu-id="27a89-112">Predict with the trained model</span></span>
> * <span data-ttu-id="27a89-113">使用加载模型部署和预测</span><span class="sxs-lookup"><span data-stu-id="27a89-113">Deploy and Predict with a loaded model</span></span>

> [!NOTE]
> <span data-ttu-id="27a89-114">本主题引用 ML.NET（目前处于预览状态），且材料可能会更改。</span><span class="sxs-lookup"><span data-stu-id="27a89-114">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="27a89-115">有关详细信息，请访问 [ML.NET 简介](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)。</span><span class="sxs-lookup"><span data-stu-id="27a89-115">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="27a89-116">此教程和相关示例目前使用的是 ML.NET 版本 0.11。</span><span class="sxs-lookup"><span data-stu-id="27a89-116">This tutorial and related sample are currently using **ML.NET version 0.11**.</span></span> <span data-ttu-id="27a89-117">有关详细信息，请参阅 [dotnet/machinelearning GitHub 存储库](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)上的发行说明。</span><span class="sxs-lookup"><span data-stu-id="27a89-117">For more information, see the release notes at the [dotnet/machinelearning github repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

## <a name="github-issue-sample-overview"></a><span data-ttu-id="27a89-118">GitHub 问题示例概述</span><span class="sxs-lookup"><span data-stu-id="27a89-118">GitHub issue sample overview</span></span>

<span data-ttu-id="27a89-119">该示例是使用 ML.NET 来定型模型的控制台应用，该模型对 GitHub 问题的 Area 标签进行分类和预测。</span><span class="sxs-lookup"><span data-stu-id="27a89-119">The sample is a console app that uses ML.NET to train a model that classifies and predicts the Area label for a GitHub issue.</span></span> <span data-ttu-id="27a89-120">它还使用第二个数据集对模型进行评估，以进行质量分析。</span><span class="sxs-lookup"><span data-stu-id="27a89-120">It also evaluates the model with a second dataset for quality analysis.</span></span> <span data-ttu-id="27a89-121">问题数据集来自 dotnet/corefx GitHub 存储库。</span><span class="sxs-lookup"><span data-stu-id="27a89-121">The issue datasets are from the dotnet/corefx GitHub repo.</span></span>

<span data-ttu-id="27a89-122">可以在 [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) 存储库中找到本教程的源代码。</span><span class="sxs-lookup"><span data-stu-id="27a89-122">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="27a89-123">系统必备</span><span class="sxs-lookup"><span data-stu-id="27a89-123">Prerequisites</span></span>

* <span data-ttu-id="27a89-124">安装了“.NET Core 跨平台开发”工作负载的 [Visual Studio 2017 15.6 或更高版本](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)。</span><span class="sxs-lookup"><span data-stu-id="27a89-124">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* <span data-ttu-id="27a89-125">[Github 问题制表符分隔文件 (issues_train.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv)。</span><span class="sxs-lookup"><span data-stu-id="27a89-125">The [Github issues tab separated file (issues_train.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv).</span></span>
* <span data-ttu-id="27a89-126">[Github 问题测试制表符分隔文件 (issues_test.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv)。</span><span class="sxs-lookup"><span data-stu-id="27a89-126">The [Github issues test tab separated file (issues_test.tsv)](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv).</span></span>

## <a name="machine-learning-workflow"></a><span data-ttu-id="27a89-127">机器学习工作流</span><span class="sxs-lookup"><span data-stu-id="27a89-127">Machine learning workflow</span></span>

<span data-ttu-id="27a89-128">本教程后面介绍了机器学习工作流，使该过程能够有序地进行。</span><span class="sxs-lookup"><span data-stu-id="27a89-128">This tutorial follows a machine learning workflow that enables the process to move in an orderly fashion.</span></span>

<span data-ttu-id="27a89-129">工作流阶段如下所示：</span><span class="sxs-lookup"><span data-stu-id="27a89-129">The workflow phases are as follows:</span></span>

1. <span data-ttu-id="27a89-130">**了解问题**</span><span class="sxs-lookup"><span data-stu-id="27a89-130">**Understand the problem**</span></span>
2. <span data-ttu-id="27a89-131">**准备数据**</span><span class="sxs-lookup"><span data-stu-id="27a89-131">**Prepare your data**</span></span>
   * <span data-ttu-id="27a89-132">**加载数据**</span><span class="sxs-lookup"><span data-stu-id="27a89-132">**Load the data**</span></span>
   * <span data-ttu-id="27a89-133">**提取功能（转换数据）**</span><span class="sxs-lookup"><span data-stu-id="27a89-133">**Extract features (Transform your data)**</span></span>
3. <span data-ttu-id="27a89-134">**生成并定型**</span><span class="sxs-lookup"><span data-stu-id="27a89-134">**Build and train**</span></span> 
   * <span data-ttu-id="27a89-135">**定型模型**</span><span class="sxs-lookup"><span data-stu-id="27a89-135">**Train the model**</span></span>
   * <span data-ttu-id="27a89-136">**评估模型**</span><span class="sxs-lookup"><span data-stu-id="27a89-136">**Evaluate the model**</span></span>
4. <span data-ttu-id="27a89-137">**部署模型**</span><span class="sxs-lookup"><span data-stu-id="27a89-137">**Deploy Model**</span></span>
   * <span data-ttu-id="27a89-138">**使用模型来预测**</span><span class="sxs-lookup"><span data-stu-id="27a89-138">**Use the Model to predict**</span></span>

### <a name="understand-the-problem"></a><span data-ttu-id="27a89-139">了解问题</span><span class="sxs-lookup"><span data-stu-id="27a89-139">Understand the problem</span></span>

<span data-ttu-id="27a89-140">首先需要了解问题，因此可以将其分解为能够支持构建和定型模型的几个部分。</span><span class="sxs-lookup"><span data-stu-id="27a89-140">You first need to understand the problem, so you can break it down to parts that can support building and training the model.</span></span> <span data-ttu-id="27a89-141">通过分解问题，可以预测和评估结果。</span><span class="sxs-lookup"><span data-stu-id="27a89-141">Breaking  down the problem allows you to predict and evaluate the results.</span></span>

<span data-ttu-id="27a89-142">本教程旨在探讨传入的 GitHub 问题属于哪个区域，目的是对其进行正确标记，从而确定优先级和进行计划安排。</span><span class="sxs-lookup"><span data-stu-id="27a89-142">The problem for this tutorial is to understand what area incoming GitHub issues belong to in order to label them correctly for prioritization and scheduling.</span></span>

<span data-ttu-id="27a89-143">可将问题划分为以下部分：</span><span class="sxs-lookup"><span data-stu-id="27a89-143">You can break down the problem to the following parts:</span></span>

* <span data-ttu-id="27a89-144">问题标题文本</span><span class="sxs-lookup"><span data-stu-id="27a89-144">the issue title text</span></span>
* <span data-ttu-id="27a89-145">问题说明文本</span><span class="sxs-lookup"><span data-stu-id="27a89-145">the issue description text</span></span>
* <span data-ttu-id="27a89-146">模型定型数据的区域值</span><span class="sxs-lookup"><span data-stu-id="27a89-146">an area value for the model training data</span></span>
* <span data-ttu-id="27a89-147">一个可评估的预测区域值，评估后可在实际操作中使用该值</span><span class="sxs-lookup"><span data-stu-id="27a89-147">a predicted area value that you can evaluate and then use operationally</span></span>

<span data-ttu-id="27a89-148">然后，需要确定区域，并借助此操作选择机器学习任务。</span><span class="sxs-lookup"><span data-stu-id="27a89-148">You then need to **determine** the area, which helps you with the machine learning task selection.</span></span>

## <a name="select-the-appropriate-machine-learning-algorithm"></a><span data-ttu-id="27a89-149">选择适当的机器学习算法</span><span class="sxs-lookup"><span data-stu-id="27a89-149">Select the appropriate machine learning algorithm</span></span>

<span data-ttu-id="27a89-150">通过此问题，你将了解以下情况：</span><span class="sxs-lookup"><span data-stu-id="27a89-150">With this problem, you know the following facts:</span></span>

<span data-ttu-id="27a89-151">定型数据：</span><span class="sxs-lookup"><span data-stu-id="27a89-151">Training data:</span></span>

<span data-ttu-id="27a89-152">可以在几个区域（区域）中标记 GitHub 问题，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="27a89-152">GitHub issues can be labeled in several areas (**Area**) as in the following examples:</span></span>

* <span data-ttu-id="27a89-153">area-System.Numerics</span><span class="sxs-lookup"><span data-stu-id="27a89-153">area-System.Numerics</span></span>
* <span data-ttu-id="27a89-154">area-System.Xml</span><span class="sxs-lookup"><span data-stu-id="27a89-154">area-System.Xml</span></span>
* <span data-ttu-id="27a89-155">area-Infrastructure</span><span class="sxs-lookup"><span data-stu-id="27a89-155">area-Infrastructure</span></span>
* <span data-ttu-id="27a89-156">area-System.Linq</span><span class="sxs-lookup"><span data-stu-id="27a89-156">area-System.Linq</span></span>
* <span data-ttu-id="27a89-157">area-System.IO</span><span class="sxs-lookup"><span data-stu-id="27a89-157">area-System.IO</span></span>

<span data-ttu-id="27a89-158">预测新 GitHub 问题的“区域”，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="27a89-158">Predict the **Area** of a new GitHub Issue such as in the following examples:</span></span>

* <span data-ttu-id="27a89-159">Contract.Assert vs Debug.Assert</span><span class="sxs-lookup"><span data-stu-id="27a89-159">Contract.Assert vs Debug.Assert</span></span>
* <span data-ttu-id="27a89-160">Make fields readonly in System.Xml</span><span class="sxs-lookup"><span data-stu-id="27a89-160">Make fields readonly in System.Xml</span></span>

<span data-ttu-id="27a89-161">分类机器学习算法最适合此方案。</span><span class="sxs-lookup"><span data-stu-id="27a89-161">The classification machine learning algorithm is best suited for this scenario.</span></span>

### <a name="about-the-classification-learning-algorithm"></a><span data-ttu-id="27a89-162">有关分类学习算法</span><span class="sxs-lookup"><span data-stu-id="27a89-162">About the classification learning algorithm</span></span>

<span data-ttu-id="27a89-163">分类是一项机器学习算法，它使用数据来确定某个项或数据行的类别、类型或类。</span><span class="sxs-lookup"><span data-stu-id="27a89-163">Classification is a machine learning algorithm that uses data to **determine** the category, type, or class of an item or row of data.</span></span> <span data-ttu-id="27a89-164">例如，可以使用分类：</span><span class="sxs-lookup"><span data-stu-id="27a89-164">For example, you can use classification to:</span></span>

* <span data-ttu-id="27a89-165">识别情绪为正面还是负面。</span><span class="sxs-lookup"><span data-stu-id="27a89-165">Identify sentiment as positive or negative.</span></span>
* <span data-ttu-id="27a89-166">将电子邮件分类为垃圾邮件或正常邮件。</span><span class="sxs-lookup"><span data-stu-id="27a89-166">Classify email as spam, junk, or good.</span></span>
* <span data-ttu-id="27a89-167">确定患者的实验室样本是否癌变。</span><span class="sxs-lookup"><span data-stu-id="27a89-167">Determine whether a patient's lab sample is cancerous.</span></span>
* <span data-ttu-id="27a89-168">根据客户对销售活动的反应倾向对客户进行分类。</span><span class="sxs-lookup"><span data-stu-id="27a89-168">Categorize customers by their propensity to respond to a sales campaign.</span></span>

<span data-ttu-id="27a89-169">分类学习算法用例通常为以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="27a89-169">Classification learning algorithm use cases are frequently one of the following types:</span></span>

* <span data-ttu-id="27a89-170">二元：A 或 B。</span><span class="sxs-lookup"><span data-stu-id="27a89-170">Binary: either A or B.</span></span>
* <span data-ttu-id="27a89-171">多类：可以通过使用单个模型来预测多个类别。</span><span class="sxs-lookup"><span data-stu-id="27a89-171">Multiclass: multiple categories that can be predicted by using a single model.</span></span>

<span data-ttu-id="27a89-172">对于此类问题，请使用多类分类学习算法，因为你的问题类别预测可能是多个类别（多类）而不是仅两个（二元）中的一个。</span><span class="sxs-lookup"><span data-stu-id="27a89-172">For this type of problem, use a Multiclass classification learning algorithm, since your issue category prediction can be one of multiple categories (multiclass) rather than just two (binary).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="27a89-173">创建控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="27a89-173">Create a console application</span></span>

### <a name="create-a-project"></a><span data-ttu-id="27a89-174">创建项目</span><span class="sxs-lookup"><span data-stu-id="27a89-174">Create a project</span></span>

1. <span data-ttu-id="27a89-175">打开 Visual Studio 2017。</span><span class="sxs-lookup"><span data-stu-id="27a89-175">Open Visual Studio 2017.</span></span> <span data-ttu-id="27a89-176">从菜单栏中选择“文件” > “新建” > “项目”。</span><span class="sxs-lookup"><span data-stu-id="27a89-176">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="27a89-177">在“新项目”对话框中，依次选择“Visual C#”和“.NET Core”节点。</span><span class="sxs-lookup"><span data-stu-id="27a89-177">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="27a89-178">然后，选择“控制台应用程序(.NET Core)”项目模板。</span><span class="sxs-lookup"><span data-stu-id="27a89-178">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="27a89-179">在“名称”文本框中，键入“GitHubIssueClassification”，然后选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="27a89-179">In the **Name** text box, type "GitHubIssueClassification" and then select the **OK** button.</span></span>

2. <span data-ttu-id="27a89-180">在项目中创建一个名为“数据”的目录来保存数据集文件：</span><span class="sxs-lookup"><span data-stu-id="27a89-180">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="27a89-181">在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新文件夹”。</span><span class="sxs-lookup"><span data-stu-id="27a89-181">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="27a89-182">键入“Data”，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="27a89-182">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="27a89-183">在项目中创建一个名为“模型”的目录来保存模型：</span><span class="sxs-lookup"><span data-stu-id="27a89-183">Create a directory named *Models* in your project to save your model:</span></span>

    <span data-ttu-id="27a89-184">在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新文件夹”。</span><span class="sxs-lookup"><span data-stu-id="27a89-184">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="27a89-185">键入“模型”，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="27a89-185">Type "Models" and hit Enter.</span></span>

4. <span data-ttu-id="27a89-186">安装“Microsoft.ML NuGet 包”：</span><span class="sxs-lookup"><span data-stu-id="27a89-186">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="27a89-187">在“解决方案资源管理器”中，右键单击项目，然后选择“管理 NuGet 包”。</span><span class="sxs-lookup"><span data-stu-id="27a89-187">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="27a89-188">将“nuget.org”选择为“包源”，选择“浏览”选项卡并搜索“Microsoft.ML”，在列表中选择该包，然后选择“安装”按钮。</span><span class="sxs-lookup"><span data-stu-id="27a89-188">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="27a89-189">选择“预览更改”对话框上的“确定”按钮，如果你同意所列包的许可条款，则选择“接受许可”对话框上的“我接受”按钮。</span><span class="sxs-lookup"><span data-stu-id="27a89-189">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="27a89-190">准备数据</span><span class="sxs-lookup"><span data-stu-id="27a89-190">Prepare your data</span></span>

1. <span data-ttu-id="27a89-191">下载 [issues_train.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv) 和 [issues_test.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv) 数据集，并将它们保存到先前创建的“数据”文件夹。</span><span class="sxs-lookup"><span data-stu-id="27a89-191">Download the [issues_train.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_train.tsv) and the [issues_test.tsv](https://raw.githubusercontent.com/dotnet/samples/master/machine-learning/tutorials/GitHubIssueClassification/Data/issues_test.tsv) data sets and save them to the *Data* folder previously created.</span></span> <span data-ttu-id="27a89-192">第一个数据集定型机器学习模型，第二个数据集可用来评估模型的准确度。</span><span class="sxs-lookup"><span data-stu-id="27a89-192">The first dataset trains the machine learning model and the second can be used to evaluate how accurate your model is.</span></span>

2. <span data-ttu-id="27a89-193">在“解决方案资源管理器”中，右键单击每个 \*.tsv 文件，然后选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="27a89-193">In Solution Explorer, right-click each of the \*.tsv files and select **Properties**.</span></span> <span data-ttu-id="27a89-194">在“高级”下，将“复制到输出目录”的值更改为“如果较新则复制”。</span><span class="sxs-lookup"><span data-stu-id="27a89-194">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="27a89-195">创建类和定义路径</span><span class="sxs-lookup"><span data-stu-id="27a89-195">Create classes and define paths</span></span>

<span data-ttu-id="27a89-196">将以下附加的 `using` 语句添加到“Program.cs”文件顶部：</span><span class="sxs-lookup"><span data-stu-id="27a89-196">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddUsings)]

<span data-ttu-id="27a89-197">创建 3 个全局字段，来保存最近下载的文件路径以及 `MLContext`、`DataView`、`PredictionEngine` 和 `TextLoader` 的全局变量：</span><span class="sxs-lookup"><span data-stu-id="27a89-197">Create three global fields to hold the paths to the recently downloaded files, and global variables for the `MLContext`,`DataView`, `PredictionEngine`, and `TextLoader`:</span></span>

* <span data-ttu-id="27a89-198">`_trainDataPath` 具有用于定型模型的数据集路径。</span><span class="sxs-lookup"><span data-stu-id="27a89-198">`_trainDataPath` has the path to the dataset used to train the model.</span></span>
* <span data-ttu-id="27a89-199">`_testDataPath` 具有用于评估模型的数据集路径。</span><span class="sxs-lookup"><span data-stu-id="27a89-199">`_testDataPath` has the path to the dataset used to evaluate the model.</span></span>
* <span data-ttu-id="27a89-200">`_modelPath` 具有在其中保存定型模型的路径。</span><span class="sxs-lookup"><span data-stu-id="27a89-200">`_modelPath` has the path where the trained model is saved.</span></span>
* <span data-ttu-id="27a89-201">`_mlContext` 是用于提供处理上下文的 <xref:Microsoft.ML.MLContext>。</span><span class="sxs-lookup"><span data-stu-id="27a89-201">`_mlContext` is the <xref:Microsoft.ML.MLContext> that provides processing context.</span></span>
* <span data-ttu-id="27a89-202">`_trainingDataView` 是用于处理定型数据集的 <xref:Microsoft.Data.DataView.IDataView>。</span><span class="sxs-lookup"><span data-stu-id="27a89-202">`_trainingDataView` is the <xref:Microsoft.Data.DataView.IDataView> used to process the training dataset.</span></span>
* <span data-ttu-id="27a89-203">`_predEngine` 是用于单个预测的 <xref:Microsoft.ML.PredictionEngine%602>。</span><span class="sxs-lookup"><span data-stu-id="27a89-203">`_predEngine` is the <xref:Microsoft.ML.PredictionEngine%602> used for single predictions.</span></span>
* <span data-ttu-id="27a89-204">`_reader` 是用于加载和转换数据集的 <xref:Microsoft.ML.Data.TextLoader>。</span><span class="sxs-lookup"><span data-stu-id="27a89-204">`_reader` is the <xref:Microsoft.ML.Data.TextLoader> used to load and transform the datasets.</span></span>

<span data-ttu-id="27a89-205">将以下代码添加到 `Main` 方法正上方的行中以指定这些路径和其他变量：</span><span class="sxs-lookup"><span data-stu-id="27a89-205">Add the following code to the line right above the `Main` method to specify those paths and the other variables:</span></span>

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DeclareGlobalVariables)]

<span data-ttu-id="27a89-206">为输入数据和预测创建一些类。</span><span class="sxs-lookup"><span data-stu-id="27a89-206">Create some classes for your input data and predictions.</span></span> <span data-ttu-id="27a89-207">向项目添加一个新类：</span><span class="sxs-lookup"><span data-stu-id="27a89-207">Add a new class to your project:</span></span>

1. <span data-ttu-id="27a89-208">在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新项”。</span><span class="sxs-lookup"><span data-stu-id="27a89-208">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="27a89-209">在“添加新项”对话框中，选择“类”并将“名称”字段更改为“GitHubIssueData.cs”。</span><span class="sxs-lookup"><span data-stu-id="27a89-209">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *GitHubIssueData.cs*.</span></span> <span data-ttu-id="27a89-210">然后，选择“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="27a89-210">Then, select the **Add** button.</span></span>

    <span data-ttu-id="27a89-211">“GitHubIssueData.cs”文件随即在代码编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="27a89-211">The *GitHubIssueData.cs* file opens in the code editor.</span></span> <span data-ttu-id="27a89-212">将下面的 `using` 语句添加到 GitHubIssueData.cs 的顶部：</span><span class="sxs-lookup"><span data-stu-id="27a89-212">Add the following `using` statement to the top of *GitHubIssueData.cs*:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/GitHubIssueClassification/GitHubIssueData.cs#AddUsings)]

<span data-ttu-id="27a89-213">删除现有类定义并向“GitHubIssueData.cs”文件添加以下代码，其中有两个类 `GitHubIssue` 和 `IssuePrediction`：</span><span class="sxs-lookup"><span data-stu-id="27a89-213">Remove the existing class definition and add the following code, which has two classes `GitHubIssue` and `IssuePrediction`, to the *GitHubIssueData.cs* file:</span></span>

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/GitHubIssueClassification/GitHubIssueData.cs#DeclareTypes)]

<span data-ttu-id="27a89-214">`GitHubIssue` 是输入数据集类，具有以下 <xref:System.String> 字段：</span><span class="sxs-lookup"><span data-stu-id="27a89-214">`GitHubIssue` is the input dataset class and has the following <xref:System.String> fields:</span></span>

* <span data-ttu-id="27a89-215">`ID` 包含 GitHub 问题 ID 的值</span><span class="sxs-lookup"><span data-stu-id="27a89-215">`ID` contains a value for the GitHub issue ID</span></span>
* <span data-ttu-id="27a89-216">`Area` 包含 `Area` 标签的值</span><span class="sxs-lookup"><span data-stu-id="27a89-216">`Area` contains a value for the `Area` label</span></span>
* <span data-ttu-id="27a89-217">`Title` 包含 GitHub 问题标题</span><span class="sxs-lookup"><span data-stu-id="27a89-217">`Title` contains the GitHub issue title</span></span>
* <span data-ttu-id="27a89-218">`Description` 包含 GitHub 问题说明</span><span class="sxs-lookup"><span data-stu-id="27a89-218">`Description` contains the GitHub issue description</span></span>

<span data-ttu-id="27a89-219">`IssuePrediction` 是在定型模型后用于预测的类。</span><span class="sxs-lookup"><span data-stu-id="27a89-219">`IssuePrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="27a89-220">它有一个 `string` (`Area`) 和一个 `PredictedLabel` `ColumnName` 属性。</span><span class="sxs-lookup"><span data-stu-id="27a89-220">It has a single `string` (`Area`) and a `PredictedLabel` `ColumnName` attribute.</span></span> <span data-ttu-id="27a89-221">`Label` 用于创建和定型模型，并且与第二个数据集结合使用来评估模型。</span><span class="sxs-lookup"><span data-stu-id="27a89-221">The `Label` is used to create and train the model, and it's also used with a second dataset to evaluate the model.</span></span> <span data-ttu-id="27a89-222">`PredictedLabel` 在预测和评估过程中使用。</span><span class="sxs-lookup"><span data-stu-id="27a89-222">The `PredictedLabel` is used during prediction and evaluation.</span></span> <span data-ttu-id="27a89-223">对于计算，将使用带定型数据的输入、预测值和模型。</span><span class="sxs-lookup"><span data-stu-id="27a89-223">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="27a89-224">使用 ML.NET 构建模型时，首先要创建一个 <xref:Microsoft.ML.MLContext>。</span><span class="sxs-lookup"><span data-stu-id="27a89-224">When building a model with ML.NET, you start by creating an <xref:Microsoft.ML.MLContext>.</span></span> <span data-ttu-id="27a89-225">`MLContext` 在概念上相当于在实体框架中使用 `DbContext`。</span><span class="sxs-lookup"><span data-stu-id="27a89-225">`MLContext` is comparable conceptually to using `DbContext` in Entity Framework.</span></span> <span data-ttu-id="27a89-226">该环境为 ML 作业提供一个上下文，可以用于异常情况跟踪和日志记录。</span><span class="sxs-lookup"><span data-stu-id="27a89-226">The environment provides a context for your ML job that can be used for exception tracking and logging.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="27a89-227">在 Main 中初始化变量</span><span class="sxs-lookup"><span data-stu-id="27a89-227">Initialize variables in Main</span></span>

<span data-ttu-id="27a89-228">使用具有随机种子 (`seed: 0`) 的新实例 `MLContext` 初始化 `_mlContext` 全局变量，以获得跨多个定型的可重复/确定性结果。</span><span class="sxs-lookup"><span data-stu-id="27a89-228">Initialize the `_mlContext` global variable  with a new instance of `MLContext` with a random seed (`seed: 0`) for repeatable/deterministic results across multiple trainings.</span></span>  <span data-ttu-id="27a89-229">用下面 `Main` 方法中的代码替换 `Console.WriteLine("Hello World!")` 行：</span><span class="sxs-lookup"><span data-stu-id="27a89-229">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreateMLContext)]

## <a name="load-the-data"></a><span data-ttu-id="27a89-230">加载数据</span><span class="sxs-lookup"><span data-stu-id="27a89-230">Load the data</span></span>

<span data-ttu-id="27a89-231">接下来，初始化 `_trainingDataView` <xref:Microsoft.Data.DataView.IDataView> 全局变量并使用 `_trainDataPath` 参数加载数据。</span><span class="sxs-lookup"><span data-stu-id="27a89-231">Next, initialize the `_trainingDataView` <xref:Microsoft.Data.DataView.IDataView> global variable and load the data with the `_trainDataPath` parameter.</span></span>

 <span data-ttu-id="27a89-232">作为 [`Transforms`](../basic-concepts-model-training-in-mldotnet.md#transformer) 的输入和输出，`DataView` 是基本的数据管道类型，与 `LINQ` 中的 `IEnumerable` 类似。</span><span class="sxs-lookup"><span data-stu-id="27a89-232">As the input and output of [`Transforms`](../basic-concepts-model-training-in-mldotnet.md#transformer), a `DataView` is the fundamental data pipeline type, comparable to `IEnumerable` for `LINQ`.</span></span>

<span data-ttu-id="27a89-233">在 ML.NET 中，数据类似于 `SQL view`。</span><span class="sxs-lookup"><span data-stu-id="27a89-233">In ML.NET, data is similar to a `SQL view`.</span></span> <span data-ttu-id="27a89-234">它是异源数据，会延迟计算并进行架构化。</span><span class="sxs-lookup"><span data-stu-id="27a89-234">It is lazily evaluated, schematized, and heterogenous.</span></span> <span data-ttu-id="27a89-235">该对象是管道的第一部分，并加载数据。</span><span class="sxs-lookup"><span data-stu-id="27a89-235">The object is the first part of the pipeline, and loads the data.</span></span> <span data-ttu-id="27a89-236">在本教程中，它会加载一个包含问题标题、说明和相应区域 GitHub 标签的数据集。</span><span class="sxs-lookup"><span data-stu-id="27a89-236">For this tutorial, it loads a dataset with issue titles, descriptions, and corresponding area GitHub label.</span></span> <span data-ttu-id="27a89-237">`DataView` 用于创建和定型模型。</span><span class="sxs-lookup"><span data-stu-id="27a89-237">The `DataView` is used to create and train the model.</span></span>

<span data-ttu-id="27a89-238">由于先前创建的 `GitHubIssue` 数据模型类型与数据集架构相匹配，因此可以将初始化、映射和数据集加载合并到一行代码中。</span><span class="sxs-lookup"><span data-stu-id="27a89-238">Since your previously created `GitHubIssue` data model type matches the dataset schema, you can combine the initialization, mapping, and dataset loading into one line of code.</span></span>

<span data-ttu-id="27a89-239">使用 [LoadFromTextFile 方法](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29)的 `MLContext.Data.LoadFromTextFile` 包装器加载数据。</span><span class="sxs-lookup"><span data-stu-id="27a89-239">Load the data using the `MLContext.Data.LoadFromTextFile` wrapper for the [LoadFromTextFile method](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29).</span></span> <span data-ttu-id="27a89-240">它返回 <xref:Microsoft.Data.DataView.IDataView>，此接口通过 `GitHubIssue` 数据模型类型推断数据集架构，并使用数据集标头。</span><span class="sxs-lookup"><span data-stu-id="27a89-240">It returns a <xref:Microsoft.Data.DataView.IDataView> which infers the dataset schema from the `GitHubIssue` data model type and uses the dataset header.</span></span> 

<span data-ttu-id="27a89-241">之前在创建 `GitHubIssue` 类时定义了数据模式。</span><span class="sxs-lookup"><span data-stu-id="27a89-241">You defined the data schema previously when you created the `GitHubIssue` class.</span></span> <span data-ttu-id="27a89-242">对于架构：</span><span class="sxs-lookup"><span data-stu-id="27a89-242">For your schema:</span></span>

* <span data-ttu-id="27a89-243">第一列 `ID`（GitHub 问题 ID）</span><span class="sxs-lookup"><span data-stu-id="27a89-243">the first column `ID` (GitHub Issue ID)</span></span>
* <span data-ttu-id="27a89-244">第二列 `Area`（定型预测）</span><span class="sxs-lookup"><span data-stu-id="27a89-244">the second column `Area` (the prediction for training)</span></span>
* <span data-ttu-id="27a89-245">第三列 `Title`（GitHub 问题标题）是用于预测 `Area` 的第一个[特征](../resources/glossary.md##feature)</span><span class="sxs-lookup"><span data-stu-id="27a89-245">the third column `Title` (GitHub issue title) is the first [feature](../resources/glossary.md##feature)  used for predicting the `Area`</span></span>
* <span data-ttu-id="27a89-246">第四列 `Description` 是用于预测 `Area` 的第二个特征</span><span class="sxs-lookup"><span data-stu-id="27a89-246">the fourth column  `Description` is the second feature used for predicting the `Area`</span></span>

<span data-ttu-id="27a89-247">要初始化并加载 `_trainingDataView` 全局变量以将其用于管道，请在 `mlContext` 初始化后添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="27a89-247">To initialize and load the `_trainingDataView` global variable in order to use it for the pipeline, add the following code after the  `mlContext` initialization:</span></span>

[!code-csharp[LoadTrainData](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadTrainData)]

<span data-ttu-id="27a89-248">将以下代码作为下一行代码添加到 `Main` 方法中：</span><span class="sxs-lookup"><span data-stu-id="27a89-248">Add the following as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallProcessData](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallProcessData)]

<span data-ttu-id="27a89-249">`ProcessData` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="27a89-249">The `ProcessData` method executes the following tasks:</span></span>

* <span data-ttu-id="27a89-250">提取并转换数据。</span><span class="sxs-lookup"><span data-stu-id="27a89-250">Extracts and transforms the data.</span></span>
* <span data-ttu-id="27a89-251">返回处理管道。</span><span class="sxs-lookup"><span data-stu-id="27a89-251">Returns the processing pipeline.</span></span>

<span data-ttu-id="27a89-252">使用下面的代码紧随 `Main` 方法后创建 `ProcessData` 方法：</span><span class="sxs-lookup"><span data-stu-id="27a89-252">Create the `ProcessData` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static IEstimator<ITransformer> ProcessData()
{

}
```

## <a name="extract-features-and-transform-the-data"></a><span data-ttu-id="27a89-253">提取功能和转换数据</span><span class="sxs-lookup"><span data-stu-id="27a89-253">Extract Features and transform the data</span></span>

<span data-ttu-id="27a89-254">预处理和清除数据任务至关重要，需要首先执行才能将数据集有效地用于机器学习。</span><span class="sxs-lookup"><span data-stu-id="27a89-254">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span> <span data-ttu-id="27a89-255">原始数据通常嘈杂不可靠，并且可能缺少值。</span><span class="sxs-lookup"><span data-stu-id="27a89-255">Raw data is often noisy and unreliable, and may be missing values.</span></span> <span data-ttu-id="27a89-256">在没有这些建模任务的情况下使用数据会产生误导性结果。</span><span class="sxs-lookup"><span data-stu-id="27a89-256">Using data without these modeling tasks can produce misleading results.</span></span>

<span data-ttu-id="27a89-257">ML.NET 的转换管道撰写一组自定义 `transforms` 集，要在定型或测试数据之前将其应用到数据。</span><span class="sxs-lookup"><span data-stu-id="27a89-257">ML.NET's transform pipelines compose a custom `transforms`set that is applied to your data before training or testing.</span></span> <span data-ttu-id="27a89-258">转换的主要目的是为了[特征化](../resources/glossary.md#feature-engineering)数据。</span><span class="sxs-lookup"><span data-stu-id="27a89-258">The transforms' primary purpose is data [featurization](../resources/glossary.md#feature-engineering).</span></span> <span data-ttu-id="27a89-259">机器学习算法理解[特征化](../resources/glossary.md#feature)数据，因此下一步是将文本数据转换为 ML 算法识别的格式。</span><span class="sxs-lookup"><span data-stu-id="27a89-259">Machine learning algorithms understand [featurized](../resources/glossary.md#feature) data, so the next step is to transform our textual data into a format that our ML algorithms recognize.</span></span> <span data-ttu-id="27a89-260">该格式是[数值向量](../resources/glossary.md#numerical-feature-vector)。</span><span class="sxs-lookup"><span data-stu-id="27a89-260">That format is a [numeric vector](../resources/glossary.md#numerical-feature-vector).</span></span>

<span data-ttu-id="27a89-261">在后续步骤中，按 `GitHubIssue` 类中定义的名称引用列。</span><span class="sxs-lookup"><span data-stu-id="27a89-261">In the next steps, we refer to the columns by the names defined in the `GitHubIssue` class.</span></span>

<span data-ttu-id="27a89-262">定型和评估模型时，默认情况下，将“标签”列中的值视为要预测的正确值。</span><span class="sxs-lookup"><span data-stu-id="27a89-262">When the model is trained and evaluated, by default, the values in the **Label** column are considered as correct values to be predicted.</span></span> <span data-ttu-id="27a89-263">由于要预测 `GitHubIssue` 的区域 GitHub 标签，所以将 `Area` 列复制到“标签”列。</span><span class="sxs-lookup"><span data-stu-id="27a89-263">As we want to predict the Area GitHub label for a `GitHubIssue`, copy the `Area` column into the **Label** column.</span></span> <span data-ttu-id="27a89-264">为此，请使用 `MLContext.Transforms.Conversion.MapValueToKey`，它是 <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A> 转换类的包装器。</span><span class="sxs-lookup"><span data-stu-id="27a89-264">To do that, use the `MLContext.Transforms.Conversion.MapValueToKey`, which is a wrapper for the <xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A> transformation class.</span></span>  <span data-ttu-id="27a89-265">`MapValueToKey` 返回实际上是管道的 <xref:Microsoft.ML.Data.EstimatorChain%601>。</span><span class="sxs-lookup"><span data-stu-id="27a89-265">The `MapValueToKey` returns an <xref:Microsoft.ML.Data.EstimatorChain%601> that will effectively be a pipeline.</span></span> <span data-ttu-id="27a89-266">命名此 `pipeline`，因为你将把定型程序附加到 `EstimatorChain`。</span><span class="sxs-lookup"><span data-stu-id="27a89-266">Name this `pipeline` as you will then append the trainer to the `EstimatorChain`.</span></span> <span data-ttu-id="27a89-267">添加下一个代码行：</span><span class="sxs-lookup"><span data-stu-id="27a89-267">Add the next line of code:</span></span>

[!code-csharp[MapValueToKey](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#MapValueToKey)]

 <span data-ttu-id="27a89-268">特征化将不同的数字键值分配给每列的不同值，供机器学习算法使用。</span><span class="sxs-lookup"><span data-stu-id="27a89-268">Featurizing assigns different numeric key values to the different values in each of the columns and is used by the machine learning algorithm.</span></span> <span data-ttu-id="27a89-269">接下来，调用 `mlContext.Transforms.Text.FeaturizeText`，它将文本（`Title` 和 `Description`）列特征化为每个名为 `TitleFeaturized` 和 `DescriptionFeaturized` 的值的数字向量。</span><span class="sxs-lookup"><span data-stu-id="27a89-269">Next, call `mlContext.Transforms.Text.FeaturizeText` which featurizes the text (`Title` and `Description`) columns into a numeric vector for each called `TitleFeaturized` and `DescriptionFeaturized`.</span></span> <span data-ttu-id="27a89-270">使用以下代码将两列的特征化附加到管道：</span><span class="sxs-lookup"><span data-stu-id="27a89-270">Append the featurization for both columns to the pipeline with the following code:</span></span>

[!code-csharp[FeaturizeText](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#FeaturizeText)]

>[!WARNING]
> <span data-ttu-id="27a89-271">ML.NET 版本 0.10 已更改转换参数的顺序。</span><span class="sxs-lookup"><span data-stu-id="27a89-271">ML.NET Version 0.10 has changed the order of the Transform parameters.</span></span> <span data-ttu-id="27a89-272">这在你构建之前不会错误输出。</span><span class="sxs-lookup"><span data-stu-id="27a89-272">This will not error out until you build.</span></span> <span data-ttu-id="27a89-273">使用用于转换的参数名称，如前面的代码片段中所示。</span><span class="sxs-lookup"><span data-stu-id="27a89-273">Use the parameter names for Transforms as illustrated in the previous code snippet.</span></span>

<span data-ttu-id="27a89-274">数据准备最后一步使用 `Concatenate` 转换类将所有功能列合并到“功能”列。</span><span class="sxs-lookup"><span data-stu-id="27a89-274">The last step in data preparation combines all of the feature columns into the **Features** column using the `Concatenate` transformation class.</span></span> <span data-ttu-id="27a89-275">默认情况下，学习算法仅处理“特征”列的特征。</span><span class="sxs-lookup"><span data-stu-id="27a89-275">By default, a learning algorithm processes only features from the **Features** column.</span></span> <span data-ttu-id="27a89-276">使用以下代码将此转换附加到管道：</span><span class="sxs-lookup"><span data-stu-id="27a89-276">Append this transformation to the pipeline with the following code:</span></span>

[!code-csharp[Concatenate](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Concatenate)]

 <span data-ttu-id="27a89-277">接下来，附加一个 <xref:Microsoft.ML.Data.EstimatorChain%601.AppendCacheCheckpoint%2A> 来缓存数据视图，以便在使用缓存多次循环访问数据时获得更好的性能，如下面的代码所示：</span><span class="sxs-lookup"><span data-stu-id="27a89-277">Next, append a <xref:Microsoft.ML.Data.EstimatorChain%601.AppendCacheCheckpoint%2A> to cache the DataView so when you iterate over the data multiple times using the cache might get better performance, as with the following code:</span></span>

[!code-csharp[AppendCache](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AppendCache)]

> [!WARNING]
> <span data-ttu-id="27a89-278">对小/中型数据集使用 AppendCacheCheckpoint 可以降低训练时间。</span><span class="sxs-lookup"><span data-stu-id="27a89-278">Use AppendCacheCheckpoint for small/medium datasets to lower training time.</span></span> <span data-ttu-id="27a89-279">在处理大型数据集时不使用它（删除 .AppendCacheCheckpoint()）。</span><span class="sxs-lookup"><span data-stu-id="27a89-279">Do NOT use it (remove .AppendCacheCheckpoint()) when handling very large datasets.</span></span>

<span data-ttu-id="27a89-280">在 `ProcessData` 方法的末尾返回管道。</span><span class="sxs-lookup"><span data-stu-id="27a89-280">Return the pipeline at the end of the `ProcessData` method.</span></span>

[!code-csharp[ReturnPipeline](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#ReturnPipeline)]

<span data-ttu-id="27a89-281">此步骤处理预处理/特征化。</span><span class="sxs-lookup"><span data-stu-id="27a89-281">This step handles preprocessing/featurization.</span></span> <span data-ttu-id="27a89-282">使用 ML.NET 中可用的其他组件可以在使用模型时生成更佳结果。</span><span class="sxs-lookup"><span data-stu-id="27a89-282">Using additional components available in ML.NET can enable better results with your model.</span></span>

## <a name="build-and-train-the-model"></a><span data-ttu-id="27a89-283">生成和定型模型</span><span class="sxs-lookup"><span data-stu-id="27a89-283">Build and train the model</span></span>

<span data-ttu-id="27a89-284">将以下调用添加到 `BuildAndTrainModel` 方法作为 `Main` 方法的下一行代码：</span><span class="sxs-lookup"><span data-stu-id="27a89-284">Add the following call to the `BuildAndTrainModel`method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallBuildAndTrainModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallBuildAndTrainModel)]

<span data-ttu-id="27a89-285">`BuildAndTrainModel` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="27a89-285">The `BuildAndTrainModel` method executes the following tasks:</span></span>

* <span data-ttu-id="27a89-286">创建定型算法类。</span><span class="sxs-lookup"><span data-stu-id="27a89-286">Creates the training algorithm class.</span></span>
* <span data-ttu-id="27a89-287">定型模型。</span><span class="sxs-lookup"><span data-stu-id="27a89-287">Trains the model.</span></span>
* <span data-ttu-id="27a89-288">根据定型数据预测区域。</span><span class="sxs-lookup"><span data-stu-id="27a89-288">Predicts area based on training data.</span></span>
* <span data-ttu-id="27a89-289">将模型保存到 `.zip` 文件。</span><span class="sxs-lookup"><span data-stu-id="27a89-289">Saves the model to a `.zip` file.</span></span>
* <span data-ttu-id="27a89-290">返回模型。</span><span class="sxs-lookup"><span data-stu-id="27a89-290">Returns the model.</span></span>

<span data-ttu-id="27a89-291">使用下面的代码紧随 `Main` 方法后创建 `BuildAndTrainModel` 方法：</span><span class="sxs-lookup"><span data-stu-id="27a89-291">Create the `BuildAndTrainModel` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static IEstimator<ITransformer> BuildAndTrainModel(IDataView trainingDataView, IEstimator<ITransformer> pipeline)
{

}
```

<span data-ttu-id="27a89-292">请注意，两个参数传递到 BuildAndTrainModel 方法；用于定性数据集 (`trainingDataView`) 的 `IDataView`，用于 ProcessData (`pipeline`) 中创建的处理管道的 <xref:Microsoft.ML.Data.EstimatorChain%601>。</span><span class="sxs-lookup"><span data-stu-id="27a89-292">Notice that two parameters are passed into the BuildAndTrainModel method; an `IDataView` for the training dataset (`trainingDataView`), and a <xref:Microsoft.ML.Data.EstimatorChain%601> for the processing pipeline created in ProcessData (`pipeline`).</span></span>

 <span data-ttu-id="27a89-293">将以下代码添加为 `BuildAndTrainModel` 方法的首行：</span><span class="sxs-lookup"><span data-stu-id="27a89-293">Add the following code as the first line of the `BuildAndTrainModel` method:</span></span>

### <a name="choose-a-learning-algorithm"></a><span data-ttu-id="27a89-294">选择学习算法</span><span class="sxs-lookup"><span data-stu-id="27a89-294">Choose a learning algorithm</span></span>

<span data-ttu-id="27a89-295">要添加学习算法，请调用返回 <xref:Microsoft.ML.Trainers.SdcaMultiClassTrainer> 对象的 `mlContext.MulticlassClassification.Trainers.StochasticDualCoordinateAscent` 包装器方法。</span><span class="sxs-lookup"><span data-stu-id="27a89-295">To add the learning algorithm, call the `mlContext.MulticlassClassification.Trainers.StochasticDualCoordinateAscent` wrapper method which returns a <xref:Microsoft.ML.Trainers.SdcaMultiClassTrainer> object.</span></span>  <span data-ttu-id="27a89-296">`SdcaMultiClassTrainer` 追加到 `pipeline` 并接受特征化的 `Title` 和 `Description` (`Features`) 以及 `Label` 输入参数，以便从历史数据中学习。</span><span class="sxs-lookup"><span data-stu-id="27a89-296">The `SdcaMultiClassTrainer` is appended to the `pipeline` and accepts the featurized `Title` and `Description` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span> <span data-ttu-id="27a89-297">还需要将标签映射到值以返回其原始可读状态。</span><span class="sxs-lookup"><span data-stu-id="27a89-297">You also need to map the label to the value to return to its original readable state.</span></span> <span data-ttu-id="27a89-298">使用以下代码执行这两个操作：</span><span class="sxs-lookup"><span data-stu-id="27a89-298">Do both of those actions with the following code:</span></span>

[!code-csharp[AddTrainer](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddTrainer)]

### <a name="train-the-model"></a><span data-ttu-id="27a89-299">定型模型</span><span class="sxs-lookup"><span data-stu-id="27a89-299">Train the model</span></span>

<span data-ttu-id="27a89-300">根据已加载和转换的数据集定型模型 <xref:Microsoft.ML.Data.TransformerChain%601>。</span><span class="sxs-lookup"><span data-stu-id="27a89-300">You train the model, <xref:Microsoft.ML.Data.TransformerChain%601>, based on the dataset that has been loaded and transformed.</span></span> <span data-ttu-id="27a89-301">一旦定义了估算器，将使用 <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> 定型模型，同时提供已经加载的定型数据。</span><span class="sxs-lookup"><span data-stu-id="27a89-301">Once the estimator has been defined, you train your model using the <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> while providing the already loaded training data.</span></span> <span data-ttu-id="27a89-302">此方法会返回要用于预测的模型。</span><span class="sxs-lookup"><span data-stu-id="27a89-302">This  method returns a model to use for predictions.</span></span> <span data-ttu-id="27a89-303">`trainingPipeline.Fit()` 定型管道，并返回基于传入的 `DataView` 的 `Transformer`。</span><span class="sxs-lookup"><span data-stu-id="27a89-303">`trainingPipeline.Fit()` trains the pipeline and returns a `Transformer` based on the `DataView` passed in.</span></span> <span data-ttu-id="27a89-304">在 `.Fit()` 方法运行之前不会执行此试验。</span><span class="sxs-lookup"><span data-stu-id="27a89-304">The experiment is not executed until the `.Fit()` method runs.</span></span>

<span data-ttu-id="27a89-305">将以下代码添加到 `BuildAndTrainModel` 方法中：</span><span class="sxs-lookup"><span data-stu-id="27a89-305">Add the following code to the `BuildAndTrainModel` method:</span></span>

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#TrainModel)]

<span data-ttu-id="27a89-306">虽然 `model` 是对多行数据进行操作的 `transformer`，但常见的生产场景是需要对单个示例进行预测。</span><span class="sxs-lookup"><span data-stu-id="27a89-306">While the `model` is a `transformer` that operates on many rows of data, a need for predictions on individual examples is a common production scenario.</span></span> <span data-ttu-id="27a89-307"><xref:Microsoft.ML.PredictionEngine%602> 是从 `CreatePredictionEngine` 方法返回的包装器。</span><span class="sxs-lookup"><span data-stu-id="27a89-307">The <xref:Microsoft.ML.PredictionEngine%602> is a wrapper that is returned from the `CreatePredictionEngine` method.</span></span> <span data-ttu-id="27a89-308">让我们添加以下代码来创建 `PredictionEngine`，作为 `BuildAndTrainModel` 方法中的下一行：</span><span class="sxs-lookup"><span data-stu-id="27a89-308">Let's add the following code to create the `PredictionEngine` as the next line in the `BuildAndTrainModel` Method:</span></span>

[!code-csharp[CreatePredictionEngine1](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine1)]

### <a name="predict-with-the-trained-model"></a><span data-ttu-id="27a89-309">使用训练的模型预测</span><span class="sxs-lookup"><span data-stu-id="27a89-309">Predict with the trained model</span></span>

<span data-ttu-id="27a89-310">通过创建一个 `GitHubIssue` 实例，在 `Predict` 方法中添加一个 GitHub 问题来测试定型模型的预测：</span><span class="sxs-lookup"><span data-stu-id="27a89-310">Add a GitHub issue to test the trained model's prediction in the `Predict` method by creating an instance of `GitHubIssue`:</span></span>

[!code-csharp[CreateTestIssue1](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreateTestIssue1)]

<span data-ttu-id="27a89-311">可以使用它来预测问题数据的单个实例的 `Area` 标签。</span><span class="sxs-lookup"><span data-stu-id="27a89-311">You can use that to predict the `Area` label of a single instance of the issue data.</span></span> <span data-ttu-id="27a89-312">要获得预测，请对数据使用 <xref:Microsoft.ML.PredictionEngine%602.Predict%2A>。</span><span class="sxs-lookup"><span data-stu-id="27a89-312">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="27a89-313">输入数据是一个字符串，且模型包含特征化。</span><span class="sxs-lookup"><span data-stu-id="27a89-313">The input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="27a89-314">管道在定型和预测期间同步。</span><span class="sxs-lookup"><span data-stu-id="27a89-314">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="27a89-315">不必专门为预测编写预处理/特征化代码，并且相同 API 负责批处理和一次性预测。</span><span class="sxs-lookup"><span data-stu-id="27a89-315">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Predict)]

### <a name="using-the-model-prediction-results"></a><span data-ttu-id="27a89-316">使用模型：预测结果</span><span class="sxs-lookup"><span data-stu-id="27a89-316">Using the model: prediction results</span></span>

<span data-ttu-id="27a89-317">显示 `GitHubIssue` 和相应的 `Area` 标签预测以便共享结果，并采取相应措施。</span><span class="sxs-lookup"><span data-stu-id="27a89-317">Display `GitHubIssue` and corresponding `Area` label prediction in order to share the results and act on them accordingly.</span></span>  <span data-ttu-id="27a89-318">使用以下 <xref:System.Console.WriteLine?displayProperty=nameWithType> 代码创建结果显示：</span><span class="sxs-lookup"><span data-stu-id="27a89-318">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputPrediction](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#OutputPrediction)]

### <a name="return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="27a89-319">返回定型模型以用于评估</span><span class="sxs-lookup"><span data-stu-id="27a89-319">Return the model trained to use for evaluation</span></span>

<span data-ttu-id="27a89-320">在 `BuildAndTrainModel` 方法末尾返回模型。</span><span class="sxs-lookup"><span data-stu-id="27a89-320">Return the model at the end of the `BuildAndTrainModel` method.</span></span>

[!code-csharp[ReturnModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#ReturnModel)]

## <a name="evaluate-the-model"></a><span data-ttu-id="27a89-321">评估模型</span><span class="sxs-lookup"><span data-stu-id="27a89-321">Evaluate the model</span></span>

<span data-ttu-id="27a89-322">你已经创建和定型模型，现在需要使用不同的数据集对其进行评估以保证质量和进行验证。</span><span class="sxs-lookup"><span data-stu-id="27a89-322">Now that you've created and trained the model, you need to evaluate it with a different dataset for quality assurance and validation.</span></span> <span data-ttu-id="27a89-323">在 `Evaluate` 方法中，将传入在 `BuildAndTrainModel` 中创建的模型以进行评估。</span><span class="sxs-lookup"><span data-stu-id="27a89-323">In the `Evaluate` method, the model created in `BuildAndTrainModel` is passed in to be evaluated.</span></span> <span data-ttu-id="27a89-324">紧随 `BuildAndTrainModel` 后创建 `Evaluate` 方法，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="27a89-324">Create the `Evaluate` method, just after `BuildAndTrainModel`, as in the following code:</span></span>

```csharp
public static void Evaluate()
{

}
```

<span data-ttu-id="27a89-325">`Evaluate` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="27a89-325">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="27a89-326">加载测试数据集。</span><span class="sxs-lookup"><span data-stu-id="27a89-326">Loads the test dataset.</span></span>
* <span data-ttu-id="27a89-327">创建多类评估程序。</span><span class="sxs-lookup"><span data-stu-id="27a89-327">Creates the multiclass evaluator.</span></span>
* <span data-ttu-id="27a89-328">评估模型并创建指标。</span><span class="sxs-lookup"><span data-stu-id="27a89-328">Evaluates the model and create metrics.</span></span>
* <span data-ttu-id="27a89-329">显示指标。</span><span class="sxs-lookup"><span data-stu-id="27a89-329">Displays the metrics.</span></span>

<span data-ttu-id="27a89-330">使用下面的代码，在 `BuildAndTrainModel` 方法调用的正下方，从 `Main` 方法中添加对新方法的调用：</span><span class="sxs-lookup"><span data-stu-id="27a89-330">Add a call to the new method from the `Main` method, right under the `BuildAndTrainModel` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallEvaluate)]

<span data-ttu-id="27a89-331">如同之前使用定型数据集执行的操作，可以将初始化、映射和测试数据集加载合并到一行代码中。</span><span class="sxs-lookup"><span data-stu-id="27a89-331">As you did previously with the training dataset, you can combine the initialization, mapping, and test dataset loading into one line of code.</span></span> <span data-ttu-id="27a89-332">可以将此数据集作为质量检查来评估模型。</span><span class="sxs-lookup"><span data-stu-id="27a89-332">You can evaluate the model using this dataset as a quality check.</span></span> <span data-ttu-id="27a89-333">将以下代码添加到 `Evaluate` 方法中：</span><span class="sxs-lookup"><span data-stu-id="27a89-333">Add the following code to the `Evaluate` method:</span></span>

[!code-csharp[LoadTestDataset](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadTestDataset)]

<span data-ttu-id="27a89-334">`MulticlassClassificationContext.Evaluate` 是 <xref:Microsoft.ML.MulticlassClassificationCatalog.Evaluate%2A> 方法的包装器，它使用指定数据集计算模型的质量指标。</span><span class="sxs-lookup"><span data-stu-id="27a89-334">The `MulticlassClassificationContext.Evaluate` is a wrapper for the <xref:Microsoft.ML.MulticlassClassificationCatalog.Evaluate%2A> method that computes the quality metrics for the model using the specified dataset.</span></span> <span data-ttu-id="27a89-335">它返回 <xref:Microsoft.ML.Data.MultiClassClassifierMetrics> 对象，其中包含由多类分类计算器计算出的总体指标。</span><span class="sxs-lookup"><span data-stu-id="27a89-335">It returns a <xref:Microsoft.ML.Data.MultiClassClassifierMetrics> object that contains the overall metrics computed by multiclass classification evaluators.</span></span>
<span data-ttu-id="27a89-336">要显示指标来确定模型质量，需要先获取这些指标。</span><span class="sxs-lookup"><span data-stu-id="27a89-336">To display the metrics to determine the quality of the model, you need to get them first.</span></span>
<span data-ttu-id="27a89-337">请注意使用机器学习 `_trainedModel` 全局变量（转换器）的 `Transform` 方法来输入要素和返回预测。</span><span class="sxs-lookup"><span data-stu-id="27a89-337">Notice the use of the `Transform` method of the machine learning `_trainedModel` global variable (a transformer) to input the features and return predictions.</span></span> <span data-ttu-id="27a89-338">将以下代码作为下一行添加到 `Evaluate` 方法中：</span><span class="sxs-lookup"><span data-stu-id="27a89-338">Add the following code to the `Evaluate` method as the next line:</span></span>

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#Evaluate)]

<span data-ttu-id="27a89-339">针对多类分类评估以下指标：</span><span class="sxs-lookup"><span data-stu-id="27a89-339">The following metrics are evaluated for multiclass classification:</span></span>

* <span data-ttu-id="27a89-340">微观准确性 - 每个“样本-类”对准确性指标的贡献度相同。</span><span class="sxs-lookup"><span data-stu-id="27a89-340">Micro Accuracy - Every sample-class pair contributes equally to the accuracy metric.</span></span>  <span data-ttu-id="27a89-341">通常会希望微观准确性尽可能接近 1。</span><span class="sxs-lookup"><span data-stu-id="27a89-341">You want Micro Accuracy to be as close to 1 as possible.</span></span>

* <span data-ttu-id="27a89-342">宏观准确性 - 每个类对准确性指标的贡献度相同。</span><span class="sxs-lookup"><span data-stu-id="27a89-342">Macro Accuracy - Every class contributes equally to the accuracy metric.</span></span> <span data-ttu-id="27a89-343">占比较小的类与占比较大的类拥有同等的权重。</span><span class="sxs-lookup"><span data-stu-id="27a89-343">Minority classes are given equal weight as the larger classes.</span></span> <span data-ttu-id="27a89-344">通常会希望宏准确性尽可能接近 1。</span><span class="sxs-lookup"><span data-stu-id="27a89-344">You want Macro Accuracy to be as close to 1 as possible.</span></span>

* <span data-ttu-id="27a89-345">对数损失 - 请参阅[对数损失](../resources/glossary.md#log-loss)。</span><span class="sxs-lookup"><span data-stu-id="27a89-345">Log-loss - see [Log Loss](../resources/glossary.md#log-loss).</span></span> <span data-ttu-id="27a89-346">通常会希望对数损失尽可能接近 0。</span><span class="sxs-lookup"><span data-stu-id="27a89-346">You want Log-loss to be as close to zero as possible.</span></span>

* <span data-ttu-id="27a89-347">对数损失减小 - 取值范围为 [-inf，100]，其中 100 表示非常精准的预测结果，0 表示准确性一般的预测。</span><span class="sxs-lookup"><span data-stu-id="27a89-347">Log-loss reduction - Ranges from [-inf, 100], where 100 is perfect predictions and 0 indicates mean predictions.</span></span> <span data-ttu-id="27a89-348">通常会希望数损失减少尽可能接近零。</span><span class="sxs-lookup"><span data-stu-id="27a89-348">You want Log-loss reduction to be as close to zero as possible.</span></span>

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="27a89-349">显示用于模型验证的指标</span><span class="sxs-lookup"><span data-stu-id="27a89-349">Displaying the metrics for model validation</span></span>

<span data-ttu-id="27a89-350">使用下面的代码显示指标、共享结果，然后处理它们：</span><span class="sxs-lookup"><span data-stu-id="27a89-350">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DisplayMetrics)]

### <a name="save-the-trained-and-evaluated-model"></a><span data-ttu-id="27a89-351">保存经过训练和评估的模型</span><span class="sxs-lookup"><span data-stu-id="27a89-351">Save the trained and evaluated model</span></span>

<span data-ttu-id="27a89-352">此时，你具有可以集成到任何现有或新 .NET 应用程序的 <xref:Microsoft.ML.Data.TransformerChain%601> 类型模型。</span><span class="sxs-lookup"><span data-stu-id="27a89-352">At this point, you have a model of type <xref:Microsoft.ML.Data.TransformerChain%601> that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="27a89-353">要将已定型的模型保存为 .zip 文件，请添加以下代码作为 `BuildAndTrainModel` 中的下一行来调用 `SaveModelAsFile` 方法：</span><span class="sxs-lookup"><span data-stu-id="27a89-353">To save your trained model to a .zip file, add the following code to call the `SaveModelAsFile` method as the next line in `BuildAndTrainModel`:</span></span>

[!code-csharp[CallSaveModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallSaveModel)]

## <a name="save-the-model-as-a-zip-file"></a><span data-ttu-id="27a89-354">将模型保存为 .zip 文件</span><span class="sxs-lookup"><span data-stu-id="27a89-354">Save the model as a .zip file</span></span>

<span data-ttu-id="27a89-355">使用下面的代码紧随 `Evaluate` 方法后创建 `SaveModelAsFile` 方法：</span><span class="sxs-lookup"><span data-stu-id="27a89-355">Create the `SaveModelAsFile` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="27a89-356">`SaveModelAsFile` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="27a89-356">The `SaveModelAsFile` method executes the following tasks:</span></span>

* <span data-ttu-id="27a89-357">将模型保存为 .zip 文件。</span><span class="sxs-lookup"><span data-stu-id="27a89-357">Saves the model as a .zip file.</span></span>

<span data-ttu-id="27a89-358">接下来，创建一个方法来保存模型，以便它可以在其他应用程序中重用和使用。</span><span class="sxs-lookup"><span data-stu-id="27a89-358">Next, create a method to save the model so that it can be reused and consumed in other applications.</span></span> <span data-ttu-id="27a89-359">`ITransformer` 有一个在 `_modelPath` 全局字段中采用的 <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> 方法和一个 <xref:System.IO.Stream> 方法。</span><span class="sxs-lookup"><span data-stu-id="27a89-359">The `ITransformer` has a <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> method that takes in the `_modelPath` global field, and a <xref:System.IO.Stream>.</span></span> <span data-ttu-id="27a89-360">要将模型保存为 zip 文件，需在调用 `SaveTo` 方法之前立即创建 `FileStream`。</span><span class="sxs-lookup"><span data-stu-id="27a89-360">To save the model as a zip file, you'll create the `FileStream` immediately before calling the `SaveTo` method.</span></span> <span data-ttu-id="27a89-361">将以下代码作为下一行添加到 `SaveModelAsFile` 方法中：</span><span class="sxs-lookup"><span data-stu-id="27a89-361">Add the following code to the `SaveModelAsFile` method as the next line:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#SaveModel)]

<span data-ttu-id="27a89-362">还可以使用以下代码通过使用 `_modelPath` 编写控制台消息来显示文件的写入位置：</span><span class="sxs-lookup"><span data-stu-id="27a89-362">You could also display where the file was written by writing a console message with the `_modelPath`, using the following code:</span></span>

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="deploy-and-predict-with-a-loaded-model"></a><span data-ttu-id="27a89-363">使用加载模型部署和预测</span><span class="sxs-lookup"><span data-stu-id="27a89-363">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="27a89-364">使用下面的代码，在 `Evaluate` 方法调用的正下方，从 `Main` 方法中添加对新方法的调用：</span><span class="sxs-lookup"><span data-stu-id="27a89-364">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallPredictIssue](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CallPredictIssue)]

<span data-ttu-id="27a89-365">使用以下代码恰好在 `Evaluate` 方法的后面（恰在 `SaveModelAsFile` 方法之前）创建 `PredictIssue` 方法：</span><span class="sxs-lookup"><span data-stu-id="27a89-365">Create the `PredictIssue` method, just after the `Evaluate` method (and just before the `SaveModelAsFile` method), using the following code:</span></span>

```csharp
private static void PredictIssue()
{

}
```

<span data-ttu-id="27a89-366">`PredictIssue` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="27a89-366">The `PredictIssue` method executes the following tasks:</span></span>

* <span data-ttu-id="27a89-367">创建测试数据的单个问题。</span><span class="sxs-lookup"><span data-stu-id="27a89-367">Creates a single issue of test data.</span></span>
* <span data-ttu-id="27a89-368">根据测试数据预测区域。</span><span class="sxs-lookup"><span data-stu-id="27a89-368">Predicts Area based on test data.</span></span>
* <span data-ttu-id="27a89-369">结合测试数据和预测进行报告。</span><span class="sxs-lookup"><span data-stu-id="27a89-369">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="27a89-370">显示预测结果。</span><span class="sxs-lookup"><span data-stu-id="27a89-370">Displays the predicted results.</span></span>

<span data-ttu-id="27a89-371">首先，使用以下代码加载先前保存的模型：</span><span class="sxs-lookup"><span data-stu-id="27a89-371">First, load the model that you saved previously with the following code:</span></span>

[!code-csharp[LoadModel](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#LoadModel)]

<span data-ttu-id="27a89-372">通过创建一个 `GitHubIssue` 实例，在 `Predict` 方法中添加一个 GitHub 问题来测试定型模型的预测：</span><span class="sxs-lookup"><span data-stu-id="27a89-372">Add a GitHub issue to test the trained model's prediction in the `Predict` method by creating an instance of `GitHubIssue`:</span></span>

[!code-csharp[AddTestIssue](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#AddTestIssue)]

[!code-csharp[CreatePredictionEngine](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#CreatePredictionEngine)]
  
<span data-ttu-id="27a89-373">现在已有一个模型，可以使用它来预测 GitHub 问题数据的单个实例的区域 GitHub 标签。</span><span class="sxs-lookup"><span data-stu-id="27a89-373">Now that you have a model, you can use that to predict the Area GitHub label of a single instance of the GitHub issue data.</span></span> <span data-ttu-id="27a89-374">要获得预测，请对数据使用 <xref:Microsoft.ML.PredictionEngine%602.Predict%2A>。</span><span class="sxs-lookup"><span data-stu-id="27a89-374">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="27a89-375">输入数据是一个字符串，且模型包含特征化。</span><span class="sxs-lookup"><span data-stu-id="27a89-375">The input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="27a89-376">管道在定型和预测期间同步。</span><span class="sxs-lookup"><span data-stu-id="27a89-376">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="27a89-377">不必专门为预测编写预处理/特征化代码，并且相同 API 负责批处理和一次性预测。</span><span class="sxs-lookup"><span data-stu-id="27a89-377">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span> <span data-ttu-id="27a89-378">在用于预测的 `PredictIssue` 方法中添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="27a89-378">Add the following code to the `PredictIssue` method for the predictions:</span></span>

[!code-csharp[PredictIssue](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#PredictIssue)]

### <a name="using-the-loaded-model-for-prediction"></a><span data-ttu-id="27a89-379">使用加载后的模型进行预测</span><span class="sxs-lookup"><span data-stu-id="27a89-379">Using the loaded model for prediction</span></span>

<span data-ttu-id="27a89-380">显示 `Area` 以便对问题进行分类并对其进行相应操作。</span><span class="sxs-lookup"><span data-stu-id="27a89-380">Display `Area` in order to categorize the issue and act on it accordingly.</span></span> <span data-ttu-id="27a89-381">使用以下 <xref:System.Console.WriteLine?displayProperty=nameWithType> 代码创建结果显示：</span><span class="sxs-lookup"><span data-stu-id="27a89-381">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[DisplayResults](../../../samples/machine-learning/tutorials/GitHubIssueClassification/Program.cs#DisplayResults)]

## <a name="results"></a><span data-ttu-id="27a89-382">结果</span><span class="sxs-lookup"><span data-stu-id="27a89-382">Results</span></span>

<span data-ttu-id="27a89-383">结果应如下所示。</span><span class="sxs-lookup"><span data-stu-id="27a89-383">Your results should be similar to the following.</span></span> <span data-ttu-id="27a89-384">管道处理期间，会显示消息。</span><span class="sxs-lookup"><span data-stu-id="27a89-384">As the pipeline processes, it displays messages.</span></span> <span data-ttu-id="27a89-385">你可能会看到警告或处理消息。</span><span class="sxs-lookup"><span data-stu-id="27a89-385">You may see warnings, or processing messages.</span></span> <span data-ttu-id="27a89-386">为简便起见，已从以下结果中删除这些消息。</span><span class="sxs-lookup"><span data-stu-id="27a89-386">These messages have been removed from the following results for clarity.</span></span>

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

<span data-ttu-id="27a89-387">祝贺你！</span><span class="sxs-lookup"><span data-stu-id="27a89-387">Congratulations!</span></span> <span data-ttu-id="27a89-388">现在，已成功生成用于为 GitHub 问题分类和预测区域标签的机器学习模型。</span><span class="sxs-lookup"><span data-stu-id="27a89-388">You've now successfully built a machine learning model for classifying and predicting an Area label for a GitHub issue.</span></span> <span data-ttu-id="27a89-389">可以在 [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) 存储库中找到本教程的源代码。</span><span class="sxs-lookup"><span data-stu-id="27a89-389">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/GitHubIssueClassification) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="27a89-390">后续步骤</span><span class="sxs-lookup"><span data-stu-id="27a89-390">Next steps</span></span>

<span data-ttu-id="27a89-391">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="27a89-391">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="27a89-392">了解问题</span><span class="sxs-lookup"><span data-stu-id="27a89-392">Understand the problem</span></span>
> * <span data-ttu-id="27a89-393">选择适当的机器学习算法</span><span class="sxs-lookup"><span data-stu-id="27a89-393">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="27a89-394">准备数据</span><span class="sxs-lookup"><span data-stu-id="27a89-394">Prepare your data</span></span>
> * <span data-ttu-id="27a89-395">转换数据</span><span class="sxs-lookup"><span data-stu-id="27a89-395">Transform the data</span></span>
> * <span data-ttu-id="27a89-396">定型模型</span><span class="sxs-lookup"><span data-stu-id="27a89-396">Train the model</span></span>
> * <span data-ttu-id="27a89-397">评估模型</span><span class="sxs-lookup"><span data-stu-id="27a89-397">Evaluate the model</span></span>
> * <span data-ttu-id="27a89-398">使用训练的模型预测</span><span class="sxs-lookup"><span data-stu-id="27a89-398">Predict with the trained model</span></span>
> * <span data-ttu-id="27a89-399">使用加载模型部署和预测</span><span class="sxs-lookup"><span data-stu-id="27a89-399">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="27a89-400">进入下一教程了解详细信息</span><span class="sxs-lookup"><span data-stu-id="27a89-400">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="27a89-401">出租车费预测器</span><span class="sxs-lookup"><span data-stu-id="27a89-401">Taxi Fare Predictor</span></span>](taxi-fare.md)

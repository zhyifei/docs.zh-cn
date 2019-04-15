---
title: 在情绪分析二元分类方案中使用 ML.NET
description: 了解如何在二元分类方案中使用 ML.NET，以了解如何使用情绪预测来采取相应措施。
ms.date: 03/07/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 202edc5127388df2397053d5703d33a39046374f
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59303110"
---
# <a name="tutorial-use-mlnet-in-a-sentiment-analysis-binary-classification-scenario"></a><span data-ttu-id="6747e-103">教程：在情绪分析二元分类方案中使用 ML.NET</span><span class="sxs-lookup"><span data-stu-id="6747e-103">Tutorial: Use ML.NET in a sentiment analysis binary classification scenario</span></span>

<span data-ttu-id="6747e-104">本示例教程通过在 Visual Studio 2017 中使用 C# 的 .NET Core 控制台应用程序，演示如何使用 ML.NET 创建情绪分类器来预测正面或负面的情绪。</span><span class="sxs-lookup"><span data-stu-id="6747e-104">This sample tutorial illustrates using ML.NET to create a sentiment classifier to predict either positive or negative sentiment via a .NET Core console application using C# in Visual Studio 2017.</span></span> <span data-ttu-id="6747e-105">在机器学习领域，这种类型的预测称为“二元分类”。</span><span class="sxs-lookup"><span data-stu-id="6747e-105">In the world of machine learning, this type of prediction is known as binary classification.</span></span>

> [!NOTE]
> <span data-ttu-id="6747e-106">本主题引用 ML.NET（目前处于预览状态），且材料可能会更改。</span><span class="sxs-lookup"><span data-stu-id="6747e-106">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="6747e-107">有关详细信息，请访问 [ML.NET 简介](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)。</span><span class="sxs-lookup"><span data-stu-id="6747e-107">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="6747e-108">此教程和相关示例目前使用的是 ML.NET 版本 0.11。</span><span class="sxs-lookup"><span data-stu-id="6747e-108">This tutorial and related sample are currently using **ML.NET version 0.11**.</span></span> <span data-ttu-id="6747e-109">有关详细信息，请参阅 [dotnet/machinelearning GitHub 存储库](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)上的发行说明</span><span class="sxs-lookup"><span data-stu-id="6747e-109">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)</span></span>

<span data-ttu-id="6747e-110">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="6747e-110">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="6747e-111">了解问题</span><span class="sxs-lookup"><span data-stu-id="6747e-111">Understand the problem</span></span>
> * <span data-ttu-id="6747e-112">选择适当的机器学习算法</span><span class="sxs-lookup"><span data-stu-id="6747e-112">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="6747e-113">准备数据</span><span class="sxs-lookup"><span data-stu-id="6747e-113">Prepare your data</span></span>
> * <span data-ttu-id="6747e-114">转换数据</span><span class="sxs-lookup"><span data-stu-id="6747e-114">Transform the data</span></span>
> * <span data-ttu-id="6747e-115">定型模型</span><span class="sxs-lookup"><span data-stu-id="6747e-115">Train the model</span></span>
> * <span data-ttu-id="6747e-116">评估模型</span><span class="sxs-lookup"><span data-stu-id="6747e-116">Evaluate the model</span></span>
> * <span data-ttu-id="6747e-117">使用训练的模型预测</span><span class="sxs-lookup"><span data-stu-id="6747e-117">Predict with the trained model</span></span>
> * <span data-ttu-id="6747e-118">使用加载模型部署和预测</span><span class="sxs-lookup"><span data-stu-id="6747e-118">Deploy and Predict with a loaded model</span></span>

## <a name="sentiment-analysis-sample-overview"></a><span data-ttu-id="6747e-119">情绪分析示例概述</span><span class="sxs-lookup"><span data-stu-id="6747e-119">Sentiment analysis sample overview</span></span>

<span data-ttu-id="6747e-120">该示例是使用 ML.NET 定型模型的控制台应用，以将情绪分类和预测为正面或负面。</span><span class="sxs-lookup"><span data-stu-id="6747e-120">The sample is a console app that uses ML.NET to train a model that classifies and predicts sentiment as either positive or negative.</span></span> <span data-ttu-id="6747e-121">Yelp 情绪数据集来自加利福尼亚大学欧文分校 (UCI)，它分为训练数据集和测试数据集。</span><span class="sxs-lookup"><span data-stu-id="6747e-121">The Yelp sentiment dataset is from University of California, Irvine (UCI), which is split into a train dataset and a test dataset.</span></span> <span data-ttu-id="6747e-122">示例还使用测试数据集评估模型用于质量分析。</span><span class="sxs-lookup"><span data-stu-id="6747e-122">The sample evaluates the model with the test dataset for quality analysis.</span></span> 

<span data-ttu-id="6747e-123">可以在 [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) 存储库中找到本教程的源代码。</span><span class="sxs-lookup"><span data-stu-id="6747e-123">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6747e-124">系统必备</span><span class="sxs-lookup"><span data-stu-id="6747e-124">Prerequisites</span></span>

* <span data-ttu-id="6747e-125">安装了“.NET Core 跨平台开发”工作负载的 [Visual Studio 2017 15.6 或更高版本](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017)。</span><span class="sxs-lookup"><span data-stu-id="6747e-125">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* [<span data-ttu-id="6747e-126">UCI Sentiment Labeled Sentences 数据集 zip 文件</span><span class="sxs-lookup"><span data-stu-id="6747e-126">The UCI Sentiment Labeled Sentences dataset zip file</span></span>](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip)

## <a name="machine-learning-workflow"></a><span data-ttu-id="6747e-127">机器学习工作流</span><span class="sxs-lookup"><span data-stu-id="6747e-127">Machine learning workflow</span></span>

<span data-ttu-id="6747e-128">本教程后面介绍了机器学习工作流，使该过程能够有序地进行。</span><span class="sxs-lookup"><span data-stu-id="6747e-128">This tutorial follows a machine learning workflow that enables the process to move in an orderly fashion.</span></span>

<span data-ttu-id="6747e-129">工作流阶段如下所示：</span><span class="sxs-lookup"><span data-stu-id="6747e-129">The workflow phases are as follows:</span></span>

1. **<span data-ttu-id="6747e-130">了解问题</span><span class="sxs-lookup"><span data-stu-id="6747e-130">Understand the problem</span></span>**
2. **<span data-ttu-id="6747e-131">准备数据</span><span class="sxs-lookup"><span data-stu-id="6747e-131">Prepare your data</span></span>**
   * **<span data-ttu-id="6747e-132">加载数据</span><span class="sxs-lookup"><span data-stu-id="6747e-132">Load the data</span></span>**
   * **<span data-ttu-id="6747e-133">提取功能（转换数据）</span><span class="sxs-lookup"><span data-stu-id="6747e-133">Extract features (Transform your data)</span></span>**
3. **<span data-ttu-id="6747e-134">生成和定型</span><span class="sxs-lookup"><span data-stu-id="6747e-134">Build and train</span></span>** 
   * **<span data-ttu-id="6747e-135">定型模型</span><span class="sxs-lookup"><span data-stu-id="6747e-135">Train the model</span></span>**
   * **<span data-ttu-id="6747e-136">评估模型</span><span class="sxs-lookup"><span data-stu-id="6747e-136">Evaluate the model</span></span>**
4. **<span data-ttu-id="6747e-137">部署模型</span><span class="sxs-lookup"><span data-stu-id="6747e-137">Deploy Model</span></span>**
   * **<span data-ttu-id="6747e-138">使用模型进行预测</span><span class="sxs-lookup"><span data-stu-id="6747e-138">Use the Model to predict</span></span>**

### <a name="understand-the-problem"></a><span data-ttu-id="6747e-139">了解问题</span><span class="sxs-lookup"><span data-stu-id="6747e-139">Understand the problem</span></span>

<span data-ttu-id="6747e-140">首先需要了解问题，因此可以将其分解为能够支持构建和定型模型的几个部分。</span><span class="sxs-lookup"><span data-stu-id="6747e-140">You first need to understand the problem, so you can break it down to parts that can support building and training the model.</span></span> <span data-ttu-id="6747e-141">分解问题可以预测和评估结果。</span><span class="sxs-lookup"><span data-stu-id="6747e-141">Breaking the problem down allows you to predict and evaluate the results.</span></span>

<span data-ttu-id="6747e-142">本教程中的问题是了解传入网站评论情绪以采取相应的措施。</span><span class="sxs-lookup"><span data-stu-id="6747e-142">The problem for this tutorial is to understand incoming website comment sentiment to take the appropriate action.</span></span>

<span data-ttu-id="6747e-143">可以将问题分解为你想要对模型进行定型的数据的情绪文本和情绪值，以及可以评估和以操作状态使用的预期情绪值。</span><span class="sxs-lookup"><span data-stu-id="6747e-143">You can break down the problem to the sentiment text and sentiment value for the data you want to train the model with, and a predicted sentiment value that you can evaluate and then use operationally.</span></span>

<span data-ttu-id="6747e-144">然后，需要确定情绪，这将帮助你进行机器学习任务选择。</span><span class="sxs-lookup"><span data-stu-id="6747e-144">You then need to **determine** the sentiment, which helps you with the machine learning task selection.</span></span>

## <a name="select-the-appropriate-machine-learning-algorithm"></a><span data-ttu-id="6747e-145">选择适当的机器学习算法</span><span class="sxs-lookup"><span data-stu-id="6747e-145">Select the appropriate machine learning algorithm</span></span>

<span data-ttu-id="6747e-146">通过此问题，你将了解以下情况：</span><span class="sxs-lookup"><span data-stu-id="6747e-146">With this problem, you know the following facts:</span></span>

<span data-ttu-id="6747e-147">训练数据：网站评论可以为正面 (1) 或负面 (0)（情绪）。</span><span class="sxs-lookup"><span data-stu-id="6747e-147">Training data: website comments can be positive (1) or negative (0) (**sentiment**).</span></span>

<span data-ttu-id="6747e-148">预测新网站评论的情绪，正面或负面，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="6747e-148">Predict the **sentiment** of a new website comment, either positive or negative, such as in the following examples:</span></span>

* <span data-ttu-id="6747e-149">我喜欢这里的服务员。</span><span class="sxs-lookup"><span data-stu-id="6747e-149">I love the wait staff here.</span></span> <span data-ttu-id="6747e-150">他们值得信赖。</span><span class="sxs-lookup"><span data-stu-id="6747e-150">They rock.</span></span>
* <span data-ttu-id="6747e-151">这里的汤是最糟糕的。</span><span class="sxs-lookup"><span data-stu-id="6747e-151">This place has the worst soup.</span></span>

<span data-ttu-id="6747e-152">分类机器学习算法最适合此方案。</span><span class="sxs-lookup"><span data-stu-id="6747e-152">The classification machine learning algorithm is best suited for this scenario.</span></span>

### <a name="about-the-classification-algorithm"></a><span data-ttu-id="6747e-153">关于分类算法</span><span class="sxs-lookup"><span data-stu-id="6747e-153">About the classification algorithm</span></span>

<span data-ttu-id="6747e-154">分类是一项机器学习算法，它使用数据来确定某个项或数据行的类别、类型或类。</span><span class="sxs-lookup"><span data-stu-id="6747e-154">Classification is a machine learning algorithm that uses data to **determine** the category, type, or class of an item or row of data.</span></span> <span data-ttu-id="6747e-155">例如，可以使用分类：</span><span class="sxs-lookup"><span data-stu-id="6747e-155">For example, you can use classification to:</span></span>

* <span data-ttu-id="6747e-156">识别情绪为正面还是负面。</span><span class="sxs-lookup"><span data-stu-id="6747e-156">Identify sentiment as positive or negative.</span></span>
* <span data-ttu-id="6747e-157">将电子邮件分类为垃圾邮件或正常邮件。</span><span class="sxs-lookup"><span data-stu-id="6747e-157">Classify email as spam, junk, or good.</span></span>
* <span data-ttu-id="6747e-158">确定患者的实验室样本是否癌变。</span><span class="sxs-lookup"><span data-stu-id="6747e-158">Determine whether a patient's lab sample is cancerous.</span></span>
* <span data-ttu-id="6747e-159">根据客户对销售活动的反应倾向对客户进行分类。</span><span class="sxs-lookup"><span data-stu-id="6747e-159">Categorize customers by their propensity to respond to a sales campaign.</span></span>

<span data-ttu-id="6747e-160">分类算法通常为以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="6747e-160">Classification algorithms are frequently one of the following types:</span></span>

* <span data-ttu-id="6747e-161">二元：A 或 B。</span><span class="sxs-lookup"><span data-stu-id="6747e-161">Binary: either A or B.</span></span>
* <span data-ttu-id="6747e-162">多类：可以通过使用单个模型来预测多个类别。</span><span class="sxs-lookup"><span data-stu-id="6747e-162">Multiclass: multiple categories that can be predicted by using a single model.</span></span>

<span data-ttu-id="6747e-163">由于需要将网站评论分为正面或负面，因此使用二元分类算法。</span><span class="sxs-lookup"><span data-stu-id="6747e-163">Because the website comments need to be classified as either positive or negative, you use the Binary Classification algorithm.</span></span> 

## <a name="create-a-console-application"></a><span data-ttu-id="6747e-164">创建控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="6747e-164">Create a console application</span></span>

1. <span data-ttu-id="6747e-165">打开 Visual Studio 2017。</span><span class="sxs-lookup"><span data-stu-id="6747e-165">Open Visual Studio 2017.</span></span> <span data-ttu-id="6747e-166">从菜单栏中选择“文件” > “新建” > “项目”。</span><span class="sxs-lookup"><span data-stu-id="6747e-166">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="6747e-167">在“新项目”对话框中，依次选择“Visual C#”和“.NET Core”节点。</span><span class="sxs-lookup"><span data-stu-id="6747e-167">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="6747e-168">然后，选择“控制台应用程序(.NET Core)”项目模板。</span><span class="sxs-lookup"><span data-stu-id="6747e-168">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="6747e-169">在“名称”文本框中，键入“SentimentAnalysis”，然后选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="6747e-169">In the **Name** text box, type "SentimentAnalysis" and then select the **OK** button.</span></span>

2. <span data-ttu-id="6747e-170">在项目中创建一个名为“数据”的目录来保存数据集文件：</span><span class="sxs-lookup"><span data-stu-id="6747e-170">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="6747e-171">在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新文件夹”。</span><span class="sxs-lookup"><span data-stu-id="6747e-171">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="6747e-172">键入“Data”，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="6747e-172">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="6747e-173">安装“Microsoft.ML NuGet 包”：</span><span class="sxs-lookup"><span data-stu-id="6747e-173">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="6747e-174">在“解决方案资源管理器”中，右键单击项目，然后选择“管理 NuGet 包”。</span><span class="sxs-lookup"><span data-stu-id="6747e-174">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="6747e-175">将“nuget.org”选择为“包源”，选择“浏览”选项卡并搜索“Microsoft.ML”，在列表中选择该包，然后选择“安装”按钮。</span><span class="sxs-lookup"><span data-stu-id="6747e-175">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="6747e-176">选择“预览更改”对话框上的“确定”按钮，如果你同意所列包的许可条款，则选择“接受许可”对话框上的“我接受”按钮。</span><span class="sxs-lookup"><span data-stu-id="6747e-176">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="6747e-177">准备数据</span><span class="sxs-lookup"><span data-stu-id="6747e-177">Prepare your data</span></span>

1. <span data-ttu-id="6747e-178">下载 [UCI Sentiment Labeled Sentences 数据集 zip 文件（请参阅以下备注中的引文）](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip)并解压缩文件。</span><span class="sxs-lookup"><span data-stu-id="6747e-178">Download [The UCI Sentiment Labeled Sentences dataset zip file (see citations in the following note)](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip), and unzip.</span></span>

2. <span data-ttu-id="6747e-179">将 `yelp_labelled.txt` 文件复制到已创建的“数据”目录中。</span><span class="sxs-lookup"><span data-stu-id="6747e-179">Copy the `yelp_labelled.txt` file into the *Data* directory you created.</span></span>

> [!NOTE]
> <span data-ttu-id="6747e-180">本教程使用的数据集摘自 KDD 2015 中由 Kotzias 等</span><span class="sxs-lookup"><span data-stu-id="6747e-180">The datasets this tutorial uses are from the 'From Group to Individual Labels using Deep Features', Kotzias et.</span></span> <span data-ttu-id="6747e-181">提出的“From Group to Individual Labels using Deep Features”，</span><span class="sxs-lookup"><span data-stu-id="6747e-181">al,.</span></span> <span data-ttu-id="6747e-182">并托管在 UCI 机器学习存储库中（Dua, D. 和 Karra Taniskidou, E.(2017)）。</span><span class="sxs-lookup"><span data-stu-id="6747e-182">KDD 2015, and hosted at the UCI Machine Learning Repository - Dua, D. and Karra Taniskidou, E. (2017).</span></span> <span data-ttu-id="6747e-183">UCI 机器学习存储库 [http://archive.ics.uci.edu/ml]。</span><span class="sxs-lookup"><span data-stu-id="6747e-183">UCI Machine Learning Repository [http://archive.ics.uci.edu/ml].</span></span> <span data-ttu-id="6747e-184">加利福尼亚州，加利福尼亚大学：欧文分校，信息与计算机科学学院。</span><span class="sxs-lookup"><span data-stu-id="6747e-184">Irvine, CA: University of California, School of Information and Computer Science.</span></span>

3. <span data-ttu-id="6747e-185">在“解决方案资源管理器”中，右键单击 `yelp_labeled.txt` 文件并选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="6747e-185">In Solution Explorer, right-click the `yelp_labeled.txt` file and select **Properties**.</span></span> <span data-ttu-id="6747e-186">在“高级”下，将“复制到输出目录”的值更改为“如果较新则复制”。</span><span class="sxs-lookup"><span data-stu-id="6747e-186">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="6747e-187">创建类和定义路径</span><span class="sxs-lookup"><span data-stu-id="6747e-187">Create classes and define paths</span></span>

<span data-ttu-id="6747e-188">将以下附加的 `using` 语句添加到“Program.cs”文件顶部：</span><span class="sxs-lookup"><span data-stu-id="6747e-188">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddUsings "Add necessary usings")]

<span data-ttu-id="6747e-189">需要创建两个全局字段来存储最近下载的数据集文件路径和已保存的模型文件路径：</span><span class="sxs-lookup"><span data-stu-id="6747e-189">You need to create two global fields to hold the recently downloaded dataset file path and the saved model file path:</span></span>

* `_dataPath` <span data-ttu-id="6747e-190">具有用于定型模型的数据集路径。</span><span class="sxs-lookup"><span data-stu-id="6747e-190">has the path to the dataset used to train the model.</span></span>
* `_modelPath` <span data-ttu-id="6747e-191">具有在其中保存定型模型的路径。</span><span class="sxs-lookup"><span data-stu-id="6747e-191">has the path where the trained model is saved.</span></span>

<span data-ttu-id="6747e-192">将以下代码添加到 `Main` 方法上方的行中，以指定这些路径：</span><span class="sxs-lookup"><span data-stu-id="6747e-192">Add the following code to the line right above the `Main` method to specify those paths:</span></span>

[!code-csharp[Declare global variables](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DeclareGlobalVariables "Declare global variables")]

<span data-ttu-id="6747e-193">需要为输入数据和预测创建一些类。</span><span class="sxs-lookup"><span data-stu-id="6747e-193">You need to create some classes for your input data and predictions.</span></span> <span data-ttu-id="6747e-194">向项目添加一个新类：</span><span class="sxs-lookup"><span data-stu-id="6747e-194">Add a new class to your project:</span></span>

1. <span data-ttu-id="6747e-195">在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新项”。</span><span class="sxs-lookup"><span data-stu-id="6747e-195">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="6747e-196">在“添加新项”对话框中，选择“类”并将“名称”字段更改为“SentimentData.cs”。</span><span class="sxs-lookup"><span data-stu-id="6747e-196">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="6747e-197">然后，选择“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="6747e-197">Then, select the **Add** button.</span></span>

    <span data-ttu-id="6747e-198">“SentimentData.cs”文件随即在代码编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="6747e-198">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="6747e-199">将下面的 `using` 语句添加到 SentimentData.cs 的顶部：</span><span class="sxs-lookup"><span data-stu-id="6747e-199">Add the following `using` statement to the top of *SentimentData.cs*:</span></span>

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#AddUsings "Add necessary usings")]

<span data-ttu-id="6747e-200">删除现有类定义并向“SentimentData.cs”文件添加以下代码，其中有两个类 `SentimentData` 和 `SentimentPrediction`：</span><span class="sxs-lookup"><span data-stu-id="6747e-200">Remove the existing class definition and add the following code, which has two classes `SentimentData` and `SentimentPrediction`, to the *SentimentData.cs* file:</span></span>

[!code-csharp[DeclareTypes](~/samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#DeclareTypes "Declare data record types")]

<span data-ttu-id="6747e-201">输入数据集类 `SentimentData` 具有带正面或负面情绪值的评论 (`SentimentText`) 和 `bool` (`Sentiment`) 的 `string`。</span><span class="sxs-lookup"><span data-stu-id="6747e-201">The input dataset class, `SentimentData`, has a `string` for the comment (`SentimentText`) and a `bool` (`Sentiment`) that has a value for sentiment of either positive or negative.</span></span> <span data-ttu-id="6747e-202">这两个字段均有随附的 <xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29> 属性。</span><span class="sxs-lookup"><span data-stu-id="6747e-202">Both fields have <xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29> attributes attached to them.</span></span> <span data-ttu-id="6747e-203">此属性描述数据文件中每个字段的顺序。</span><span class="sxs-lookup"><span data-stu-id="6747e-203">This attribute describes the order of each field in the data file.</span></span>  <span data-ttu-id="6747e-204">此外，`Sentiment` 属性具有 <xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A>，可将其指定为 `Label` 字段。</span><span class="sxs-lookup"><span data-stu-id="6747e-204">In addition, the `Sentiment` property has a <xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A> to designate it as the `Label` field.</span></span> `SentimentPrediction` <span data-ttu-id="6747e-205">是在定型模型后用于预测的类。</span><span class="sxs-lookup"><span data-stu-id="6747e-205">is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="6747e-206">它有一个布尔值 (`Sentiment`) 和一个 `PredictedLabel` `ColumnName` 属性。</span><span class="sxs-lookup"><span data-stu-id="6747e-206">It has a single boolean (`Sentiment`) and a `PredictedLabel` `ColumnName` attribute.</span></span> <span data-ttu-id="6747e-207">`Label` 用于创建和训练模型，并且与拆分测试数据集结合使用来评估模型。</span><span class="sxs-lookup"><span data-stu-id="6747e-207">The `Label` is used to create and train the model, and it's also used with the split out test dataset to evaluate the model.</span></span> <span data-ttu-id="6747e-208">`PredictedLabel` 在预测和评估过程中使用。</span><span class="sxs-lookup"><span data-stu-id="6747e-208">The `PredictedLabel` is used during prediction and evaluation.</span></span> <span data-ttu-id="6747e-209">对于计算，将使用带定型数据的输入、预测值和模型。</span><span class="sxs-lookup"><span data-stu-id="6747e-209">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="6747e-210">使用 ML.NET 构建模型时，首先要创建一个 <xref:Microsoft.ML.MLContext>。</span><span class="sxs-lookup"><span data-stu-id="6747e-210">When building a model with ML.NET you start by creating an <xref:Microsoft.ML.MLContext>.</span></span> `MLContext` <span data-ttu-id="6747e-211">在概念上相当于在实体框架中使用 `DbContext`。</span><span class="sxs-lookup"><span data-stu-id="6747e-211">is comparable conceptually to using `DbContext` in Entity Framework.</span></span> <span data-ttu-id="6747e-212">该环境为 ML 作业提供一个上下文，可以用于异常情况跟踪和日志记录。</span><span class="sxs-lookup"><span data-stu-id="6747e-212">The environment provides a context for your ML job that can be used for exception tracking and logging.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="6747e-213">在 Main 中初始化变量</span><span class="sxs-lookup"><span data-stu-id="6747e-213">Initialize variables in Main</span></span>

<span data-ttu-id="6747e-214">创建一个名为 `mlContext` 的变量并将其初始化为 `MLContext` 的新实例。</span><span class="sxs-lookup"><span data-stu-id="6747e-214">Create a variable called `mlContext` and initialize it with a new instance of `MLContext`.</span></span>  <span data-ttu-id="6747e-215">用下面 `Main` 方法中的代码替换 `Console.WriteLine("Hello World!")` 行：</span><span class="sxs-lookup"><span data-stu-id="6747e-215">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateMLContext "Create the ML Context")]

<span data-ttu-id="6747e-216">将以下代码作为下一行代码添加到 `Main` 方法中：</span><span class="sxs-lookup"><span data-stu-id="6747e-216">Add the following as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallLoadData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallLoadData)]

<span data-ttu-id="6747e-217">`LoadData` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="6747e-217">The `LoadData` method executes the following tasks:</span></span>

* <span data-ttu-id="6747e-218">加载数据。</span><span class="sxs-lookup"><span data-stu-id="6747e-218">Loads the data.</span></span>
* <span data-ttu-id="6747e-219">将加载的数据集拆分为训练数据集和测试数据集。</span><span class="sxs-lookup"><span data-stu-id="6747e-219">Splits the loaded dataset into train and test datasets.</span></span>
* <span data-ttu-id="6747e-220">返回拆分的训练数据集和测试数据集。</span><span class="sxs-lookup"><span data-stu-id="6747e-220">Returns the split train and test datasets.</span></span>

<span data-ttu-id="6747e-221">使用下面的代码紧随 `Main` 方法后创建 `LoadData` 方法：</span><span class="sxs-lookup"><span data-stu-id="6747e-221">Create the `LoadData` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static TrainCatalogBase.TrainTestData LoadData(MLContext mlContext)
{

}
```
## <a name="load-the-data"></a><span data-ttu-id="6747e-222">加载数据</span><span class="sxs-lookup"><span data-stu-id="6747e-222">Load the data</span></span>

<span data-ttu-id="6747e-223">由于先前创建的 `SentimentData` 数据模型类型与数据集架构匹配，因此可使用 [LoadFromTextFile 方法](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29)的 `MLContext.Data.LoadFromTextFile` 包装器，将初始化、映射和数据集加载合并到一行代码中。</span><span class="sxs-lookup"><span data-stu-id="6747e-223">Since your previously created `SentimentData` data model type matches the dataset schema, you can combine the initialization, mapping, and dataset loading into one line of code using the `MLContext.Data.LoadFromTextFile` wrapper for the [LoadFromTextFile method](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29).</span></span> <span data-ttu-id="6747e-224">它将返回 <xref:Microsoft.Data.DataView.IDataView>。</span><span class="sxs-lookup"><span data-stu-id="6747e-224">It returns a <xref:Microsoft.Data.DataView.IDataView>.</span></span> 

 <span data-ttu-id="6747e-225">作为 `Transforms` 的输入和输出，`DataView` 是基本的数据管道类型，与 `LINQ` 中的 `IEnumerable` 类似。</span><span class="sxs-lookup"><span data-stu-id="6747e-225">As the input and output of `Transforms`, a `DataView` is the fundamental data pipeline type, comparable to `IEnumerable` for `LINQ`.</span></span>

<span data-ttu-id="6747e-226">在 ML.NET 中，数据类似于 SQL 视图。</span><span class="sxs-lookup"><span data-stu-id="6747e-226">In ML.NET, data is similar to a SQL view.</span></span> <span data-ttu-id="6747e-227">它是异源数据，会延迟计算并进行架构化。</span><span class="sxs-lookup"><span data-stu-id="6747e-227">It is lazily evaluated, schematized, and heterogenous.</span></span> <span data-ttu-id="6747e-228">该对象是管道的第一部分，并加载数据。</span><span class="sxs-lookup"><span data-stu-id="6747e-228">The object is the first part of the pipeline, and loads the data.</span></span> <span data-ttu-id="6747e-229">对于本教程，它会加载具有注释和相应正面或负面情绪的数据集。</span><span class="sxs-lookup"><span data-stu-id="6747e-229">For this tutorial, it loads a dataset with comments and corresponding toxic or non toxic sentiment.</span></span> <span data-ttu-id="6747e-230">这用于创建模型并对其进行定型。</span><span class="sxs-lookup"><span data-stu-id="6747e-230">This is used to create the model, and train it.</span></span>

 <span data-ttu-id="6747e-231">将以下代码添加为 `LoadData` 方法的首行：</span><span class="sxs-lookup"><span data-stu-id="6747e-231">Add the following code as the first line of the `LoadData` method:</span></span>

[!code-csharp[LoadData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#LoadData "loading dataset")]

### <a name="split-the-dataset-for-model-training-and-testing"></a><span data-ttu-id="6747e-232">拆分数据集以进行模型训练和测试</span><span class="sxs-lookup"><span data-stu-id="6747e-232">Split the dataset for model training and testing</span></span>

<span data-ttu-id="6747e-233">接下来，需要使用训练数据集来训练型模型，也需要使用测试数据集来评估模型。</span><span class="sxs-lookup"><span data-stu-id="6747e-233">Next, you need both a training dataset to train the model and a test dataset to evaluate the model.</span></span> <span data-ttu-id="6747e-234">使用包装 <xref:Microsoft.ML.StaticPipe.TrainingStaticExtensions.TrainTestSplit%2A> 的 `MLContext.BinaryClassification.TrainTestSplit` 将已加载的数据集拆分为训练数据集和测试数据集，并将它们返回到 <xref:Microsoft.ML.TrainCatalogBase.TrainTestData> 内。</span><span class="sxs-lookup"><span data-stu-id="6747e-234">Use the `MLContext.BinaryClassification.TrainTestSplit` which wraps <xref:Microsoft.ML.StaticPipe.TrainingStaticExtensions.TrainTestSplit%2A> to split the loaded dataset into train and test datasets and return them inside of a <xref:Microsoft.ML.TrainCatalogBase.TrainTestData>.</span></span> <span data-ttu-id="6747e-235">可以使用 `testFraction` 参数指定测试集的部分数据。</span><span class="sxs-lookup"><span data-stu-id="6747e-235">You can specify the fraction of data for the test set with the `testFraction`parameter.</span></span> <span data-ttu-id="6747e-236">默认为 10%，但在本例中使用 20% 的数据，通过更多数据进行评估。</span><span class="sxs-lookup"><span data-stu-id="6747e-236">The default is 10% but you use 20% in this case to use more data for the evaluation.</span></span>  

<span data-ttu-id="6747e-237">要将加载的数据拆分为所需的数据集，请添加以下代码作为 `LoadData` 方法中的下一行：</span><span class="sxs-lookup"><span data-stu-id="6747e-237">To split the loaded data into the needed datasets, add the following code as the next line in the `LoadData` method:</span></span>

[!code-csharp[SplitData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#SplitData "Split the Data")]

<span data-ttu-id="6747e-238">在 `LoadData` 方法末尾返回 `splitDataView`：</span><span class="sxs-lookup"><span data-stu-id="6747e-238">Return the `splitDataView` at the end of the `LoadData` method:</span></span>

[!code-csharp[ReturnSplitData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#ReturnSplitData)]

## <a name="build-and-train-the-model"></a><span data-ttu-id="6747e-239">生成和定型模型</span><span class="sxs-lookup"><span data-stu-id="6747e-239">Build and train the model</span></span>

<span data-ttu-id="6747e-240">将以下调用添加到 `BuildAndTrainModel` 方法作为 `Main` 方法的下一行代码：</span><span class="sxs-lookup"><span data-stu-id="6747e-240">Add the following call to the `BuildAndTrainModel`method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallBuildAndTrainModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallBuildAndTrainModel)]

<span data-ttu-id="6747e-241">`BuildAndTrainModel` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="6747e-241">The `BuildAndTrainModel` method executes the following tasks:</span></span>

* <span data-ttu-id="6747e-242">提取并转换数据。</span><span class="sxs-lookup"><span data-stu-id="6747e-242">Extracts and transforms the data.</span></span>
* <span data-ttu-id="6747e-243">定型模型。</span><span class="sxs-lookup"><span data-stu-id="6747e-243">Trains the model.</span></span>
* <span data-ttu-id="6747e-244">根据测试数据预测情绪。</span><span class="sxs-lookup"><span data-stu-id="6747e-244">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="6747e-245">返回模型。</span><span class="sxs-lookup"><span data-stu-id="6747e-245">Returns the model.</span></span>

<span data-ttu-id="6747e-246">使用下面的代码紧随 `Main` 方法后创建 `BuildAndTrainModel` 方法：</span><span class="sxs-lookup"><span data-stu-id="6747e-246">Create the `BuildAndTrainModel` method, just after the `Main` method, using the following code:</span></span>

```csharp
public static ITransformer BuildAndTrainModel(MLContext mlContext, IDataView splitTrainSet)
{

}
```

<span data-ttu-id="6747e-247">请注意，传递到 Train 方法的两个参数；`MLContext` 用于上下文 (`mlContext`)，`IDataView` 用于训练数据集 (`splitTrainSet`)。</span><span class="sxs-lookup"><span data-stu-id="6747e-247">Notice that two parameters are passed into the Train method; a `MLContext` for the context (`mlContext`), and an `IDataView`for the training dataset (`splitTrainSet`).</span></span> 

## <a name="extract-and-transform-the-data"></a><span data-ttu-id="6747e-248">提取和转换数据</span><span class="sxs-lookup"><span data-stu-id="6747e-248">Extract and transform the data</span></span>

<span data-ttu-id="6747e-249">预处理和清除数据任务至关重要，需要首先执行才能将数据集有效地用于机器学习。</span><span class="sxs-lookup"><span data-stu-id="6747e-249">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span> <span data-ttu-id="6747e-250">原始数据通常嘈杂不可靠，并且可能缺少值。</span><span class="sxs-lookup"><span data-stu-id="6747e-250">Raw data is often noisy and unreliable, and may be missing values.</span></span> <span data-ttu-id="6747e-251">在没有这些建模任务的情况下使用数据会产生误导性结果。</span><span class="sxs-lookup"><span data-stu-id="6747e-251">Using data without these modeling tasks can produce misleading results.</span></span>

<span data-ttu-id="6747e-252">ML.NET 的转换管道撰写一组自定义转换，在定型或测试数据之前将其应用到数据。</span><span class="sxs-lookup"><span data-stu-id="6747e-252">ML.NET's transform pipelines compose a custom set of transforms that are applied to your data before training or testing.</span></span> <span data-ttu-id="6747e-253">转换的主要目的是为了[特征化](../resources/glossary.md#feature-engineering)数据。</span><span class="sxs-lookup"><span data-stu-id="6747e-253">The transforms' primary purpose is data [featurization](../resources/glossary.md#feature-engineering).</span></span> <span data-ttu-id="6747e-254">机器学习算法理解[特征化](../resources/glossary.md#feature)数据，因此下一步是将文本数据转换为 ML 算法识别的格式。</span><span class="sxs-lookup"><span data-stu-id="6747e-254">Machine learning algorithms understand [featurized](../resources/glossary.md#feature) data, so the next step is to transform our textual data into a format that our ML algorithms recognize.</span></span> <span data-ttu-id="6747e-255">该格式是[数值向量](../resources/glossary.md#numerical-feature-vector)。</span><span class="sxs-lookup"><span data-stu-id="6747e-255">That format is a [numeric vector](../resources/glossary.md#numerical-feature-vector).</span></span>

<span data-ttu-id="6747e-256">下一步，调用将文本列 (`SentimentText`) 列特征化为机器学习算法使用的名为 `Features` 的数值向量的 `mlContext.Transforms.Text.FeaturizeText`。</span><span class="sxs-lookup"><span data-stu-id="6747e-256">Next, call `mlContext.Transforms.Text.FeaturizeText` which featurizes the text column (`SentimentText`) column into a numeric vector called `Features` used by the machine learning algorithm.</span></span> <span data-ttu-id="6747e-257">此为包装器调用，它返回实际上是管道的 <xref:Microsoft.ML.Data.EstimatorChain%601>。</span><span class="sxs-lookup"><span data-stu-id="6747e-257">This is a wrapper call that returns an <xref:Microsoft.ML.Data.EstimatorChain%601> that will effectively be a pipeline.</span></span> <span data-ttu-id="6747e-258">命名此 `pipeline`，因为你将把定型程序附加到 `EstimatorChain`。</span><span class="sxs-lookup"><span data-stu-id="6747e-258">Name this `pipeline` as you will then append the trainer to the `EstimatorChain`.</span></span> <span data-ttu-id="6747e-259">将此添加为下一个代码行：</span><span class="sxs-lookup"><span data-stu-id="6747e-259">Add this as the next line of code:</span></span>

[!code-csharp[FeaturizeText](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#FeaturizeText "Featurize the text")]

>[!WARNING]
> <span data-ttu-id="6747e-260">ML.NET 版本 0.10 更改了转换参数的顺序。</span><span class="sxs-lookup"><span data-stu-id="6747e-260">ML.NET Version 0.10 changed the order of the Transform parameters.</span></span> <span data-ttu-id="6747e-261">在运行应用程序和生成模型之前，这不会出错。</span><span class="sxs-lookup"><span data-stu-id="6747e-261">This will not error out until you run the application and build the model.</span></span> <span data-ttu-id="6747e-262">使用用于转换的参数名称，如前面的代码片段中所示。</span><span class="sxs-lookup"><span data-stu-id="6747e-262">Use the parameter names for Transforms as illustrated in the previous code snippet.</span></span>

<span data-ttu-id="6747e-263">这是预处理/特征化步骤。</span><span class="sxs-lookup"><span data-stu-id="6747e-263">This is the preprocessing/featurization step.</span></span> <span data-ttu-id="6747e-264">使用 ML.NET 中可用的其他组件可以在使用模型时生成更佳结果。</span><span class="sxs-lookup"><span data-stu-id="6747e-264">Using additional components available in ML.NET can enable better results with your model.</span></span>

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="6747e-265">选择学习算法</span><span class="sxs-lookup"><span data-stu-id="6747e-265">Choose a learning algorithm</span></span>

<span data-ttu-id="6747e-266">若要添加定型程序，调用返回 <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryClassificationTrainer> 对象的 `mlContext.BinaryClassification.Trainers.FastTree` 包装器方法。</span><span class="sxs-lookup"><span data-stu-id="6747e-266">To add the trainer, call the `mlContext.BinaryClassification.Trainers.FastTree` wrapper method which returns a <xref:Microsoft.ML.Trainers.FastTree.FastTreeBinaryClassificationTrainer> object.</span></span> <span data-ttu-id="6747e-267">这是一个将在此管道中使用的决策树学习器。</span><span class="sxs-lookup"><span data-stu-id="6747e-267">This is a decision tree learner you'll use in this pipeline.</span></span> <span data-ttu-id="6747e-268">`FastTreeBinaryClassificationTrainer` 追加到 `pipeline` 并接受特征化的 `SentimentText` (`Features`) 和 `Label` 输入参数，以便从历史数据中学习。</span><span class="sxs-lookup"><span data-stu-id="6747e-268">The `FastTreeBinaryClassificationTrainer` is appended to the `pipeline` and accepts the featurized `SentimentText` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span>

<span data-ttu-id="6747e-269">将以下代码添加到 `BuildAndTrainModel` 方法中：</span><span class="sxs-lookup"><span data-stu-id="6747e-269">Add the following code to the `BuildAndTrainModel` method:</span></span>

[!code-csharp[FastTreeBinaryClassificationTrainer](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddTrainer "Add a FastTreeBinaryClassificationTrainer")]

## <a name="train-the-model"></a><span data-ttu-id="6747e-270">定型模型</span><span class="sxs-lookup"><span data-stu-id="6747e-270">Train the model</span></span>

<span data-ttu-id="6747e-271">根据已加载和转换的数据集定型模型 <xref:Microsoft.ML.Data.TransformerChain%601>。</span><span class="sxs-lookup"><span data-stu-id="6747e-271">You train the model, <xref:Microsoft.ML.Data.TransformerChain%601>, based on the dataset that has been loaded and transformed.</span></span> <span data-ttu-id="6747e-272">一旦定义了估算器，将使用 <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> 方法训练模型，同时提供已加载的训练数据。</span><span class="sxs-lookup"><span data-stu-id="6747e-272">Once the estimator has been defined, you train your model using the <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> method while providing the already loaded training data.</span></span> <span data-ttu-id="6747e-273">这将返回要用于预测的模型。</span><span class="sxs-lookup"><span data-stu-id="6747e-273">This returns a model to use for predictions.</span></span> `pipeline.Fit()` <span data-ttu-id="6747e-274">定型管道，并返回基于传入的 `DataView` 的 `Transformer`。</span><span class="sxs-lookup"><span data-stu-id="6747e-274">trains the pipeline and returns a `Transformer` based on the `DataView` passed in.</span></span> <span data-ttu-id="6747e-275">在 `.Fit()` 方法运行之前不会执行此试验。</span><span class="sxs-lookup"><span data-stu-id="6747e-275">The experiment is not executed until the `.Fit()` method runs.</span></span>

<span data-ttu-id="6747e-276">将以下代码添加到 `BuildAndTrainModel` 方法中：</span><span class="sxs-lookup"><span data-stu-id="6747e-276">Add the following code to the `BuildAndTrainModel` method:</span></span>

[!code-csharp[TrainModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#TrainModel "Train the model")]

### <a name="save-and-return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="6747e-277">保存并返回定型模型以用于评估</span><span class="sxs-lookup"><span data-stu-id="6747e-277">Save and Return the model trained to use for evaluation</span></span>

<span data-ttu-id="6747e-278">此时，你具有可以集成到任何现有或新 .NET 应用程序的 <xref:Microsoft.ML.Data.TransformerChain%601> 类型模型。</span><span class="sxs-lookup"><span data-stu-id="6747e-278">At this point, you have a model of type <xref:Microsoft.ML.Data.TransformerChain%601> that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="6747e-279">在 `BuildAndTrainModel` 方法末尾返回模型。</span><span class="sxs-lookup"><span data-stu-id="6747e-279">Return the model at the end of the `BuildAndTrainModel` method.</span></span>

[!code-csharp[ReturnModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#ReturnModel "Return the model")]

## <a name="evaluate-the-model"></a><span data-ttu-id="6747e-280">评估模型</span><span class="sxs-lookup"><span data-stu-id="6747e-280">Evaluate the model</span></span>

<span data-ttu-id="6747e-281">你已经创建和定型模型，现在需要使用不同的数据集对其进行评估以保证质量和进行验证。</span><span class="sxs-lookup"><span data-stu-id="6747e-281">Now that you've created and trained the model, you need to evaluate it with a different dataset for quality assurance and validation.</span></span> <span data-ttu-id="6747e-282">在 `Evaluate` 方法中，将传入在 `BuildAndTrainModel` 中创建的模型以进行评估。</span><span class="sxs-lookup"><span data-stu-id="6747e-282">In the `Evaluate` method, the model created in `BuildAndTrainModel` is passed in to be evaluated.</span></span> <span data-ttu-id="6747e-283">紧随 `BuildAndTrainModel` 后创建 `Evaluate` 方法，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="6747e-283">Create the `Evaluate` method, just after `BuildAndTrainModel`, as in the following code:</span></span>

```csharp
public static void Evaluate(MLContext mlContext, ITransformer model, IDataView splitTestSet)
{

}
```

<span data-ttu-id="6747e-284">`Evaluate` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="6747e-284">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="6747e-285">加载测试数据集。</span><span class="sxs-lookup"><span data-stu-id="6747e-285">Loads the test dataset.</span></span>
* <span data-ttu-id="6747e-286">创建 binaryclassification 计算器。</span><span class="sxs-lookup"><span data-stu-id="6747e-286">Creates the binaryclassification evaluator.</span></span>
* <span data-ttu-id="6747e-287">评估模型并创建指标。</span><span class="sxs-lookup"><span data-stu-id="6747e-287">Evaluates the model and creates metrics.</span></span>
* <span data-ttu-id="6747e-288">显示指标。</span><span class="sxs-lookup"><span data-stu-id="6747e-288">Displays the metrics.</span></span>

<span data-ttu-id="6747e-289">使用下面的代码，在 `Train` 方法调用的正下方，从 `Main` 方法中添加对新方法的调用：</span><span class="sxs-lookup"><span data-stu-id="6747e-289">Add a call to the new method from the `Main` method, right under the `Train` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallEvaluate "Call the Evaluate method")]

<span data-ttu-id="6747e-290">接下来，将使用机器学习 `model` 参数（转换器）和 `splitTestSet` 参数来输入特性，并返回预测。</span><span class="sxs-lookup"><span data-stu-id="6747e-290">Next, you'll use the machine learning `model` parameter (a transformer) and the `splitTestSet` parameter to input the features and return predictions.</span></span> <span data-ttu-id="6747e-291">将以下代码作为下一行添加到 `Evaluate` 方法中：</span><span class="sxs-lookup"><span data-stu-id="6747e-291">Add the following code to the `Evaluate` method as the next line:</span></span>

[!code-csharp[PredictWithTransformer](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#TransformData "Predict using the Transformer")]

<span data-ttu-id="6747e-292">`mlContext.BinaryClassification.Evaluate` 方法使用指定数据集计算 `PredictionModel` 的质量指标。</span><span class="sxs-lookup"><span data-stu-id="6747e-292">The `mlContext.BinaryClassification.Evaluate` method computes the quality metrics for the `PredictionModel` using the specified dataset.</span></span> <span data-ttu-id="6747e-293">它返回 <xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics> 对象，其中包含由二元分类计算器计算出的总体指标。</span><span class="sxs-lookup"><span data-stu-id="6747e-293">It returns a <xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics> object that contains the overall metrics computed by binary classification evaluators.</span></span> <span data-ttu-id="6747e-294">若要显示这些指标来确定模型质量，需要先获取指标。</span><span class="sxs-lookup"><span data-stu-id="6747e-294">To display these to determine the quality of the model, you need to get the metrics first.</span></span> <span data-ttu-id="6747e-295">将以下代码作为下一行添加到 `Evaluate` 方法中：</span><span class="sxs-lookup"><span data-stu-id="6747e-295">Add the following code as the next line in the `Evaluate` method:</span></span>

[!code-csharp[ComputeMetrics](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Evaluate "Compute Metrics")]

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="6747e-296">显示用于模型验证的指标</span><span class="sxs-lookup"><span data-stu-id="6747e-296">Displaying the metrics for model validation</span></span>

<span data-ttu-id="6747e-297">使用下面的代码显示指标、共享结果，然后处理它们：</span><span class="sxs-lookup"><span data-stu-id="6747e-297">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DisplayMetrics "Display selected metrics")]

<span data-ttu-id="6747e-298">若要在返回之前将模型保存到 .zip 文件，请添加以下代码作为 `Evaluate` 中的下一行来调用 `SaveModelAsFile` 方法：</span><span class="sxs-lookup"><span data-stu-id="6747e-298">To save your model to a .zip file before returning, add the following code to call the `SaveModelAsFile` method as the next line in `Evaluate`:</span></span>

[!code-csharp[SaveModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallSaveModel "Save the model")]

## <a name="save-the-model-as-azip-file"></a><span data-ttu-id="6747e-299">将模型保存为 .zip 文件</span><span class="sxs-lookup"><span data-stu-id="6747e-299">Save the model as a.zip file</span></span>

<span data-ttu-id="6747e-300">使用下面的代码紧随 `Evaluate` 方法后创建 `SaveModelAsFile` 方法：</span><span class="sxs-lookup"><span data-stu-id="6747e-300">Create the `SaveModelAsFile` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="6747e-301">`SaveModelAsFile` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="6747e-301">The `SaveModelAsFile` method executes the following tasks:</span></span>

* <span data-ttu-id="6747e-302">将模型保存为 .zip 文件。</span><span class="sxs-lookup"><span data-stu-id="6747e-302">Saves the model as a .zip file.</span></span>

<span data-ttu-id="6747e-303">接下来，创建一个方法来保存模型，以便它可以在其他应用程序中重用和使用。</span><span class="sxs-lookup"><span data-stu-id="6747e-303">Next, create a method to save the model so that it can be reused and consumed in other applications.</span></span> <span data-ttu-id="6747e-304">`ITransformer` 有一个在 `_modelPath` 全局字段中采用的 <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> 方法和一个 <xref:System.IO.Stream> 方法。</span><span class="sxs-lookup"><span data-stu-id="6747e-304">The `ITransformer` has a <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> method that takes in the `_modelPath` global field, and a <xref:System.IO.Stream>.</span></span> <span data-ttu-id="6747e-305">要将其保存为 zip 文件，将在调用 `SaveTo` 方法之前立即创建 `FileStream`。</span><span class="sxs-lookup"><span data-stu-id="6747e-305">To save this as a zip file, you'll create the `FileStream` immediately before calling the `SaveTo` method.</span></span> <span data-ttu-id="6747e-306">将以下代码作为下一行添加到 `SaveModelAsFile` 方法中：</span><span class="sxs-lookup"><span data-stu-id="6747e-306">Add the following code to the `SaveModelAsFile` method as the next line:</span></span>

[!code-csharp[SaveToMethod](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#SaveModel "Add the SaveTo Method")]

<span data-ttu-id="6747e-307">还可以使用以下代码通过使用 `_modelPath` 编写控制台消息来显示文件的写入位置：</span><span class="sxs-lookup"><span data-stu-id="6747e-307">You could also display where the file was written by writing a console message with the `_modelPath`, using the following code:</span></span>

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="predict-the-test-data-outcome-with-the-saved-model"></a><span data-ttu-id="6747e-308">使用保存的模型预测测试数据结果</span><span class="sxs-lookup"><span data-stu-id="6747e-308">Predict the test data outcome with the saved model</span></span>

<span data-ttu-id="6747e-309">使用下面的代码紧随 `Evaluate` 方法后创建 `UseModelWithSingleItem` 方法：</span><span class="sxs-lookup"><span data-stu-id="6747e-309">Create the `UseModelWithSingleItem` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void UseModelWithSingleItem(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="6747e-310">`UseModelWithSingleItem` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="6747e-310">The `UseModelWithSingleItem` method executes the following tasks:</span></span>

* <span data-ttu-id="6747e-311">创建测试数据的单个注释。</span><span class="sxs-lookup"><span data-stu-id="6747e-311">Creates a single comment of test data.</span></span>
* <span data-ttu-id="6747e-312">根据测试数据预测情绪。</span><span class="sxs-lookup"><span data-stu-id="6747e-312">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="6747e-313">结合测试数据和预测进行报告。</span><span class="sxs-lookup"><span data-stu-id="6747e-313">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="6747e-314">显示预测结果。</span><span class="sxs-lookup"><span data-stu-id="6747e-314">Displays the predicted results.</span></span>

<span data-ttu-id="6747e-315">使用下面的代码，在 `Evaluate` 方法调用的正下方，从 `Main` 方法中添加对新方法的调用：</span><span class="sxs-lookup"><span data-stu-id="6747e-315">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallUseModelWithSingleItem](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallUseModelWithSingleItem "Call the UseModelWithSingleItem method")]

<span data-ttu-id="6747e-316">虽然 `model` 是对多行数据进行操作的 `transformer`，但是一个非常常见的生产场景是，需要对单个示例进行预测。</span><span class="sxs-lookup"><span data-stu-id="6747e-316">While the `model` is a `transformer` that operates on many rows of data, a very common production scenario is a need for predictions on individual examples.</span></span> <span data-ttu-id="6747e-317"><xref:Microsoft.ML.PredictionEngine%602> 是从 `CreatePredictionEngine` 方法返回的包装器。</span><span class="sxs-lookup"><span data-stu-id="6747e-317">The <xref:Microsoft.ML.PredictionEngine%602> is a wrapper that is returned from the `CreatePredictionEngine` method.</span></span> <span data-ttu-id="6747e-318">让我们添加以下代码来创建 `PredictionEngine`，作为 `Predict` 方法中的第一行：</span><span class="sxs-lookup"><span data-stu-id="6747e-318">Let's add the following code to create the `PredictionEngine` as the first line in the `Predict` Method:</span></span>

[!code-csharp[CreatePredictionEngine](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreatePredictionEngine1 "Create the PredictionEngine")]
  
<span data-ttu-id="6747e-319">通过创建一个 `SentimentData` 实例，在 `Predict` 方法中添加一个注释来测试定型模型的预测：</span><span class="sxs-lookup"><span data-stu-id="6747e-319">Add a comment to test the trained model's prediction in the `Predict` method by creating an instance of `SentimentData`:</span></span>

[!code-csharp[PredictionData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateTestIssue1 "Create test data for single prediction")]

 <span data-ttu-id="6747e-320">可以使用它来预测单个注释数据实例的正面或负面情绪。</span><span class="sxs-lookup"><span data-stu-id="6747e-320">You can use that to predict the positive or negative sentiment of a single instance of the comment data.</span></span> <span data-ttu-id="6747e-321">要获得预测，请对数据使用 <xref:Microsoft.ML.PredictionEngine%602.Predict%2A>。</span><span class="sxs-lookup"><span data-stu-id="6747e-321">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="6747e-322">请注意，输入数据是一个字符串，且模型包含特征化。</span><span class="sxs-lookup"><span data-stu-id="6747e-322">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="6747e-323">管道在定型和预测期间同步。</span><span class="sxs-lookup"><span data-stu-id="6747e-323">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="6747e-324">不必专门为预测编写预处理/特征化代码，并且相同 API 负责批处理和一次性预测。</span><span class="sxs-lookup"><span data-stu-id="6747e-324">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span>

[!code-csharp[Predict](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Predict "Create a prediction of sentiment")]

### <a name="use-the-model-prediction"></a><span data-ttu-id="6747e-325">使用模型：预测</span><span class="sxs-lookup"><span data-stu-id="6747e-325">Use the model: prediction</span></span>

<span data-ttu-id="6747e-326">显示 `SentimentText` 和相应的情绪预测以便共享结果，并采取相应措施。</span><span class="sxs-lookup"><span data-stu-id="6747e-326">Display `SentimentText` and corresponding sentiment prediction in order to share the results and act on them accordingly.</span></span> <span data-ttu-id="6747e-327">这称为操作化，使用返回的数据作为操作策略的一部分。</span><span class="sxs-lookup"><span data-stu-id="6747e-327">This is called operationalization, using the returned data as part of the operational policies.</span></span> <span data-ttu-id="6747e-328">使用以下 <xref:System.Console.WriteLine?displayProperty=nameWithType> 代码创建结果显示：</span><span class="sxs-lookup"><span data-stu-id="6747e-328">Create a display for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputPrediction](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#OutputPrediction "Display prediction output")]

## <a name="deploy-and-predict-with-a-loaded-model"></a><span data-ttu-id="6747e-329">使用加载模型部署和预测</span><span class="sxs-lookup"><span data-stu-id="6747e-329">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="6747e-330">使用下面的代码在 `SaveModelAsFile` 方法前创建 `UseLoadedModelWithBatchItems` 方法：</span><span class="sxs-lookup"><span data-stu-id="6747e-330">Create the `UseLoadedModelWithBatchItems` method, just before the `SaveModelAsFile` method, using the following code:</span></span>

```csharp
public static void UseLoadedModelWithBatchItems(MLContext mlContext)
{

}
```

<span data-ttu-id="6747e-331">`UseLoadedModelWithBatchItems` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="6747e-331">The `UseLoadedModelWithBatchItems` method executes the following tasks:</span></span>

* <span data-ttu-id="6747e-332">创建批处理测试数据。</span><span class="sxs-lookup"><span data-stu-id="6747e-332">Creates batch test data.</span></span>
* <span data-ttu-id="6747e-333">根据测试数据预测情绪。</span><span class="sxs-lookup"><span data-stu-id="6747e-333">Predicts sentiment based on test data.</span></span>
* <span data-ttu-id="6747e-334">结合测试数据和预测进行报告。</span><span class="sxs-lookup"><span data-stu-id="6747e-334">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="6747e-335">显示预测结果。</span><span class="sxs-lookup"><span data-stu-id="6747e-335">Displays the predicted results.</span></span>

<span data-ttu-id="6747e-336">使用下面的代码，在 `UseModelWithSingleItem` 方法调用的正下方，从 `Main` 方法中添加对新方法的调用：</span><span class="sxs-lookup"><span data-stu-id="6747e-336">Add a call to the new method from the `Main` method, right under the `UseModelWithSingleItem` method call, using the following code:</span></span>

[!code-csharp[CallPredictModelLoaded](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallUseLoadedModelWithBatchItems "Call the CallUseLoadedModelWithBatchItems method")]

<span data-ttu-id="6747e-337">添加一些评论，以测试 `UseLoadedModelWithBatchItems` 方法中的定型模型预测：</span><span class="sxs-lookup"><span data-stu-id="6747e-337">Add some comments to test the trained model's predictions in the `UseLoadedModelWithBatchItems` method:</span></span>

[!code-csharp[PredictionData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateTestIssues "Create test data for predictions")]

<span data-ttu-id="6747e-338">加载模型</span><span class="sxs-lookup"><span data-stu-id="6747e-338">Load the model</span></span>

[!code-csharp[LoadTheModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#LoadModel "Load the model")]

<span data-ttu-id="6747e-339">现在你有一个模型，可以使用它来预测使用 <xref:Microsoft.ML.ITransformer.Transform%2A> 方法的评论数据的正面或负面情绪。</span><span class="sxs-lookup"><span data-stu-id="6747e-339">Now that you have a model, you can use that to predict the Toxic or Non Toxic sentiment of the comment data using the <xref:Microsoft.ML.ITransformer.Transform%2A> method.</span></span> <span data-ttu-id="6747e-340">要获得预测，请使用新数据上的 `Predict`。</span><span class="sxs-lookup"><span data-stu-id="6747e-340">To get a prediction, use `Predict` on new data.</span></span> <span data-ttu-id="6747e-341">请注意，输入数据是一个字符串，且模型包含特征化。</span><span class="sxs-lookup"><span data-stu-id="6747e-341">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="6747e-342">管道在定型和预测期间同步。</span><span class="sxs-lookup"><span data-stu-id="6747e-342">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="6747e-343">不必专门为预测编写预处理/特征化代码，并且相同 API 负责批处理和一次性预测。</span><span class="sxs-lookup"><span data-stu-id="6747e-343">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span> <span data-ttu-id="6747e-344">在用于预测的 `UseLoadedModelWithBatchItems` 方法中添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="6747e-344">Add the following code to the `UseLoadedModelWithBatchItems` method for the predictions:</span></span>

[!code-csharp[Predict](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Prediction "Create predictions of sentiments")]

### <a name="use-the-loaded-model-for-prediction"></a><span data-ttu-id="6747e-345">使用加载后的模型进行预测</span><span class="sxs-lookup"><span data-stu-id="6747e-345">Use the loaded model for prediction</span></span>

<span data-ttu-id="6747e-346">显示 `SentimentText` 和相应的情绪预测以便共享结果，并采取相应措施。</span><span class="sxs-lookup"><span data-stu-id="6747e-346">Display `SentimentText` and corresponding sentiment prediction in order to share the results and act on them accordingly.</span></span> <span data-ttu-id="6747e-347">这称为操作化，使用返回的数据作为操作策略的一部分。</span><span class="sxs-lookup"><span data-stu-id="6747e-347">This is called operationalization, using the returned data as part of the operational policies.</span></span> <span data-ttu-id="6747e-348">使用以下 <xref:System.Console.WriteLine?displayProperty=nameWithType> 代码创建结果标头：</span><span class="sxs-lookup"><span data-stu-id="6747e-348">Create a header for the results using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[OutputHeaders](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddInfoMessage "Display prediction outputs")]

<span data-ttu-id="6747e-349">在显示预测结果之前，将情绪和预测结合在一起以查看原始评论及其预测情绪。</span><span class="sxs-lookup"><span data-stu-id="6747e-349">Before displaying the predicted results, combine the sentiment and prediction together to see the original comment with its predicted sentiment.</span></span> <span data-ttu-id="6747e-350">下面的代码使用 <xref:System.Linq.Enumerable.Zip%2A> 方法来实现此目的，因此请在下一步添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="6747e-350">The following code uses the <xref:System.Linq.Enumerable.Zip%2A> method to make that happen, so add that code next:</span></span>

[!code-csharp[BuildTuples](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#BuildSentimentPredictionPairs "Build the pairs of sentiment data and predictions")]

<span data-ttu-id="6747e-351">将 `SentimentText` 和 `Sentiment` 合并到一个类后，现在可以使用 <xref:System.Console.WriteLine?displayProperty=nameWithType> 方法来显示结果：</span><span class="sxs-lookup"><span data-stu-id="6747e-351">Now that you've combined the `SentimentText` and `Sentiment` into a class, you can display the results using the <xref:System.Console.WriteLine?displayProperty=nameWithType> method:</span></span>

[!code-csharp[DisplayPredictions](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DisplayResults "Display the predictions")]

<span data-ttu-id="6747e-352">因为推测的元组元素名称是 C# 7.1 中的新功能，且项目的默认语言版本为 C# 7.0，你需要将语言版本更改为 C# 7.1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="6747e-352">Because inferred tuple element names are a new feature in C# 7.1 and the default language version of the project is C# 7.0, you need to change the language version to C# 7.1 or higher.</span></span>
<span data-ttu-id="6747e-353">要完成此操作，右键单击“解决方案资源管理器”中的项目节点，然后选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="6747e-353">To do that, right-click on the project node in **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="6747e-354">选择**生成**选项卡并选择**高级**按钮。</span><span class="sxs-lookup"><span data-stu-id="6747e-354">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="6747e-355">在下拉列表中，选择“C# 7.1”（或更高版本）。</span><span class="sxs-lookup"><span data-stu-id="6747e-355">In the dropdown, select  **C# 7.1** (or a higher version).</span></span> <span data-ttu-id="6747e-356">选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="6747e-356">Select the **OK** button.</span></span>

## <a name="results"></a><span data-ttu-id="6747e-357">结果</span><span class="sxs-lookup"><span data-stu-id="6747e-357">Results</span></span>

<span data-ttu-id="6747e-358">结果应如下所示。</span><span class="sxs-lookup"><span data-stu-id="6747e-358">Your results should be similar to the following.</span></span> <span data-ttu-id="6747e-359">管道处理期间，会显示消息。</span><span class="sxs-lookup"><span data-stu-id="6747e-359">As the pipeline processes, it displays messages.</span></span> <span data-ttu-id="6747e-360">你可能会看到警告或处理消息。</span><span class="sxs-lookup"><span data-stu-id="6747e-360">You may see warnings, or processing messages.</span></span> <span data-ttu-id="6747e-361">为清楚起见，已经从下面的结果中删除这些内容。</span><span class="sxs-lookup"><span data-stu-id="6747e-361">These have been removed from the following results for clarity.</span></span>

```console
Model quality metrics evaluation
--------------------------------
Accuracy: 79.14%
Auc: 86.27%
F1Score: 80.60%

=============== End of model evaluation ===============
The model is saved to C:\Tutorials\SentimentAnalysis\bin\Debug\netcoreapp2.1\Data\Model.zip

=============== Prediction Test of model with a single sample and test dataset ===============

Sentiment: This was a very bad steak | Prediction: Negative | Probability: 0.4641322
=============== End of Predictions ===============


=============== Prediction Test of loaded model with a multiple samples ===============

Sentiment: This was a horrible meal | Prediction: Negative | Probability: 0.1391833
Sentiment: I love this spaghetti. | Prediction: Positive | Probability: 0.9819039
=============== End of predictions ===============

=============== End of process ===============
Press any key to continue . . .

```

<span data-ttu-id="6747e-362">祝贺你！</span><span class="sxs-lookup"><span data-stu-id="6747e-362">Congratulations!</span></span> <span data-ttu-id="6747e-363">现在，你已成功生成用于分类和预测消息情绪的机器学习模型。</span><span class="sxs-lookup"><span data-stu-id="6747e-363">You've now successfully built a machine learning model for classifying and predicting messages sentiment.</span></span> 

<span data-ttu-id="6747e-364">生成成功的模型是一个迭代过程。</span><span class="sxs-lookup"><span data-stu-id="6747e-364">Building successful models is an iterative process.</span></span> <span data-ttu-id="6747e-365">由于本教程使用小型数据集来提供快速模型训练，因此该模型的初始质量较低。</span><span class="sxs-lookup"><span data-stu-id="6747e-365">This model has initial lower quality as the tutorial uses small datasets to provide quick model training.</span></span> <span data-ttu-id="6747e-366">如果对模型质量不满意，可以通过尝试提供更大的训练数据集，或通过为每种算法选择具有不同超参数的不同训练算法来改进它。</span><span class="sxs-lookup"><span data-stu-id="6747e-366">If you aren't satisfied with the model quality, you can try to improve it by providing larger training datasets or by choosing different training algorithms with different hyper-parameters for each algorithm.</span></span>

<span data-ttu-id="6747e-367">可以在 [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) 存储库中找到本教程的源代码。</span><span class="sxs-lookup"><span data-stu-id="6747e-367">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6747e-368">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6747e-368">Next steps</span></span>

<span data-ttu-id="6747e-369">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="6747e-369">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="6747e-370">了解问题</span><span class="sxs-lookup"><span data-stu-id="6747e-370">Understand the problem</span></span>
> * <span data-ttu-id="6747e-371">选择适当的机器学习算法</span><span class="sxs-lookup"><span data-stu-id="6747e-371">Select the appropriate machine learning algorithm</span></span>
> * <span data-ttu-id="6747e-372">准备数据</span><span class="sxs-lookup"><span data-stu-id="6747e-372">Prepare your data</span></span>
> * <span data-ttu-id="6747e-373">转换数据</span><span class="sxs-lookup"><span data-stu-id="6747e-373">Transform the data</span></span>
> * <span data-ttu-id="6747e-374">定型模型</span><span class="sxs-lookup"><span data-stu-id="6747e-374">Train the model</span></span>
> * <span data-ttu-id="6747e-375">评估模型</span><span class="sxs-lookup"><span data-stu-id="6747e-375">Evaluate the model</span></span>
> * <span data-ttu-id="6747e-376">使用训练的模型预测</span><span class="sxs-lookup"><span data-stu-id="6747e-376">Predict with the trained model</span></span>
> * <span data-ttu-id="6747e-377">使用加载模型部署和预测</span><span class="sxs-lookup"><span data-stu-id="6747e-377">Deploy and Predict with a loaded model</span></span>

<span data-ttu-id="6747e-378">进入下一教程了解详细信息</span><span class="sxs-lookup"><span data-stu-id="6747e-378">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="6747e-379">问题分类</span><span class="sxs-lookup"><span data-stu-id="6747e-379">Issue Classification</span></span>](github-issue-classification.md)

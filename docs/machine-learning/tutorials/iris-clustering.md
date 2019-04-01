---
title: 使用聚类分析学习器对鸢尾花分类 - ML.NET
description: 了解如何在聚类分析方案中使用 ML.NET
author: pkulikov
ms.author: johalex
ms.date: 03/18/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: be59760091767b7229d80693cd69434581a8b140
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2019
ms.locfileid: "58634409"
---
# <a name="tutorial-cluster-iris-flowers-using-a-clustering-learner-with-mlnet"></a><span data-ttu-id="ddc37-103">教程：借助 ML.NET 使用聚类分析学习器对鸢尾花分类</span><span class="sxs-lookup"><span data-stu-id="ddc37-103">Tutorial: Cluster iris flowers using a clustering learner with ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="ddc37-104">本主题引用 ML.NET（目前处于预览状态），且材料可能会更改。</span><span class="sxs-lookup"><span data-stu-id="ddc37-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="ddc37-105">有关详细信息，请参阅 [ML.NET 简介](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)。</span><span class="sxs-lookup"><span data-stu-id="ddc37-105">For more information, see the [ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="ddc37-106">此教程和相关示例目前使用的是 ML.NET 版本 0.11。</span><span class="sxs-lookup"><span data-stu-id="ddc37-106">This tutorial and related sample are currently using **ML.NET version 0.11**.</span></span> <span data-ttu-id="ddc37-107">有关详细信息，请参阅 [dotnet/machinelearning GitHub 存储库](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)上的发行说明。</span><span class="sxs-lookup"><span data-stu-id="ddc37-107">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="ddc37-108">本教程演示如何使用 ML.NET 为[鸢尾花数据集](https://en.wikipedia.org/wiki/Iris_flower_data_set)构建[聚类分析模型](../resources/tasks.md#clustering)。</span><span class="sxs-lookup"><span data-stu-id="ddc37-108">This tutorial illustrates how to use ML.NET to build a [clustering model](../resources/tasks.md#clustering) for the [iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set).</span></span>

<span data-ttu-id="ddc37-109">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="ddc37-109">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="ddc37-110">了解问题</span><span class="sxs-lookup"><span data-stu-id="ddc37-110">Understand the problem</span></span>
> - <span data-ttu-id="ddc37-111">选择适当的机器学习任务</span><span class="sxs-lookup"><span data-stu-id="ddc37-111">Select the appropriate machine learning task</span></span>
> - <span data-ttu-id="ddc37-112">准备数据</span><span class="sxs-lookup"><span data-stu-id="ddc37-112">Prepare the data</span></span>
> - <span data-ttu-id="ddc37-113">加载和转换数据</span><span class="sxs-lookup"><span data-stu-id="ddc37-113">Load and transform the data</span></span>
> - <span data-ttu-id="ddc37-114">选择学习算法</span><span class="sxs-lookup"><span data-stu-id="ddc37-114">Choose a learning algorithm</span></span>
> - <span data-ttu-id="ddc37-115">定型模型</span><span class="sxs-lookup"><span data-stu-id="ddc37-115">Train the model</span></span>
> - <span data-ttu-id="ddc37-116">使用预测模型</span><span class="sxs-lookup"><span data-stu-id="ddc37-116">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ddc37-117">系统必备</span><span class="sxs-lookup"><span data-stu-id="ddc37-117">Prerequisites</span></span>

- <span data-ttu-id="ddc37-118">安装了“.NET Core 跨平台开发”工作负载的 [Visual Studio 2017 15.6 或更高版本](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)。</span><span class="sxs-lookup"><span data-stu-id="ddc37-118">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="ddc37-119">了解问题</span><span class="sxs-lookup"><span data-stu-id="ddc37-119">Understand the problem</span></span>

<span data-ttu-id="ddc37-120">此问题的本质即基于花卉特征将鸢尾花数据归入不同的组。</span><span class="sxs-lookup"><span data-stu-id="ddc37-120">This problem is about dividing the set of iris flowers in different groups based on the flower features.</span></span> <span data-ttu-id="ddc37-121">这些特征包括：花萼的长度和宽度以及花瓣的长度和宽度。</span><span class="sxs-lookup"><span data-stu-id="ddc37-121">Those features are the length and width of a sepal and the length and width of a petal.</span></span> <span data-ttu-id="ddc37-122">此教程假设每朵花的类型都是未知的。</span><span class="sxs-lookup"><span data-stu-id="ddc37-122">For this tutorial, assume that the type of each flower is unknown.</span></span> <span data-ttu-id="ddc37-123">需通过这些特征了解数据集的结构，并预测数据实例与此结构的拟合程度。</span><span class="sxs-lookup"><span data-stu-id="ddc37-123">You want to learn the structure of a data set from the features and predict how a data instance fits this structure.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="ddc37-124">选择适当的机器学习任务</span><span class="sxs-lookup"><span data-stu-id="ddc37-124">Select the appropriate machine learning task</span></span>

<span data-ttu-id="ddc37-125">鉴于不知道每朵花属于哪个分组，应选择[非监管式机器学习](../resources/glossary.md#unsupervised-machine-learning)任务。</span><span class="sxs-lookup"><span data-stu-id="ddc37-125">As you don't know to which group each flower belongs to, you choose the [unsupervised machine learning](../resources/glossary.md#unsupervised-machine-learning) task.</span></span> <span data-ttu-id="ddc37-126">为将数据归入不同的组，并使同一组中的元素互相之间更为相似（与其他组中的元素相比），应使用[聚类分析](../resources/tasks.md#clustering)机器学习任务。</span><span class="sxs-lookup"><span data-stu-id="ddc37-126">To divide a data set in groups in such a way that elements in the same group are more similar to each other than to those in other groups, use a [clustering](../resources/tasks.md#clustering) machine learning task.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="ddc37-127">创建控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="ddc37-127">Create a console application</span></span>

1. <span data-ttu-id="ddc37-128">打开 Visual Studio 2017。</span><span class="sxs-lookup"><span data-stu-id="ddc37-128">Open Visual Studio 2017.</span></span> <span data-ttu-id="ddc37-129">从菜单栏中选择“文件” > “新建” > “项目”。</span><span class="sxs-lookup"><span data-stu-id="ddc37-129">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="ddc37-130">在“新项目”对话框中，依次选择“Visual C#”和“.NET Core”节点。</span><span class="sxs-lookup"><span data-stu-id="ddc37-130">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="ddc37-131">然后，选择“控制台应用程序(.NET Core)”项目模板。</span><span class="sxs-lookup"><span data-stu-id="ddc37-131">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="ddc37-132">在“名称”文本框中，键入“IrisFlowerClustering”，然后选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="ddc37-132">In the **Name** text box, type "IrisFlowerClustering" and then select the **OK** button.</span></span>

1. <span data-ttu-id="ddc37-133">在项目中创建一个名为“数据”的目录来保存数据集和模型文件：</span><span class="sxs-lookup"><span data-stu-id="ddc37-133">Create a directory named *Data* in your project to store the data set and model files:</span></span>

    <span data-ttu-id="ddc37-134">在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新文件夹”。</span><span class="sxs-lookup"><span data-stu-id="ddc37-134">In **Solution Explorer**, right-click the project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="ddc37-135">键入“Data”，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="ddc37-135">Type "Data" and hit Enter.</span></span>

1. <span data-ttu-id="ddc37-136">安装“Microsoft.ML NuGet”包：</span><span class="sxs-lookup"><span data-stu-id="ddc37-136">Install the **Microsoft.ML** NuGet package:</span></span>

    <span data-ttu-id="ddc37-137">在“解决方案资源管理器”中，右键单击项目，然后选择“管理 NuGet 包”。</span><span class="sxs-lookup"><span data-stu-id="ddc37-137">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="ddc37-138">将“nuget.org”选择为“包源”，选择“浏览”选项卡并搜索“Microsoft.ML”，在列表中选择该包，然后选择“安装”按钮。</span><span class="sxs-lookup"><span data-stu-id="ddc37-138">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="ddc37-139">选择“预览更改”对话框上的“确定”按钮，如果你同意所列包的许可条款，则选择“接受许可”对话框上的“我接受”按钮。</span><span class="sxs-lookup"><span data-stu-id="ddc37-139">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="prepare-the-data"></a><span data-ttu-id="ddc37-140">准备数据</span><span class="sxs-lookup"><span data-stu-id="ddc37-140">Prepare the data</span></span>

1. <span data-ttu-id="ddc37-141">下载 [iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) 数据集并将其保存至在上一步中创建的“数据”文件夹。</span><span class="sxs-lookup"><span data-stu-id="ddc37-141">Download the [iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) data set and save it to the *Data* folder you've created at the previous step.</span></span> <span data-ttu-id="ddc37-142">若要详细了解鸢尾花数据集，请参阅[鸢尾花数据集](https://en.wikipedia.org/wiki/Iris_flower_data_set)维基百科页面，以及该数据集的源[鸢尾花数据集](https://archive.ics.uci.edu/ml/datasets/Iris)页面。</span><span class="sxs-lookup"><span data-stu-id="ddc37-142">For more information about the iris data set, see the [Iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set) Wikipedia page and the [Iris Data Set](https://archive.ics.uci.edu/ml/datasets/Iris) page, which is the source of the data set.</span></span>

1. <span data-ttu-id="ddc37-143">在“解决方案资源管理器”中，右键单击“iris.data”文件并选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="ddc37-143">In **Solution Explorer**, right-click the *iris.data* file and select **Properties**.</span></span> <span data-ttu-id="ddc37-144">在“高级”下，将“复制到输出目录”的值更改为“如果较新则复制”。</span><span class="sxs-lookup"><span data-stu-id="ddc37-144">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="ddc37-145">该 iris.data 文件包含五列，分别代表以下内容：</span><span class="sxs-lookup"><span data-stu-id="ddc37-145">The *iris.data* file contains five columns that represent:</span></span>

- <span data-ttu-id="ddc37-146">花萼长度（厘米）</span><span class="sxs-lookup"><span data-stu-id="ddc37-146">sepal length in centimetres</span></span>
- <span data-ttu-id="ddc37-147">花萼宽度（厘米）</span><span class="sxs-lookup"><span data-stu-id="ddc37-147">sepal width in centimetres</span></span>
- <span data-ttu-id="ddc37-148">花瓣长度（厘米）</span><span class="sxs-lookup"><span data-stu-id="ddc37-148">petal length in centimetres</span></span>
- <span data-ttu-id="ddc37-149">花瓣宽度（厘米）</span><span class="sxs-lookup"><span data-stu-id="ddc37-149">petal width in centimetres</span></span>
- <span data-ttu-id="ddc37-150">鸢尾花类型</span><span class="sxs-lookup"><span data-stu-id="ddc37-150">type of iris flower</span></span>

<span data-ttu-id="ddc37-151">考虑到聚类分析示例，本教程忽略最后一列。</span><span class="sxs-lookup"><span data-stu-id="ddc37-151">For the sake of the clustering example, this tutorial ignores the last column.</span></span>

## <a name="create-data-classes"></a><span data-ttu-id="ddc37-152">创建数据类</span><span class="sxs-lookup"><span data-stu-id="ddc37-152">Create data classes</span></span>

<span data-ttu-id="ddc37-153">创建输入数据和预测类：</span><span class="sxs-lookup"><span data-stu-id="ddc37-153">Create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="ddc37-154">在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新项”。</span><span class="sxs-lookup"><span data-stu-id="ddc37-154">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="ddc37-155">在“添加新项”对话框中，选择“类”并将“名称”字段更改为“IrisData.cs”。</span><span class="sxs-lookup"><span data-stu-id="ddc37-155">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *IrisData.cs*.</span></span> <span data-ttu-id="ddc37-156">然后，选择“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="ddc37-156">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="ddc37-157">将以下 `using` 指令添加到新文件：</span><span class="sxs-lookup"><span data-stu-id="ddc37-157">Add the following `using` directive to the new file:</span></span>

   [!code-csharp[Add necessary usings](~/samples/machine-learning/tutorials/IrisFlowerClustering/IrisData.cs#Usings)]

<span data-ttu-id="ddc37-158">删除现有类定义并向“IrisData.cs”文件添加以下代码，其中定义了两个类 `IrisData` 和 `ClusterPrediction`：</span><span class="sxs-lookup"><span data-stu-id="ddc37-158">Remove the existing class definition and add the following code, which defines the classes `IrisData` and `ClusterPrediction`, to the *IrisData.cs* file:</span></span>

[!code-csharp[Define data classes](~/samples/machine-learning/tutorials/IrisFlowerClustering/IrisData.cs#ClassDefinitions)]

<span data-ttu-id="ddc37-159">`IrisData` 是输入数据类，并且具有针对数据集每个特征的定义。</span><span class="sxs-lookup"><span data-stu-id="ddc37-159">`IrisData` is the input data class and has definitions for each feature from the data set.</span></span> <span data-ttu-id="ddc37-160">使用 [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute) 属性在数据集文件中指定源列的索引。</span><span class="sxs-lookup"><span data-stu-id="ddc37-160">Use the [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute) attribute to specify the indices of the source columns in the data set file.</span></span>

<span data-ttu-id="ddc37-161">`ClusterPrediction` 类表示应用到 `IrisData` 实例的聚类分析模型的输出。</span><span class="sxs-lookup"><span data-stu-id="ddc37-161">The `ClusterPrediction` class represents the output of the clustering model applied to an `IrisData` instance.</span></span> <span data-ttu-id="ddc37-162">使用 [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute) 属性将 `PredictedClusterId` 和 `Distances` 字段分别绑定至 PredictedLabel 和 Score 列。</span><span class="sxs-lookup"><span data-stu-id="ddc37-162">Use the [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute to bind the `PredictedClusterId` and `Distances` fields to the **PredictedLabel** and **Score** columns respectively.</span></span> <span data-ttu-id="ddc37-163">在聚类分析任务中，这些列具有以下含义：</span><span class="sxs-lookup"><span data-stu-id="ddc37-163">In case of the clustering task those columns have the following meaning:</span></span>

- <span data-ttu-id="ddc37-164">**PredictedLabel** 列包含所预测的群集的 ID。</span><span class="sxs-lookup"><span data-stu-id="ddc37-164">**PredictedLabel** column contains the ID of the predicted cluster.</span></span>
- <span data-ttu-id="ddc37-165">**Score** 列包含一个数组，该数组中的数与群集形心之间的距离为欧氏距离的平方。</span><span class="sxs-lookup"><span data-stu-id="ddc37-165">**Score** column contains an array with squared Euclidean distances to the cluster centroids.</span></span> <span data-ttu-id="ddc37-166">该数组的长度等于群集数。</span><span class="sxs-lookup"><span data-stu-id="ddc37-166">The array length is equal to the number of clusters.</span></span>

> [!NOTE]
> <span data-ttu-id="ddc37-167">使用 `float` 类型来表示输入和预测数据类中的浮点值。</span><span class="sxs-lookup"><span data-stu-id="ddc37-167">Use the `float` type to represent floating-point values in the input and prediction data classes.</span></span>

## <a name="define-data-and-model-paths"></a><span data-ttu-id="ddc37-168">定义数据和模型路径</span><span class="sxs-lookup"><span data-stu-id="ddc37-168">Define data and model paths</span></span>

<span data-ttu-id="ddc37-169">返回到 Program.cs 文件并添加两个字段，以保存数据集文件以及用于保存模型的文件的路径：</span><span class="sxs-lookup"><span data-stu-id="ddc37-169">Go back to the *Program.cs* file and add two fields to hold the paths to the data set file and to the file to save the model:</span></span>

- <span data-ttu-id="ddc37-170">`_dataPath` 包含具有用于定型模型的数据集的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="ddc37-170">`_dataPath` contains the path to the file with the data set used to train the model.</span></span>
- <span data-ttu-id="ddc37-171">`_modelPath` 包含用于存储定型模型的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="ddc37-171">`_modelPath` contains the path to the file where the trained model is stored.</span></span>

<span data-ttu-id="ddc37-172">将以下代码添加到 `Main` 方法上方，以指定这些路径：</span><span class="sxs-lookup"><span data-stu-id="ddc37-172">Add the following code right above the `Main` method to specify those paths:</span></span>

[!code-csharp[Initialize paths](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#Paths)]

<span data-ttu-id="ddc37-173">要编译前面的代码，请将以下 `using` 指令添加到 Program.cs 文件顶部：</span><span class="sxs-lookup"><span data-stu-id="ddc37-173">To make the preceding code compile, add the following `using` directives at the top of the *Program.cs* file:</span></span>

[!code-csharp[Add usings for paths](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#UsingsForPaths)]

## <a name="create-ml-context"></a><span data-ttu-id="ddc37-174">创建 ML 上下文</span><span class="sxs-lookup"><span data-stu-id="ddc37-174">Create ML context</span></span>

<span data-ttu-id="ddc37-175">将以下附加 `using` 指令添加到 Program.cs 文件顶部：</span><span class="sxs-lookup"><span data-stu-id="ddc37-175">Add the following additional `using` directives to the top of the *Program.cs* file:</span></span>

[!code-csharp[Add Microsoft.ML usings](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#MLUsings)]

<span data-ttu-id="ddc37-176">在 `Main` 方法中，请使用以下代码替换 `Console.WriteLine("Hello World!");` 行：</span><span class="sxs-lookup"><span data-stu-id="ddc37-176">In the `Main` method, replace the `Console.WriteLine("Hello World!");` line with the following code:</span></span>

[!code-csharp[Create ML context](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#CreateContext)]

<span data-ttu-id="ddc37-177"><xref:Microsoft.ML.MLContext?displayProperty=nameWithType> 类表示机器学习环境，并提供用于数据加载、模型定型、预测和其他任务的日志记录和入口点的机制。</span><span class="sxs-lookup"><span data-stu-id="ddc37-177">The <xref:Microsoft.ML.MLContext?displayProperty=nameWithType> class represents the machine learning environment and provides mechanisms for logging and entry points for data loading, model training, prediction, and other tasks.</span></span> <span data-ttu-id="ddc37-178">这在概念上相当于在实体框架中使用 `DbContext`。</span><span class="sxs-lookup"><span data-stu-id="ddc37-178">This is comparable conceptually to using `DbContext` in Entity Framework.</span></span>

## <a name="setup-data-loading"></a><span data-ttu-id="ddc37-179">设置数据加载</span><span class="sxs-lookup"><span data-stu-id="ddc37-179">Setup data loading</span></span>

<span data-ttu-id="ddc37-180">将以下代码添加到 `Main` 方法以设置加载数据的方式：</span><span class="sxs-lookup"><span data-stu-id="ddc37-180">Add the following code to the `Main` method to setup the way to load data:</span></span>

[!code-csharp[Create text loader](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#SetupTextLoader)]

<span data-ttu-id="ddc37-181">使用 [LoadFromTextFile 方法](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29)的泛型 `MLContext.Data.LoadFromTextFile` 包装器加载数据。</span><span class="sxs-lookup"><span data-stu-id="ddc37-181">Load the data using the generic `MLContext.Data.LoadFromTextFile` wrapper for the [LoadFromTextFile method](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29).</span></span> <span data-ttu-id="ddc37-182">它返回 <xref:Microsoft.Data.DataView.IDataView>，该对象从 `IrisData` 数据模型类型推断出数据集架构，使用数据集标头并用逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="ddc37-182">It returns a <xref:Microsoft.Data.DataView.IDataView> which infers the dataset schema from the `IrisData` data model type, uses the dataset header and is separated by a comma.</span></span>

## <a name="create-a-learning-pipeline"></a><span data-ttu-id="ddc37-183">创建学习管道</span><span class="sxs-lookup"><span data-stu-id="ddc37-183">Create a learning pipeline</span></span>

<span data-ttu-id="ddc37-184">对于本教程，聚类分析任务的学习管道包含两个以下步骤：</span><span class="sxs-lookup"><span data-stu-id="ddc37-184">For this tutorial, the learning pipeline of the clustering task comprises two following steps:</span></span>

- <span data-ttu-id="ddc37-185">将加载的列连接到“Features”列，由聚类分析训练程序使用；</span><span class="sxs-lookup"><span data-stu-id="ddc37-185">concatenate loaded columns into one **Features** column, which is used by a clustering trainer;</span></span>
- <span data-ttu-id="ddc37-186">借助 <xref:Microsoft.ML.Trainers.KMeansPlusPlusTrainer> 训练程序使用 k - 平均值 + + 聚类分析算法来定型模型。</span><span class="sxs-lookup"><span data-stu-id="ddc37-186">use a <xref:Microsoft.ML.Trainers.KMeansPlusPlusTrainer> trainer to train the model using the k-means++ clustering algorithm.</span></span>

<span data-ttu-id="ddc37-187">将以下代码添加到 `Main` 方法中：</span><span class="sxs-lookup"><span data-stu-id="ddc37-187">Add the following code to the `Main` method:</span></span>

[!code-csharp[Create pipeline](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#CreatePipeline)]

<span data-ttu-id="ddc37-188">该代码指定该数据集应拆分为三个群集。</span><span class="sxs-lookup"><span data-stu-id="ddc37-188">The code specifies that the data set should be split in three clusters.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="ddc37-189">定型模型</span><span class="sxs-lookup"><span data-stu-id="ddc37-189">Train the model</span></span>

<span data-ttu-id="ddc37-190">前述部分中添加的步骤准备了用于定型的管道，但尚未执行。</span><span class="sxs-lookup"><span data-stu-id="ddc37-190">The steps added in the preceding sections prepared the pipeline for training, however, none have been executed.</span></span> <span data-ttu-id="ddc37-191">将以下行添加到 `Main` 方法以执行数据加载和模型定型：</span><span class="sxs-lookup"><span data-stu-id="ddc37-191">Add the following line to the `Main` method to perform data loading and model training:</span></span>

[!code-csharp[Train the model](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#TrainModel)]

### <a name="save-the-model"></a><span data-ttu-id="ddc37-192">保存模型</span><span class="sxs-lookup"><span data-stu-id="ddc37-192">Save the model</span></span>

<span data-ttu-id="ddc37-193">此时，你具有可以集成到任何现有或新 .NET 应用程序的模型。</span><span class="sxs-lookup"><span data-stu-id="ddc37-193">At this point, you have a model that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="ddc37-194">要将模型保存为 .zip 文件，请将以下代码添加到 `Main` 方法中：</span><span class="sxs-lookup"><span data-stu-id="ddc37-194">To save your model to a .zip file, add the following code to the `Main` method:</span></span>

[!code-csharp[Save the model](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#SaveModel)]

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="ddc37-195">使用预测模型</span><span class="sxs-lookup"><span data-stu-id="ddc37-195">Use the model for predictions</span></span>

<span data-ttu-id="ddc37-196">要进行预测，请使用通过转换器管道获取输入类型实例和生成输出类型实例的 <xref:Microsoft.ML.PredictionEngine%602> 类。</span><span class="sxs-lookup"><span data-stu-id="ddc37-196">To make predictions, use the <xref:Microsoft.ML.PredictionEngine%602> class that takes instances of the input type through the transformer pipeline and produces instances of the output type.</span></span> <span data-ttu-id="ddc37-197">将以下行添加到 `Main` 方法以创建该类的实例：</span><span class="sxs-lookup"><span data-stu-id="ddc37-197">Add the following line to the `Main` method to create an instance of that class:</span></span>

[!code-csharp[Create predictor](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#Predictor)]

<span data-ttu-id="ddc37-198">将 `TestIrisData` 类创建到房屋测试数据实例：</span><span class="sxs-lookup"><span data-stu-id="ddc37-198">Create the `TestIrisData` class to house test data instances:</span></span>

1. <span data-ttu-id="ddc37-199">在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新项”。</span><span class="sxs-lookup"><span data-stu-id="ddc37-199">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="ddc37-200">在“添加新项”对话框中，选择“类”并将“名称”字段更改为“TestIrisData.cs”。</span><span class="sxs-lookup"><span data-stu-id="ddc37-200">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TestIrisData.cs*.</span></span> <span data-ttu-id="ddc37-201">然后，选择“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="ddc37-201">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="ddc37-202">将类修改为静态，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="ddc37-202">Modify the class to be static like in the following example:</span></span>

   [!code-csharp[Make class static](~/samples/machine-learning/tutorials/IrisFlowerClustering/TestIrisData.cs#Static)]

<span data-ttu-id="ddc37-203">本教程引入此类中的一个鸢尾花数据实例。</span><span class="sxs-lookup"><span data-stu-id="ddc37-203">This tutorial introduces one iris data instance within this class.</span></span> <span data-ttu-id="ddc37-204">可以添加其他方案来体验此模型。</span><span class="sxs-lookup"><span data-stu-id="ddc37-204">You can add other scenarios to experiment with the model.</span></span> <span data-ttu-id="ddc37-205">将下面的代码添加到 `TestIrisData` 类中：</span><span class="sxs-lookup"><span data-stu-id="ddc37-205">Add the following code into the `TestIrisData` class:</span></span>

[!code-csharp[Test data](~/samples/machine-learning/tutorials/IrisFlowerClustering/TestIrisData.cs#TestData)]

<span data-ttu-id="ddc37-206">若要查找指定项所属的群集，请返回至 Program.cs 文件并将以下代码添加进 `Main` 方法：</span><span class="sxs-lookup"><span data-stu-id="ddc37-206">To find out the cluster to which the specified item belongs to, go back to the *Program.cs* file and add the following code into the `Main` method:</span></span>

[!code-csharp[Predict and output results](~/samples/machine-learning/tutorials/IrisFlowerClustering/Program.cs#PredictionExample)]

<span data-ttu-id="ddc37-207">运行该程序以查看哪个群集包含所指定的数据实例，以及从该实例到群集形心的距离的平方值。</span><span class="sxs-lookup"><span data-stu-id="ddc37-207">Run the program to see which cluster contains the specified data instance and squared distances from that instance to the cluster centroids.</span></span> <span data-ttu-id="ddc37-208">结果应如下所示：</span><span class="sxs-lookup"><span data-stu-id="ddc37-208">Your results should be similar to the following:</span></span>

```text
Cluster: 2
Distances: 11.69127 0.02159119 25.59896
```

<span data-ttu-id="ddc37-209">祝贺你！</span><span class="sxs-lookup"><span data-stu-id="ddc37-209">Congratulations!</span></span> <span data-ttu-id="ddc37-210">现已成功地生成用于鸢尾花聚类分析的机器学习模型并将其用于预测。</span><span class="sxs-lookup"><span data-stu-id="ddc37-210">You've now successfully built a machine learning model for iris clustering and used it to make predictions.</span></span> <span data-ttu-id="ddc37-211">可以在 [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisFlowerClustering) GitHub 存储库中找到本教程的源代码。</span><span class="sxs-lookup"><span data-stu-id="ddc37-211">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisFlowerClustering) GitHub repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ddc37-212">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ddc37-212">Next steps</span></span>

<span data-ttu-id="ddc37-213">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="ddc37-213">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="ddc37-214">了解问题</span><span class="sxs-lookup"><span data-stu-id="ddc37-214">Understand the problem</span></span>
> - <span data-ttu-id="ddc37-215">选择适当的机器学习任务</span><span class="sxs-lookup"><span data-stu-id="ddc37-215">Select the appropriate machine learning task</span></span>
> - <span data-ttu-id="ddc37-216">准备数据</span><span class="sxs-lookup"><span data-stu-id="ddc37-216">Prepare the data</span></span>
> - <span data-ttu-id="ddc37-217">加载和转换数据</span><span class="sxs-lookup"><span data-stu-id="ddc37-217">Load and transform the data</span></span>
> - <span data-ttu-id="ddc37-218">选择学习算法</span><span class="sxs-lookup"><span data-stu-id="ddc37-218">Choose a learning algorithm</span></span>
> - <span data-ttu-id="ddc37-219">定型模型</span><span class="sxs-lookup"><span data-stu-id="ddc37-219">Train the model</span></span>
> - <span data-ttu-id="ddc37-220">使用预测模型</span><span class="sxs-lookup"><span data-stu-id="ddc37-220">Use the model for predictions</span></span>

<span data-ttu-id="ddc37-221">查看我们的 GitHub 存储库以继续学习，并找到更多示例。</span><span class="sxs-lookup"><span data-stu-id="ddc37-221">Check out our GitHub repository to continue learning and find more samples.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="ddc37-222">dotnet/machinelearning GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="ddc37-222">dotnet/machinelearning GitHub repository</span></span>](https://github.com/dotnet/machinelearning/)

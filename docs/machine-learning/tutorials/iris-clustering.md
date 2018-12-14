---
title: 使用聚类分析学习器对鸢尾花分类 - ML.NET
description: 了解如何在聚类分析方案中使用 ML.NET
author: pkulikov
ms.author: johalex
ms.date: 07/02/2018
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 5bd73c774f60466daaf52215c34e7e17b5f5cc9c
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53145618"
---
# <a name="tutorial-cluster-iris-flowers-using-a-clustering-learner-with-mlnet"></a><span data-ttu-id="24af2-103">教程：借助 ML.NET 使用聚类分析学习器对鸢尾花分类</span><span class="sxs-lookup"><span data-stu-id="24af2-103">Tutorial: Cluster iris flowers using a clustering learner with ML.NET</span></span>

> [!NOTE]
> <span data-ttu-id="24af2-104">本主题引用 ML.NET（目前处于预览状态），且材料可能会更改。</span><span class="sxs-lookup"><span data-stu-id="24af2-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="24af2-105">有关详细信息，请参阅 [ML.NET 简介](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)。</span><span class="sxs-lookup"><span data-stu-id="24af2-105">For more information, see the [ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="24af2-106">本教程演示如何使用 ML.NET 为[鸢尾花数据集](https://en.wikipedia.org/wiki/Iris_flower_data_set)构建[聚类分析模型](../resources/tasks.md#clustering)。</span><span class="sxs-lookup"><span data-stu-id="24af2-106">This tutorial illustrates how to use ML.NET to build a [clustering model](../resources/tasks.md#clustering) for the [iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set).</span></span>

<span data-ttu-id="24af2-107">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="24af2-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="24af2-108">了解问题</span><span class="sxs-lookup"><span data-stu-id="24af2-108">Understand the problem</span></span>
> - <span data-ttu-id="24af2-109">选择适当的机器学习任务</span><span class="sxs-lookup"><span data-stu-id="24af2-109">Select the appropriate machine learning task</span></span>
> - <span data-ttu-id="24af2-110">准备数据</span><span class="sxs-lookup"><span data-stu-id="24af2-110">Prepare the data</span></span>
> - <span data-ttu-id="24af2-111">加载和转换数据</span><span class="sxs-lookup"><span data-stu-id="24af2-111">Load and transform the data</span></span>
> - <span data-ttu-id="24af2-112">选择学习算法</span><span class="sxs-lookup"><span data-stu-id="24af2-112">Choose a learning algorithm</span></span>
> - <span data-ttu-id="24af2-113">定型模型</span><span class="sxs-lookup"><span data-stu-id="24af2-113">Train the model</span></span>
> - <span data-ttu-id="24af2-114">使用预测模型</span><span class="sxs-lookup"><span data-stu-id="24af2-114">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="24af2-115">系统必备</span><span class="sxs-lookup"><span data-stu-id="24af2-115">Prerequisites</span></span>

- <span data-ttu-id="24af2-116">安装了“.NET Core 跨平台开发”工作负载的 [Visual Studio 2017 15.6 或更高版本](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)。</span><span class="sxs-lookup"><span data-stu-id="24af2-116">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="24af2-117">了解问题</span><span class="sxs-lookup"><span data-stu-id="24af2-117">Understand the problem</span></span>

<span data-ttu-id="24af2-118">此问题的本质即基于花卉特征将鸢尾花数据归入不同的组。</span><span class="sxs-lookup"><span data-stu-id="24af2-118">This problem is about dividing the set of iris flowers in different groups based on the flower features.</span></span> <span data-ttu-id="24af2-119">这些特征包括：花萼的长度和宽度以及花瓣的长度和宽度。</span><span class="sxs-lookup"><span data-stu-id="24af2-119">Those features are the length and width of a sepal and the length and width of a petal.</span></span> <span data-ttu-id="24af2-120">此教程假设每朵花的类型都是未知的。</span><span class="sxs-lookup"><span data-stu-id="24af2-120">For this tutorial, assume that the type of each flower is unknown.</span></span> <span data-ttu-id="24af2-121">需通过这些特征了解数据集的结构，并预测数据实例与此结构的拟合程度。</span><span class="sxs-lookup"><span data-stu-id="24af2-121">You want to learn the structure of a data set from the features and predict how a data instance fits this structure.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="24af2-122">选择适当的机器学习任务</span><span class="sxs-lookup"><span data-stu-id="24af2-122">Select the appropriate machine learning task</span></span>

<span data-ttu-id="24af2-123">鉴于不知道每朵花属于哪个分组，应选择[非监管式机器学习](../resources/glossary.md#unsupervised-machine-learning)任务。</span><span class="sxs-lookup"><span data-stu-id="24af2-123">As you don't know to which group each flower belongs to, you choose the [unsupervised machine learning](../resources/glossary.md#unsupervised-machine-learning) task.</span></span> <span data-ttu-id="24af2-124">为将数据归入不同的组，并使同一组中的元素互相之间更为相似（与其他组中的元素相比），应使用[聚类分析](../resources/tasks.md#clustering)机器学习任务。</span><span class="sxs-lookup"><span data-stu-id="24af2-124">To divide a data set in groups in such a way that elements in the same group are more similar to each other than to those in other groups, use a [clustering](../resources/tasks.md#clustering) machine learning task.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="24af2-125">创建控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="24af2-125">Create a console application</span></span>

1. <span data-ttu-id="24af2-126">打开 Visual Studio 2017。</span><span class="sxs-lookup"><span data-stu-id="24af2-126">Open Visual Studio 2017.</span></span> <span data-ttu-id="24af2-127">从菜单栏中选择“文件” > “新建” > “项目”。</span><span class="sxs-lookup"><span data-stu-id="24af2-127">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="24af2-128">在“新项目”对话框中，依次选择“Visual C#”和“.NET Core”节点。</span><span class="sxs-lookup"><span data-stu-id="24af2-128">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="24af2-129">然后，选择“控制台应用程序(.NET Core)”项目模板。</span><span class="sxs-lookup"><span data-stu-id="24af2-129">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="24af2-130">在“名称”文本框中，键入“IrisClustering”，然后选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="24af2-130">In the **Name** text box, type "IrisClustering" and then select the **OK** button.</span></span>

1. <span data-ttu-id="24af2-131">在项目中创建一个名为“数据”的目录来保存数据集和模型文件：</span><span class="sxs-lookup"><span data-stu-id="24af2-131">Create a directory named *Data* in your project to store the data set and model files:</span></span>

    <span data-ttu-id="24af2-132">在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新文件夹”。</span><span class="sxs-lookup"><span data-stu-id="24af2-132">In **Solution Explorer**, right-click the project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="24af2-133">键入“数据”，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="24af2-133">Type "Data" and hit Enter.</span></span>

1. <span data-ttu-id="24af2-134">安装“Microsoft.ML NuGet”包：</span><span class="sxs-lookup"><span data-stu-id="24af2-134">Install the **Microsoft.ML** NuGet package:</span></span>

    <span data-ttu-id="24af2-135">在“解决方案资源管理器”中，右键单击项目，然后选择“管理 NuGet 包”。</span><span class="sxs-lookup"><span data-stu-id="24af2-135">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="24af2-136">将“nuget.org”选择为“包源”，选择“浏览”选项卡并搜索“Microsoft.ML”，在列表中选择该包，然后选择“安装”按钮。</span><span class="sxs-lookup"><span data-stu-id="24af2-136">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="24af2-137">选择“预览更改”对话框上的“确定”按钮，如果你同意所列包的许可条款，则选择“接受许可”对话框上的“我接受”按钮。</span><span class="sxs-lookup"><span data-stu-id="24af2-137">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="prepare-the-data"></a><span data-ttu-id="24af2-138">准备数据</span><span class="sxs-lookup"><span data-stu-id="24af2-138">Prepare the data</span></span>

1. <span data-ttu-id="24af2-139">下载 [iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) 数据集并将其保存至在上一步中创建的“数据”文件夹。</span><span class="sxs-lookup"><span data-stu-id="24af2-139">Download the [iris.data](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) data set and save it to the *Data* folder you've created at the previous step.</span></span> <span data-ttu-id="24af2-140">若要详细了解鸢尾花数据集，请参阅[鸢尾花数据集](https://en.wikipedia.org/wiki/Iris_flower_data_set)维基百科页面，以及该数据集的源[鸢尾花数据集](http://archive.ics.uci.edu/ml/datasets/Iris)页面。</span><span class="sxs-lookup"><span data-stu-id="24af2-140">For more information about the iris data set, see the [Iris flower data set](https://en.wikipedia.org/wiki/Iris_flower_data_set) Wikipedia page and the [Iris Data Set](http://archive.ics.uci.edu/ml/datasets/Iris) page, which is the source of the data set.</span></span>

1. <span data-ttu-id="24af2-141">在“解决方案资源管理器”中，右键单击“iris.data”文件并选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="24af2-141">In **Solution Explorer**, right-click the *iris.data* file and select **Properties**.</span></span> <span data-ttu-id="24af2-142">在“高级”下，将“复制到输出目录”的值更改为“如果较新则复制”。</span><span class="sxs-lookup"><span data-stu-id="24af2-142">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="24af2-143">该 iris.data 文件包含五列，分别代表以下内容：</span><span class="sxs-lookup"><span data-stu-id="24af2-143">The *iris.data* file contains five columns that represent:</span></span>

- <span data-ttu-id="24af2-144">花萼长度（厘米）</span><span class="sxs-lookup"><span data-stu-id="24af2-144">sepal length in centimetres</span></span>
- <span data-ttu-id="24af2-145">花萼宽度（厘米）</span><span class="sxs-lookup"><span data-stu-id="24af2-145">sepal width in centimetres</span></span>
- <span data-ttu-id="24af2-146">花瓣长度（厘米）</span><span class="sxs-lookup"><span data-stu-id="24af2-146">petal length in centimetres</span></span>
- <span data-ttu-id="24af2-147">花瓣宽度（厘米）</span><span class="sxs-lookup"><span data-stu-id="24af2-147">petal width in centimetres</span></span>
- <span data-ttu-id="24af2-148">鸢尾花类型</span><span class="sxs-lookup"><span data-stu-id="24af2-148">type of iris flower</span></span>

<span data-ttu-id="24af2-149">考虑到聚类分析示例，本教程忽略最后一列。</span><span class="sxs-lookup"><span data-stu-id="24af2-149">For the sake of the clustering example, this tutorial ignores the last column.</span></span>

## <a name="create-data-classes"></a><span data-ttu-id="24af2-150">创建数据类</span><span class="sxs-lookup"><span data-stu-id="24af2-150">Create data classes</span></span>

<span data-ttu-id="24af2-151">创建输入数据和预测类：</span><span class="sxs-lookup"><span data-stu-id="24af2-151">Create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="24af2-152">在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新项”。</span><span class="sxs-lookup"><span data-stu-id="24af2-152">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="24af2-153">在“添加新项”对话框中，选择“类”并将“名称”字段更改为“IrisData.cs”。</span><span class="sxs-lookup"><span data-stu-id="24af2-153">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *IrisData.cs*.</span></span> <span data-ttu-id="24af2-154">然后，选择“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="24af2-154">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="24af2-155">将以下 `using` 指令添加到新文件：</span><span class="sxs-lookup"><span data-stu-id="24af2-155">Add the following `using` directive to the new file:</span></span>

   [!code-csharp[Add necessary usings](../../../samples/machine-learning/tutorials/IrisClustering/IrisData.cs#1)]

<span data-ttu-id="24af2-156">删除现有类定义并向“IrisData.cs”文件添加以下代码，其中定义了两个类 `IrisData` 和 `ClusterPrediction`：</span><span class="sxs-lookup"><span data-stu-id="24af2-156">Remove the existing class definition and add the following code, which defines the classes `IrisData` and `ClusterPrediction`, to the *IrisData.cs* file:</span></span>

[!code-csharp[Define data classes](../../../samples/machine-learning/tutorials/IrisClustering/IrisData.cs#2)]

<span data-ttu-id="24af2-157">`IrisData` 是输入数据类，并且具有针对数据集每个特征的定义。</span><span class="sxs-lookup"><span data-stu-id="24af2-157">`IrisData` is the input data class and has definitions for each feature from the data set.</span></span> <span data-ttu-id="24af2-158">使用 [Column](xref:Microsoft.ML.Runtime.Api.ColumnAttribute) 属性在数据集文件中指定源列的索引。</span><span class="sxs-lookup"><span data-stu-id="24af2-158">Use the [Column](xref:Microsoft.ML.Runtime.Api.ColumnAttribute) attribute to specify the indices of the source columns in the data set file.</span></span>

<span data-ttu-id="24af2-159">`ClusterPrediction` 类表示应用到 `IrisData` 实例的聚类分析模型的输出。</span><span class="sxs-lookup"><span data-stu-id="24af2-159">The `ClusterPrediction` class represents the output of the clustering model applied to an `IrisData` instance.</span></span> <span data-ttu-id="24af2-160">使用 [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute) 属性将 `PredictedClusterId` 和 `Distances` 字段分别绑定至 PredictedLabel 和 Score 列。</span><span class="sxs-lookup"><span data-stu-id="24af2-160">Use the [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute) attribute to bind the `PredictedClusterId` and `Distances` fields to the **PredictedLabel** and **Score** columns respectively.</span></span> <span data-ttu-id="24af2-161">在聚类分析任务中，这些列具有以下含义：</span><span class="sxs-lookup"><span data-stu-id="24af2-161">In case of the clustering task those columns have the following meaning:</span></span>

- <span data-ttu-id="24af2-162">**PredictedLabel** 列包含所预测的群集的 ID。</span><span class="sxs-lookup"><span data-stu-id="24af2-162">**PredictedLabel** column contains the ID of the predicted cluster.</span></span>
- <span data-ttu-id="24af2-163">**Score** 列包含一个数组，该数组中的数与群集形心之间的距离为欧氏距离的平方。</span><span class="sxs-lookup"><span data-stu-id="24af2-163">**Score** column contains an array with squared Euclidean distances to the cluster centroids.</span></span> <span data-ttu-id="24af2-164">该数组的长度等于群集数。</span><span class="sxs-lookup"><span data-stu-id="24af2-164">The array length is equal to the number of clusters.</span></span>

> [!NOTE]
> <span data-ttu-id="24af2-165">使用 `float` 类型来表示输入和预测数据类中的浮点值。</span><span class="sxs-lookup"><span data-stu-id="24af2-165">Use the `float` type to represent floating-point values in the input and prediction data classes.</span></span>

## <a name="define-data-and-model-paths"></a><span data-ttu-id="24af2-166">定义数据和模型路径</span><span class="sxs-lookup"><span data-stu-id="24af2-166">Define data and model paths</span></span>

<span data-ttu-id="24af2-167">返回到 Program.cs 文件并添加两个字段，以保存数据集文件以及用于保存模型的文件的路径：</span><span class="sxs-lookup"><span data-stu-id="24af2-167">Go back to the *Program.cs* file and add two fields to hold the paths to the data set file and to the file to save the model:</span></span>

- <span data-ttu-id="24af2-168">`_dataPath` 包含具有用于定型模型的数据集的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="24af2-168">`_dataPath` contains the path to the file with the data set used to train the model.</span></span>
- <span data-ttu-id="24af2-169">`_modelPath` 包含用于存储定型模型的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="24af2-169">`_modelPath` contains the path to the file where the trained model is stored.</span></span>

<span data-ttu-id="24af2-170">将以下代码添加到 `Main` 方法上方，以指定这些路径：</span><span class="sxs-lookup"><span data-stu-id="24af2-170">Add the following code right above the `Main` method to specify those paths:</span></span>

[!code-csharp[Initialize paths](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#1)]

<span data-ttu-id="24af2-171">要编译前面的代码，请将以下 `using` 指令添加到 Program.cs 文件顶部：</span><span class="sxs-lookup"><span data-stu-id="24af2-171">To make the preceding code compile, add the following `using` directives at the top of the *Program.cs* file:</span></span>

[!code-csharp[Add usings for paths](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#2)]

## <a name="create-a-learning-pipeline"></a><span data-ttu-id="24af2-172">创建学习管道</span><span class="sxs-lookup"><span data-stu-id="24af2-172">Create a learning pipeline</span></span>

<span data-ttu-id="24af2-173">将以下附加 `using` 指令添加到 Program.cs 文件顶部：</span><span class="sxs-lookup"><span data-stu-id="24af2-173">Add the following additional `using` directives to the top of the *Program.cs* file:</span></span>

[!code-csharp[Add Microsoft.ML usings](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#3)]

<span data-ttu-id="24af2-174">将 `Main` 方法中的 `Console.WriteLine("Hello World!")` 替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="24af2-174">In the `Main` method, replace the `Console.WriteLine("Hello World!")` with the following code:</span></span>

[!code-csharp[Call the Train method](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#4)]

<span data-ttu-id="24af2-175">`Train` 方法定型模型。</span><span class="sxs-lookup"><span data-stu-id="24af2-175">The `Train` method trains the model.</span></span> <span data-ttu-id="24af2-176">使用以下代码在 `Main` 方法下创建该方法：</span><span class="sxs-lookup"><span data-stu-id="24af2-176">Create that method just below the `Main` method, using the following code:</span></span>

```csharp
private static PredictionModel<IrisData, ClusterPrediction> Train()
{

}
```

<span data-ttu-id="24af2-177">学习管道加载所有数据和所需的算法来定型模型。</span><span class="sxs-lookup"><span data-stu-id="24af2-177">The learning pipeline loads all of the data and algorithms necessary to train the model.</span></span> <span data-ttu-id="24af2-178">将以下代码添加到 `Train` 方法：</span><span class="sxs-lookup"><span data-stu-id="24af2-178">Add the following code into the `Train` method:</span></span>

[!code-csharp[Initialize pipeline](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#5)]

## <a name="load-and-transform-data"></a><span data-ttu-id="24af2-179">加载和转换数据</span><span class="sxs-lookup"><span data-stu-id="24af2-179">Load and transform data</span></span>

<span data-ttu-id="24af2-180">第一个步骤是加载定型数据集。</span><span class="sxs-lookup"><span data-stu-id="24af2-180">The first step to perform is to load the training data set.</span></span> <span data-ttu-id="24af2-181">在本例中，定型数据集存储在具有 `_dataPath` 字段所定义路径的文本文件中。</span><span class="sxs-lookup"><span data-stu-id="24af2-181">In our case, the training data set is stored in the text file with a path defined by the `_dataPath` field.</span></span> <span data-ttu-id="24af2-182">文件中的列用逗号 (",") 分割。</span><span class="sxs-lookup"><span data-stu-id="24af2-182">Columns in the file are separated by the comma (",").</span></span> <span data-ttu-id="24af2-183">将以下代码添加到 `Train` 方法：</span><span class="sxs-lookup"><span data-stu-id="24af2-183">Add the following code into the `Train` method:</span></span>

[!code-csharp[Add step to load data](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#6)]

<span data-ttu-id="24af2-184">下一步是使用 <xref:Microsoft.ML.Legacy.Transforms.ColumnConcatenator> 转换类将所有特征列合并到“特征”列。</span><span class="sxs-lookup"><span data-stu-id="24af2-184">The next step is to combine all of the feature columns into the **Features** column using the <xref:Microsoft.ML.Legacy.Transforms.ColumnConcatenator> transformation class.</span></span> <span data-ttu-id="24af2-185">默认情况下，学习算法仅处理“特征”列的特征。</span><span class="sxs-lookup"><span data-stu-id="24af2-185">By default, a learning algorithm processes only features from the **Features** column.</span></span> <span data-ttu-id="24af2-186">添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="24af2-186">Add the following code:</span></span>

[!code-csharp[Add step to concatenate columns](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#7)]

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="24af2-187">选择学习算法</span><span class="sxs-lookup"><span data-stu-id="24af2-187">Choose a learning algorithm</span></span>

<span data-ttu-id="24af2-188">在将数据添加到管道，并将其转换为正确的输入格式之后，可以选择学习算法（学习器）。</span><span class="sxs-lookup"><span data-stu-id="24af2-188">After adding the data to the pipeline and transforming it into the correct input format, you select a learning algorithm (**learner**).</span></span> <span data-ttu-id="24af2-189">学习器定型模型。</span><span class="sxs-lookup"><span data-stu-id="24af2-189">The learner trains the model.</span></span> <span data-ttu-id="24af2-190">ML.NET 提供一种 <xref:Microsoft.ML.Legacy.Trainers.KMeansPlusPlusClusterer> 学习器，该学习器通过一种经过改进的、用于选择初始群集形心的方法来实现 [k-means 算法](https://en.wikipedia.org/wiki/K-means_clustering)。</span><span class="sxs-lookup"><span data-stu-id="24af2-190">ML.NET provides a <xref:Microsoft.ML.Legacy.Trainers.KMeansPlusPlusClusterer> learner that implements [k-means algorithm](https://en.wikipedia.org/wiki/K-means_clustering) with an improved method for choosing the initial cluster centroids.</span></span>

<span data-ttu-id="24af2-191">将下面的代码添加到在上一步中添加的数据处理代码后面的 `Train` 方法中：</span><span class="sxs-lookup"><span data-stu-id="24af2-191">Add the following code into the `Train` method following the data processing code added in the previous step:</span></span>

[!code-csharp[Add a learner step](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#8)]

<span data-ttu-id="24af2-192">使用 <xref:Microsoft.ML.Legacy.Trainers.KMeansPlusPlusClusterer.K?displayProperty=nameWithType> 属性指定群集数。</span><span class="sxs-lookup"><span data-stu-id="24af2-192">Use the <xref:Microsoft.ML.Legacy.Trainers.KMeansPlusPlusClusterer.K?displayProperty=nameWithType> property to specify number of clusters.</span></span> <span data-ttu-id="24af2-193">上述代码指定该数据集应拆分为三个群集。</span><span class="sxs-lookup"><span data-stu-id="24af2-193">The code above specifies that the data set should be split in three clusters.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="24af2-194">定型模型</span><span class="sxs-lookup"><span data-stu-id="24af2-194">Train the model</span></span>

<span data-ttu-id="24af2-195">前述部分中添加的步骤准备了用于定型的管道，但尚未执行。</span><span class="sxs-lookup"><span data-stu-id="24af2-195">The steps added in the preceding sections prepared the pipeline for training, however, none have been executed.</span></span> <span data-ttu-id="24af2-196">`pipeline.Train<TInput, TOutput>` 方法生成的模型接收 `TInput` 类型实例并输出 `TOutput` 类型实例。</span><span class="sxs-lookup"><span data-stu-id="24af2-196">The `pipeline.Train<TInput, TOutput>` method produces the model that takes in an instance of the `TInput` type and outputs an instance of the `TOutput` type.</span></span> <span data-ttu-id="24af2-197">将以下代码添加到 `Train` 方法：</span><span class="sxs-lookup"><span data-stu-id="24af2-197">Add the following code into the `Train` method:</span></span>

[!code-csharp[Train the model and return](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#9)]

### <a name="save-the-model"></a><span data-ttu-id="24af2-198">保存模型</span><span class="sxs-lookup"><span data-stu-id="24af2-198">Save the model</span></span>

<span data-ttu-id="24af2-199">此时，你具有可以集成到任何现有或新 .NET 应用程序的模型。</span><span class="sxs-lookup"><span data-stu-id="24af2-199">At this point, you have a model that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="24af2-200">若要将模型保存到 .zip 文件，请将下面的代码添加到调用 `Train` 方法下的 `Main` 方法中：</span><span class="sxs-lookup"><span data-stu-id="24af2-200">To save your model to a .zip file, add the following code to the `Main` method below the call to the `Train` method:</span></span>

[!code-csharp[Save the model](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#10)]

<span data-ttu-id="24af2-201">在 `Main` 方法中使用 `await` 意味着 `Main` 方法必须具有 `async` 修饰符并返回 `Task`：</span><span class="sxs-lookup"><span data-stu-id="24af2-201">Using `await` in the `Main` method means the `Main` method must have the `async` modifier and return a `Task`:</span></span>

[!code-csharp[Make the Main method async](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#11)]

<span data-ttu-id="24af2-202">还需要将以下 `using` 指令添加到 Program.cs 文件顶部：</span><span class="sxs-lookup"><span data-stu-id="24af2-202">You also need to add the following `using` directive at the top of the *Program.cs* file:</span></span>

[!code-csharp[Add System.Threading.Tasks using](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#12)]

<span data-ttu-id="24af2-203">由于 `async Main` 方法是 C# 7.1 中的新增功能，且项目的默认语言版本为 C# 7.0，因此需要将语言版本更改为 C# 7.1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="24af2-203">Because the `async Main` method is the feature added in C# 7.1 and the default language version of the project is C# 7.0, you need to change the language version to C# 7.1 or higher.</span></span> <span data-ttu-id="24af2-204">要完成此操作，右键单击“解决方案资源管理器”中的项目节点，然后选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="24af2-204">To do that, right-click the project node in **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="24af2-205">选择**生成**选项卡并选择**高级**按钮。</span><span class="sxs-lookup"><span data-stu-id="24af2-205">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="24af2-206">在下拉列表中，选择“C# 7.1”（或更高版本）。</span><span class="sxs-lookup"><span data-stu-id="24af2-206">In the dropdown, select  **C# 7.1** (or a higher version).</span></span> <span data-ttu-id="24af2-207">选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="24af2-207">Select the **OK** button.</span></span>

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="24af2-208">使用预测模型</span><span class="sxs-lookup"><span data-stu-id="24af2-208">Use the model for predictions</span></span>

<span data-ttu-id="24af2-209">将 `TestIrisData` 类创建到房屋测试数据实例：</span><span class="sxs-lookup"><span data-stu-id="24af2-209">Create the `TestIrisData` class to house test data instances:</span></span>

1. <span data-ttu-id="24af2-210">在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新项”。</span><span class="sxs-lookup"><span data-stu-id="24af2-210">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="24af2-211">在“添加新项”对话框中，选择“类”并将“名称”字段更改为“TestIrisData.cs”。</span><span class="sxs-lookup"><span data-stu-id="24af2-211">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TestIrisData.cs*.</span></span> <span data-ttu-id="24af2-212">然后，选择“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="24af2-212">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="24af2-213">将类修改为静态，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="24af2-213">Modify the class to be static like in the following example:</span></span>

   [!code-csharp[Make class static](../../../samples/machine-learning/tutorials/IrisClustering/TestIrisData.cs#1)]

<span data-ttu-id="24af2-214">本教程引入此类中的一个鸢尾花数据实例。</span><span class="sxs-lookup"><span data-stu-id="24af2-214">This tutorial introduces one iris data instance within this class.</span></span> <span data-ttu-id="24af2-215">可以添加其他方案来体验此模型。</span><span class="sxs-lookup"><span data-stu-id="24af2-215">You can add other scenarios to experiment with the model.</span></span> <span data-ttu-id="24af2-216">将下面的代码添加到 `TestIrisData` 类中：</span><span class="sxs-lookup"><span data-stu-id="24af2-216">Add the following code into the `TestIrisData` class:</span></span>

[!code-csharp[Test data](../../../samples/machine-learning/tutorials/IrisClustering/TestIrisData.cs#2)]

<span data-ttu-id="24af2-217">若要查找指定项所属的群集，请返回至 Program.cs 文件并将以下代码添加进 `Main` 方法：</span><span class="sxs-lookup"><span data-stu-id="24af2-217">To find out the cluster to which the specified item belongs to, go back to the *Program.cs* file and add the following code into the `Main` method:</span></span>

[!code-csharp[Predict and output results](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#13)]

<span data-ttu-id="24af2-218">运行该程序以查看哪个群集包含所指定的数据实例，以及从该实例到群集形心的距离的平方值。</span><span class="sxs-lookup"><span data-stu-id="24af2-218">Run the program to see which cluster contains the specified data instance and squared distances from that instance to the cluster centroids.</span></span> <span data-ttu-id="24af2-219">结果应如下所示。</span><span class="sxs-lookup"><span data-stu-id="24af2-219">Your results should be similar to the following.</span></span> <span data-ttu-id="24af2-220">在进行管道处理时，可能会显示警告或处理消息。</span><span class="sxs-lookup"><span data-stu-id="24af2-220">As the pipeline processes, it might display warnings or processing messages.</span></span> <span data-ttu-id="24af2-221">为清楚起见，已经从下面的输出中删除这些内容。</span><span class="sxs-lookup"><span data-stu-id="24af2-221">These have been removed from the following output for clarity.</span></span>

```text
Cluster: 2
Distances: 0.4192338 0.0008847713 0.9660053
```

<span data-ttu-id="24af2-222">祝贺你！</span><span class="sxs-lookup"><span data-stu-id="24af2-222">Congratulations!</span></span> <span data-ttu-id="24af2-223">现已成功地生成用于鸢尾花聚类分析的机器学习模型并将其用于预测。</span><span class="sxs-lookup"><span data-stu-id="24af2-223">You've now successfully built a machine learning model for iris clustering and used it to make predictions.</span></span> <span data-ttu-id="24af2-224">可以在 [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisClustering) GitHub 存储库中找到本教程的源代码。</span><span class="sxs-lookup"><span data-stu-id="24af2-224">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisClustering) GitHub repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="24af2-225">后续步骤</span><span class="sxs-lookup"><span data-stu-id="24af2-225">Next steps</span></span>

<span data-ttu-id="24af2-226">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="24af2-226">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="24af2-227">了解问题</span><span class="sxs-lookup"><span data-stu-id="24af2-227">Understand the problem</span></span>
> - <span data-ttu-id="24af2-228">选择适当的机器学习任务</span><span class="sxs-lookup"><span data-stu-id="24af2-228">Select the appropriate machine learning task</span></span>
> - <span data-ttu-id="24af2-229">准备数据</span><span class="sxs-lookup"><span data-stu-id="24af2-229">Prepare the data</span></span>
> - <span data-ttu-id="24af2-230">加载和转换数据</span><span class="sxs-lookup"><span data-stu-id="24af2-230">Load and transform the data</span></span>
> - <span data-ttu-id="24af2-231">选择学习算法</span><span class="sxs-lookup"><span data-stu-id="24af2-231">Choose a learning algorithm</span></span>
> - <span data-ttu-id="24af2-232">定型模型</span><span class="sxs-lookup"><span data-stu-id="24af2-232">Train the model</span></span>
> - <span data-ttu-id="24af2-233">使用预测模型</span><span class="sxs-lookup"><span data-stu-id="24af2-233">Use the model for predictions</span></span>

<span data-ttu-id="24af2-234">查看我们的 GitHub 存储库以继续学习，并找到更多示例。</span><span class="sxs-lookup"><span data-stu-id="24af2-234">Check out our GitHub repository to continue learning and find more samples.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="24af2-235">dotnet/machinelearning GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="24af2-235">dotnet/machinelearning GitHub repository</span></span>](https://github.com/dotnet/machinelearning/)

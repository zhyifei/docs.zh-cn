---
title: 在 ML.NET 中使用回归学习器预测费用
description: 在 ML.NET 中使用回归学习器预测费用。
author: aditidugar
ms.author: johalex
ms.date: 03/20/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 79b8abd0fb01062900b2ae4e14c02d8844bb6ef9
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59295973"
---
# <a name="tutorial-predict-prices-using-a-regression-learner-with-mlnet"></a><span data-ttu-id="13291-103">教程：在 ML.NET 中使用回归学习器预测费用</span><span class="sxs-lookup"><span data-stu-id="13291-103">Tutorial: Predict prices using a regression learner with ML.NET</span></span>

<span data-ttu-id="13291-104">本教程演示如何使用 ML.NET 构建[回归模型](../resources/glossary.md#regression)来预测费用，特别是纽约市出租车费。</span><span class="sxs-lookup"><span data-stu-id="13291-104">This tutorial illustrates how to use ML.NET to build a [regression model](../resources/glossary.md#regression) for predicting prices, specifically, New York City taxi fares.</span></span>

> [!NOTE]
> <span data-ttu-id="13291-105">本主题引用 ML.NET（目前处于预览状态），且材料可能会更改。</span><span class="sxs-lookup"><span data-stu-id="13291-105">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="13291-106">有关详细信息，请参阅 [ML.NET 简介](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)。</span><span class="sxs-lookup"><span data-stu-id="13291-106">For more information, see the [ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="13291-107">此教程和相关示例目前使用的是 ML.NET 版本 0.11。</span><span class="sxs-lookup"><span data-stu-id="13291-107">This tutorial and related sample are currently using **ML.NET version 0.11**.</span></span> <span data-ttu-id="13291-108">有关详细信息，请参阅 [dotnet/machinelearning GitHub 存储库](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)上的发行说明。</span><span class="sxs-lookup"><span data-stu-id="13291-108">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="13291-109">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="13291-109">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="13291-110">了解问题</span><span class="sxs-lookup"><span data-stu-id="13291-110">Understand the problem</span></span>
> * <span data-ttu-id="13291-111">选择适当的机器学习任务</span><span class="sxs-lookup"><span data-stu-id="13291-111">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="13291-112">准备和了解数据</span><span class="sxs-lookup"><span data-stu-id="13291-112">Prepare and understand the data</span></span>
> * <span data-ttu-id="13291-113">创建学习管道</span><span class="sxs-lookup"><span data-stu-id="13291-113">Create a learning pipeline</span></span>
> * <span data-ttu-id="13291-114">加载和转换数据</span><span class="sxs-lookup"><span data-stu-id="13291-114">Load and transform the data</span></span>
> * <span data-ttu-id="13291-115">选择学习算法</span><span class="sxs-lookup"><span data-stu-id="13291-115">Choose a learning algorithm</span></span>
> * <span data-ttu-id="13291-116">定型模型</span><span class="sxs-lookup"><span data-stu-id="13291-116">Train the model</span></span>
> * <span data-ttu-id="13291-117">评估模型</span><span class="sxs-lookup"><span data-stu-id="13291-117">Evaluate the model</span></span>
> * <span data-ttu-id="13291-118">使用预测模型</span><span class="sxs-lookup"><span data-stu-id="13291-118">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="13291-119">系统必备</span><span class="sxs-lookup"><span data-stu-id="13291-119">Prerequisites</span></span>

* <span data-ttu-id="13291-120">安装了“.NET Core 跨平台开发”工作负载的 [Visual Studio 2017 15.6 或更高版本](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017)。</span><span class="sxs-lookup"><span data-stu-id="13291-120">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="13291-121">了解问题</span><span class="sxs-lookup"><span data-stu-id="13291-121">Understand the problem</span></span>

<span data-ttu-id="13291-122">此问题是有关“预测纽约市的出租车行程费用”。</span><span class="sxs-lookup"><span data-stu-id="13291-122">This problem is about predicting the fare of a taxi trip in New York City.</span></span> <span data-ttu-id="13291-123">从表面看，似乎只取决于行程距离。</span><span class="sxs-lookup"><span data-stu-id="13291-123">At first glance, it may seem to depend simply on the distance traveled.</span></span> <span data-ttu-id="13291-124">但是，由于其他因素（比如额外的乘客或使用信用卡而非现金付款），纽约的出租车供应商收费不同。</span><span class="sxs-lookup"><span data-stu-id="13291-124">However, taxi vendors in New York charge varying amounts for other factors such as additional passengers or paying with a credit card instead of cash.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="13291-125">选择适当的机器学习任务</span><span class="sxs-lookup"><span data-stu-id="13291-125">Select the appropriate machine learning task</span></span>

<span data-ttu-id="13291-126">你想要预测价格值，该值是基于数据集中的其他因素的实际值。</span><span class="sxs-lookup"><span data-stu-id="13291-126">You want to predict the price value, which is a real value, based on the other factors in the data set.</span></span> <span data-ttu-id="13291-127">要执行此操作，选择[回归](../resources/glossary.md#regression)机器学习任务。</span><span class="sxs-lookup"><span data-stu-id="13291-127">To do that you choose a [regression](../resources/glossary.md#regression) machine learning task.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="13291-128">创建控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="13291-128">Create a console application</span></span>

1. <span data-ttu-id="13291-129">打开 Visual Studio 2017。</span><span class="sxs-lookup"><span data-stu-id="13291-129">Open Visual Studio 2017.</span></span> <span data-ttu-id="13291-130">从菜单栏中选择“文件” > “新建” > “项目”。</span><span class="sxs-lookup"><span data-stu-id="13291-130">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="13291-131">在“新项目”对话框中，依次选择“Visual C#”和“.NET Core”节点。</span><span class="sxs-lookup"><span data-stu-id="13291-131">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="13291-132">然后，选择“控制台应用程序(.NET Core)”项目模板。</span><span class="sxs-lookup"><span data-stu-id="13291-132">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="13291-133">在“名称”文本框中，键入“TaxiFarePrediction”，然后选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="13291-133">In the **Name** text box, type "TaxiFarePrediction" and then select the **OK** button.</span></span>

1. <span data-ttu-id="13291-134">在项目中创建一个名为“数据”的目录来保存数据集和模型文件：</span><span class="sxs-lookup"><span data-stu-id="13291-134">Create a directory named *Data* in your project to store the data set and model files:</span></span>

    <span data-ttu-id="13291-135">在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新文件夹”。</span><span class="sxs-lookup"><span data-stu-id="13291-135">In **Solution Explorer**, right-click the project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="13291-136">键入“Data”，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="13291-136">Type "Data" and hit Enter.</span></span>

1. <span data-ttu-id="13291-137">安装“Microsoft.ML”NuGet 包：</span><span class="sxs-lookup"><span data-stu-id="13291-137">Install the **Microsoft.ML** NuGet Package:</span></span>

    <span data-ttu-id="13291-138">在“解决方案资源管理器”中，右键单击项目，然后选择“管理 NuGet 包”。</span><span class="sxs-lookup"><span data-stu-id="13291-138">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="13291-139">将“nuget.org”选择为“包源”，选择“浏览”选项卡并搜索“Microsoft.ML”，在列表中选择该包，然后选择“安装”按钮。</span><span class="sxs-lookup"><span data-stu-id="13291-139">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="13291-140">选择“预览更改”对话框上的“确定”按钮，如果你同意所列包的许可条款，则选择“接受许可”对话框上的“我接受”按钮。</span><span class="sxs-lookup"><span data-stu-id="13291-140">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="13291-141">准备和了解数据</span><span class="sxs-lookup"><span data-stu-id="13291-141">Prepare and understand the data</span></span>

1. <span data-ttu-id="13291-142">下载 [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) 和 [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) 数据集，并将它们保存到先前创建的“数据”文件夹。</span><span class="sxs-lookup"><span data-stu-id="13291-142">Download the [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) and the [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) data sets and save them to the *Data* folder you've created at the previous step.</span></span> <span data-ttu-id="13291-143">我们使用这些数据集定型机器学习模型，然后评估模型的准确性。</span><span class="sxs-lookup"><span data-stu-id="13291-143">We use these data sets to train the machine learning model and then evaluate how accurate the model is.</span></span> <span data-ttu-id="13291-144">这些数据集最初来自 [NYC TLC 出租车行程数据集](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml)。</span><span class="sxs-lookup"><span data-stu-id="13291-144">These data sets are originally from the [NYC TLC Taxi Trip data set](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span></span>

1. <span data-ttu-id="13291-145">在“解决方案资源管理器”中，右键单击每个 \*.csv 文件，然后选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="13291-145">In **Solution Explorer**, right-click each of the \*.csv files and select **Properties**.</span></span> <span data-ttu-id="13291-146">在“高级”下，将“复制到输出目录”的值更改为“如果较新则复制”。</span><span class="sxs-lookup"><span data-stu-id="13291-146">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

1. <span data-ttu-id="13291-147">打开“taxi-fare-train.csv”数据集并查看第一行中的列标题。</span><span class="sxs-lookup"><span data-stu-id="13291-147">Open the **taxi-fare-train.csv** data set and look at column headers in the first row.</span></span> <span data-ttu-id="13291-148">查看每个列。</span><span class="sxs-lookup"><span data-stu-id="13291-148">Take a look at each of the columns.</span></span> <span data-ttu-id="13291-149">了解数据并确定哪些列是“特征”以及哪些是“标签”。</span><span class="sxs-lookup"><span data-stu-id="13291-149">Understand the data and decide which columns are **features** and which one is the **label**.</span></span>

<span data-ttu-id="13291-150">“标签”是希望预测的列的标识符。</span><span class="sxs-lookup"><span data-stu-id="13291-150">The **label** is the identifier of the column you want to predict.</span></span> <span data-ttu-id="13291-151">标识的“特征”用于预测标签。</span><span class="sxs-lookup"><span data-stu-id="13291-151">The identified **features** are used to predict the label.</span></span>

<span data-ttu-id="13291-152">提供的数据集包含以下列：</span><span class="sxs-lookup"><span data-stu-id="13291-152">The provided data set contains the following columns:</span></span>

* <span data-ttu-id="13291-153">**vendor_id：** 出租车供应商的 ID 是一项特征。</span><span class="sxs-lookup"><span data-stu-id="13291-153">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
* <span data-ttu-id="13291-154">**rate_code：** 出租车行程的费率类型是一项特征。</span><span class="sxs-lookup"><span data-stu-id="13291-154">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
* <span data-ttu-id="13291-155">**passenger_count：** 行程中的乘客人数是一项特征。</span><span class="sxs-lookup"><span data-stu-id="13291-155">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
* <span data-ttu-id="13291-156">**trip_time_in_secs：** 这次行程所花的时间。</span><span class="sxs-lookup"><span data-stu-id="13291-156">**trip_time_in_secs:** The amount of time the trip took.</span></span> <span data-ttu-id="13291-157">希望在行程完成前预测行程费用。</span><span class="sxs-lookup"><span data-stu-id="13291-157">You want to predict the fare of the trip before the trip is completed.</span></span> <span data-ttu-id="13291-158">当时并不知道行程有多长。</span><span class="sxs-lookup"><span data-stu-id="13291-158">At that moment you don't know how long the trip would take.</span></span> <span data-ttu-id="13291-159">因此，行程时间不是一项特征，需要从模型删除此列。</span><span class="sxs-lookup"><span data-stu-id="13291-159">Thus, the trip time is not a feature and you'll exclude this column from the model.</span></span>
* <span data-ttu-id="13291-160">**trip_distance：** 行程距离是一项特征。</span><span class="sxs-lookup"><span data-stu-id="13291-160">**trip_distance:** The distance of the trip is a feature.</span></span>
* <span data-ttu-id="13291-161">**payment_type：** 付款方式（现金或信用卡）是一项特征。</span><span class="sxs-lookup"><span data-stu-id="13291-161">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
* <span data-ttu-id="13291-162">**fare_amount：** 支付的总出租车费用是一个标签。</span><span class="sxs-lookup"><span data-stu-id="13291-162">**fare_amount:** The total taxi fare paid is the label.</span></span>

## <a name="create-data-classes"></a><span data-ttu-id="13291-163">创建数据类</span><span class="sxs-lookup"><span data-stu-id="13291-163">Create data classes</span></span>

<span data-ttu-id="13291-164">创建输入数据和预测类：</span><span class="sxs-lookup"><span data-stu-id="13291-164">Create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="13291-165">在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新项”。</span><span class="sxs-lookup"><span data-stu-id="13291-165">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="13291-166">在“添加新项”对话框中，选择“类”并将“名称”字段更改为“TaxiTrip.cs”。</span><span class="sxs-lookup"><span data-stu-id="13291-166">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TaxiTrip.cs*.</span></span> <span data-ttu-id="13291-167">然后，选择“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="13291-167">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="13291-168">将以下 `using` 指令添加到新文件：</span><span class="sxs-lookup"><span data-stu-id="13291-168">Add the following `using` directives to the new file:</span></span>

   [!code-csharp[AddUsings](~/samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#1 "Add necessary usings")]

<span data-ttu-id="13291-169">删除现有类定义并向“TaxiTrip.cs”文件添加以下代码，其中有两个类 `TaxiTrip` 和 `TaxiTripFarePrediction`：</span><span class="sxs-lookup"><span data-stu-id="13291-169">Remove the existing class definition and add the following code, which has two classes `TaxiTrip` and `TaxiTripFarePrediction`, to the *TaxiTrip.cs* file:</span></span>

[!code-csharp[DefineTaxiTrip](~/samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#2 "Define the taxi trip and fare predictions classes")]

`TaxiTrip` <span data-ttu-id="13291-170">是输入数据类且具有针对每个数据集列的定义。</span><span class="sxs-lookup"><span data-stu-id="13291-170">is the input data class and has definitions for each of the data set columns.</span></span> <span data-ttu-id="13291-171">使用 <xref:Microsoft.ML.Data.LoadColumnAttribute> 属性在数据集中指定源列的索引。</span><span class="sxs-lookup"><span data-stu-id="13291-171">Use the <xref:Microsoft.ML.Data.LoadColumnAttribute> attribute to specify the indices of the source columns in the data set.</span></span>

<span data-ttu-id="13291-172">`TaxiTripFarePrediction` 类表示预测的结果。</span><span class="sxs-lookup"><span data-stu-id="13291-172">The `TaxiTripFarePrediction` class represents predicted results.</span></span> <span data-ttu-id="13291-173">它应用了单个浮动 `FareAmount` 字段，附带 `Score` <xref:Microsoft.ML.Data.ColumnNameAttribute> 属性。</span><span class="sxs-lookup"><span data-stu-id="13291-173">It has a single float field, `FareAmount`, with a `Score` <xref:Microsoft.ML.Data.ColumnNameAttribute> attribute applied.</span></span> <span data-ttu-id="13291-174">对于回归任务，“分数”列包含预测的标签值。</span><span class="sxs-lookup"><span data-stu-id="13291-174">In case of the regression task the **Score** column contains predicted label values.</span></span>

> [!NOTE]
> <span data-ttu-id="13291-175">使用 `float` 类型来表示输入和预测数据类中的浮点值。</span><span class="sxs-lookup"><span data-stu-id="13291-175">Use the `float` type to represent floating-point values in the input and prediction data classes.</span></span>

## <a name="define-data-and-model-paths"></a><span data-ttu-id="13291-176">定义数据和模型路径</span><span class="sxs-lookup"><span data-stu-id="13291-176">Define data and model paths</span></span>

<span data-ttu-id="13291-177">将以下附加的 `using` 语句添加到“Program.cs”文件顶部：</span><span class="sxs-lookup"><span data-stu-id="13291-177">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#1 "Add necessary usings")]

<span data-ttu-id="13291-178">需要创建三个字段，用于保留有数据集的文件的路径，以及用于保存模型的文件的路径：</span><span class="sxs-lookup"><span data-stu-id="13291-178">You need to create three fields to hold the paths to the files with data sets and the file to save the model:</span></span>

* `_trainDataPath` <span data-ttu-id="13291-179">包含具有用于定型模型的数据集的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="13291-179">contains the path to the file with the data set used to train the model.</span></span>
* `_testDataPath` <span data-ttu-id="13291-180">包含具有用于评估模型的数据集的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="13291-180">contains the path to the file with the data set used to evaluate the model.</span></span>
* `_modelPath` <span data-ttu-id="13291-181">包含用于存储定型模型的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="13291-181">contains the path to the file where the trained model is stored.</span></span>

<span data-ttu-id="13291-182">将以下代码添加到 `Main` 方法正上方，以指定这些路径和 `_textLoader` 变量：</span><span class="sxs-lookup"><span data-stu-id="13291-182">Add the following code right above the `Main` method to specify those paths and for the `_textLoader` variable:</span></span>

[!code-csharp[InitializePaths](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#2 "Define variables to store the data file paths")]

<span data-ttu-id="13291-183">使用 ML.NET 生成模型时，首先要创建 ML 上下文。</span><span class="sxs-lookup"><span data-stu-id="13291-183">When building a model with ML.NET you start by creating an ML Context.</span></span> <span data-ttu-id="13291-184">这在概念上相当于在实体框架中使用 `DbContext`。</span><span class="sxs-lookup"><span data-stu-id="13291-184">This is comparable conceptually to using `DbContext` in Entity Framework.</span></span> <span data-ttu-id="13291-185">该环境为机器学习作业提供一个上下文，可以用于异常情况跟踪和日志记录。</span><span class="sxs-lookup"><span data-stu-id="13291-185">The environment provides a context for your machine learning job that can be used for exception tracking and logging.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="13291-186">在 Main 中初始化变量</span><span class="sxs-lookup"><span data-stu-id="13291-186">Initialize variables in Main</span></span>

<span data-ttu-id="13291-187">创建一个名为 `mlContext` 的变量并将其初始化为 `MLContext` 的新实例。</span><span class="sxs-lookup"><span data-stu-id="13291-187">Create a variable called `mlContext` and initialize it with a new instance of `MLContext`.</span></span>  <span data-ttu-id="13291-188">用下面 `Main` 方法中的代码替换 `Console.WriteLine("Hello World!")` 行：</span><span class="sxs-lookup"><span data-stu-id="13291-188">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#3 "Create the ML Context")]

<span data-ttu-id="13291-189">在 `Main` 方法中添加以下代码作为调用 `Train` 方法的下一行代码：</span><span class="sxs-lookup"><span data-stu-id="13291-189">Add the following as the next line of code in the `Main` method to call the `Train` method:</span></span>

[!code-csharp[Train](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#5 "Train your model")]

<span data-ttu-id="13291-190">`Train` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="13291-190">The `Train` method executes the following tasks:</span></span>

* <span data-ttu-id="13291-191">加载数据。</span><span class="sxs-lookup"><span data-stu-id="13291-191">Loads the data.</span></span>
* <span data-ttu-id="13291-192">提取并转换数据。</span><span class="sxs-lookup"><span data-stu-id="13291-192">Extracts and transforms the data.</span></span>
* <span data-ttu-id="13291-193">定型模型。</span><span class="sxs-lookup"><span data-stu-id="13291-193">Trains the model.</span></span>
* <span data-ttu-id="13291-194">将模型保存为 .zip 文件。</span><span class="sxs-lookup"><span data-stu-id="13291-194">Saves the model as .zip file.</span></span>
* <span data-ttu-id="13291-195">返回模型。</span><span class="sxs-lookup"><span data-stu-id="13291-195">Returns the model.</span></span>

<span data-ttu-id="13291-196">`Train` 方法定型模型。</span><span class="sxs-lookup"><span data-stu-id="13291-196">The `Train` method trains the model.</span></span> <span data-ttu-id="13291-197">使用以下代码在 `Main` 下创建该方法：</span><span class="sxs-lookup"><span data-stu-id="13291-197">Create that method just below `Main`, using the following code:</span></span>

```csharp
public static ITransformer Train(MLContext mlContext, string dataPath)
{

}
```

<span data-ttu-id="13291-198">我们会将两个参数传递到 `Train` 方法；`MLContext` 用于上下文 (`mlContext`)，字符串用于数据集路径 (`dataPath`)。</span><span class="sxs-lookup"><span data-stu-id="13291-198">We are passing two parameters into the `Train` method; an `MLContext` for the context (`mlContext`), and a string for the dataset path (`dataPath`).</span></span> <span data-ttu-id="13291-199">我们将重用此方法来加载数据集。</span><span class="sxs-lookup"><span data-stu-id="13291-199">We're going to reuse this method for loading datasets.</span></span>

## <a name="load-and-transform-data"></a><span data-ttu-id="13291-200">加载和转换数据</span><span class="sxs-lookup"><span data-stu-id="13291-200">Load and transform data</span></span>

<span data-ttu-id="13291-201">使用 [LoadFromTextFile 方法](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29)的 `MLContext.Data.LoadFromTextFile` 包装器加载数据。</span><span class="sxs-lookup"><span data-stu-id="13291-201">Load the data using the `MLContext.Data.LoadFromTextFile` wrapper for the [LoadFromTextFile method](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29).</span></span> <span data-ttu-id="13291-202">它将返回 <xref:Microsoft.Data.DataView.IDataView>。</span><span class="sxs-lookup"><span data-stu-id="13291-202">It returns a <xref:Microsoft.Data.DataView.IDataView>.</span></span> 

<span data-ttu-id="13291-203">作为 `Transforms` 的输入和输出，`DataView` 是基本的数据管道类型，与 `LINQ` 中的 `IEnumerable` 类似。</span><span class="sxs-lookup"><span data-stu-id="13291-203">As the input and output of `Transforms`, a `DataView` is the fundamental data pipeline type, comparable to `IEnumerable` for `LINQ`.</span></span>

<span data-ttu-id="13291-204">在 ML.NET 中，数据类似于 SQL 视图。</span><span class="sxs-lookup"><span data-stu-id="13291-204">In ML.NET, data is similar to a SQL view.</span></span> <span data-ttu-id="13291-205">它是异源数据，会延迟计算并进行架构化。</span><span class="sxs-lookup"><span data-stu-id="13291-205">It is lazily evaluated, schematized, and heterogenous.</span></span> <span data-ttu-id="13291-206">该对象是管道的第一部分，并加载数据。</span><span class="sxs-lookup"><span data-stu-id="13291-206">The object is the first part of the pipeline, and loads the data.</span></span> <span data-ttu-id="13291-207">本教程会加载具有出租车行程定价信息的数据集。</span><span class="sxs-lookup"><span data-stu-id="13291-207">For this tutorial, it loads a dataset with taxi trip pricing information.</span></span> <span data-ttu-id="13291-208">这用于创建模型并对其进行定型。</span><span class="sxs-lookup"><span data-stu-id="13291-208">This is used to create the model, and train it.</span></span>

<span data-ttu-id="13291-209">将以下代码添加为 `Train` 方法的首行：</span><span class="sxs-lookup"><span data-stu-id="13291-209">Add the following code as the first line of the `Train` method:</span></span>

[!code-csharp[LoadTrainData](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#6 "loading training dataset")]

<span data-ttu-id="13291-210">在后续步骤中，我们按 `TaxiTrip` 类中定义的名称引用列。</span><span class="sxs-lookup"><span data-stu-id="13291-210">In the next steps we refer to the columns by the names defined in the `TaxiTrip` class.</span></span>

<span data-ttu-id="13291-211">定型和评估模型时，默认情况下，将“标签”列中的值视为要预测的正确值。</span><span class="sxs-lookup"><span data-stu-id="13291-211">When the model is trained and evaluated, by default, the values in the **Label** column are considered as correct values to be predicted.</span></span> <span data-ttu-id="13291-212">希望预测出租车费时，将 `FareAmount` 列复制到“标签”列。</span><span class="sxs-lookup"><span data-stu-id="13291-212">As we want to predict the taxi trip fare, copy the `FareAmount` column into the **Label** column.</span></span> <span data-ttu-id="13291-213">若要执行此操作，请使用 `CopyColumnsEstimator` 转换类，并添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="13291-213">To do that, use the `CopyColumnsEstimator` transformation class, and add the following code:</span></span>

[!code-csharp[CopyColumnsEstimator](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#7 "Use the CopyColumnsEstimator")]

<span data-ttu-id="13291-214">定型模型的算法需要数字特性，所以必须将分类数据（`VendorId`、`RateCode` 和 `PaymentType`）值转换为数字（`VendorIdEncoded`、`RateCodeEncoded` 和 `PaymentTypeEncoded`）。</span><span class="sxs-lookup"><span data-stu-id="13291-214">The algorithm that trains the model requires **numeric** features, so you have to transform the categorical data (`VendorId`, `RateCode`, and `PaymentType`) values into numbers (`VendorIdEncoded`, `RateCodeEncoded`, and `PaymentTypeEncoded`).</span></span> <span data-ttu-id="13291-215">为此，请使用 Microsoft.ML.Transforms.OneHotEncodingTransformer> 转换类（它将不同的数字键值分配到每列的不同值），并添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="13291-215">To do that, use the Microsoft.ML.Transforms.OneHotEncodingTransformer> transformation class, which assigns different numeric key values to the different values in each of the columns, and add the following code:</span></span>

[!code-csharp[OneHotEncodingEstimator](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#8 "Use the OneHotEncodingEstimator")]

<span data-ttu-id="13291-216">数据准备最后一步使用 `mlContext.Transforms.Concatenate` 转换类将所有功能列合并到“功能”列。</span><span class="sxs-lookup"><span data-stu-id="13291-216">The last step in data preparation combines all of the feature columns into the **Features** column using the `mlContext.Transforms.Concatenate` transformation class.</span></span> <span data-ttu-id="13291-217">默认情况下，学习算法仅处理“特征”列的特征。</span><span class="sxs-lookup"><span data-stu-id="13291-217">By default, a learning algorithm processes only features from the **Features** column.</span></span> <span data-ttu-id="13291-218">添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="13291-218">Add the following code:</span></span>

[!code-csharp[ColumnConcatenatingEstimator](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#9 "Use the ColumnConcatenatingEstimator")]

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="13291-219">选择学习算法</span><span class="sxs-lookup"><span data-stu-id="13291-219">Choose a learning algorithm</span></span>

<span data-ttu-id="13291-220">在将数据添加到管道，并将其转换为正确的输入格式之后，可以选择学习算法（学习器）。</span><span class="sxs-lookup"><span data-stu-id="13291-220">After adding the data to the pipeline and transforming it into the correct input format, we select a learning algorithm (**learner**).</span></span> <span data-ttu-id="13291-221">学习器定型模型。</span><span class="sxs-lookup"><span data-stu-id="13291-221">The learner trains the model.</span></span> <span data-ttu-id="13291-222">为此问题选择了“回归任务”，所以使用 `FastTreeRegressionTrainer` 学习器（ML.NET 提供的一种回归学习器）。</span><span class="sxs-lookup"><span data-stu-id="13291-222">We chose a **regression** task for this problem, so we use a `FastTreeRegressionTrainer` learner, which is one of the regression learners provided by ML.NET.</span></span>

<span data-ttu-id="13291-223">`FastTreeRegressionTrainer` 定型算法使用梯度提升。</span><span class="sxs-lookup"><span data-stu-id="13291-223">The `FastTreeRegressionTrainer` training algorithm utilizes gradient boosting.</span></span> <span data-ttu-id="13291-224">梯度提升是针对回归问题的一项机器学习技术。</span><span class="sxs-lookup"><span data-stu-id="13291-224">Gradient boosting is a machine learning technique for regression problems.</span></span> <span data-ttu-id="13291-225">它将以步进方式生成每个回归树。</span><span class="sxs-lookup"><span data-stu-id="13291-225">It builds each regression tree in a step-wise fashion.</span></span> <span data-ttu-id="13291-226">它使用预定义的损失函数测量每个步骤中的错误，并在下一步中对其进行校正。</span><span class="sxs-lookup"><span data-stu-id="13291-226">It uses a pre-defined loss function to measure the error in each step and correct for it in the next.</span></span> <span data-ttu-id="13291-227">其结果是一种预测模型，实际上是一组较弱的预测模型。</span><span class="sxs-lookup"><span data-stu-id="13291-227">The result is a prediction model that is actually an ensemble of weaker prediction models.</span></span> <span data-ttu-id="13291-228">有关梯度提升的详细信息，请参阅[提升的决策树回归](/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression)。</span><span class="sxs-lookup"><span data-stu-id="13291-228">For more information about gradient boosting, see [Boosted Decision Tree Regression](/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression).</span></span>

<span data-ttu-id="13291-229">将下面的代码添加到 `Train` 方法以将 `FastTreeRegressionTrainer` 添加到在上一步中添加的数据处理代码：</span><span class="sxs-lookup"><span data-stu-id="13291-229">Add the following code into the `Train` method to add the `FastTreeRegressionTrainer` to the data processing code added in the previous step:</span></span>

[!code-csharp[FastTreeRegressionTrainer](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#10 "Add the FastTreeRegressionTrainer")]

## <a name="train-the-model"></a><span data-ttu-id="13291-230">定型模型</span><span class="sxs-lookup"><span data-stu-id="13291-230">Train the model</span></span>

<span data-ttu-id="13291-231">最后一步是定型模型。</span><span class="sxs-lookup"><span data-stu-id="13291-231">The final step is to train the model.</span></span> <span data-ttu-id="13291-232">根据已加载和转换的数据集定型模型 <xref:Microsoft.ML.Data.TransformerChain>。</span><span class="sxs-lookup"><span data-stu-id="13291-232">We train the model, <xref:Microsoft.ML.Data.TransformerChain>, based on the dataset that has been loaded and transformed.</span></span> <span data-ttu-id="13291-233">一旦定义了估算器，我们将使用 <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> 定型模型，同时提供已经加载的定型数据。</span><span class="sxs-lookup"><span data-stu-id="13291-233">Once the estimator has been defined, we train the model using the <xref:Microsoft.ML.Data.EstimatorChain%601.Fit%2A> while providing the already loaded training data.</span></span> <span data-ttu-id="13291-234">这将返回要用于预测的模型。</span><span class="sxs-lookup"><span data-stu-id="13291-234">This returns a model to use for predictions.</span></span> `pipeline.Fit()` <span data-ttu-id="13291-235">定型管道，并返回基于传入的 `DataView` 的 `Transformer`。</span><span class="sxs-lookup"><span data-stu-id="13291-235">trains the pipeline and returns a `Transformer` based on the `DataView` passed in.</span></span> <span data-ttu-id="13291-236">在发生这种情况之前不会执行此试验。</span><span class="sxs-lookup"><span data-stu-id="13291-236">The experiment is not executed until this happens.</span></span>

[!code-csharp[TrainModel](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#11 "Train the model")]

### <a name="save-the-model"></a><span data-ttu-id="13291-237">保存模型</span><span class="sxs-lookup"><span data-stu-id="13291-237">Save the model</span></span>

<span data-ttu-id="13291-238">此时，你具有可以集成到任何现有或新 .NET 应用程序的 <xref:Microsoft.ML.Data.TransformerChain> 类型模型。</span><span class="sxs-lookup"><span data-stu-id="13291-238">At this point, you have a model of type <xref:Microsoft.ML.Data.TransformerChain> that can be integrated into any of your existing or new .NET applications.</span></span> <span data-ttu-id="13291-239">要将模型保存到 .zip 文件中，请在 `Train` 方法的末尾添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="13291-239">To save the model to a .zip file, add the following code at the end of the `Train` method:</span></span>

[!code-csharp[SaveModel](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#12 "Save the model as a .zip file and return the model")]

## <a name="save-the-model-as-a-zip-file"></a><span data-ttu-id="13291-240">将模型保存为 .zip 文件</span><span class="sxs-lookup"><span data-stu-id="13291-240">Save the model as a .zip file</span></span>

<span data-ttu-id="13291-241">使用下面的代码紧随 `Train` 方法后创建 `SaveModelAsFile` 方法：</span><span class="sxs-lookup"><span data-stu-id="13291-241">Create the `SaveModelAsFile` method, just after the `Train` method, using the following code:</span></span>

```csharp
private static void SaveModelAsFile(MLContext mlContext, ITransformer model)
{

}
```

<span data-ttu-id="13291-242">`SaveModelAsFile` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="13291-242">The `SaveModelAsFile` method executes the following tasks:</span></span>

* <span data-ttu-id="13291-243">将模型保存为 .zip 文件。</span><span class="sxs-lookup"><span data-stu-id="13291-243">Saves the model as a .zip file.</span></span>

<span data-ttu-id="13291-244">我们需要创建一个方法来保存模型，以便它可以在其他应用程序中重用和使用。</span><span class="sxs-lookup"><span data-stu-id="13291-244">We need to create a method to save the model so that it can be reused and consumed in other applications.</span></span> <span data-ttu-id="13291-245">`ITransformer` 有一个在 `_modelPath` 全局字段中采用的 <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> 方法和一个 <xref:System.IO.Stream> 方法。</span><span class="sxs-lookup"><span data-stu-id="13291-245">The `ITransformer` has a <xref:Microsoft.ML.Data.TransformerChain%601.SaveTo(Microsoft.ML.IHostEnvironment,System.IO.Stream)> method that takes in the `_modelPath` global field, and a <xref:System.IO.Stream>.</span></span> <span data-ttu-id="13291-246">由于我们想将其保存为 zip 文件，我们将在调用 `SaveTo` 方法之前立即创建 `FileStream`。</span><span class="sxs-lookup"><span data-stu-id="13291-246">Since we want to save this as a zip file, we'll create the `FileStream` immediately before calling the `SaveTo` method.</span></span> <span data-ttu-id="13291-247">将以下代码作为下一行添加到 `SaveModelAsFile` 方法中：</span><span class="sxs-lookup"><span data-stu-id="13291-247">Add the following code to the `SaveModelAsFile` method as the next line:</span></span>

[!code-csharp[SaveToMethod](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#13 "Add the SaveTo Method")]

<span data-ttu-id="13291-248">我们还可以使用以下代码通过使用 `_modelPath` 编写控制台消息来显示文件的写入位置：</span><span class="sxs-lookup"><span data-stu-id="13291-248">We could also display where the file was written by writing a console message with the `_modelPath`, using the following code:</span></span>

```csharp
Console.WriteLine("The model is saved to {0}", _modelPath);
```

## <a name="evaluate-the-model"></a><span data-ttu-id="13291-249">评估模型</span><span class="sxs-lookup"><span data-stu-id="13291-249">Evaluate the model</span></span>

<span data-ttu-id="13291-250">评估是检查模型预测标签值情况的过程。</span><span class="sxs-lookup"><span data-stu-id="13291-250">Evaluation is the process of checking how well the model predicts label values.</span></span> <span data-ttu-id="13291-251">模型对定型模型中未使用的数据做出好的预测非常重要。</span><span class="sxs-lookup"><span data-stu-id="13291-251">It's important that the model makes good predictions on data that was not used to train the model.</span></span> <span data-ttu-id="13291-252">执行此操作的一种方法是将数据拆分到定型和测试数据集，如此教程中所示。</span><span class="sxs-lookup"><span data-stu-id="13291-252">One way to do this is to split the data into training and test data sets, as it's done in this tutorial.</span></span> <span data-ttu-id="13291-253">你已在定型数据上定型模型，现在可以看到它在测试数据上的表现。</span><span class="sxs-lookup"><span data-stu-id="13291-253">Now that you've trained the model on the training data, you can see how well it performs on the test data.</span></span>

<span data-ttu-id="13291-254">`Evaluate` 方法评估模型。</span><span class="sxs-lookup"><span data-stu-id="13291-254">The `Evaluate` method evaluates the model.</span></span> <span data-ttu-id="13291-255">若要创建该方法，请将以下代码添加到 `Train` 方法下：</span><span class="sxs-lookup"><span data-stu-id="13291-255">To create that method, add the following code below the `Train` method:</span></span>

```csharp
private static void Evaluate(MLContext mlContext, ITransformer model)
{

}
```
<span data-ttu-id="13291-256">`Evaluate` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="13291-256">The `Evaluate` method executes the following tasks:</span></span>

* <span data-ttu-id="13291-257">加载测试数据集。</span><span class="sxs-lookup"><span data-stu-id="13291-257">Loads the test dataset.</span></span>
* <span data-ttu-id="13291-258">创建回归计算器。</span><span class="sxs-lookup"><span data-stu-id="13291-258">Creates the regression evaluator.</span></span>
* <span data-ttu-id="13291-259">评估模型并创建指标。</span><span class="sxs-lookup"><span data-stu-id="13291-259">Evaluates the model and creates metrics.</span></span>
* <span data-ttu-id="13291-260">显示指标。</span><span class="sxs-lookup"><span data-stu-id="13291-260">Displays the metrics.</span></span>

<span data-ttu-id="13291-261">使用下面的代码，在 `Train` 方法调用的正下方，从 `Main` 方法中添加对新方法的调用：</span><span class="sxs-lookup"><span data-stu-id="13291-261">Add a call to the new method from the `Main` method, right under the `Train` method call, using the following code:</span></span>

[!code-csharp[CallEvaluate](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#14 "Call the Evaluate method")]

<span data-ttu-id="13291-262">使用 `MLContext.Data.LoadFromTextFile` 包装器加载测试数据集。</span><span class="sxs-lookup"><span data-stu-id="13291-262">Load the test dataset using the `MLContext.Data.LoadFromTextFile` wrapper.</span></span> <span data-ttu-id="13291-263">可以将此数据集作为质量检查来评估模型。</span><span class="sxs-lookup"><span data-stu-id="13291-263">You can evaluate the model using this dataset as a quality check.</span></span> <span data-ttu-id="13291-264">将以下代码添加到 `Evaluate` 方法中：</span><span class="sxs-lookup"><span data-stu-id="13291-264">Add the following code to the `Evaluate` method:</span></span>

[!code-csharp[LoadTestDataset](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#15 "Load the test dataset")]

<span data-ttu-id="13291-265">接下来，使用机器学习 `model` 参数（转换器）来输入特性，并返回预测。</span><span class="sxs-lookup"><span data-stu-id="13291-265">Next, use the machine learning `model` parameter (a transformer) to input the features and return predictions.</span></span> <span data-ttu-id="13291-266">将以下代码作为下一行添加到 `Evaluate` 方法中：</span><span class="sxs-lookup"><span data-stu-id="13291-266">Add the following code to the `Evaluate` method as the next line:</span></span>

[!code-csharp[PredictWithTransformer](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#16 "Predict using the Transformer")]

<span data-ttu-id="13291-267">`RegressionContext.Evaluate` 方法使用指定数据集计算 `PredictionModel` 的质量指标。</span><span class="sxs-lookup"><span data-stu-id="13291-267">The `RegressionContext.Evaluate` method computes the quality metrics for the `PredictionModel` using the specified dataset.</span></span> <span data-ttu-id="13291-268">它返回一个 <xref:Microsoft.ML.Data.RegressionMetrics> 对象，其中包含由回归计算器计算出的总体指标。</span><span class="sxs-lookup"><span data-stu-id="13291-268">It returns a <xref:Microsoft.ML.Data.RegressionMetrics> object that contains the overall metrics computed by regression evaluators.</span></span> <span data-ttu-id="13291-269">若要显示这些指标来确定模型质量，需要先获取指标。</span><span class="sxs-lookup"><span data-stu-id="13291-269">To display these to determine the quality of the model, you need to get the metrics first.</span></span> <span data-ttu-id="13291-270">将以下代码作为下一行添加到 `Evaluate` 方法中：</span><span class="sxs-lookup"><span data-stu-id="13291-270">Add the following code as the next line in the `Evaluate` method:</span></span>

[!code-csharp[ComputeMetrics](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#17 "Compute Metrics")]

<span data-ttu-id="13291-271">添加以下代码以评估模型并生成评估模型：</span><span class="sxs-lookup"><span data-stu-id="13291-271">Add the following code to evaluate the model and produce the evaluation metrics:</span></span>

```csharp
Console.WriteLine();
Console.WriteLine($"*************************************************");
Console.WriteLine($"*       Model quality metrics evaluation         ");
Console.WriteLine($"*------------------------------------------------");
```

<span data-ttu-id="13291-272">[RSquared](../resources/glossary.md#coefficient-of-determination) 是回归模型的另一种评估指标。</span><span class="sxs-lookup"><span data-stu-id="13291-272">[RSquared](../resources/glossary.md#coefficient-of-determination) is another evaluation metric of the regression models.</span></span> <span data-ttu-id="13291-273">RSquared 在 0 和 1 之间取值。</span><span class="sxs-lookup"><span data-stu-id="13291-273">RSquared takes values between 0 and 1.</span></span> <span data-ttu-id="13291-274">值越接近 1，模型就越好。</span><span class="sxs-lookup"><span data-stu-id="13291-274">The closer its value is to 1, the better the model is.</span></span> <span data-ttu-id="13291-275">将以下代码添加到 `Evaluate` 方法以显示 RSquared 值：</span><span class="sxs-lookup"><span data-stu-id="13291-275">Add the following code into the `Evaluate` method to display the RSquared value:</span></span>

[!code-csharp[DisplayRSquared](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#18 "Display the RSquared metric.")]

<span data-ttu-id="13291-276">[RMS](../resources/glossary.md##root-of-mean-squared-error-rmse) 是回归模型的一种评估指标。</span><span class="sxs-lookup"><span data-stu-id="13291-276">[RMS](../resources/glossary.md##root-of-mean-squared-error-rmse) is one of the evaluation metrics of the regression model.</span></span> <span data-ttu-id="13291-277">指标越低，模型就越好。</span><span class="sxs-lookup"><span data-stu-id="13291-277">The lower it is, the better the model is.</span></span> <span data-ttu-id="13291-278">将以下代码添加到 `Evaluate` 方法以显示 RMS 值：</span><span class="sxs-lookup"><span data-stu-id="13291-278">Add the following code into the `Evaluate` method to display the RMS value:</span></span>

[!code-csharp[DisplayRMS](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#19 "Display the RMS metric.")]

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="13291-279">使用预测模型</span><span class="sxs-lookup"><span data-stu-id="13291-279">Use the model for predictions</span></span>

## <a name="predict-the-test-data-outcome-with-the-model-and-a-single-comment"></a><span data-ttu-id="13291-280">使用模型和单个注释预测测试数据结果</span><span class="sxs-lookup"><span data-stu-id="13291-280">Predict the test data outcome with the model and a single comment</span></span>

<span data-ttu-id="13291-281">使用下面的代码紧随 `Evaluate` 方法后创建 `TestSinglePrediction` 方法：</span><span class="sxs-lookup"><span data-stu-id="13291-281">Create the `TestSinglePrediction` method, just after the `Evaluate` method, using the following code:</span></span>

```csharp
private static void TestSinglePrediction(MLContext mlContext)
{

}
```

<span data-ttu-id="13291-282">`TestSinglePrediction` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="13291-282">The `TestSinglePrediction` method executes the following tasks:</span></span>

* <span data-ttu-id="13291-283">创建测试数据的单个注释。</span><span class="sxs-lookup"><span data-stu-id="13291-283">Creates a single comment of test data.</span></span>
* <span data-ttu-id="13291-284">根据测试数据预测费用。</span><span class="sxs-lookup"><span data-stu-id="13291-284">Predicts fare amount based on test data.</span></span>
* <span data-ttu-id="13291-285">结合测试数据和预测进行报告。</span><span class="sxs-lookup"><span data-stu-id="13291-285">Combines test data and predictions for reporting.</span></span>
* <span data-ttu-id="13291-286">显示预测结果。</span><span class="sxs-lookup"><span data-stu-id="13291-286">Displays the predicted results.</span></span>

<span data-ttu-id="13291-287">使用下面的代码，在 `Evaluate` 方法调用的正下方，从 `Main` 方法中添加对新方法的调用：</span><span class="sxs-lookup"><span data-stu-id="13291-287">Add a call to the new method from the `Main` method, right under the `Evaluate` method call, using the following code:</span></span>

[!code-csharp[CallTestSinglePrediction](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#20 "Call the TestSinglePrediction method")]

<span data-ttu-id="13291-288">由于我们想从保存的 zip 文件加载模型，我们将在创建 `FileStream` 之后立即调用 `Load` 方法。</span><span class="sxs-lookup"><span data-stu-id="13291-288">Since we want to load the model from the zip file we saved, we'll create the `FileStream` immediately before calling the `Load` method.</span></span> <span data-ttu-id="13291-289">将以下代码作为下一行添加到 `TestSinglePrediction` 方法中：</span><span class="sxs-lookup"><span data-stu-id="13291-289">Add the following code to the `TestSinglePrediction` method as the next line:</span></span>

[!code-csharp[LoadTheModel](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#21 "Load the model")]

<span data-ttu-id="13291-290">虽然 `model` 是对多行数据进行操作的 `transformer`，但是一个非常常见的生产场景是，需要对单个示例进行预测。</span><span class="sxs-lookup"><span data-stu-id="13291-290">While the `model` is a `transformer` that operates on many rows of data, a very common production scenario is a need for predictions on individual examples.</span></span> <span data-ttu-id="13291-291"><xref:Microsoft.ML.PredictionEngine%602> 是从 `CreatePredictionEngine` 方法返回的包装器。</span><span class="sxs-lookup"><span data-stu-id="13291-291">The <xref:Microsoft.ML.PredictionEngine%602> is a wrapper that is returned from the `CreatePredictionEngine` method.</span></span> <span data-ttu-id="13291-292">让我们添加以下代码来创建 `PredictionEngine`，作为 `TestSinglePrediction` 方法中的下一行：</span><span class="sxs-lookup"><span data-stu-id="13291-292">Let's add the following code to create the `PredictionEngine` as the next line in the `TestSinglePrediction` Method:</span></span>

[!code-csharp[MakePredictionEngine](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#22 "Create the PredictionFunction")]
  
<span data-ttu-id="13291-293">本教程使用此类中的一个测试行程。</span><span class="sxs-lookup"><span data-stu-id="13291-293">This tutorial uses one test trip within this class.</span></span> <span data-ttu-id="13291-294">稍后可以添加其他方案，以尝试使用此模型。</span><span class="sxs-lookup"><span data-stu-id="13291-294">Later you can add other scenarios to experiment with the model.</span></span> <span data-ttu-id="13291-295">通过创建一个 `TaxiTrip` 实例，在 `TestSinglePrediction` 方法中添加一个行程来测试定型模型的成本预测：</span><span class="sxs-lookup"><span data-stu-id="13291-295">Add a trip to test the trained model's prediction of cost in the `TestSinglePrediction` method by creating an instance of `TaxiTrip`:</span></span>

[!code-csharp[PredictionData](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#23 "Create test data for single prediction")]

 <span data-ttu-id="13291-296">我们可以使用它根据出租车行程数据的单个实例来预测费用。</span><span class="sxs-lookup"><span data-stu-id="13291-296">We can use that to predict the fare based on a single instance of the taxi trip data.</span></span> <span data-ttu-id="13291-297">要获得预测，请对数据使用 <xref:Microsoft.ML.PredictionEngine%602.Predict%2A>。</span><span class="sxs-lookup"><span data-stu-id="13291-297">To get a prediction, use <xref:Microsoft.ML.PredictionEngine%602.Predict%2A> on the data.</span></span> <span data-ttu-id="13291-298">请注意，输入数据是一个字符串，且模型包含特征化。</span><span class="sxs-lookup"><span data-stu-id="13291-298">Note that the input data is a string and the model includes the featurization.</span></span> <span data-ttu-id="13291-299">管道在定型和预测期间同步。</span><span class="sxs-lookup"><span data-stu-id="13291-299">Your pipeline is in sync during training and prediction.</span></span> <span data-ttu-id="13291-300">不必专门为预测编写预处理/特征化代码，并且相同 API 负责批处理和一次性预测。</span><span class="sxs-lookup"><span data-stu-id="13291-300">You didn’t have to write preprocessing/featurization code specifically for predictions, and the same API takes care of both batch and one-time predictions.</span></span>

[!code-csharp[Predict](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#24 "Create a prediction of taxi fare")]

<span data-ttu-id="13291-301">若要显示指定行程的预测费用，请将下面的代码添加到 `TestSinglePrediction` 方法中：</span><span class="sxs-lookup"><span data-stu-id="13291-301">To display the predicted fare of the specified trip, add the following code into the `TestSinglePrediction` method:</span></span>

[!code-csharp[Predict](~/samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#25 "Display the prediction.")]

<span data-ttu-id="13291-302">运行此程序，查看测试用例的预测出租车费。</span><span class="sxs-lookup"><span data-stu-id="13291-302">Run the program to see the predicted taxi fare for your test case.</span></span>

<span data-ttu-id="13291-303">祝贺你！</span><span class="sxs-lookup"><span data-stu-id="13291-303">Congratulations!</span></span> <span data-ttu-id="13291-304">你已成功生成用于预测出租车费的机器学习模型、评估其准确性，并用其进行预测。</span><span class="sxs-lookup"><span data-stu-id="13291-304">You've now successfully built a machine learning model for predicting taxi trip fares, evaluated its accuracy, and used it to make predictions.</span></span> <span data-ttu-id="13291-305">可以在 [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction) GitHub 存储库中找到本教程的源代码。</span><span class="sxs-lookup"><span data-stu-id="13291-305">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction) GitHub repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="13291-306">后续步骤</span><span class="sxs-lookup"><span data-stu-id="13291-306">Next steps</span></span>

<span data-ttu-id="13291-307">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="13291-307">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="13291-308">了解问题</span><span class="sxs-lookup"><span data-stu-id="13291-308">Understand the problem</span></span>
> * <span data-ttu-id="13291-309">选择适当的机器学习任务</span><span class="sxs-lookup"><span data-stu-id="13291-309">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="13291-310">准备和了解数据</span><span class="sxs-lookup"><span data-stu-id="13291-310">Prepare and understand the data</span></span>
> * <span data-ttu-id="13291-311">创建学习管道</span><span class="sxs-lookup"><span data-stu-id="13291-311">Create a learning pipeline</span></span>
> * <span data-ttu-id="13291-312">加载和转换数据</span><span class="sxs-lookup"><span data-stu-id="13291-312">Load and transform the data</span></span>
> * <span data-ttu-id="13291-313">选择学习算法</span><span class="sxs-lookup"><span data-stu-id="13291-313">Choose a learning algorithm</span></span>
> * <span data-ttu-id="13291-314">定型模型</span><span class="sxs-lookup"><span data-stu-id="13291-314">Train the model</span></span>
> * <span data-ttu-id="13291-315">评估模型</span><span class="sxs-lookup"><span data-stu-id="13291-315">Evaluate the model</span></span>
> * <span data-ttu-id="13291-316">使用预测模型</span><span class="sxs-lookup"><span data-stu-id="13291-316">Use the model for predictions</span></span>

<span data-ttu-id="13291-317">进入下一教程了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="13291-317">Advance to the next tutorial to learn more.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="13291-318">Iris 聚类分析</span><span class="sxs-lookup"><span data-stu-id="13291-318">Iris clustering</span></span>](iris-clustering.md)

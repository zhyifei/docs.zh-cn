---
title: 使用 ML.NET 预测纽约出租车费（回归）
description: 了解如何在回归方案中使用 ML.NET。
author: aditidugar
ms.author: johalex
ms.date: 06/05/2018
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 048ed1d38408c1ba4901c554cae33d5552c9e303
ms.sourcegitcommit: 5b0802832fb9ad684d34e69b8644a16a5b7c4810
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/06/2018
ms.locfileid: "34860644"
---
# <a name="tutorial-use-mlnet-to-predict-new-york-taxi-fares-regression"></a><span data-ttu-id="d1858-103">教程：使用 ML.NET 预测纽约出租车费（回归）</span><span class="sxs-lookup"><span data-stu-id="d1858-103">Tutorial: Use ML.NET to predict New York taxi fares (regression)</span></span>

> [!NOTE]
> <span data-ttu-id="d1858-104">本主题引用 ML.NET（目前处于预览状态），且材料可能会更改。</span><span class="sxs-lookup"><span data-stu-id="d1858-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="d1858-105">有关详细信息，请访问 [ML.NET 简介](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)。</span><span class="sxs-lookup"><span data-stu-id="d1858-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="d1858-106">本教程演示如何使用 ML.NET 构建[回归模型](../resources/glossary.md#regression)来预测纽约市出租车费。</span><span class="sxs-lookup"><span data-stu-id="d1858-106">This tutorial illustrates how to use ML.NET to build a [regression model](../resources/glossary.md#regression) for predicting New York City taxi fares.</span></span>

<span data-ttu-id="d1858-107">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="d1858-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="d1858-108">了解问题</span><span class="sxs-lookup"><span data-stu-id="d1858-108">Understand the problem</span></span>
> * <span data-ttu-id="d1858-109">选择适当的机器学习任务</span><span class="sxs-lookup"><span data-stu-id="d1858-109">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="d1858-110">准备和了解数据</span><span class="sxs-lookup"><span data-stu-id="d1858-110">Prepare and understand your data</span></span>
> * <span data-ttu-id="d1858-111">创建学习管道</span><span class="sxs-lookup"><span data-stu-id="d1858-111">Create a learning pipeline</span></span>
> * <span data-ttu-id="d1858-112">加载和转换数据</span><span class="sxs-lookup"><span data-stu-id="d1858-112">Load and transform your data</span></span>
> * <span data-ttu-id="d1858-113">选择学习算法</span><span class="sxs-lookup"><span data-stu-id="d1858-113">Choose a learning algorithm</span></span>
> * <span data-ttu-id="d1858-114">定型模型</span><span class="sxs-lookup"><span data-stu-id="d1858-114">Train the model</span></span>
> * <span data-ttu-id="d1858-115">评估模型</span><span class="sxs-lookup"><span data-stu-id="d1858-115">Evaluate the model</span></span>
> * <span data-ttu-id="d1858-116">使用预测模型</span><span class="sxs-lookup"><span data-stu-id="d1858-116">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d1858-117">系统必备</span><span class="sxs-lookup"><span data-stu-id="d1858-117">Prerequisites</span></span>

* <span data-ttu-id="d1858-118">安装了“.NET Core 跨平台开发”工作负载的 [Visual Studio 2017 15.6 或更高版本](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)。</span><span class="sxs-lookup"><span data-stu-id="d1858-118">[Visual Studio 2017 15.6 or later](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="d1858-119">了解问题</span><span class="sxs-lookup"><span data-stu-id="d1858-119">Understand the problem</span></span>

<span data-ttu-id="d1858-120">此问题围绕“预测纽约市的出租车行程费用”展开。</span><span class="sxs-lookup"><span data-stu-id="d1858-120">This problem is centered around **predicting the fare of a taxi trip in New York City**.</span></span> <span data-ttu-id="d1858-121">从表面看，似乎只取决于行程距离。</span><span class="sxs-lookup"><span data-stu-id="d1858-121">At first glance, it may seem to depend simply on the distance traveled.</span></span> <span data-ttu-id="d1858-122">但是，由于其他因素（比如额外的乘客或使用信用卡而非现金付款），纽约的出租车供应商收费不同。</span><span class="sxs-lookup"><span data-stu-id="d1858-122">However, taxi vendors in New York charge varying amounts for other factors such as additional passengers or paying with a credit card instead of cash.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="d1858-123">选择适当的机器学习任务</span><span class="sxs-lookup"><span data-stu-id="d1858-123">Select the appropriate machine learning task</span></span>

<span data-ttu-id="d1858-124">若要预测出租车费，首先选择适当的机器学习任务。</span><span class="sxs-lookup"><span data-stu-id="d1858-124">To predict the taxi fare, you first select the appropriate machine learning task.</span></span> <span data-ttu-id="d1858-125">你希望基于数据集中的其他因素预测实际值（表示价格的双精度值）。</span><span class="sxs-lookup"><span data-stu-id="d1858-125">You are looking to predict a real value (a double that represents price) based on the other factors in the dataset.</span></span> <span data-ttu-id="d1858-126">你选择[回归](../resources/glossary.md#regression)任务。</span><span class="sxs-lookup"><span data-stu-id="d1858-126">You choose a [**regression**](../resources/glossary.md#regression) task.</span></span>

<span data-ttu-id="d1858-127">定型模型的过程标识数据集中哪些因素在预测最终车费价格时最具影响力。</span><span class="sxs-lookup"><span data-stu-id="d1858-127">The process of training the model identifies which factors in the dataset are most influential when predicting the final fare price.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="d1858-128">创建控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="d1858-128">Create a console application</span></span>

1. <span data-ttu-id="d1858-129">打开 Visual Studio 2017。</span><span class="sxs-lookup"><span data-stu-id="d1858-129">Open Visual Studio 2017.</span></span> <span data-ttu-id="d1858-130">从菜单栏中选择“文件” > “新建” > “项目”。</span><span class="sxs-lookup"><span data-stu-id="d1858-130">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="d1858-131">在“新项目”对话框中，依次选择“Visual C#”和“.NET Core”节点。</span><span class="sxs-lookup"><span data-stu-id="d1858-131">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="d1858-132">然后，选择“控制台应用程序(.NET Core)”项目模板。</span><span class="sxs-lookup"><span data-stu-id="d1858-132">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="d1858-133">在“名称”文本框中，键入“TaxiFarePrediction”，然后选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="d1858-133">In the **Name** text box, type "TaxiFarePrediction" and then select the **OK** button.</span></span>

2. <span data-ttu-id="d1858-134">在项目中创建一个名为“数据”的目录来保存数据集文件：</span><span class="sxs-lookup"><span data-stu-id="d1858-134">Create a directory named *Data* in your project to save your data set files:</span></span>

    <span data-ttu-id="d1858-135">在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新文件夹”。</span><span class="sxs-lookup"><span data-stu-id="d1858-135">In **Solution Explorer**, right-click on your project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="d1858-136">键入“数据”，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="d1858-136">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="d1858-137">安装“Microsoft.ML NuGet 包”：</span><span class="sxs-lookup"><span data-stu-id="d1858-137">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="d1858-138">在“解决方案资源管理器”中，右键单击项目，然后选择“管理 NuGet 包”。</span><span class="sxs-lookup"><span data-stu-id="d1858-138">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="d1858-139">将“nuget.org”选择为“包源”，选择“浏览”选项卡并搜索“Microsoft.ML”，在列表中选择该包，然后选择“安装”按钮。</span><span class="sxs-lookup"><span data-stu-id="d1858-139">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="d1858-140">选择“预览更改”对话框上的“确定”按钮，如果你同意所列包的许可条款，则选择“接受许可”对话框上的“我接受”按钮。</span><span class="sxs-lookup"><span data-stu-id="d1858-140">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="prepare-and-understand-your-data"></a><span data-ttu-id="d1858-141">准备和了解数据</span><span class="sxs-lookup"><span data-stu-id="d1858-141">Prepare and understand your data</span></span>

1. <span data-ttu-id="d1858-142">下载 [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) 和 [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) 数据集，并将它们保存到先前创建的“数据”文件夹。</span><span class="sxs-lookup"><span data-stu-id="d1858-142">Download the [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) and the [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) data sets and save them to the *Data* folder previously created.</span></span> <span data-ttu-id="d1858-143">“出租车行程”数据集定型机器学习模型，且可用来评估模型的准确度。</span><span class="sxs-lookup"><span data-stu-id="d1858-143">The Taxi Trip data set trains the machine learning model and can be used to evaluate how accurate your model is.</span></span> <span data-ttu-id="d1858-144">这些数据集最初来自 [NYC TLC 出租车行程数据集](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml)。</span><span class="sxs-lookup"><span data-stu-id="d1858-144">These data sets are originally from the [NYC TLC Taxi Trip data set](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span></span>

2. <span data-ttu-id="d1858-145">在“解决方案资源管理器”中，右键单击每个 \*.csv 文件，然后选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="d1858-145">In Solution Explorer, right-click each of the \*.csv files and select **Properties**.</span></span> <span data-ttu-id="d1858-146">在“高级”下，将“复制到输出目录”的值更改为“始终”。</span><span class="sxs-lookup"><span data-stu-id="d1858-146">Under **Advanced**, change the value of **Copy to Output Directory** to **Always**.</span></span>

3. <span data-ttu-id="d1858-147">在代码编辑器中打开“taxi-fare-train.csv”数据集并查看第一行中的列标题。</span><span class="sxs-lookup"><span data-stu-id="d1858-147">Open the **taxi-fare-train.csv** data set in the code editor and look at column headers in the first row.</span></span> <span data-ttu-id="d1858-148">查看每个列。</span><span class="sxs-lookup"><span data-stu-id="d1858-148">Take a look at each of the columns.</span></span> <span data-ttu-id="d1858-149">了解数据并确定哪些列是“特征”以及哪些是“标签”。</span><span class="sxs-lookup"><span data-stu-id="d1858-149">Understand the data and decide which columns are **features** and which is the **label**.</span></span>

<span data-ttu-id="d1858-150">“标签”是你尝试预测的列的标识符。</span><span class="sxs-lookup"><span data-stu-id="d1858-150">The **label** is the identifier of the column you are trying to predict.</span></span> <span data-ttu-id="d1858-151">标识的“特征”用于预测标签。</span><span class="sxs-lookup"><span data-stu-id="d1858-151">The identified **features** are used to predict the label.</span></span>

* <span data-ttu-id="d1858-152">vendor_id：出租车供应商的 ID 是一项特征。</span><span class="sxs-lookup"><span data-stu-id="d1858-152">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
* <span data-ttu-id="d1858-153">rate_code：出租车行程的费率类型是一项特征。</span><span class="sxs-lookup"><span data-stu-id="d1858-153">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
* <span data-ttu-id="d1858-154">passenger_count：行程乘客数是一项特征。</span><span class="sxs-lookup"><span data-stu-id="d1858-154">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
* <span data-ttu-id="d1858-155">trip_time_in_secs：行程花费的时间量。</span><span class="sxs-lookup"><span data-stu-id="d1858-155">**trip_time_in_secs:** The amount of time the trip took.</span></span> <span data-ttu-id="d1858-156">在行程完成之前，你不会知道行程花费的时间。</span><span class="sxs-lookup"><span data-stu-id="d1858-156">You won't know how long the trip takes until after it is completed.</span></span> <span data-ttu-id="d1858-157">从模型中排除此列。</span><span class="sxs-lookup"><span data-stu-id="d1858-157">You exclude this column from the model.</span></span>
* <span data-ttu-id="d1858-158">trip_distance：行程距离是一项特征。</span><span class="sxs-lookup"><span data-stu-id="d1858-158">**trip_distance:** The distance of the trip is a feature.</span></span>
* <span data-ttu-id="d1858-159">payment_type：付款方式（现金或信用卡）是一项特征。</span><span class="sxs-lookup"><span data-stu-id="d1858-159">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
* <span data-ttu-id="d1858-160">fare_amount：支付的总出租车费是一个标签。</span><span class="sxs-lookup"><span data-stu-id="d1858-160">**fare_amount:** The total taxi fare paid is the label.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="d1858-161">创建类和定义路径</span><span class="sxs-lookup"><span data-stu-id="d1858-161">Create classes and define paths</span></span>

<span data-ttu-id="d1858-162">将以下附加的 `using` 语句添加到“Program.cs”文件顶部：</span><span class="sxs-lookup"><span data-stu-id="d1858-162">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#1 "Add necessary usings")]

<span data-ttu-id="d1858-163">需要创建三个全局变量，来保存最近下载的文件路径和保存模型：</span><span class="sxs-lookup"><span data-stu-id="d1858-163">You need to create three global variables to hold the paths to the recently downloaded files and to save the model:</span></span>

* <span data-ttu-id="d1858-164">`_datapath` 具有用于定型模型的数据集路径。</span><span class="sxs-lookup"><span data-stu-id="d1858-164">`_datapath` has the path to the data set used to train the model.</span></span>
* <span data-ttu-id="d1858-165">`_testdatapath` 具有用于评估模型的数据集路径。</span><span class="sxs-lookup"><span data-stu-id="d1858-165">`_testdatapath` has the path to the data set used to evaluate the model.</span></span>
* <span data-ttu-id="d1858-166">`_modelpath` 具有在其中存储定型模型的路径。</span><span class="sxs-lookup"><span data-stu-id="d1858-166">`_modelpath` has the path where the trained model is stored.</span></span>

<span data-ttu-id="d1858-167">将以下代码添加到上面 `Main` 右侧的行中，以指定将最近下载的文件：</span><span class="sxs-lookup"><span data-stu-id="d1858-167">Add the following code to the line right above `Main` to specify the recently downloaded files:</span></span>

[!code-csharp[InitializePaths](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#2 "Define variables to store the data file paths")]

<span data-ttu-id="d1858-168">接下来，创建输入数据和预测类：</span><span class="sxs-lookup"><span data-stu-id="d1858-168">Next, create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="d1858-169">在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新项”。</span><span class="sxs-lookup"><span data-stu-id="d1858-169">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="d1858-170">在“添加新项”对话框中，选择“类”并将“名称”字段更改为“TaxiTrip.cs”。</span><span class="sxs-lookup"><span data-stu-id="d1858-170">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TaxiTrip.cs*.</span></span> <span data-ttu-id="d1858-171">然后，选择“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="d1858-171">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="d1858-172">将以下 `using` 语句添加到新文件中：</span><span class="sxs-lookup"><span data-stu-id="d1858-172">Add the following `using` statements to the new file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#1 "Add necessary usings")]

<span data-ttu-id="d1858-173">删除现有类定义并向“TaxiTrip.cs”文件添加以下代码，其中有两个类 `TaxiTrip` 和 `TaxiTripFarePrediction`：</span><span class="sxs-lookup"><span data-stu-id="d1858-173">Remove the existing class definition and add the following code, which has two classes `TaxiTrip` and `TaxiTripFarePrediction`, to the *TaxiTrip.cs* file:</span></span>

[!code-csharp[DefineTaxiTrip](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#2 "Define the taxi trip and fare predictions classes")]

<span data-ttu-id="d1858-174">`TaxiTrip` 是输入数据集类且具有针对每个数据集列的定义。</span><span class="sxs-lookup"><span data-stu-id="d1858-174">`TaxiTrip` is the input data set class and has definitions for each of the data set columns.</span></span> <span data-ttu-id="d1858-175">`TaxiTripFarePrediction` 类用于模型定型后的预测。</span><span class="sxs-lookup"><span data-stu-id="d1858-175">The `TaxiTripFarePrediction` class is used for prediction after the model has been trained.</span></span> <span data-ttu-id="d1858-176">它应用了单个浮点 (`FareAmount`) 和一个`Score` [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute) 属性。</span><span class="sxs-lookup"><span data-stu-id="d1858-176">It has a single float (`FareAmount`) and a `Score` [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute) attribute applied.</span></span>

<span data-ttu-id="d1858-177">现在回到“Program.cs”文件。</span><span class="sxs-lookup"><span data-stu-id="d1858-177">Now go back to the **Program.cs** file.</span></span> <span data-ttu-id="d1858-178">在 `Main` 中，将 `Console.WriteLine("Hello World!")` 替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="d1858-178">In `Main`, replace the `Console.WriteLine("Hello World!")` with the following code:</span></span>

```csharp
PredictionModel<TaxiTrip, TaxiTripFarePrediction> model = Train();
```

<span data-ttu-id="d1858-179">`Train` 方法定型模型。</span><span class="sxs-lookup"><span data-stu-id="d1858-179">The `Train` method trains your model.</span></span> <span data-ttu-id="d1858-180">使用以下代码在 `Main` 下创建该函数：</span><span class="sxs-lookup"><span data-stu-id="d1858-180">Create that function just below `Main`, using the following code:</span></span>

```csharp
public static PredictionModel<TaxiTrip, TaxiTripFarePrediction> Train()
{

}
```

## <a name="create-a-learning-pipeline"></a><span data-ttu-id="d1858-181">创建学习管道</span><span class="sxs-lookup"><span data-stu-id="d1858-181">Create a learning pipeline</span></span>

<span data-ttu-id="d1858-182">学习管道加载所有数据和所需的算法来定型模型。</span><span class="sxs-lookup"><span data-stu-id="d1858-182">The learning pipeline loads all of the data and algorithms necessary to train the model.</span></span> <span data-ttu-id="d1858-183">将以下代码添加到 `Train()` 方法：</span><span class="sxs-lookup"><span data-stu-id="d1858-183">Add the following code into the `Train()` method:</span></span>

```csharp
var pipeline = new LearningPipeline();
```

## <a name="load-and-transform-your-data"></a><span data-ttu-id="d1858-184">加载和转换数据</span><span class="sxs-lookup"><span data-stu-id="d1858-184">Load and transform your data</span></span>

<span data-ttu-id="d1858-185">接下来，将数据加载到管道。</span><span class="sxs-lookup"><span data-stu-id="d1858-185">Next, load your data into the pipeline.</span></span> <span data-ttu-id="d1858-186">指向最初创建的 `_datapath` 并指定 .csv 文件的分隔符 (,)。</span><span class="sxs-lookup"><span data-stu-id="d1858-186">Point to the `_datapath` created initially and specify the delimiter of the .csv file (,).</span></span> <span data-ttu-id="d1858-187">将下面的代码添加到最后一步下的 `Train()` 方法：</span><span class="sxs-lookup"><span data-stu-id="d1858-187">Add the following code into the `Train()` method underneath the last step:</span></span>

```csharp
pipeline.Add(new TextLoader(_datapath).CreateFrom<TaxiTrip>(separator:','));
```

<span data-ttu-id="d1858-188">你将引用列，而无需在代码中创建的下划线。</span><span class="sxs-lookup"><span data-stu-id="d1858-188">You'll refer to the columns without the underscores in the code you're creating.</span></span> <span data-ttu-id="d1858-189">使用 `ColumnCopier()` 函数将 `FareAmount` 列复制到列名为“标签”的新列。</span><span class="sxs-lookup"><span data-stu-id="d1858-189">Copy the `FareAmount` column into a new column called "Label" using the `ColumnCopier()` function.</span></span> <span data-ttu-id="d1858-190">此列为“标签”。</span><span class="sxs-lookup"><span data-stu-id="d1858-190">This column is the **Label**.</span></span>

```csharp
pipeline.Add(new ColumnCopier(("FareAmount", "Label")));
```

<span data-ttu-id="d1858-191">执行一些“特征工程”来转换数据，以便可以有效地用于机器学习。</span><span class="sxs-lookup"><span data-stu-id="d1858-191">Conduct some **feature engineering** to transform the data so that it can be used effectively for machine learning.</span></span> <span data-ttu-id="d1858-192">定型模型的算法需要数值特征，需要将分类数据（`VendorId`、`RateCode` 和 `PaymentType`）转换为数字。</span><span class="sxs-lookup"><span data-stu-id="d1858-192">The algorithm that trains the model requires **numeric** features, you transform the categorical data (`VendorId`, `RateCode`, and `PaymentType`) into numbers.</span></span> <span data-ttu-id="d1858-193">`CategoricalOneHotVectorizer()` 函数将数字键指派给每个这些列中的值。</span><span class="sxs-lookup"><span data-stu-id="d1858-193">The `CategoricalOneHotVectorizer()` function assigns a numeric key to the values in each of these columns.</span></span> <span data-ttu-id="d1858-194">通过添加此代码来转换数据：</span><span class="sxs-lookup"><span data-stu-id="d1858-194">Transform your data by adding this code:</span></span>

```csharp
pipeline.Add(new CategoricalOneHotVectorizer("VendorId",
                                             "RateCode",
                                             "PaymentType"));
```

<span data-ttu-id="d1858-195">数据准备的最后一步使用 `ColumnConcatenator()` 函数将所有特征合并到一个向量。</span><span class="sxs-lookup"><span data-stu-id="d1858-195">The last step in data preparation combines all of your **features** into one vector using the `ColumnConcatenator()` function.</span></span> <span data-ttu-id="d1858-196">此必要步骤可帮助算法轻松处理特征。</span><span class="sxs-lookup"><span data-stu-id="d1858-196">This necessary step helps the algorithm easily process your features.</span></span> <span data-ttu-id="d1858-197">添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="d1858-197">Add the following code:</span></span>

```csharp
pipeline.Add(new ColumnConcatenator("Features",
                                    "VendorId",
                                    "RateCode",
                                    "PassengerCount",
                                    "TripDistance",
                                    "PaymentType"));
```

<span data-ttu-id="d1858-198">请注意，不包含 `trip_time_in_secs` 列。</span><span class="sxs-lookup"><span data-stu-id="d1858-198">Notice that the `trip_time_in_secs` column isn't included.</span></span> <span data-ttu-id="d1858-199">你已确定它不是一项有用的预测特征。</span><span class="sxs-lookup"><span data-stu-id="d1858-199">You already determined that it isn't a useful prediction feature.</span></span>

> [!NOTE]
> <span data-ttu-id="d1858-200">必须按照上面指定的顺序将这些步骤添加到管道才能成功执行。</span><span class="sxs-lookup"><span data-stu-id="d1858-200">These steps must be added to Pipeline in the order specified above for successful execution.</span></span>

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="d1858-201">选择学习算法</span><span class="sxs-lookup"><span data-stu-id="d1858-201">Choose a learning algorithm</span></span>

<span data-ttu-id="d1858-202">在将数据添加到管道，并将其转换为正确的输入格式之后，可以选择学习算法（学习器）。</span><span class="sxs-lookup"><span data-stu-id="d1858-202">After adding the data to the pipeline and transforming it into the correct input format, you select a learning algorithm (**learner**).</span></span> <span data-ttu-id="d1858-203">学习算法定型模型。</span><span class="sxs-lookup"><span data-stu-id="d1858-203">The learning algorithm trains the model.</span></span> <span data-ttu-id="d1858-204">针对此问题选择“回归任务”，以此向管道添加一个名为 `FastTreeRegressor()` 的学习器来利用“梯度提升”。</span><span class="sxs-lookup"><span data-stu-id="d1858-204">You chose a **regression task** for this problem, so you add a learner called `FastTreeRegressor()` to the pipeline that utilizes **gradient boosting**.</span></span>

<span data-ttu-id="d1858-205">梯度提升是针对回归问题的一项机器学习技术。</span><span class="sxs-lookup"><span data-stu-id="d1858-205">Gradient boosting is a machine learning technique for regression problems.</span></span> <span data-ttu-id="d1858-206">它将以步进方式生成每个回归树。</span><span class="sxs-lookup"><span data-stu-id="d1858-206">It builds each regression tree in a step-wise fashion.</span></span> <span data-ttu-id="d1858-207">它使用预定义的损失函数测量每个步骤中的错误，并在下一步中对其进行校正。</span><span class="sxs-lookup"><span data-stu-id="d1858-207">It uses a pre-defined loss function to measure the error in each step and correct for it in the next.</span></span> <span data-ttu-id="d1858-208">其结果是一种预测模型，实际上是一组较弱的预测模型。</span><span class="sxs-lookup"><span data-stu-id="d1858-208">The result is a prediction model that is actually an ensemble of weaker prediction models.</span></span> <span data-ttu-id="d1858-209">有关梯度提升的详细信息，请参阅[提升的决策树回归](https://docs.microsoft.com/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression)。</span><span class="sxs-lookup"><span data-stu-id="d1858-209">For more information about gradient boosting, see [Boosted Decision Tree Regression](https://docs.microsoft.com/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression).</span></span>

<span data-ttu-id="d1858-210">将下面的代码添加到在上一步中添加的数据处理代码后面的 `Train()` 方法中：</span><span class="sxs-lookup"><span data-stu-id="d1858-210">Add the following code into the `Train()` method following the data processing code added in the last step:</span></span>

```csharp
pipeline.Add(new FastTreeRegressor());
```

<span data-ttu-id="d1858-211">你已将前面所有步骤作为单个语句添加到管道，但 C# 包含可以更轻松地创建和初始化管道的方便集合初始化语法。</span><span class="sxs-lookup"><span data-stu-id="d1858-211">You added all the preceding steps to the pipeline as individual statements, but C# has a handy collection initialization syntax that makes it simpler to create and initialize the pipeline.</span></span> <span data-ttu-id="d1858-212">将目前添加到 `Train()` 方法的代码替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="d1858-212">Replace the code you added so far to the `Train()` method with the following code:</span></span>

[!code-csharp[CreatePipeline](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#3 "Create and initialize the learning pipeline")]

## <a name="train-the-model"></a><span data-ttu-id="d1858-213">定型模型</span><span class="sxs-lookup"><span data-stu-id="d1858-213">Train the model</span></span>

<span data-ttu-id="d1858-214">最后一步是定型模型。</span><span class="sxs-lookup"><span data-stu-id="d1858-214">The final step is to train the model.</span></span> <span data-ttu-id="d1858-215">在此之前，管道中未执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="d1858-215">Until this point, nothing in the pipeline has been executed.</span></span> <span data-ttu-id="d1858-216">`pipeline.Train<T_Input, T_Output>()` 函数采用预定义的 `TaxiTrip` 类类型并输出 `TaxiTripFarePrediction` 类型。</span><span class="sxs-lookup"><span data-stu-id="d1858-216">The `pipeline.Train<T_Input, T_Output>()` function takes in the pre-defined `TaxiTrip` class type and outputs a `TaxiTripFarePrediction` type.</span></span> <span data-ttu-id="d1858-217">将此最后一段代码添加到 `Train()` 函数：</span><span class="sxs-lookup"><span data-stu-id="d1858-217">Add this final piece of code into the `Train()` function:</span></span>

[!code-csharp[TrainMOdel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#4 "Train your model")]

<span data-ttu-id="d1858-218">就是这么简单！</span><span class="sxs-lookup"><span data-stu-id="d1858-218">And that's it!</span></span> <span data-ttu-id="d1858-219">已成功定型机器学习模型，可以用来预测 NYC 的出租车费。</span><span class="sxs-lookup"><span data-stu-id="d1858-219">You have successfully trained a machine learning model that can predict taxi fares in NYC.</span></span> <span data-ttu-id="d1858-220">现在，请观察模型的准确度并了解如何使用它。</span><span class="sxs-lookup"><span data-stu-id="d1858-220">Now take a look to understand how accurate your model is and learn how to consume it.</span></span>

## <a name="save-the-model"></a><span data-ttu-id="d1858-221">保存模型</span><span class="sxs-lookup"><span data-stu-id="d1858-221">Save the model</span></span>

<span data-ttu-id="d1858-222">继续下一步之前，通过在 `Train()` 函数的末尾添加以下代码，将模型保存到一个 .zip 文件：</span><span class="sxs-lookup"><span data-stu-id="d1858-222">Before you go onto the next step, save your model to a .zip file by adding the following code at the end of your `Train()` function:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#5 "Save the model asynchronously and return the model")]

<span data-ttu-id="d1858-223">将 `await` 语句添加到 `model.WriteAsync()` 调用中意味着 `Train()` 方法必须更改为返回 `Task` 的异步方法。</span><span class="sxs-lookup"><span data-stu-id="d1858-223">Adding the `await` statement to the `model.WriteAsync()` call means that the `Train()` method must be changed to an async method that returns a `Task`.</span></span> <span data-ttu-id="d1858-224">修改 `Train` 的签名，如下面的代码所示：</span><span class="sxs-lookup"><span data-stu-id="d1858-224">Modify the signature of `Train` as shown in the following code:</span></span>

[!code-csharp[AsyncTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#6 "Make the Train method async and return a task.")]

<span data-ttu-id="d1858-225">更改 `Train` 方法的返回类型意味着你需要将 `await` 添加到调用 `Main` 方法中的 `Train` 的代码，如下面的代码所示：</span><span class="sxs-lookup"><span data-stu-id="d1858-225">Changing the return type of the `Train` method means you have to add an `await` to the code that calls `Train` in the `Main` method as shown in the following code:</span></span>

[!code-csharp[AwaitTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#7 "Await the Train method")]

<span data-ttu-id="d1858-226">在 `Main` 方法中添加 `await` 意味着 `Main` 方法必须具有 `async` 修饰符并返回 `Task`：</span><span class="sxs-lookup"><span data-stu-id="d1858-226">Adding an `await` in your `Main` method means the `Main` method must have the `async` modifier and return a `Task`:</span></span>

[!code-csharp[AsyncMain](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#8 "Make the Main method async and return a task.")]

<span data-ttu-id="d1858-227">还需要将下面的 using 语句添加到文件顶部：</span><span class="sxs-lookup"><span data-stu-id="d1858-227">You also need to add the following using statement at the top of the file:</span></span>

[!code-csharp[UsingTasks](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#9 "Add System.Threading.Tasks. to your usings.")]

<span data-ttu-id="d1858-228">因为 `async Main` 方法是 C# 7.1 中的新功能，且项目的默认语言版本为 C# 7.0，你需要将语言版本更改为 C# 7.1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="d1858-228">Because the `async Main` method is a new feature in C# 7.1 and the default language version of the project is C# 7.0, you need to change the language version to C# 7.1 or higher.</span></span>
<span data-ttu-id="d1858-229">要完成此操作，右键单击“解决方案资源管理器”中的项目节点，然后选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="d1858-229">To do that, right-click on the project node in **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="d1858-230">选择**生成**选项卡并选择**高级**按钮。</span><span class="sxs-lookup"><span data-stu-id="d1858-230">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="d1858-231">在下拉列表中，选择“C# 7.1”（或更高版本）。</span><span class="sxs-lookup"><span data-stu-id="d1858-231">In the dropdown, select  **C# 7.1** (or a higher version).</span></span> <span data-ttu-id="d1858-232">选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="d1858-232">Select the **OK** button.</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="d1858-233">评估模型</span><span class="sxs-lookup"><span data-stu-id="d1858-233">Evaluate the model</span></span>

<span data-ttu-id="d1858-234">评估是检查模型工作情况的过程。</span><span class="sxs-lookup"><span data-stu-id="d1858-234">Evaluation is the process of checking how well the model works.</span></span> <span data-ttu-id="d1858-235">务必使模型对它在定型时未使用的数据进行准确预测。</span><span class="sxs-lookup"><span data-stu-id="d1858-235">It's important that your model makes good predictions on data that it didn't use when it was trained.</span></span> <span data-ttu-id="d1858-236">实现此目的的一种方法是将数据拆分为定型和测试数据集，就像在本教程所执行的那样。</span><span class="sxs-lookup"><span data-stu-id="d1858-236">One way to do this is by splitting the data into train and test datasets, as you did in this tutorial.</span></span> <span data-ttu-id="d1858-237">你已在定型数据上定型模型，现在可以看到它在测试数据上的表现。</span><span class="sxs-lookup"><span data-stu-id="d1858-237">Now that you've trained the model on the train data, you can see how well it performs on the test data.</span></span>

<span data-ttu-id="d1858-238">返回到 `Main` 函数，并在调用 `Train()` 方法下添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="d1858-238">Go back to your `Main` function and add the following code beneath the call to the `Train()`method:</span></span>

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#10 "Evaluate the model.")]

<span data-ttu-id="d1858-239">`Evaluate()` 函数对模型进行评估。</span><span class="sxs-lookup"><span data-stu-id="d1858-239">The `Evaluate()` function evaluates your model.</span></span> <span data-ttu-id="d1858-240">在 `Train()` 下创建该函数。</span><span class="sxs-lookup"><span data-stu-id="d1858-240">Create that function below `Train()`.</span></span> <span data-ttu-id="d1858-241">添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="d1858-241">Add the following code:</span></span>

```csharp
private static void Evaluate(PredictionModel<TaxiTrip, TaxiTripFarePrediction> model)
{

}
```

<span data-ttu-id="d1858-242">使用 `TextLoader()` 函数加载测试数据。</span><span class="sxs-lookup"><span data-stu-id="d1858-242">Load the test data using the `TextLoader()` function.</span></span> <span data-ttu-id="d1858-243">将以下代码添加到 `Evaluate()` 方法：</span><span class="sxs-lookup"><span data-stu-id="d1858-243">Add the following code into the `Evaluate()` method:</span></span>

[!code-csharp[LoadTestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#12 "Load the test data.")]

<span data-ttu-id="d1858-244">添加以下代码以评估模型并为其生成指标：</span><span class="sxs-lookup"><span data-stu-id="d1858-244">Add the following code to evaluate the model and produce the metrics for it:</span></span>

[!code-csharp[EvaluateAndMeasure](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#13 "Evaluate the model and its predictions.")]

<span data-ttu-id="d1858-245">RMS 是一项用于评估回归问题的指标。</span><span class="sxs-lookup"><span data-stu-id="d1858-245">RMS is one metric for evaluating regression problems.</span></span> <span data-ttu-id="d1858-246">指标越低，模型就越好。</span><span class="sxs-lookup"><span data-stu-id="d1858-246">The lower it is, the better your model.</span></span> <span data-ttu-id="d1858-247">将下面的代码添加到 `Evaluate()` 函数以打印模型的 RMS。</span><span class="sxs-lookup"><span data-stu-id="d1858-247">Add the following code into the `Evaluate()` function to print the RMS for your model.</span></span>

[!code-csharp[DisplayRMS](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#14 "Display the RMS metric.")]

<span data-ttu-id="d1858-248">RSquared 是另一项用于评估回归问题的指标。</span><span class="sxs-lookup"><span data-stu-id="d1858-248">RSquared is another metric for evaluating regression problems.</span></span> <span data-ttu-id="d1858-249">RSquared 将是介于 0 和 1 之间的值。</span><span class="sxs-lookup"><span data-stu-id="d1858-249">RSquared will be a value between 0 and 1.</span></span> <span data-ttu-id="d1858-250">越接近 1，模型越好。</span><span class="sxs-lookup"><span data-stu-id="d1858-250">The closer you are to 1, the better your model.</span></span> <span data-ttu-id="d1858-251">将下面的代码添加到 `Evaluate()` 函数以打印模型的 RSquared 值。</span><span class="sxs-lookup"><span data-stu-id="d1858-251">Add the following code into the `Evaluate()` function to print the RSquared value for your model.</span></span>

[!code-csharp[DisplayRSquared](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#15 "Display the RSquared metric.")]

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="d1858-252">使用预测模型</span><span class="sxs-lookup"><span data-stu-id="d1858-252">Use the model for predictions</span></span>

<span data-ttu-id="d1858-253">接下来，创建一个类来存放测试场景，可以使用这些场景来确保模型正常工作：</span><span class="sxs-lookup"><span data-stu-id="d1858-253">Next, create a class to house test scenarios that you can use to make sure your model is working correctly:</span></span>

1. <span data-ttu-id="d1858-254">在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新项”。</span><span class="sxs-lookup"><span data-stu-id="d1858-254">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="d1858-255">在“添加新项”对话框中，选择“类”并将“名称”字段更改为“TestTrips.cs”。</span><span class="sxs-lookup"><span data-stu-id="d1858-255">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TestTrips.cs*.</span></span> <span data-ttu-id="d1858-256">然后，选择“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="d1858-256">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="d1858-257">将类修改为静态，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="d1858-257">Modify the class to be static like in the following example:</span></span>

[!code-csharp[StaticClass](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#1 "Change class to be a static class.")]

<span data-ttu-id="d1858-258">本教程使用此类中的一个测试行程。</span><span class="sxs-lookup"><span data-stu-id="d1858-258">This tutorial uses one test trip within this class.</span></span> <span data-ttu-id="d1858-259">稍后可以添加其他方案，以尝试使用此示例。</span><span class="sxs-lookup"><span data-stu-id="d1858-259">Later you can add other scenarios to experiment with this sample.</span></span> <span data-ttu-id="d1858-260">将下面的代码添加到 `TestTrips` 类中：</span><span class="sxs-lookup"><span data-stu-id="d1858-260">Add the following code into the `TestTrips` class:</span></span>

[!code-csharp[TestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#2 "Create aq trip to predict its cost.")]

<span data-ttu-id="d1858-261">此行程实际费用为 29.5，但使用 0 作为占位符。</span><span class="sxs-lookup"><span data-stu-id="d1858-261">This trip's actual fare is 29.5, but use 0 as a placeholder.</span></span> <span data-ttu-id="d1858-262">机器学习算法将预测费用。</span><span class="sxs-lookup"><span data-stu-id="d1858-262">The machine learning algorithm will predict the fare.</span></span>

<span data-ttu-id="d1858-263">在 `Main` 函数中添加以下代码。</span><span class="sxs-lookup"><span data-stu-id="d1858-263">Add the following code in your `Main` function.</span></span> <span data-ttu-id="d1858-264">它使用 `TestTrip` 数据测试模型：</span><span class="sxs-lookup"><span data-stu-id="d1858-264">It tests out your model using the `TestTrip` data:</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#16 "Try a prediction.")]

<span data-ttu-id="d1858-265">运行此程序，查看测试用例的预测出租车费。</span><span class="sxs-lookup"><span data-stu-id="d1858-265">Run the program to see the predicted taxi fare for your test case.</span></span>

<span data-ttu-id="d1858-266">祝贺你！</span><span class="sxs-lookup"><span data-stu-id="d1858-266">Congratulations!</span></span> <span data-ttu-id="d1858-267">你已成功生成用于预测出租车费的机器学习模型、评估其准确性，并对其进行了测试。</span><span class="sxs-lookup"><span data-stu-id="d1858-267">You've now successfully built a machine learning model for predicting taxi fares, evaluated its accuracy, and tested it.</span></span> <span data-ttu-id="d1858-268">可以在 [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction) 存储库中找到本教程的源代码。</span><span class="sxs-lookup"><span data-stu-id="d1858-268">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d1858-269">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d1858-269">Next steps</span></span>

<span data-ttu-id="d1858-270">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="d1858-270">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="d1858-271">了解问题</span><span class="sxs-lookup"><span data-stu-id="d1858-271">Understand the problem</span></span>
> * <span data-ttu-id="d1858-272">选择适当的机器学习任务</span><span class="sxs-lookup"><span data-stu-id="d1858-272">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="d1858-273">准备和了解数据</span><span class="sxs-lookup"><span data-stu-id="d1858-273">Prepare and understand your data</span></span>
> * <span data-ttu-id="d1858-274">创建学习管道</span><span class="sxs-lookup"><span data-stu-id="d1858-274">Create a learning pipeline</span></span>
> * <span data-ttu-id="d1858-275">加载和转换数据</span><span class="sxs-lookup"><span data-stu-id="d1858-275">Load and transform your data</span></span>
> * <span data-ttu-id="d1858-276">选择学习算法</span><span class="sxs-lookup"><span data-stu-id="d1858-276">Choose a learning algorithm</span></span>
> * <span data-ttu-id="d1858-277">定型模型</span><span class="sxs-lookup"><span data-stu-id="d1858-277">Train the model</span></span>
> * <span data-ttu-id="d1858-278">评估模型</span><span class="sxs-lookup"><span data-stu-id="d1858-278">Evaluate the model</span></span>
> * <span data-ttu-id="d1858-279">使用预测模型</span><span class="sxs-lookup"><span data-stu-id="d1858-279">Use the model for predictions</span></span>

<span data-ttu-id="d1858-280">查看我们的 GitHub 存储库以继续学习，并找到更多示例。</span><span class="sxs-lookup"><span data-stu-id="d1858-280">Check out our GitHub repository to continue learning and find more samples.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="d1858-281">dotnet/machinelearning GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="d1858-281">dotnet/machinelearning GitHub repository</span></span>](https://github.com/dotnet/machinelearning/)

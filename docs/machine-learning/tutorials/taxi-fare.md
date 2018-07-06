---
title: 使用 ML.NET 预测纽约出租车费（回归）
description: 了解如何在回归方案中使用 ML.NET。
author: aditidugar
ms.author: johalex
ms.date: 06/18/2018
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 9706dad0a8e32651496e0404be4501c2c70e9d75
ms.sourcegitcommit: ed7b4b9b77d35e94a35a2634e8c874f46603fb2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2018
ms.locfileid: "36948626"
---
# <a name="tutorial-use-mlnet-to-predict-new-york-taxi-fares-regression"></a><span data-ttu-id="54483-103">教程：使用 ML.NET 预测纽约出租车费（回归）</span><span class="sxs-lookup"><span data-stu-id="54483-103">Tutorial: Use ML.NET to predict New York taxi fares (regression)</span></span>

> [!NOTE]
> <span data-ttu-id="54483-104">本主题引用 ML.NET（目前处于预览状态），且材料可能会更改。</span><span class="sxs-lookup"><span data-stu-id="54483-104">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="54483-105">有关详细信息，请访问 [ML.NET 简介](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)。</span><span class="sxs-lookup"><span data-stu-id="54483-105">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="54483-106">本教程演示如何使用 ML.NET 构建[回归模型](../resources/glossary.md#regression)来预测纽约市出租车费。</span><span class="sxs-lookup"><span data-stu-id="54483-106">This tutorial illustrates how to use ML.NET to build a [regression model](../resources/glossary.md#regression) for predicting New York City taxi fares.</span></span>

<span data-ttu-id="54483-107">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="54483-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="54483-108">了解问题</span><span class="sxs-lookup"><span data-stu-id="54483-108">Understand the problem</span></span>
> * <span data-ttu-id="54483-109">选择适当的机器学习任务</span><span class="sxs-lookup"><span data-stu-id="54483-109">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="54483-110">准备和了解数据</span><span class="sxs-lookup"><span data-stu-id="54483-110">Prepare and understand the data</span></span>
> * <span data-ttu-id="54483-111">创建学习管道</span><span class="sxs-lookup"><span data-stu-id="54483-111">Create a learning pipeline</span></span>
> * <span data-ttu-id="54483-112">加载和转换数据</span><span class="sxs-lookup"><span data-stu-id="54483-112">Load and transform the data</span></span>
> * <span data-ttu-id="54483-113">选择学习算法</span><span class="sxs-lookup"><span data-stu-id="54483-113">Choose a learning algorithm</span></span>
> * <span data-ttu-id="54483-114">定型模型</span><span class="sxs-lookup"><span data-stu-id="54483-114">Train the model</span></span>
> * <span data-ttu-id="54483-115">评估模型</span><span class="sxs-lookup"><span data-stu-id="54483-115">Evaluate the model</span></span>
> * <span data-ttu-id="54483-116">使用预测模型</span><span class="sxs-lookup"><span data-stu-id="54483-116">Use the model for predictions</span></span>

## <a name="prerequisites"></a><span data-ttu-id="54483-117">系统必备</span><span class="sxs-lookup"><span data-stu-id="54483-117">Prerequisites</span></span>

* <span data-ttu-id="54483-118">安装了“.NET Core 跨平台开发”工作负载的 [Visual Studio 2017 15.6 或更高版本](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)。</span><span class="sxs-lookup"><span data-stu-id="54483-118">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="understand-the-problem"></a><span data-ttu-id="54483-119">了解问题</span><span class="sxs-lookup"><span data-stu-id="54483-119">Understand the problem</span></span>

<span data-ttu-id="54483-120">此问题围绕“预测纽约市的出租车行程费用”展开。</span><span class="sxs-lookup"><span data-stu-id="54483-120">This problem is centered around **predicting the fare of a taxi trip in New York City**.</span></span> <span data-ttu-id="54483-121">从表面看，似乎只取决于行程距离。</span><span class="sxs-lookup"><span data-stu-id="54483-121">At first glance, it may seem to depend simply on the distance traveled.</span></span> <span data-ttu-id="54483-122">但是，由于其他因素（比如额外的乘客或使用信用卡而非现金付款），纽约的出租车供应商收费不同。</span><span class="sxs-lookup"><span data-stu-id="54483-122">However, taxi vendors in New York charge varying amounts for other factors such as additional passengers or paying with a credit card instead of cash.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="54483-123">选择适当的机器学习任务</span><span class="sxs-lookup"><span data-stu-id="54483-123">Select the appropriate machine learning task</span></span>

<span data-ttu-id="54483-124">若要预测出租车费，首先选择适当的机器学习任务。</span><span class="sxs-lookup"><span data-stu-id="54483-124">To predict the taxi fare, you first select the appropriate machine learning task.</span></span> <span data-ttu-id="54483-125">你希望基于数据集中的其他因素预测实际值（表示价格的双精度值）。</span><span class="sxs-lookup"><span data-stu-id="54483-125">You are looking to predict a real value (a double that represents price) based on the other factors in the dataset.</span></span> <span data-ttu-id="54483-126">你选择[回归](../resources/glossary.md#regression)任务。</span><span class="sxs-lookup"><span data-stu-id="54483-126">You choose a [**regression**](../resources/glossary.md#regression) task.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="54483-127">创建控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="54483-127">Create a console application</span></span>

1. <span data-ttu-id="54483-128">打开 Visual Studio 2017。</span><span class="sxs-lookup"><span data-stu-id="54483-128">Open Visual Studio 2017.</span></span> <span data-ttu-id="54483-129">从菜单栏中选择“文件” > “新建” > “项目”。</span><span class="sxs-lookup"><span data-stu-id="54483-129">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="54483-130">在“新项目”对话框中，依次选择“Visual C#”和“.NET Core”节点。</span><span class="sxs-lookup"><span data-stu-id="54483-130">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="54483-131">然后，选择“控制台应用程序(.NET Core)”项目模板。</span><span class="sxs-lookup"><span data-stu-id="54483-131">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="54483-132">在“名称”文本框中，键入“TaxiFarePrediction”，然后选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="54483-132">In the **Name** text box, type "TaxiFarePrediction" and then select the **OK** button.</span></span>

2. <span data-ttu-id="54483-133">在项目中创建一个名为“数据”的目录来保存数据集文件：</span><span class="sxs-lookup"><span data-stu-id="54483-133">Create a directory named *Data* in your project to save the data set files:</span></span>

    <span data-ttu-id="54483-134">在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新文件夹”。</span><span class="sxs-lookup"><span data-stu-id="54483-134">In **Solution Explorer**, right-click the project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="54483-135">键入“数据”，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="54483-135">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="54483-136">安装“Microsoft.ML NuGet 包”：</span><span class="sxs-lookup"><span data-stu-id="54483-136">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="54483-137">在“解决方案资源管理器”中，右键单击项目，然后选择“管理 NuGet 包”。</span><span class="sxs-lookup"><span data-stu-id="54483-137">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="54483-138">将“nuget.org”选择为“包源”，选择“浏览”选项卡并搜索“Microsoft.ML”，在列表中选择该包，然后选择“安装”按钮。</span><span class="sxs-lookup"><span data-stu-id="54483-138">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="54483-139">选择“预览更改”对话框上的“确定”按钮，如果你同意所列包的许可条款，则选择“接受许可”对话框上的“我接受”按钮。</span><span class="sxs-lookup"><span data-stu-id="54483-139">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="54483-140">准备和了解数据</span><span class="sxs-lookup"><span data-stu-id="54483-140">Prepare and understand the data</span></span>

1. <span data-ttu-id="54483-141">下载 [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) 和 [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) 数据集，并将它们保存到先前创建的“数据”文件夹。</span><span class="sxs-lookup"><span data-stu-id="54483-141">Download the [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) and the [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) data sets and save them to the *Data* folder you've created at the previous step.</span></span> <span data-ttu-id="54483-142">我们使用这些数据集定型机器学习模型，然后评估模型的准确性。</span><span class="sxs-lookup"><span data-stu-id="54483-142">We use these data sets to train the machine learning model and then evaluate how accurate the model is.</span></span> <span data-ttu-id="54483-143">这些数据集最初来自 [NYC TLC 出租车行程数据集](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml)。</span><span class="sxs-lookup"><span data-stu-id="54483-143">These data sets are originally from the [NYC TLC Taxi Trip data set](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span></span>

2. <span data-ttu-id="54483-144">在“解决方案资源管理器”中，右键单击每个 \*.csv 文件，然后选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="54483-144">In **Solution Explorer**, right-click each of the \*.csv files and select **Properties**.</span></span> <span data-ttu-id="54483-145">在“高级”下，将“复制到输出目录”的值更改为“始终”。</span><span class="sxs-lookup"><span data-stu-id="54483-145">Under **Advanced**, change the value of **Copy to Output Directory** to **Always**.</span></span>

3. <span data-ttu-id="54483-146">打开“taxi-fare-train.csv”数据集并查看第一行中的列标题。</span><span class="sxs-lookup"><span data-stu-id="54483-146">Open the **taxi-fare-train.csv** data set and look at column headers in the first row.</span></span> <span data-ttu-id="54483-147">查看每个列。</span><span class="sxs-lookup"><span data-stu-id="54483-147">Take a look at each of the columns.</span></span> <span data-ttu-id="54483-148">了解数据并确定哪些列是“特征”以及哪些是“标签”。</span><span class="sxs-lookup"><span data-stu-id="54483-148">Understand the data and decide which columns are **features** and which one is the **label**.</span></span>

<span data-ttu-id="54483-149">“标签”是希望预测的列的标识符。</span><span class="sxs-lookup"><span data-stu-id="54483-149">The **label** is the identifier of the column you want to predict.</span></span> <span data-ttu-id="54483-150">标识的“特征”用于预测标签。</span><span class="sxs-lookup"><span data-stu-id="54483-150">The identified **features** are used to predict the label.</span></span>

<span data-ttu-id="54483-151">提供的数据集包含以下列：</span><span class="sxs-lookup"><span data-stu-id="54483-151">The provided data set contains the following columns:</span></span>

* <span data-ttu-id="54483-152">vendor_id：出租车供应商的 ID 是一项特征。</span><span class="sxs-lookup"><span data-stu-id="54483-152">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
* <span data-ttu-id="54483-153">rate_code：出租车行程的费率类型是一项特征。</span><span class="sxs-lookup"><span data-stu-id="54483-153">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
* <span data-ttu-id="54483-154">passenger_count：行程乘客数是一项特征。</span><span class="sxs-lookup"><span data-stu-id="54483-154">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
* <span data-ttu-id="54483-155">trip_time_in_secs：行程花费的时间量。</span><span class="sxs-lookup"><span data-stu-id="54483-155">**trip_time_in_secs:** The amount of time the trip took.</span></span> <span data-ttu-id="54483-156">希望在行程完成前预测行程费用。</span><span class="sxs-lookup"><span data-stu-id="54483-156">You want to predict the fare of the trip before the trip is completed.</span></span> <span data-ttu-id="54483-157">当时并不知道行程有多长。</span><span class="sxs-lookup"><span data-stu-id="54483-157">At that moment you don't know how long the trip would take.</span></span> <span data-ttu-id="54483-158">因此，行程时间不是一项特征，需要从模型删除此列。</span><span class="sxs-lookup"><span data-stu-id="54483-158">Thus, the trip time is not a feature and you'll exclude this column from the model.</span></span>
* <span data-ttu-id="54483-159">trip_distance：行程距离是一项特征。</span><span class="sxs-lookup"><span data-stu-id="54483-159">**trip_distance:** The distance of the trip is a feature.</span></span>
* <span data-ttu-id="54483-160">payment_type：付款方式（现金或信用卡）是一项特征。</span><span class="sxs-lookup"><span data-stu-id="54483-160">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
* <span data-ttu-id="54483-161">fare_amount：支付的总出租车费是一个标签。</span><span class="sxs-lookup"><span data-stu-id="54483-161">**fare_amount:** The total taxi fare paid is the label.</span></span>

## <a name="create-data-classes"></a><span data-ttu-id="54483-162">创建数据类</span><span class="sxs-lookup"><span data-stu-id="54483-162">Create data classes</span></span>

<span data-ttu-id="54483-163">创建输入数据和预测类：</span><span class="sxs-lookup"><span data-stu-id="54483-163">Create classes for the input data and the predictions:</span></span>

1. <span data-ttu-id="54483-164">在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新项”。</span><span class="sxs-lookup"><span data-stu-id="54483-164">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="54483-165">在“添加新项”对话框中，选择“类”并将“名称”字段更改为“TaxiTrip.cs”。</span><span class="sxs-lookup"><span data-stu-id="54483-165">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TaxiTrip.cs*.</span></span> <span data-ttu-id="54483-166">然后，选择“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="54483-166">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="54483-167">将以下 `using` 指令添加到新文件：</span><span class="sxs-lookup"><span data-stu-id="54483-167">Add the following `using` directives to the new file:</span></span>

   [!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#1 "Add necessary usings")]

<span data-ttu-id="54483-168">删除现有类定义并向“TaxiTrip.cs”文件添加以下代码，其中有两个类 `TaxiTrip` 和 `TaxiTripFarePrediction`：</span><span class="sxs-lookup"><span data-stu-id="54483-168">Remove the existing class definition and add the following code, which has two classes `TaxiTrip` and `TaxiTripFarePrediction`, to the *TaxiTrip.cs* file:</span></span>

[!code-csharp[DefineTaxiTrip](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#2 "Define the taxi trip and fare predictions classes")]

<span data-ttu-id="54483-169">`TaxiTrip` 是输入数据类且具有针对每个数据集列的定义。</span><span class="sxs-lookup"><span data-stu-id="54483-169">`TaxiTrip` is the input data class and has definitions for each of the data set columns.</span></span> <span data-ttu-id="54483-170">使用[列](xref:Microsoft.ML.Runtime.Api.ColumnAttribute)属性在数据集中指定源列的索引。</span><span class="sxs-lookup"><span data-stu-id="54483-170">Use the [Column](xref:Microsoft.ML.Runtime.Api.ColumnAttribute) attribute to specify the indices of the source columns in the data set.</span></span>

<span data-ttu-id="54483-171">使用 `TaxiTripFarePrediction` 类表示预测的结果。</span><span class="sxs-lookup"><span data-stu-id="54483-171">The `TaxiTripFarePrediction` class is used to represent predicted results.</span></span> <span data-ttu-id="54483-172">它应用了单个浮动 (`FareAmount`) 字段，附带 `Score` [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute) 属性。</span><span class="sxs-lookup"><span data-stu-id="54483-172">It has a single float (`FareAmount`) field with a `Score` [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute) attribute applied.</span></span> <span data-ttu-id="54483-173">“分数”列是 ML.NET 中的特殊列。</span><span class="sxs-lookup"><span data-stu-id="54483-173">The **Score** column is the special column in ML.NET.</span></span> <span data-ttu-id="54483-174">模型将预测值输出到该列。</span><span class="sxs-lookup"><span data-stu-id="54483-174">The model outputs predicted values into that column.</span></span>

## <a name="define-data-and-model-paths"></a><span data-ttu-id="54483-175">定义数据和模型路径</span><span class="sxs-lookup"><span data-stu-id="54483-175">Define data and model paths</span></span>

<span data-ttu-id="54483-176">返回到 Program.cs 文件并添加三个字段，以保存具有数据集的文件的路径以及用于保存模型的文件的路径：</span><span class="sxs-lookup"><span data-stu-id="54483-176">Go back to the *Program.cs* file and add three fields to hold the paths to the files with data sets and the file to save the model:</span></span>

* <span data-ttu-id="54483-177">`_datapath` 包含具有用于定型模型的数据集的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="54483-177">`_datapath` contains the path to the file with the data set used to train the model.</span></span>
* <span data-ttu-id="54483-178">`_testdatapath` 包含具有用于评估模型的数据集的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="54483-178">`_testdatapath` contains the path to the file with the data set used to evaluate the model.</span></span>
* <span data-ttu-id="54483-179">`_modelpath` 包含用于存储定型模型的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="54483-179">`_modelpath` contains the path to the file where the trained model is stored.</span></span>

<span data-ttu-id="54483-180">将以下代码添加到 `Main` 方法上方，以指定这些路径：</span><span class="sxs-lookup"><span data-stu-id="54483-180">Add the following code right above the `Main` method to specify those paths:</span></span>

[!code-csharp[InitializePaths](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#2 "Define variables to store the data file paths")]

<span data-ttu-id="54483-181">要编译前面的代码，请将以下 `using` 指令添加到 Program.cs 文件顶部：</span><span class="sxs-lookup"><span data-stu-id="54483-181">To make the preceding code compile, add the following `using` directives at the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsingsForPaths](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#17 "Using statements for path definitions")]

## <a name="create-a-learning-pipeline"></a><span data-ttu-id="54483-182">创建学习管道</span><span class="sxs-lookup"><span data-stu-id="54483-182">Create a learning pipeline</span></span>

<span data-ttu-id="54483-183">将以下附加 `using` 指令添加到 Program.cs 文件顶部：</span><span class="sxs-lookup"><span data-stu-id="54483-183">Add the following additional `using` directives to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#1 "Add necessary usings")]

<span data-ttu-id="54483-184">在 `Main` 中，将 `Console.WriteLine("Hello World!")` 替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="54483-184">In `Main`, replace the `Console.WriteLine("Hello World!")` with the following code:</span></span>

```csharp
PredictionModel<TaxiTrip, TaxiTripFarePrediction> model = Train();
```

<span data-ttu-id="54483-185">`Train` 方法定型模型。</span><span class="sxs-lookup"><span data-stu-id="54483-185">The `Train` method trains the model.</span></span> <span data-ttu-id="54483-186">使用以下代码在 `Main` 下创建该方法：</span><span class="sxs-lookup"><span data-stu-id="54483-186">Create that method just below `Main`, using the following code:</span></span>

```csharp
public static PredictionModel<TaxiTrip, TaxiTripFarePrediction> Train()
{

}
```

<span data-ttu-id="54483-187">学习管道加载所有数据和所需的算法来定型模型。</span><span class="sxs-lookup"><span data-stu-id="54483-187">The learning pipeline loads all of the data and algorithms necessary to train the model.</span></span> <span data-ttu-id="54483-188">将以下代码添加到 `Train` 方法：</span><span class="sxs-lookup"><span data-stu-id="54483-188">Add the following code into the `Train` method:</span></span>

```csharp
var pipeline = new LearningPipeline();
```

## <a name="load-and-transform-data"></a><span data-ttu-id="54483-189">加载和转换数据</span><span class="sxs-lookup"><span data-stu-id="54483-189">Load and transform data</span></span>

<span data-ttu-id="54483-190">学习管道执行的第一步是从定型数据集加载数据。</span><span class="sxs-lookup"><span data-stu-id="54483-190">The first step that the learning pipeline performs is loading data from the training data set.</span></span> <span data-ttu-id="54483-191">在本例中，定型数据集存储在具有 `_datapath` 字段所定义路径的文本文件中。</span><span class="sxs-lookup"><span data-stu-id="54483-191">In our case, training data set is stored in the text file with a path defined by the `_datapath` field.</span></span> <span data-ttu-id="54483-192">该文件包含有列名的标头，所以加载数据时应忽略第一行。</span><span class="sxs-lookup"><span data-stu-id="54483-192">That file contains the header with the column names, so the first row should be ignored while loading data.</span></span> <span data-ttu-id="54483-193">文件中的列用逗号 (",") 分割。</span><span class="sxs-lookup"><span data-stu-id="54483-193">Columns in the file are separated by the comma (",").</span></span> <span data-ttu-id="54483-194">将以下代码添加到 `Train` 方法：</span><span class="sxs-lookup"><span data-stu-id="54483-194">Add the following code into the `Train` method:</span></span>

```csharp
pipeline.Add(new TextLoader(_datapath).CreateFrom<TaxiTrip>(useHeader: true, separator: ','));
```

<span data-ttu-id="54483-195">在后续步骤中，我们按 `TaxiTrip` 类中定义的名称引用列。</span><span class="sxs-lookup"><span data-stu-id="54483-195">In the next steps we refer to the columns by the names defined in the `TaxiTrip` class.</span></span>

<span data-ttu-id="54483-196">定型和评估模型时，将“标签”列中的值视为要预测的正确值。</span><span class="sxs-lookup"><span data-stu-id="54483-196">When the model is trained and evaluated, the values in the **Label** column are considered as correct values to be predicted.</span></span> <span data-ttu-id="54483-197">希望预测出租车费时，将 `FareAmount` 列复制到“标签”列。</span><span class="sxs-lookup"><span data-stu-id="54483-197">As we want to predict the taxi trip fare, copy the `FareAmount` column into the **Label** column.</span></span> <span data-ttu-id="54483-198">为此，请使用 <xref:Microsoft.ML.Transforms.ColumnCopier> 并添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="54483-198">To do that, use <xref:Microsoft.ML.Transforms.ColumnCopier> and add the following code:</span></span>

```csharp
pipeline.Add(new ColumnCopier(("FareAmount", "Label")));
```

<span data-ttu-id="54483-199">定型模型的算法需要数值特征，所以必须将分类数据（`VendorId`、`RateCode` 和 `PaymentType`）值转换为数字。</span><span class="sxs-lookup"><span data-stu-id="54483-199">The algorithm that trains the model requires **numeric** features, so you have to transform the categorical data (`VendorId`, `RateCode`, and `PaymentType`) values into numbers.</span></span> <span data-ttu-id="54483-200">为此，请使用 <xref:Microsoft.ML.Transforms.CategoricalOneHotVectorizer>，它将不同的数字键值分配到每行的不同值，并添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="54483-200">To do that, use <xref:Microsoft.ML.Transforms.CategoricalOneHotVectorizer>, which assigns different numeric key values to the different values in each of the columns, and add the following code:</span></span>

```csharp
pipeline.Add(new CategoricalOneHotVectorizer("VendorId",
                                             "RateCode",
                                             "PaymentType"));
```

<span data-ttu-id="54483-201">数据准备最后一步使用 <xref:Microsoft.ML.Transforms.ColumnConcatenator> 转换类将所有功能列合并到“功能”列。</span><span class="sxs-lookup"><span data-stu-id="54483-201">The last step in data preparation combines all of the feature columns into the **Features** column using the <xref:Microsoft.ML.Transforms.ColumnConcatenator> transformation class.</span></span> <span data-ttu-id="54483-202">此步骤是必需的，因为学习器仅处理“功能”列的功能。</span><span class="sxs-lookup"><span data-stu-id="54483-202">This step is necessary as a learner processes only features from the **Features** column.</span></span> <span data-ttu-id="54483-203">添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="54483-203">Add the following code:</span></span>

```csharp
pipeline.Add(new ColumnConcatenator("Features",
                                    "VendorId",
                                    "RateCode",
                                    "PassengerCount",
                                    "TripDistance",
                                    "PaymentType"));
```

<span data-ttu-id="54483-204">请注意，不包括 `TripTime` 列（对应数据集文件中的 `trip_time_in_secs` 列）。</span><span class="sxs-lookup"><span data-stu-id="54483-204">Notice that the `TripTime` column, which corresponds to the `trip_time_in_secs` column in the data set file, isn't included.</span></span> <span data-ttu-id="54483-205">你已确定它不是一项有用的预测特征。</span><span class="sxs-lookup"><span data-stu-id="54483-205">You already determined that it isn't a useful prediction feature.</span></span>

> [!NOTE]
> <span data-ttu-id="54483-206">必须按照上面指定的顺序将这些步骤添加到管道才能成功执行。</span><span class="sxs-lookup"><span data-stu-id="54483-206">These steps must be added to the pipeline in the order specified above for successful execution.</span></span>

## <a name="choose-a-learning-algorithm"></a><span data-ttu-id="54483-207">选择学习算法</span><span class="sxs-lookup"><span data-stu-id="54483-207">Choose a learning algorithm</span></span>

<span data-ttu-id="54483-208">在将数据添加到管道，并将其转换为正确的输入格式之后，可以选择学习算法（学习器）。</span><span class="sxs-lookup"><span data-stu-id="54483-208">After adding the data to the pipeline and transforming it into the correct input format, you select a learning algorithm (**learner**).</span></span> <span data-ttu-id="54483-209">学习器定型模型。</span><span class="sxs-lookup"><span data-stu-id="54483-209">The learner trains the model.</span></span> <span data-ttu-id="54483-210">为此问题选择了“回归任务”，所以添加 <xref:Microsoft.ML.Trainers.FastTreeRegressor> 学习器（ML.NET 提供的一种回归学习器）。</span><span class="sxs-lookup"><span data-stu-id="54483-210">You chose a **regression task** for this problem, so you add a <xref:Microsoft.ML.Trainers.FastTreeRegressor> learner, which is one of the regression learners provided by ML.NET.</span></span>

<span data-ttu-id="54483-211"><xref:Microsoft.ML.Trainers.FastTreeRegressor> 学习器利用梯度提升。</span><span class="sxs-lookup"><span data-stu-id="54483-211"><xref:Microsoft.ML.Trainers.FastTreeRegressor> learner utilizes gradient boosting.</span></span> <span data-ttu-id="54483-212">梯度提升是针对回归问题的一项机器学习技术。</span><span class="sxs-lookup"><span data-stu-id="54483-212">Gradient boosting is a machine learning technique for regression problems.</span></span> <span data-ttu-id="54483-213">它将以步进方式生成每个回归树。</span><span class="sxs-lookup"><span data-stu-id="54483-213">It builds each regression tree in a step-wise fashion.</span></span> <span data-ttu-id="54483-214">它使用预定义的损失函数测量每个步骤中的错误，并在下一步中对其进行校正。</span><span class="sxs-lookup"><span data-stu-id="54483-214">It uses a pre-defined loss function to measure the error in each step and correct for it in the next.</span></span> <span data-ttu-id="54483-215">其结果是一种预测模型，实际上是一组较弱的预测模型。</span><span class="sxs-lookup"><span data-stu-id="54483-215">The result is a prediction model that is actually an ensemble of weaker prediction models.</span></span> <span data-ttu-id="54483-216">有关梯度提升的详细信息，请参阅[提升的决策树回归](/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression)。</span><span class="sxs-lookup"><span data-stu-id="54483-216">For more information about gradient boosting, see [Boosted Decision Tree Regression](/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression).</span></span>

<span data-ttu-id="54483-217">将下面的代码添加到在上一步中添加的数据处理代码后面的 `Train` 方法中：</span><span class="sxs-lookup"><span data-stu-id="54483-217">Add the following code into the `Train` method following the data processing code added in the previous step:</span></span>

```csharp
pipeline.Add(new FastTreeRegressor());
```

<span data-ttu-id="54483-218">你已将前面所有步骤作为单个语句添加到管道，但 C# 包含可以更轻松地创建和初始化管道的方便集合初始化语法。</span><span class="sxs-lookup"><span data-stu-id="54483-218">You added all the preceding steps to the pipeline as individual statements, but C# has a handy collection initialization syntax that makes it simpler to create and initialize the pipeline.</span></span> <span data-ttu-id="54483-219">将目前添加到 `Train` 方法的代码替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="54483-219">Replace the code you added so far to the `Train` method with the following code:</span></span>

[!code-csharp[CreatePipeline](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#3 "Create and initialize the learning pipeline")]

## <a name="train-the-model"></a><span data-ttu-id="54483-220">定型模型</span><span class="sxs-lookup"><span data-stu-id="54483-220">Train the model</span></span>

<span data-ttu-id="54483-221">最后一步是定型模型。</span><span class="sxs-lookup"><span data-stu-id="54483-221">The final step is to train the model.</span></span> <span data-ttu-id="54483-222">在此之前，管道中未执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="54483-222">Until this point, nothing in the pipeline has been executed.</span></span> <span data-ttu-id="54483-223">`pipeline.Train<TInput, TOutput>` 方法生成的模型接收 `TInput` 类型实例并输出 `TOutput` 类型实例。</span><span class="sxs-lookup"><span data-stu-id="54483-223">The `pipeline.Train<TInput, TOutput>` method produces the model that takes in an instance of the `TInput` type and outputs an instance of the `TOutput` type.</span></span> <span data-ttu-id="54483-224">将以下代码添加到 `Train` 方法：</span><span class="sxs-lookup"><span data-stu-id="54483-224">Add the following code into the `Train` method:</span></span>

[!code-csharp[TrainMOdel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#4 "Train your model")]

<span data-ttu-id="54483-225">就是这么简单！</span><span class="sxs-lookup"><span data-stu-id="54483-225">And that's it!</span></span> <span data-ttu-id="54483-226">已成功定型机器学习模型，可以用来预测 NYC 的出租车费。</span><span class="sxs-lookup"><span data-stu-id="54483-226">You have successfully trained a machine learning model that can predict taxi fares in NYC.</span></span> <span data-ttu-id="54483-227">现在，我们看一下模型的精确性并了解如何用它来预测出租车费的值。</span><span class="sxs-lookup"><span data-stu-id="54483-227">Now let's take a look to understand how accurate the model is and learn how to use it to predict taxi fare values.</span></span>

### <a name="save-the-model"></a><span data-ttu-id="54483-228">保存模型</span><span class="sxs-lookup"><span data-stu-id="54483-228">Save the model</span></span>

<span data-ttu-id="54483-229">继续下一步之前，通过在 `Train` 方法的末尾添加以下代码，将模型保存到一个 .zip 文件：</span><span class="sxs-lookup"><span data-stu-id="54483-229">Before you go onto the next step, save the model to a .zip file by adding the following code at the end of the `Train` method:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#5 "Save the model asynchronously and return the model")]

<span data-ttu-id="54483-230">将 `await` 语句添加到 `model.WriteAsync` 调用中意味着 `Train` 方法必须更改为返回任务的异步方法。</span><span class="sxs-lookup"><span data-stu-id="54483-230">Adding the `await` statement to the `model.WriteAsync` call means that the `Train` method must be changed to an async method that returns a task.</span></span> <span data-ttu-id="54483-231">修改 `Train` 的签名，如下面的代码所示：</span><span class="sxs-lookup"><span data-stu-id="54483-231">Modify the signature of `Train` as shown in the following code:</span></span>

[!code-csharp[AsyncTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#6 "Make the Train method async and return a task.")]

<span data-ttu-id="54483-232">更改 `Train` 方法的返回类型意味着你需要将 `await` 添加到调用 `Main` 方法中的 `Train` 的代码，如下面的代码所示：</span><span class="sxs-lookup"><span data-stu-id="54483-232">Changing the return type of the `Train` method means you have to add an `await` to the code that calls `Train` in the `Main` method as shown in the following code:</span></span>

[!code-csharp[AwaitTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#7 "Await the Train method")]

<span data-ttu-id="54483-233">在 `Main` 方法中使用 `await` 意味着 `Main` 方法必须具有 `async` 修饰符并返回 `Task`：</span><span class="sxs-lookup"><span data-stu-id="54483-233">Using `await` in the `Main` method means the `Main` method must have the `async` modifier and return a `Task`:</span></span>

[!code-csharp[AsyncMain](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#8 "Make the Main method async and return a task.")]

<span data-ttu-id="54483-234">还需要将以下 `using` 指令添加到文件顶部：</span><span class="sxs-lookup"><span data-stu-id="54483-234">You also need to add the following `using` directive at the top of the file:</span></span>

[!code-csharp[UsingTasks](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#9 "Add System.Threading.Tasks. to your usings.")]

<span data-ttu-id="54483-235">由于 `async Main` 方法是 C# 7.1 中的新增功能，且项目的默认语言版本为 C# 7.0，因此需要将语言版本更改为 C# 7.1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="54483-235">Because the `async Main` method is the feature added in C# 7.1 and the default language version of the project is C# 7.0, you need to change the language version to C# 7.1 or higher.</span></span> <span data-ttu-id="54483-236">要完成此操作，右键单击“解决方案资源管理器”中的项目节点，然后选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="54483-236">To do that, right-click the project node in **Solution Explorer** and select **Properties**.</span></span> <span data-ttu-id="54483-237">选择**生成**选项卡并选择**高级**按钮。</span><span class="sxs-lookup"><span data-stu-id="54483-237">Select the **Build** tab and select the **Advanced** button.</span></span> <span data-ttu-id="54483-238">在下拉列表中，选择“C# 7.1”（或更高版本）。</span><span class="sxs-lookup"><span data-stu-id="54483-238">In the dropdown, select  **C# 7.1** (or a higher version).</span></span> <span data-ttu-id="54483-239">选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="54483-239">Select the **OK** button.</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="54483-240">评估模型</span><span class="sxs-lookup"><span data-stu-id="54483-240">Evaluate the model</span></span>

<span data-ttu-id="54483-241">评估是检查模型预测标签值情况的过程。</span><span class="sxs-lookup"><span data-stu-id="54483-241">Evaluation is the process of checking how well the model predicts label values.</span></span> <span data-ttu-id="54483-242">模型对定型模型中未使用的数据做出好的预测非常重要。</span><span class="sxs-lookup"><span data-stu-id="54483-242">It's important that the model makes good predictions on data that was not used to train the model.</span></span> <span data-ttu-id="54483-243">执行此操作的一种方法是将数据拆分到定型和测试数据集，如此教程中所示。</span><span class="sxs-lookup"><span data-stu-id="54483-243">One way to do this is to split the data into train and test data sets, as it's done in this tutorial.</span></span> <span data-ttu-id="54483-244">你已在定型数据上定型模型，现在可以看到它在测试数据上的表现。</span><span class="sxs-lookup"><span data-stu-id="54483-244">Now that you've trained the model on the train data, you can see how well it performs on the test data.</span></span>

<span data-ttu-id="54483-245">返回到 `Main` 方法，并在调用 `Train` 方法下添加以下代码：</span><span class="sxs-lookup"><span data-stu-id="54483-245">Go back to the `Main` method and add the following code beneath the call to the `Train`method:</span></span>

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#10 "Evaluate the model.")]

<span data-ttu-id="54483-246">`Evaluate` 方法评估模型。</span><span class="sxs-lookup"><span data-stu-id="54483-246">The `Evaluate` method evaluates the model.</span></span> <span data-ttu-id="54483-247">若要创建该方法，请将以下代码添加到 `Train` 方法下：</span><span class="sxs-lookup"><span data-stu-id="54483-247">To create that method, add the following code below the `Train` method:</span></span>

```csharp
private static void Evaluate(PredictionModel<TaxiTrip, TaxiTripFarePrediction> model)
{

}
```

<span data-ttu-id="54483-248">将以下代码添加到 `Evaluate` 方法，设置测试数据的加载：</span><span class="sxs-lookup"><span data-stu-id="54483-248">Add the following code into the `Evaluate` method to setup loading of the test data:</span></span>

[!code-csharp[LoadTestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#12 "Load the test data.")]

<span data-ttu-id="54483-249">添加以下代码以评估模型并生成评估模型：</span><span class="sxs-lookup"><span data-stu-id="54483-249">Add the following code to evaluate the model and produce the evaluation metrics:</span></span>

[!code-csharp[EvaluateAndMeasure](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#13 "Evaluate the model and its predictions.")]

<span data-ttu-id="54483-250">[RMS](../resources/glossary.md##root-of-mean-squared-error-rmse) 是回归模型的一种评估指标。</span><span class="sxs-lookup"><span data-stu-id="54483-250">[RMS](../resources/glossary.md##root-of-mean-squared-error-rmse) is one of the evaluation metrics of the regression model.</span></span> <span data-ttu-id="54483-251">指标越低，模型就越好。</span><span class="sxs-lookup"><span data-stu-id="54483-251">The lower it is, the better the model is.</span></span> <span data-ttu-id="54483-252">将以下代码添加到 `Evaluate` 方法以显示 RMS 值：</span><span class="sxs-lookup"><span data-stu-id="54483-252">Add the following code into the `Evaluate` method to display the RMS value:</span></span>

[!code-csharp[DisplayRMS](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#14 "Display the RMS metric.")]

<span data-ttu-id="54483-253">[RSquared](../resources/glossary.md#coefficient-of-determination) 是回归模型的另一种评估指标。</span><span class="sxs-lookup"><span data-stu-id="54483-253">[RSquared](../resources/glossary.md#coefficient-of-determination) is another evaluation metric of the regression models.</span></span> <span data-ttu-id="54483-254">RSquared 在 0 和 1 之间取值。</span><span class="sxs-lookup"><span data-stu-id="54483-254">RSquared takes values between 0 and 1.</span></span> <span data-ttu-id="54483-255">值越接近 1，模型就越好。</span><span class="sxs-lookup"><span data-stu-id="54483-255">The closer its value is to 1, the better the model is.</span></span> <span data-ttu-id="54483-256">将以下代码添加到 `Evaluate` 方法以显示 RSquared 值：</span><span class="sxs-lookup"><span data-stu-id="54483-256">Add the following code into the `Evaluate` method to display the RSquared value:</span></span>

[!code-csharp[DisplayRSquared](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#15 "Display the RSquared metric.")]

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="54483-257">使用预测模型</span><span class="sxs-lookup"><span data-stu-id="54483-257">Use the model for predictions</span></span>

<span data-ttu-id="54483-258">接下来，创建一个类来存放测试场景，可以使用这些场景来确保模型正常工作：</span><span class="sxs-lookup"><span data-stu-id="54483-258">Next, create a class to house test scenarios that you can use to make sure the model is working correctly:</span></span>

1. <span data-ttu-id="54483-259">在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新项”。</span><span class="sxs-lookup"><span data-stu-id="54483-259">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>
1. <span data-ttu-id="54483-260">在“添加新项”对话框中，选择“类”并将“名称”字段更改为“TestTrips.cs”。</span><span class="sxs-lookup"><span data-stu-id="54483-260">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *TestTrips.cs*.</span></span> <span data-ttu-id="54483-261">然后，选择“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="54483-261">Then, select the **Add** button.</span></span>
1. <span data-ttu-id="54483-262">将类修改为静态，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="54483-262">Modify the class to be static like in the following example:</span></span>

   [!code-csharp[StaticClass](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#1 "Change class to be a static class.")]

<span data-ttu-id="54483-263">本教程使用此类中的一个测试行程。</span><span class="sxs-lookup"><span data-stu-id="54483-263">This tutorial uses one test trip within this class.</span></span> <span data-ttu-id="54483-264">稍后可以添加其他方案，以尝试使用此模型。</span><span class="sxs-lookup"><span data-stu-id="54483-264">Later you can add other scenarios to experiment with the model.</span></span> <span data-ttu-id="54483-265">将下面的代码添加到 `TestTrips` 类中：</span><span class="sxs-lookup"><span data-stu-id="54483-265">Add the following code into the `TestTrips` class:</span></span>

[!code-csharp[TestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#2 "Create aq trip to predict its cost.")]

<span data-ttu-id="54483-266">行程实际费用为 29.5。</span><span class="sxs-lookup"><span data-stu-id="54483-266">This trip's actual fare is 29.5.</span></span> <span data-ttu-id="54483-267">使用 0 作为占位符，模型将预测费用。</span><span class="sxs-lookup"><span data-stu-id="54483-267">Use 0 as a placeholder, as the model will predict the fare.</span></span>

<span data-ttu-id="54483-268">若要预测指定行程的费用，请返回到 Program.cs 文件并将以下代码添加到 `Main` 方法：</span><span class="sxs-lookup"><span data-stu-id="54483-268">To predict the fare of the specified trip, go back to the *Program.cs* file and add the following code into the `Main` method:</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#16 "Try a prediction.")]

<span data-ttu-id="54483-269">运行此程序，查看测试用例的预测出租车费。</span><span class="sxs-lookup"><span data-stu-id="54483-269">Run the program to see the predicted taxi fare for your test case.</span></span>

<span data-ttu-id="54483-270">祝贺你！</span><span class="sxs-lookup"><span data-stu-id="54483-270">Congratulations!</span></span> <span data-ttu-id="54483-271">你已成功生成用于预测出租车费的机器学习模型、评估其准确性，并用其进行预测。</span><span class="sxs-lookup"><span data-stu-id="54483-271">You've now successfully built a machine learning model for predicting taxi trip fares, evaluated its accuracy, and used it to make predictions.</span></span> <span data-ttu-id="54483-272">可以在 [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction) 存储库中找到本教程的源代码。</span><span class="sxs-lookup"><span data-stu-id="54483-272">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="54483-273">后续步骤</span><span class="sxs-lookup"><span data-stu-id="54483-273">Next steps</span></span>

<span data-ttu-id="54483-274">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="54483-274">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="54483-275">了解问题</span><span class="sxs-lookup"><span data-stu-id="54483-275">Understand the problem</span></span>
> * <span data-ttu-id="54483-276">选择适当的机器学习任务</span><span class="sxs-lookup"><span data-stu-id="54483-276">Select the appropriate machine learning task</span></span>
> * <span data-ttu-id="54483-277">准备和了解数据</span><span class="sxs-lookup"><span data-stu-id="54483-277">Prepare and understand the data</span></span>
> * <span data-ttu-id="54483-278">创建学习管道</span><span class="sxs-lookup"><span data-stu-id="54483-278">Create a learning pipeline</span></span>
> * <span data-ttu-id="54483-279">加载和转换数据</span><span class="sxs-lookup"><span data-stu-id="54483-279">Load and transform the data</span></span>
> * <span data-ttu-id="54483-280">选择学习算法</span><span class="sxs-lookup"><span data-stu-id="54483-280">Choose a learning algorithm</span></span>
> * <span data-ttu-id="54483-281">定型模型</span><span class="sxs-lookup"><span data-stu-id="54483-281">Train the model</span></span>
> * <span data-ttu-id="54483-282">评估模型</span><span class="sxs-lookup"><span data-stu-id="54483-282">Evaluate the model</span></span>
> * <span data-ttu-id="54483-283">使用预测模型</span><span class="sxs-lookup"><span data-stu-id="54483-283">Use the model for predictions</span></span>

<span data-ttu-id="54483-284">查看我们的 GitHub 存储库以继续学习，并找到更多示例。</span><span class="sxs-lookup"><span data-stu-id="54483-284">Check out our GitHub repository to continue learning and find more samples.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="54483-285">dotnet/machinelearning GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="54483-285">dotnet/machinelearning GitHub repository</span></span>](https://github.com/dotnet/machinelearning/)

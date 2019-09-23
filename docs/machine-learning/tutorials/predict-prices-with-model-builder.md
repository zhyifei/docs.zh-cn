---
title: 教程：将回归与模型生成器配合使用以预测价格
description: 本教程演示如何使用 ML.NET 模型生成器生成回归模型以预测价格，特别是纽约市的出租车费。
author: luisquintanilla
ms.author: luquinta
ms.date: 09/18/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: bb344a7f01e8ffe0e40578c6fb2f28bebd2eb807
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117958"
---
# <a name="tutorial-predict-prices-using-regression-with-model-builder"></a><span data-ttu-id="06042-103">教程：将回归与模型生成器配合使用以预测价格</span><span class="sxs-lookup"><span data-stu-id="06042-103">Tutorial: Predict prices using regression with Model Builder</span></span>

<span data-ttu-id="06042-104">了解如何使用 ML.NET 模型生成器来生成用于预测价格的回归模型。</span><span class="sxs-lookup"><span data-stu-id="06042-104">Learn how to use ML.NET Model Builder to build a regression model() to predict prices.</span></span>  <span data-ttu-id="06042-105">在本教程中开发的.NET 控制台应用根据纽约市出租车费的历史数据预测出租车费。</span><span class="sxs-lookup"><span data-stu-id="06042-105">The .NET console app that you develop in this tutorial predicts taxi fares based on historical New York taxi fare data.</span></span>

<span data-ttu-id="06042-106">模型生成器价格预测模板可用于任何需要数值预测值的方案。</span><span class="sxs-lookup"><span data-stu-id="06042-106">The Model Builder price prediction template can be used for any scenario requiring a numerical prediction value.</span></span> <span data-ttu-id="06042-107">示例方案包括：房价预测、需求预测和销售额预测。</span><span class="sxs-lookup"><span data-stu-id="06042-107">Example scenarios include: house price prediction, demand prediction, and sales forecasting.</span></span>

<span data-ttu-id="06042-108">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="06042-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="06042-109">准备和了解数据</span><span class="sxs-lookup"><span data-stu-id="06042-109">Prepare and understand the data</span></span>
> - <span data-ttu-id="06042-110">选择方案</span><span class="sxs-lookup"><span data-stu-id="06042-110">Choose a scenario</span></span>
> - <span data-ttu-id="06042-111">加载数据</span><span class="sxs-lookup"><span data-stu-id="06042-111">Load the data</span></span>
> - <span data-ttu-id="06042-112">定型模型</span><span class="sxs-lookup"><span data-stu-id="06042-112">Train the model</span></span>
> - <span data-ttu-id="06042-113">评估模型</span><span class="sxs-lookup"><span data-stu-id="06042-113">Evaluate the model</span></span>
> - <span data-ttu-id="06042-114">使用预测模型</span><span class="sxs-lookup"><span data-stu-id="06042-114">Use the model for predictions</span></span>

> [!NOTE]
> <span data-ttu-id="06042-115">模型生成器当前为预览版。</span><span class="sxs-lookup"><span data-stu-id="06042-115">Model Builder is currently in Preview.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="06042-116">先决条件</span><span class="sxs-lookup"><span data-stu-id="06042-116">Pre-requisites</span></span>

<span data-ttu-id="06042-117">请访问[模型生成器安装指南](../how-to-guides/install-model-builder.md)，查看先决条件和安装说明的列表。</span><span class="sxs-lookup"><span data-stu-id="06042-117">For a list of pre-requisites and installation instructions, visit the [Model Builder installation guide](../how-to-guides/install-model-builder.md).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="06042-118">创建控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="06042-118">Create a console application</span></span>

1. <span data-ttu-id="06042-119">创建名为“TaxiFarePrediction”的“.NET Core 控制台应用程序”  。</span><span class="sxs-lookup"><span data-stu-id="06042-119">Create a **.NET Core Console Application** called "TaxiFarePrediction".</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="06042-120">准备和了解数据</span><span class="sxs-lookup"><span data-stu-id="06042-120">Prepare and understand the data</span></span>

1. <span data-ttu-id="06042-121">在项目中创建一个名为“数据”的目录来保存数据集文件  。</span><span class="sxs-lookup"><span data-stu-id="06042-121">Create a directory named *Data* in your project to store the data set files.</span></span>

1. <span data-ttu-id="06042-122">用于训练和评估机器学习模型的数据集最初来自 NYC TLC 出租车行程数据集。</span><span class="sxs-lookup"><span data-stu-id="06042-122">The data set used to train and evaluate the machine learning model is originally from the NYC TLC Taxi Trip data set.</span></span>

    <span data-ttu-id="06042-123">要下载数据集，请导航至 [taxi-fare-train.csv 下载链接](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/taxi-fare-train.csv)。</span><span class="sxs-lookup"><span data-stu-id="06042-123">To download the data set, navigate to the [taxi-fare-train.csv download link](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/taxi-fare-train.csv).</span></span>

    <span data-ttu-id="06042-124">页面加载完成后，右键单击页面上的任意位置，然后选择“另存为”  。</span><span class="sxs-lookup"><span data-stu-id="06042-124">When the page loads, right-click anywhere on the page and select **Save as**.</span></span>

    <span data-ttu-id="06042-125">使用“另存为”对话框  将文件保存在你在上一步创建的“数据”  文件夹中。</span><span class="sxs-lookup"><span data-stu-id="06042-125">Use the **Save As Dialog** to save the file in the *Data* folder you created at the previous step.</span></span>

1. <span data-ttu-id="06042-126">在解决方案资源管理器中，右键单击“taxi-fare-train.csv”文件并选择“属性”    。</span><span class="sxs-lookup"><span data-stu-id="06042-126">In **Solution Explorer**, right-click the *taxi-fare-train.csv* file and select **Properties**.</span></span> <span data-ttu-id="06042-127">在“高级”下，将“复制到输出目录”的值更改为“如果较新则复制”    。</span><span class="sxs-lookup"><span data-stu-id="06042-127">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="06042-128">`taxi-fare-train.csv` 数据集中的每一行都包含一辆出租车的详细行程。</span><span class="sxs-lookup"><span data-stu-id="06042-128">Each row in the `taxi-fare-train.csv` data set contains details of trips made by a taxi.</span></span>

1. <span data-ttu-id="06042-129">打开“taxi-fare-train.csv”数据集 </span><span class="sxs-lookup"><span data-stu-id="06042-129">Open the **taxi-fare-train.csv** data set</span></span>

    <span data-ttu-id="06042-130">提供的数据集包含以下列：</span><span class="sxs-lookup"><span data-stu-id="06042-130">The provided data set contains the following columns:</span></span>

    - <span data-ttu-id="06042-131">**vendor_id：** 出租车供应商的 ID 是一项特征。</span><span class="sxs-lookup"><span data-stu-id="06042-131">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
    - <span data-ttu-id="06042-132">**rate_code：** 出租车行程的费率类型是一项特征。</span><span class="sxs-lookup"><span data-stu-id="06042-132">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
    - <span data-ttu-id="06042-133">**passenger_count：** 行程中的乘客人数是一项特征。</span><span class="sxs-lookup"><span data-stu-id="06042-133">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
    - <span data-ttu-id="06042-134">**trip_time_in_secs：** 这次行程所花的时间。</span><span class="sxs-lookup"><span data-stu-id="06042-134">**trip_time_in_secs:** The amount of time the trip took.</span></span>
    - <span data-ttu-id="06042-135">**trip_distance：** 行程距离是一项特征。</span><span class="sxs-lookup"><span data-stu-id="06042-135">**trip_distance:** The distance of the trip is a feature.</span></span>
    - <span data-ttu-id="06042-136">**payment_type：** 付款方式（现金或信用卡）是一项特征。</span><span class="sxs-lookup"><span data-stu-id="06042-136">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
    - <span data-ttu-id="06042-137">**fare_amount：** 支付的总出租车费用是一个标签。</span><span class="sxs-lookup"><span data-stu-id="06042-137">**fare_amount:** The total taxi fare paid is the label.</span></span>

<span data-ttu-id="06042-138">`label` 是要预测的列。</span><span class="sxs-lookup"><span data-stu-id="06042-138">The `label` is the column you want to predict.</span></span> <span data-ttu-id="06042-139">在执行回归任务时，目标是预测一个数字值。</span><span class="sxs-lookup"><span data-stu-id="06042-139">When performing a regression task, the goal is to predict a numerical value.</span></span> <span data-ttu-id="06042-140">在此价格预测方案中，要预测的是出租车的乘车费用。</span><span class="sxs-lookup"><span data-stu-id="06042-140">In this price prediction scenario, the cost of a taxi ride is being predicted.</span></span> <span data-ttu-id="06042-141">所以“fare_amount”是标签  。</span><span class="sxs-lookup"><span data-stu-id="06042-141">Therefore, the **fare_amount** is the label.</span></span> <span data-ttu-id="06042-142">标识的 `features` 是为模型提供的用来预测 `label` 的输入。</span><span class="sxs-lookup"><span data-stu-id="06042-142">The identified `features` are the inputs you give the model to predict the `label`.</span></span> <span data-ttu-id="06042-143">在这种情况下，剩余的列都用作特征或输入来预测车费金额。</span><span class="sxs-lookup"><span data-stu-id="06042-143">In this case, the rest of the columns are used as features or inputs to predict the fare amount.</span></span>

## <a name="choose-a-scenario"></a><span data-ttu-id="06042-144">选择方案</span><span class="sxs-lookup"><span data-stu-id="06042-144">Choose a scenario</span></span>

<span data-ttu-id="06042-145">为了训练模型，需要从模型生成器提供的可用机器学习方案列表中进行选择。</span><span class="sxs-lookup"><span data-stu-id="06042-145">To train your model, you need to select from the list of available machine learning scenarios provided by Model Builder.</span></span> <span data-ttu-id="06042-146">在本例中，选择的方案是 `Price Prediction`。</span><span class="sxs-lookup"><span data-stu-id="06042-146">In this case, the scenario is `Price Prediction`.</span></span>

1. <span data-ttu-id="06042-147">在“解决方案资源管理器”中，右键单击“TaxiFarePrediction”项目，然后选择“添加” > “机器学习”     。</span><span class="sxs-lookup"><span data-stu-id="06042-147">In **Solution Explorer**, right-click the *TaxiFarePrediction* project, and select **Add** > **Machine Learning**.</span></span>
1. <span data-ttu-id="06042-148">在模型生成器工具的方案步骤中，选择“价格预测”方案  。</span><span class="sxs-lookup"><span data-stu-id="06042-148">In the scenario step of the Model Builder tool, select *Price Prediction* scenario.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="06042-149">加载数据</span><span class="sxs-lookup"><span data-stu-id="06042-149">Load the data</span></span>

<span data-ttu-id="06042-150">模型生成器接受来自两个源的数据：SQL Server 数据库或者 csv 或 tsv 格式的本地文件。</span><span class="sxs-lookup"><span data-stu-id="06042-150">Model Builder accepts data from two sources, a SQL Server database or a local file in csv or tsv format.</span></span>

1. <span data-ttu-id="06042-151">在模型生成器工具的数据步骤中，选择数据源下拉列表中的“文件”  。</span><span class="sxs-lookup"><span data-stu-id="06042-151">In the data step of the Model Builder tool, select *File* from the data source dropdown.</span></span>
1. <span data-ttu-id="06042-152">选择“选择文件”文本框旁边的按钮，并使用文件资源管理器浏览到“数据”目录中的“taxi-fare-test.csv”，然后选择该文件   </span><span class="sxs-lookup"><span data-stu-id="06042-152">Select the button next to the *Select a file* text box and use File Explorer to browse and select the *taxi-fare-test.csv* in the *Data* directory</span></span>
1. <span data-ttu-id="06042-153">在“要预测的标签或列”下拉列表中选择“fare_amount”，并浏览到模型生成器工具的训练步骤   。</span><span class="sxs-lookup"><span data-stu-id="06042-153">Choose *fare_amount* in the *Label or Column to Predict* dropdown and navigate to the train step of the Model Builder tool.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="06042-154">定型模型</span><span class="sxs-lookup"><span data-stu-id="06042-154">Train the model</span></span>

<span data-ttu-id="06042-155">在本教程中，用于训练价格预测模型的机器学习任务是回归。</span><span class="sxs-lookup"><span data-stu-id="06042-155">The machine learning task used to train the price prediction model in this tutorial is regression.</span></span> <span data-ttu-id="06042-156">在模型训练过程中，模型生成器使用不同的回归算法和设置训练各个模型，以便为数据集找到性能最佳的模型。</span><span class="sxs-lookup"><span data-stu-id="06042-156">During the model training process, Model Builder trains separate models using different regression algorithms and settings to find the best performing model for your dataset.</span></span>

<span data-ttu-id="06042-157">模型训练所需的时间与数据量成正比。</span><span class="sxs-lookup"><span data-stu-id="06042-157">The time required for the model to train is proportionate to the amount of data.</span></span> <span data-ttu-id="06042-158">模型生成器会根据数据源的大小自动选择“训练时间(秒)”的默认值  。</span><span class="sxs-lookup"><span data-stu-id="06042-158">Model Builder automatically selects a default value for **Time to train (seconds)** based on the size of your data source.</span></span>

1. <span data-ttu-id="06042-159">如果不希望延长训练时间，则保持“训练时间(秒)”的默认值不变  。</span><span class="sxs-lookup"><span data-stu-id="06042-159">Leave the default value as is for *Time to train (seconds)* unless you prefer to train for a longer time.</span></span>
2. <span data-ttu-id="06042-160">选择“开始训练”  。</span><span class="sxs-lookup"><span data-stu-id="06042-160">Select *Start Training*.</span></span>

<span data-ttu-id="06042-161">在训练过程中，进度数据显示在训练步骤中的 `Progress` 部分。</span><span class="sxs-lookup"><span data-stu-id="06042-161">Throughout the training process, progress data is displayed in the `Progress` section of the train step.</span></span>

- <span data-ttu-id="06042-162">“状态”显示训练进程的完成状态。</span><span class="sxs-lookup"><span data-stu-id="06042-162">Status displays the completion status of the training process.</span></span>
- <span data-ttu-id="06042-163">“最高准确性”显示截至目前由模型生成器找到的性能最佳的模型的准确性。</span><span class="sxs-lookup"><span data-stu-id="06042-163">Best accuracy displays the accuracy of the best performing model found by Model Builder so far.</span></span> <span data-ttu-id="06042-164">准确性越高，意味着模型对测试数据的预测越准确。</span><span class="sxs-lookup"><span data-stu-id="06042-164">Higher accuracy means the model predicted more correctly on test data.</span></span>
- <span data-ttu-id="06042-165">“最佳算法”显示截至目前由模型生成器找到的性能最佳的算法的名称。</span><span class="sxs-lookup"><span data-stu-id="06042-165">Best algorithm displays the name of the best performing algorithm performed found by Model Builder so far.</span></span>
- <span data-ttu-id="06042-166">“最新算法”显示模型生成器为了训练模型采用的最新算法名称。</span><span class="sxs-lookup"><span data-stu-id="06042-166">Last algorithm displays the name of the algorithm most recently used by Model Builder to train the model.</span></span>

<span data-ttu-id="06042-167">训练完成后，导航到评估步骤。</span><span class="sxs-lookup"><span data-stu-id="06042-167">Once training is complete, navigate to the evaluate step.</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="06042-168">评估模型</span><span class="sxs-lookup"><span data-stu-id="06042-168">Evaluate the model</span></span>

<span data-ttu-id="06042-169">训练步骤的成果将是一个模型，该模型具备最佳的性能。</span><span class="sxs-lookup"><span data-stu-id="06042-169">The result of the training step will be one model which had the best performance.</span></span> <span data-ttu-id="06042-170">在模型生成器工具的评估步骤中，输出部分将包含“最佳模型”项中性能最佳的模型使用的算法，并包含“最佳模型质量 (RSquared)”中的指标   。</span><span class="sxs-lookup"><span data-stu-id="06042-170">In the evaluate step of the Model Builder tool, the output section, will contain the algorithm used by the best performing model in the *Best Model* entry along with metrics in *Best Model Quality (RSquared)*.</span></span> <span data-ttu-id="06042-171">此外还有一个摘要表格，包含性能最佳的前五种模型以及它们的指标信息。</span><span class="sxs-lookup"><span data-stu-id="06042-171">Additionally, a summary table containing top five models and their metrics.</span></span>

<span data-ttu-id="06042-172">如果对自己的准确性指标不满意，尝试提高模型准确性的简单方法是增加模型的训练时间或使用更多数据。</span><span class="sxs-lookup"><span data-stu-id="06042-172">If you're not satisfied with your accuracy metrics, some easy ways to try and improve model accuracy are to increase the amount of time to train the model or use more data.</span></span> <span data-ttu-id="06042-173">否则，导航到代码步骤。</span><span class="sxs-lookup"><span data-stu-id="06042-173">Otherwise, navigate to the code step.</span></span>

## <a name="add-the-code-to-make-predictions"></a><span data-ttu-id="06042-174">添加代码进行预测</span><span class="sxs-lookup"><span data-stu-id="06042-174">Add the code to make predictions</span></span>

<span data-ttu-id="06042-175">训练期间会创建两个项目。</span><span class="sxs-lookup"><span data-stu-id="06042-175">Two projects will be created as a result of the training process.</span></span>

- <span data-ttu-id="06042-176">TaxiFarePredictionML.ConsoleApp：包含模型训练和要使用的代码的 .NET Core 控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="06042-176">TaxiFarePredictionML.ConsoleApp: A .NET Core Console application that contains the model training and consumption code.</span></span>
- <span data-ttu-id="06042-177">TaxiFarePredictionML.Model：一个 .NET Standard 类库，包含定义输入和输出模型数据架构的数据模型，以及在训练期间性能最佳的模型的持久版本。</span><span class="sxs-lookup"><span data-stu-id="06042-177">TaxiFarePredictionML.Model: A .NET Standard class library containing the data models that define the schema of input and output model data as well as the persisted version of the best performing model during training.</span></span>

1. <span data-ttu-id="06042-178">在模型生成器工具的代码步骤中，选择“添加项目”，将自动生成的项目添加到解决方案  。</span><span class="sxs-lookup"><span data-stu-id="06042-178">In the code step of the Model Builder tool, select **Add Projects** to add the auto-generated projects to the solution.</span></span>
1. <span data-ttu-id="06042-179">右键单击“TaxiFarePrediction”项目  。</span><span class="sxs-lookup"><span data-stu-id="06042-179">Right-click *TaxiFarePrediction* project.</span></span> <span data-ttu-id="06042-180">然后选择“添加”>“引用”  。</span><span class="sxs-lookup"><span data-stu-id="06042-180">Then, **Add > Reference**.</span></span> <span data-ttu-id="06042-181">选择“项目”>“解决方案”节点，在列表中勾选“TaxiFarePredictionML.Model”项目并选择“确定”   。</span><span class="sxs-lookup"><span data-stu-id="06042-181">Choose the **Projects > Solution** node and from the list, check the *TaxiFarePredictionML.Model* project and select OK.</span></span>
1. <span data-ttu-id="06042-182">打开 TaxiFarePrediction 项目中的 Program.cs 文件   。</span><span class="sxs-lookup"><span data-stu-id="06042-182">Open the *Program.cs* file in the *TaxiFarePrediction* project.</span></span>
1. <span data-ttu-id="06042-183">添加以下 using 语句以引用 Microsoft.ML  NuGet 包和 TaxiFarePredictionML.Model 项目  ：</span><span class="sxs-lookup"><span data-stu-id="06042-183">Add the following using statements to reference the *Microsoft.ML* NuGet package and *TaxiFarePredictionML.Model* project:</span></span>

    ```csharp
    using System;
    using Microsoft.ML;
    using TaxiFarePredictionML.Model.DataModels;
    ```

1. <span data-ttu-id="06042-184">将 `ConsumeModel` 方法添加到 `Program` 类。</span><span class="sxs-lookup"><span data-stu-id="06042-184">Add the `ConsumeModel` method to the `Program` class.</span></span>

    ```csharp
    static ModelOutput ConsumeModel(ModelInput input)
    {
        // 1. Load the model
        MLContext mlContext = new MLContext();
        ITransformer mlModel = mlContext.Model.Load("MLModel.zip", out var modelInputSchema);

        // 2. Create PredictionEngine
        var predictionEngine = mlContext.Model.CreatePredictionEngine<ModelInput, ModelOutput>(mlModel);

        // 3. Use PredictionEngine to use model on input data
        ModelOutput result = predictionEngine.Predict(input);

        // 4. Return prediction result
        return result;
    }
    ```

    <span data-ttu-id="06042-185">`ConsumeModel` 将加载训练的模型，为模型创建 [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) 并使用它对新数据进行预测。</span><span class="sxs-lookup"><span data-stu-id="06042-185">The `ConsumeModel` will load the trained model, create a [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) for the model and use it to make predictions on new data.</span></span>

1. <span data-ttu-id="06042-186">要使用模型对新数据进行预测，请创建 `ModelInput` 类的新实例并使用 `ConsumeModel` 方法。</span><span class="sxs-lookup"><span data-stu-id="06042-186">To make a prediction on new data using the model, create a new instance of the `ModelInput` class and use the `ConsumeModel` method.</span></span> <span data-ttu-id="06042-187">请注意，费用金额不是输入的一部分。</span><span class="sxs-lookup"><span data-stu-id="06042-187">Notice that the fare amount is not part of the input.</span></span> <span data-ttu-id="06042-188">这是因为模型将为它生成预测。</span><span class="sxs-lookup"><span data-stu-id="06042-188">This is because the model will generate the prediction for it.</span></span> <span data-ttu-id="06042-189">将以下代码添加到 `Main` 方法，并运行应用程序</span><span class="sxs-lookup"><span data-stu-id="06042-189">Add the following code to the `Main` method and run the application</span></span>

    ```csharp
    // Create sample data
    ModelInput input = new ModelInput()
    {
        Vendor_id = "CMT",
        Rate_code = 1,
        Passenger_count = 1,
        Trip_time_in_secs = 1271,
        Trip_distance = 3.8f,
        Payment_type = "CRD"
    };

    // Make prediction
    ModelOutput prediction = ConsumeModel(input);

    // Print Prediction
    Console.WriteLine($"Predicted Fare: {prediction.Score}");
    Console.ReadKey();
    ```

    <span data-ttu-id="06042-190">该程序生成的输出应类似于下面的代码段：</span><span class="sxs-lookup"><span data-stu-id="06042-190">The output generated by the program should look similar to the snippet below:</span></span>

    ```bash
    Predicted Fare: 16.82245
    ```

<span data-ttu-id="06042-191">如果稍后需要在另一个解决方案中引用生成的项目，可以在 `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` 目录中找到它们。</span><span class="sxs-lookup"><span data-stu-id="06042-191">If you need to reference the generated projects at a later time inside of another solution, you can find them inside the `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` directory.</span></span>

## <a name="next-steps"></a><span data-ttu-id="06042-192">后续步骤</span><span class="sxs-lookup"><span data-stu-id="06042-192">Next Steps</span></span>

<span data-ttu-id="06042-193">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="06042-193">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="06042-194">准备和了解数据</span><span class="sxs-lookup"><span data-stu-id="06042-194">Prepare and understand the data</span></span>
> - <span data-ttu-id="06042-195">选择方案</span><span class="sxs-lookup"><span data-stu-id="06042-195">Choose a scenario</span></span>
> - <span data-ttu-id="06042-196">加载数据</span><span class="sxs-lookup"><span data-stu-id="06042-196">Load the data</span></span>
> - <span data-ttu-id="06042-197">定型模型</span><span class="sxs-lookup"><span data-stu-id="06042-197">Train the model</span></span>
> - <span data-ttu-id="06042-198">评估模型</span><span class="sxs-lookup"><span data-stu-id="06042-198">Evaluate the model</span></span>
> - <span data-ttu-id="06042-199">使用预测模型</span><span class="sxs-lookup"><span data-stu-id="06042-199">Use the model for predictions</span></span>

### <a name="additional-resources"></a><span data-ttu-id="06042-200">其他资源</span><span class="sxs-lookup"><span data-stu-id="06042-200">Additional Resources</span></span>

<span data-ttu-id="06042-201">若要详细了解本教程中所述的主题，请访问以下资源:</span><span class="sxs-lookup"><span data-stu-id="06042-201">To learn more about topics mentioned in this tutorial, visit the following resources:</span></span>

- [<span data-ttu-id="06042-202">模型生成器应用场景</span><span class="sxs-lookup"><span data-stu-id="06042-202">Model Builder Scenarios</span></span>](../automate-training-with-model-builder.md#scenarios)
- [<span data-ttu-id="06042-203">回归</span><span class="sxs-lookup"><span data-stu-id="06042-203">Regression</span></span>](../resources/glossary.md#regression)
- [<span data-ttu-id="06042-204">回归模型指标</span><span class="sxs-lookup"><span data-stu-id="06042-204">Regression Model Metrics</span></span>](../resources/metrics.md#metrics-for-regression)
- [<span data-ttu-id="06042-205">NYC TLC 出租车行程数据集</span><span class="sxs-lookup"><span data-stu-id="06042-205">NYC TLC Taxi Trip data set</span></span>](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml)

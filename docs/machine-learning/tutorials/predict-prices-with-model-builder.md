---
title: 将回归与模型生成器配合使用以预测价格
description: 本教程演示如何使用 ML.NET 模型生成器生成回归模型以预测价格，特别是纽约市的出租车费。
author: luisquintanilla
ms.author: luquinta
ms.date: 06/26/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: d9a6f193d877fc1a679b7a3cafd7491e021cb2ad
ms.sourcegitcommit: b5c59eaaf8bf48ef3ec259f228cb328d6d4c0ceb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2019
ms.locfileid: "67539624"
---
# <a name="predict-prices-using-regression-with-model-builder"></a><span data-ttu-id="5e673-103">将回归与模型生成器配合使用以预测价格</span><span class="sxs-lookup"><span data-stu-id="5e673-103">Predict prices using regression with Model Builder</span></span>

<span data-ttu-id="5e673-104">了解如何使用 ML.NET 模型生成器来生成用于预测价格的[回归模型](../resources/glossary.md#regression)。</span><span class="sxs-lookup"><span data-stu-id="5e673-104">Learn how to use ML.NET Model Builder to build a [regression model](../resources/glossary.md#regression) to predict prices.</span></span>  <span data-ttu-id="5e673-105">在本教程中开发的.NET 控制台应用根据纽约市出租车费的历史数据预测出租车费。</span><span class="sxs-lookup"><span data-stu-id="5e673-105">The .NET console app that you develop in this tutorial predicts taxi fares based on historical New York taxi fare data.</span></span>

<span data-ttu-id="5e673-106">模型生成器价格预测模板可用于任何需要数值预测值的方案。</span><span class="sxs-lookup"><span data-stu-id="5e673-106">The Model Builder price prediction template can be used for any scenario requiring a numerical prediction value.</span></span> <span data-ttu-id="5e673-107">示例方案包括：房价预测、需求预测和销售额预测。</span><span class="sxs-lookup"><span data-stu-id="5e673-107">Example scenarios include: house price prediction, demand prediction, and sales forecasting.</span></span>

<span data-ttu-id="5e673-108">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="5e673-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="5e673-109">准备和了解数据</span><span class="sxs-lookup"><span data-stu-id="5e673-109">Prepare and understand the data</span></span>
> * <span data-ttu-id="5e673-110">选择方案</span><span class="sxs-lookup"><span data-stu-id="5e673-110">Choose a scenario</span></span>
> * <span data-ttu-id="5e673-111">加载数据</span><span class="sxs-lookup"><span data-stu-id="5e673-111">Load the data</span></span>
> * <span data-ttu-id="5e673-112">定型模型</span><span class="sxs-lookup"><span data-stu-id="5e673-112">Train the model</span></span>
> * <span data-ttu-id="5e673-113">评估模型</span><span class="sxs-lookup"><span data-stu-id="5e673-113">Evaluate the model</span></span>
> * <span data-ttu-id="5e673-114">使用预测模型</span><span class="sxs-lookup"><span data-stu-id="5e673-114">Use the model for predictions</span></span>

> [!NOTE]
> <span data-ttu-id="5e673-115">模型生成器当前为预览版。</span><span class="sxs-lookup"><span data-stu-id="5e673-115">Model Builder is currently in Preview.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="5e673-116">先决条件</span><span class="sxs-lookup"><span data-stu-id="5e673-116">Pre-requisites</span></span>

<span data-ttu-id="5e673-117">请访问[模型生成器安装指南](../how-to-guides/install-model-builder.md)，查看先决条件和安装说明的列表。</span><span class="sxs-lookup"><span data-stu-id="5e673-117">For a list of pre-requisites and installation instructions, visit the [Model Builder installation guide](../how-to-guides/install-model-builder.md).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="5e673-118">创建控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="5e673-118">Create a console application</span></span>

1. <span data-ttu-id="5e673-119">创建名为“TaxiFarePrediction”的“.NET Core 控制台应用程序”  。</span><span class="sxs-lookup"><span data-stu-id="5e673-119">Create a **.NET Core Console Application** called "TaxiFarePrediction".</span></span>

1. <span data-ttu-id="5e673-120">安装“Microsoft.ML”NuGet 包  ：</span><span class="sxs-lookup"><span data-stu-id="5e673-120">Install the **Microsoft.ML** NuGet Package:</span></span>

    <span data-ttu-id="5e673-121">在“解决方案资源管理器”中，右键单击“TaxiFarePrediction”项目，然后选择“管理 NuGet 包”    。</span><span class="sxs-lookup"><span data-stu-id="5e673-121">In **Solution Explorer**, right-click the *TaxiFarePrediction* project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="5e673-122">选择“nuget.org”作为包源，然后选择“浏览”选项卡并搜索“Microsoft.ML”，在列表中选择包，再选择“安装”按钮    。</span><span class="sxs-lookup"><span data-stu-id="5e673-122">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select the package in the list, and select the **Install** button.</span></span> <span data-ttu-id="5e673-123">选择“预览更改”  对话框上的“确定”  按钮，如果你同意所列包的许可条款，则选择“接受许可”  对话框上的“我接受”  按钮。</span><span class="sxs-lookup"><span data-stu-id="5e673-123">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

## <a name="prepare-and-understand-the-data"></a><span data-ttu-id="5e673-124">准备和了解数据</span><span class="sxs-lookup"><span data-stu-id="5e673-124">Prepare and understand the data</span></span>

1. <span data-ttu-id="5e673-125">在项目中创建一个名为“数据”的目录来保存数据集文件  。</span><span class="sxs-lookup"><span data-stu-id="5e673-125">Create a directory named *Data* in your project to store the data set files.</span></span>

1. <span data-ttu-id="5e673-126">下载 [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) 数据集并将其保存至在上一步中创建的“数据”文件夹  。</span><span class="sxs-lookup"><span data-stu-id="5e673-126">Download the [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) data set and save it to the *Data* folder you created at the previous step.</span></span> <span data-ttu-id="5e673-127">此数据集用于训练和评估机器学习模型。</span><span class="sxs-lookup"><span data-stu-id="5e673-127">This data set is used to train and evaluate the machine learning model.</span></span> <span data-ttu-id="5e673-128">该数据集最初来自 [NYC TLC 出租车行程数据集](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml)。</span><span class="sxs-lookup"><span data-stu-id="5e673-128">This data set is originally from the [NYC TLC Taxi Trip data set](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml).</span></span>

1. <span data-ttu-id="5e673-129">在解决方案资源管理器中，右键单击“taxi-fare-train.csv”文件并选择“属性”    。</span><span class="sxs-lookup"><span data-stu-id="5e673-129">In **Solution Explorer**, right-click the *taxi-fare-train.csv* file and select **Properties**.</span></span> <span data-ttu-id="5e673-130">在“高级”下，将“复制到输出目录”的值更改为“如果较新则复制”    。</span><span class="sxs-lookup"><span data-stu-id="5e673-130">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="5e673-131">`taxi-fare-train.csv` 数据集中的每一行都包含一辆出租车的详细行程。</span><span class="sxs-lookup"><span data-stu-id="5e673-131">Each row in the `taxi-fare-train.csv` data set contains details of trips made by a taxi.</span></span>

1. <span data-ttu-id="5e673-132">打开“taxi-fare-train.csv”数据集 </span><span class="sxs-lookup"><span data-stu-id="5e673-132">Open the **taxi-fare-train.csv** data set</span></span>

    <span data-ttu-id="5e673-133">提供的数据集包含以下列：</span><span class="sxs-lookup"><span data-stu-id="5e673-133">The provided data set contains the following columns:</span></span>

    * <span data-ttu-id="5e673-134">**vendor_id：** 出租车供应商的 ID 是一项特征。</span><span class="sxs-lookup"><span data-stu-id="5e673-134">**vendor_id:** The ID of the taxi vendor is a feature.</span></span>
    * <span data-ttu-id="5e673-135">**rate_code：** 出租车行程的费率类型是一项特征。</span><span class="sxs-lookup"><span data-stu-id="5e673-135">**rate_code:** The rate type of the taxi trip is a feature.</span></span>
    * <span data-ttu-id="5e673-136">**passenger_count：** 行程中的乘客人数是一项特征。</span><span class="sxs-lookup"><span data-stu-id="5e673-136">**passenger_count:** The number of passengers on the trip is a feature.</span></span>
    * <span data-ttu-id="5e673-137">**trip_time_in_secs：** 这次行程所花的时间。</span><span class="sxs-lookup"><span data-stu-id="5e673-137">**trip_time_in_secs:** The amount of time the trip took.</span></span> <span data-ttu-id="5e673-138">希望在行程完成前预测行程费用。</span><span class="sxs-lookup"><span data-stu-id="5e673-138">You want to predict the fare of the trip before the trip is completed.</span></span> <span data-ttu-id="5e673-139">当时并不知道行程有多长。</span><span class="sxs-lookup"><span data-stu-id="5e673-139">At that moment you don't know how long the trip would take.</span></span> <span data-ttu-id="5e673-140">因此，行程时间不是一项特征，需要从模型删除此列。</span><span class="sxs-lookup"><span data-stu-id="5e673-140">Thus, the trip time is not a feature and you'll exclude this column from the model.</span></span>
    * <span data-ttu-id="5e673-141">**trip_distance：** 行程距离是一项特征。</span><span class="sxs-lookup"><span data-stu-id="5e673-141">**trip_distance:** The distance of the trip is a feature.</span></span>
    * <span data-ttu-id="5e673-142">**payment_type：** 付款方式（现金或信用卡）是一项特征。</span><span class="sxs-lookup"><span data-stu-id="5e673-142">**payment_type:** The payment method (cash or credit card) is a feature.</span></span>
    * <span data-ttu-id="5e673-143">**fare_amount：** 支付的总出租车费用是一个标签。</span><span class="sxs-lookup"><span data-stu-id="5e673-143">**fare_amount:** The total taxi fare paid is the label.</span></span>

<span data-ttu-id="5e673-144">`label` 是要预测的列。</span><span class="sxs-lookup"><span data-stu-id="5e673-144">The `label` is the column you want to predict.</span></span> <span data-ttu-id="5e673-145">在执行回归任务时，目标是预测一个数字值。</span><span class="sxs-lookup"><span data-stu-id="5e673-145">When performing a regression task, the goal is to predict a numerical value.</span></span> <span data-ttu-id="5e673-146">在此价格预测方案中，要预测的是出租车的乘车费用。</span><span class="sxs-lookup"><span data-stu-id="5e673-146">In this price prediction scenario, the cost of a taxi ride is being predicted.</span></span> <span data-ttu-id="5e673-147">所以“fare_amount”是标签  。</span><span class="sxs-lookup"><span data-stu-id="5e673-147">Therefore, the **fare_amount** is the label.</span></span> <span data-ttu-id="5e673-148">标识的 `features` 是为模型提供的用来预测 `label` 的输入。</span><span class="sxs-lookup"><span data-stu-id="5e673-148">The identified `features` are the inputs you give the model to predict the `label`.</span></span> <span data-ttu-id="5e673-149">在这种情况下，剩余的列都用作特征或输入来预测车费金额。</span><span class="sxs-lookup"><span data-stu-id="5e673-149">In this case, the rest of the columns are used as features or inputs to predict the fare amount.</span></span>

## <a name="choose-a-scenario"></a><span data-ttu-id="5e673-150">选择方案</span><span class="sxs-lookup"><span data-stu-id="5e673-150">Choose a scenario</span></span>

<span data-ttu-id="5e673-151">为了训练模型，需要从模型生成器提供的可用机器学习方案列表中进行选择。</span><span class="sxs-lookup"><span data-stu-id="5e673-151">To train your model, you need to select from the list of available machine learning scenarios provided by Model Builder.</span></span> <span data-ttu-id="5e673-152">在本例中，选择的方案是 `Price Prediction`。</span><span class="sxs-lookup"><span data-stu-id="5e673-152">In this case, the scenario is `Price Prediction`.</span></span> <span data-ttu-id="5e673-153">请访问[模型生成器概述文章](../automate-training-with-model-builder.md#scenarios)，查看更多列表内容。</span><span class="sxs-lookup"><span data-stu-id="5e673-153">For a more extensive list visit the [Model Builder overview article](../automate-training-with-model-builder.md#scenarios).</span></span>

1. <span data-ttu-id="5e673-154">在“解决方案资源管理器”中，右键单击“TaxiFarePrediction”项目，然后选择“添加” > “机器学习”     。</span><span class="sxs-lookup"><span data-stu-id="5e673-154">In **Solution Explorer**, right-click the *TaxiFarePrediction* project, and select **Add** > **Machine Learning**.</span></span>
1. <span data-ttu-id="5e673-155">在模型生成器工具的方案步骤中，选择“价格预测”方案  。</span><span class="sxs-lookup"><span data-stu-id="5e673-155">In the scenario step of the Model Builder tool, select *Price Prediction* scenario.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="5e673-156">加载数据</span><span class="sxs-lookup"><span data-stu-id="5e673-156">Load the data</span></span>

<span data-ttu-id="5e673-157">模型生成器有两个数据源：SQL Server 数据库或者 csv 或 tsv 格式的本地文件。</span><span class="sxs-lookup"><span data-stu-id="5e673-157">Model Builder accepts data from two sources, a SQL Server database or a local file csv or tsv file.</span></span> <span data-ttu-id="5e673-158">若要详细了解数据格式要求，请访问以下[链接](../how-to-guides/install-model-builder.md#limitations)。</span><span class="sxs-lookup"><span data-stu-id="5e673-158">For more information on data format requirements, visit the following [link](../how-to-guides/install-model-builder.md#limitations).</span></span>

1. <span data-ttu-id="5e673-159">在模型生成器工具的数据步骤中，选择数据源下拉列表中的“文件”  。</span><span class="sxs-lookup"><span data-stu-id="5e673-159">In the data step of the Model Builder tool, select *File* from the data source dropdown.</span></span>
1. <span data-ttu-id="5e673-160">选择“选择文件”文本框旁边的按钮，并使用文件资源管理器浏览到“数据”目录中的“taxi-fare-test.csv”，然后选择该文件   </span><span class="sxs-lookup"><span data-stu-id="5e673-160">Select the button next to the *Select a file* text box and use File Explorer to browse and select the *taxi-fare-test.csv* in the *Data* directory</span></span>
1. <span data-ttu-id="5e673-161">在“要预测的标签或列”下拉列表中选择“fare_amount”，并浏览到模型生成器工具的训练步骤   。</span><span class="sxs-lookup"><span data-stu-id="5e673-161">Choose *fare_amount* in the *Label or Column to Predict* dropdown and navigate to the train step of the Model Builder tool.</span></span>

## <a name="train-the-model"></a><span data-ttu-id="5e673-162">定型模型</span><span class="sxs-lookup"><span data-stu-id="5e673-162">Train the model</span></span>

<span data-ttu-id="5e673-163">在本教程中，用于训练价格预测模型的机器学习任务是回归。</span><span class="sxs-lookup"><span data-stu-id="5e673-163">The machine learning task used to train the price prediction model in this tutorial is regression.</span></span> <span data-ttu-id="5e673-164">在模型训练过程中，模型生成器使用不同的回归算法和设置训练各个模型，以便为数据集找到性能最佳的模型。</span><span class="sxs-lookup"><span data-stu-id="5e673-164">During the model training process, Model Builder trains separate models using different regression algorithms and settings to find the best performing model for your dataset.</span></span>

<span data-ttu-id="5e673-165">模型训练所需的时间与数据量成正比。</span><span class="sxs-lookup"><span data-stu-id="5e673-165">The time required for the model to train is proportionate to the amount of data.</span></span> <span data-ttu-id="5e673-166">请参考此图表，为 `Time to train (seconds)` 字段选择适当的值：</span><span class="sxs-lookup"><span data-stu-id="5e673-166">Use this chart as guidance to select an adequate value for the `Time to train (seconds)` field:</span></span>

<span data-ttu-id="5e673-167">\*数据集大小</span><span class="sxs-lookup"><span data-stu-id="5e673-167">\*Dataset Size</span></span>  | <span data-ttu-id="5e673-168">数据集类型</span><span class="sxs-lookup"><span data-stu-id="5e673-168">Dataset Type</span></span>       | <span data-ttu-id="5e673-169">平均训练时间\*</span><span class="sxs-lookup"><span data-stu-id="5e673-169">Avg. Time to train\*</span></span>
------------- | ------------------ | --------------
<span data-ttu-id="5e673-170">0 - 10 Mb</span><span class="sxs-lookup"><span data-stu-id="5e673-170">0 - 10 Mb</span></span>     | <span data-ttu-id="5e673-171">数值和文本</span><span class="sxs-lookup"><span data-stu-id="5e673-171">Numeric and Text</span></span>   | <span data-ttu-id="5e673-172">10 秒</span><span class="sxs-lookup"><span data-stu-id="5e673-172">10 sec</span></span>
<span data-ttu-id="5e673-173">10 - 100 Mb</span><span class="sxs-lookup"><span data-stu-id="5e673-173">10 - 100 Mb</span></span>   | <span data-ttu-id="5e673-174">数值和文本</span><span class="sxs-lookup"><span data-stu-id="5e673-174">Numeric and Text</span></span>   | <span data-ttu-id="5e673-175">10 分钟</span><span class="sxs-lookup"><span data-stu-id="5e673-175">10 min</span></span>
<span data-ttu-id="5e673-176">100 - 500 Mb</span><span class="sxs-lookup"><span data-stu-id="5e673-176">100 - 500 Mb</span></span>  | <span data-ttu-id="5e673-177">数值和文本</span><span class="sxs-lookup"><span data-stu-id="5e673-177">Numeric and Text</span></span>   | <span data-ttu-id="5e673-178">30 分钟</span><span class="sxs-lookup"><span data-stu-id="5e673-178">30 min</span></span>
<span data-ttu-id="5e673-179">500 - 1 Gb</span><span class="sxs-lookup"><span data-stu-id="5e673-179">500 - 1 Gb</span></span>    | <span data-ttu-id="5e673-180">数值和文本</span><span class="sxs-lookup"><span data-stu-id="5e673-180">Numeric and Text</span></span>   | <span data-ttu-id="5e673-181">60 分钟</span><span class="sxs-lookup"><span data-stu-id="5e673-181">60 min</span></span>
<span data-ttu-id="5e673-182">1 Gb 以上</span><span class="sxs-lookup"><span data-stu-id="5e673-182">1 Gb+</span></span>         | <span data-ttu-id="5e673-183">数值和文本</span><span class="sxs-lookup"><span data-stu-id="5e673-183">Numeric and Text</span></span>   | <span data-ttu-id="5e673-184">3 小时以上</span><span class="sxs-lookup"><span data-stu-id="5e673-184">3 hour+</span></span>

1. <span data-ttu-id="5e673-185">由于训练用的数据文件超过 10 MB，所以请使用 600 秒（10 分钟）作为“训练时间(秒)”的值  。</span><span class="sxs-lookup"><span data-stu-id="5e673-185">Because the training data file is more than 10MB, use 600 seconds (10 minutes) as the value for *Time to train (seconds)*.</span></span>
2. <span data-ttu-id="5e673-186">选择“开始训练”  。</span><span class="sxs-lookup"><span data-stu-id="5e673-186">Select *Start Training*.</span></span>

<span data-ttu-id="5e673-187">在训练过程中，进度数据显示在训练步骤中的 `Progress` 部分。</span><span class="sxs-lookup"><span data-stu-id="5e673-187">Throughout the training process, progress data is displayed in the `Progress` section of the train step.</span></span>

- <span data-ttu-id="5e673-188">“状态”显示训练进程的完成状态。</span><span class="sxs-lookup"><span data-stu-id="5e673-188">Status displays the completion status of the training process.</span></span>
- <span data-ttu-id="5e673-189">“最高准确性”显示截至目前由模型生成器找到的性能最佳的模型的准确性。</span><span class="sxs-lookup"><span data-stu-id="5e673-189">Best accuracy displays the accuracy of the best performing model found by Model Builder so far.</span></span> <span data-ttu-id="5e673-190">准确性越高，意味着模型对测试数据的预测越准确。</span><span class="sxs-lookup"><span data-stu-id="5e673-190">Higher accuracy means the model predicted more correctly on test data.</span></span>
- <span data-ttu-id="5e673-191">“最佳算法”显示截至目前由模型生成器找到的性能最佳的算法的名称。</span><span class="sxs-lookup"><span data-stu-id="5e673-191">Best algorithm displays the name of the best performing algorithm performed found by Model Builder so far.</span></span>
- <span data-ttu-id="5e673-192">“最新算法”显示模型生成器为了训练模型采用的最新算法名称。</span><span class="sxs-lookup"><span data-stu-id="5e673-192">Last algorithm displays the name of the algorithm most recently used by Model Builder to train the model.</span></span>

<span data-ttu-id="5e673-193">训练完成后，导航到评估步骤。</span><span class="sxs-lookup"><span data-stu-id="5e673-193">Once training is complete, navigate to the evaluate step.</span></span>

## <a name="evaluate-the-model"></a><span data-ttu-id="5e673-194">评估模型</span><span class="sxs-lookup"><span data-stu-id="5e673-194">Evaluate the model</span></span>

<span data-ttu-id="5e673-195">训练步骤的成果将是一个模型，该模型具备最佳的性能。</span><span class="sxs-lookup"><span data-stu-id="5e673-195">The result of the training step will be one model which had the best performance.</span></span> <span data-ttu-id="5e673-196">在模型生成器工具的评估步骤中，输出部分将包含“最佳模型”项中性能最佳的模型使用的算法，并包含“最佳模型质量 (RSquared)”中的指标   。</span><span class="sxs-lookup"><span data-stu-id="5e673-196">In the evaluate step of the Model Builder tool, the output section, will contain the algorithm used by the best performing model in the *Best Model* entry along with metrics in *Best Model Quality (RSquared)*.</span></span> <span data-ttu-id="5e673-197">此外还有一个摘要表格，包含性能最佳的前五种模型以及它们的指标信息。</span><span class="sxs-lookup"><span data-stu-id="5e673-197">Additionally, a summary table containing top five models and their metrics.</span></span> <span data-ttu-id="5e673-198">请访问以下链接，了解有关[评估模型指标](https://docs.microsoft.com/dotnet/machine-learning/resources/metrics)的更多信息。</span><span class="sxs-lookup"><span data-stu-id="5e673-198">Visit the following link to learn more about [evaluating model metrics](https://docs.microsoft.com/dotnet/machine-learning/resources/metrics).</span></span>

<span data-ttu-id="5e673-199">如果对自己的准确性指标不满意，尝试提高模型准确性的简单方法是增加模型的训练时间或使用更多数据。</span><span class="sxs-lookup"><span data-stu-id="5e673-199">If you're not satisfied with your accuracy metrics, some easy ways to try and improve model accuracy are to increase the amount of time to train the model or use more data.</span></span>

## <a name="use-the-model-for-predictions"></a><span data-ttu-id="5e673-200">使用预测模型</span><span class="sxs-lookup"><span data-stu-id="5e673-200">Use the model for predictions</span></span>

<span data-ttu-id="5e673-201">训练期间会创建两个项目。</span><span class="sxs-lookup"><span data-stu-id="5e673-201">Two projects will be created as a result of the training process.</span></span>

- <span data-ttu-id="5e673-202">TaxiFarePredictionML.ConsoleApp：包含模型训练和要使用的代码的 .NET 控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="5e673-202">TaxiFarePredictionML.ConsoleApp: A .NET Console application that contains the model training and consumption code.</span></span>
- <span data-ttu-id="5e673-203">TaxiFarePredictionML.Model：一个 .NET Standard 类库，包含定义输入和输出模型数据架构的数据模型，以及在训练期间性能最佳的模型的持久版本。</span><span class="sxs-lookup"><span data-stu-id="5e673-203">TaxiFarePredictionML.Model: A .NET Standard class library containing the data models that define the schema of input and output model data as well as the persisted version of the best performing model during training.</span></span>

1. <span data-ttu-id="5e673-204">在模型生成器工具的代码部分中，选择“添加项目”以将项目添加到解决方案  。</span><span class="sxs-lookup"><span data-stu-id="5e673-204">In the code section of the Model Builder tool, select **Added Projects** to add the projects to the solution.</span></span>
2. <span data-ttu-id="5e673-205">在“解决方案资源管理器”中，右键单击“TaxiFarePrediction”项目  。</span><span class="sxs-lookup"><span data-stu-id="5e673-205">In solution explorer, right-click the *TaxiFarePrediction* project.</span></span> <span data-ttu-id="5e673-206">然后选择“添加”>“现有项”  。</span><span class="sxs-lookup"><span data-stu-id="5e673-206">Then, select **Add > Existing Item**.</span></span> <span data-ttu-id="5e673-207">在文件类型下拉列表中选择 `All Files`，导航到 TaxiFarePredictionML.Model 项目目录，然后选择 `MLModel.zip` 文件  。</span><span class="sxs-lookup"><span data-stu-id="5e673-207">For file type drop down, select `All Files`, navigate to the *TaxiFarePredictionML.Model* project directory and select the `MLModel.zip` file.</span></span> <span data-ttu-id="5e673-208">然后右键单击新添加的 `MLModel.zip` 文件，并选择“属性”  。</span><span class="sxs-lookup"><span data-stu-id="5e673-208">Then right-click the recently added `MLModel.zip` file and select *Properties*.</span></span> <span data-ttu-id="5e673-209">在“复制到输出目录”处，从下拉列表中选择“如果较新则复制”  。</span><span class="sxs-lookup"><span data-stu-id="5e673-209">For the Copy to Output Directory option, select *Copy if Newer* from the dropdown.</span></span>
3. <span data-ttu-id="5e673-210">右键单击“TaxiFarePrediction”项目  。</span><span class="sxs-lookup"><span data-stu-id="5e673-210">Right-click *TaxiFarePrediction* project.</span></span> <span data-ttu-id="5e673-211">然后选择“添加”>“引用”  。</span><span class="sxs-lookup"><span data-stu-id="5e673-211">Then, **Add > Reference**.</span></span> <span data-ttu-id="5e673-212">选择“项目”>“解决方案”节点，在列表中勾选“TaxiFarePredictionML.Model”项目并选择“确定”   。</span><span class="sxs-lookup"><span data-stu-id="5e673-212">Choose the **Projects > Solution** node and from the list, check the *TaxiFarePredictionML.Model* project and select OK.</span></span>

4. <span data-ttu-id="5e673-213">打开 TaxiFarePrediction 项目中的 Program.cs 文件   。</span><span class="sxs-lookup"><span data-stu-id="5e673-213">Open the *Program.cs* file in the *TaxiFarePrediction* project.</span></span>
5. <span data-ttu-id="5e673-214">添加以下 using 语句：</span><span class="sxs-lookup"><span data-stu-id="5e673-214">Add the following using statements:</span></span>

    ```csharp
    using System;
    using Microsoft.ML;
    using TaxiFarePredictionML.Model.DataModels;
    ```

6. <span data-ttu-id="5e673-215">将 `ConsumeModel` 方法添加到 `Program` 类。</span><span class="sxs-lookup"><span data-stu-id="5e673-215">Add the `ConsumeModel` method to the `Program` class.</span></span> <span data-ttu-id="5e673-216">`ConsumeModel` 将基于模型生成器生成的模型创建一个 `PredictionEngine`，对新数据进行预测并将其打印到控制台。</span><span class="sxs-lookup"><span data-stu-id="5e673-216">The `ConsumeModel` will create a `PredictionEngine` based on the model generated by Model Builder to make predictions on new data and print them out to the console.</span></span>

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

7. <span data-ttu-id="5e673-217">将以下代码添加到 `Main` 方法，并运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="5e673-217">Add the following code to the `Main` method and run the application.</span></span>

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

    <span data-ttu-id="5e673-218">该程序生成的输出应类似于下面的代码段：</span><span class="sxs-lookup"><span data-stu-id="5e673-218">The output generated by the program should look similar to the snippet below:</span></span>

    ```bash
    Predicted Fare: 16.82245
    ```

<span data-ttu-id="5e673-219">如果稍后需要在另一个解决方案中引用生成的项目，可以在 `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` 目录中找到它们。</span><span class="sxs-lookup"><span data-stu-id="5e673-219">If you need to reference the generated projects at a later time inside of another solution, you can find them inside the `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` directory.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5e673-220">后续步骤</span><span class="sxs-lookup"><span data-stu-id="5e673-220">Next Steps</span></span>

<span data-ttu-id="5e673-221">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="5e673-221">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="5e673-222">准备和了解数据</span><span class="sxs-lookup"><span data-stu-id="5e673-222">Prepare and understand the data</span></span>
> * <span data-ttu-id="5e673-223">选择方案</span><span class="sxs-lookup"><span data-stu-id="5e673-223">Choose a scenario</span></span>
> * <span data-ttu-id="5e673-224">加载数据</span><span class="sxs-lookup"><span data-stu-id="5e673-224">Load the data</span></span>
> * <span data-ttu-id="5e673-225">定型模型</span><span class="sxs-lookup"><span data-stu-id="5e673-225">Train the model</span></span>
> * <span data-ttu-id="5e673-226">评估模型</span><span class="sxs-lookup"><span data-stu-id="5e673-226">Evaluate the model</span></span>
> * <span data-ttu-id="5e673-227">使用预测模型</span><span class="sxs-lookup"><span data-stu-id="5e673-227">Use the model for predictions</span></span>

<span data-ttu-id="5e673-228">请继续阅读以下操作指南文章，了解如何部署模型。</span><span class="sxs-lookup"><span data-stu-id="5e673-228">Advance to either of the following how-to articles to learn how to deploy your model.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="5e673-229">将模型部署到 Azure Functions</span><span class="sxs-lookup"><span data-stu-id="5e673-229">Deploy a model to Azure Functions</span></span>](../how-to-guides/serve-model-serverless-azure-functions-ml-net.md)
> [!div class="nextstepaction"]
> [<span data-ttu-id="5e673-230">将模型部署到 Web API</span><span class="sxs-lookup"><span data-stu-id="5e673-230">Deploy a model to a Web API</span></span>](../how-to-guides/serve-model-web-api-ml-net.md)

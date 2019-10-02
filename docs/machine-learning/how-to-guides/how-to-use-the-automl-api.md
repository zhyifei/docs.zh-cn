---
title: 如何使用 ML.NET 自动化 ML API
description: ML.NET 自动化 ML API 可自动化模型生成过程并生成可供部署的模型。 了解可用于配置自动化机器学习任务的选项。
ms.date: 04/24/2019
ms.custom: mvc,how-to
ms.openlocfilehash: a7057337fb6ff19a1e402d7bf74a766b246ea3c1
ms.sourcegitcommit: 8b8dd14dde727026fd0b6ead1ec1df2e9d747a48
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/27/2019
ms.locfileid: "71332722"
---
# <a name="how-to-use-the-mlnet-automated-machine-learning-api"></a><span data-ttu-id="7f90b-104">如何使用 ML.NET 自动化机器学习 API</span><span class="sxs-lookup"><span data-stu-id="7f90b-104">How to use the ML.NET automated machine learning API</span></span>

<span data-ttu-id="7f90b-105">自动化机器学习 (AutoML) 可自动化将机器学习应用于数据的过程。</span><span class="sxs-lookup"><span data-stu-id="7f90b-105">Automated machine learning (AutoML) automates the process of applying machine learning to data.</span></span> <span data-ttu-id="7f90b-106">在给定数据集的情况下，可以运行 AutoML **试验**来迭代不同的数据特征、机器学习算法和超参数，从而选择最佳模型。</span><span class="sxs-lookup"><span data-stu-id="7f90b-106">Given a dataset, you can run an AutoML **experiment** to iterate over different data featurizations, machine learning algorithms, and hyperparameters to select the best model.</span></span>

> [!NOTE]
> <span data-ttu-id="7f90b-107">本主题涉及 ML.NET 目前处于预览状态的自动化机器学习 API。</span><span class="sxs-lookup"><span data-stu-id="7f90b-107">This topic refers to the automated machine learning API for ML.NET, which is currently in preview.</span></span> <span data-ttu-id="7f90b-108">材料可能会有所变化。</span><span class="sxs-lookup"><span data-stu-id="7f90b-108">Material may be subject to change.</span></span>

## <a name="load-data"></a><span data-ttu-id="7f90b-109">加载数据</span><span class="sxs-lookup"><span data-stu-id="7f90b-109">Load data</span></span>

<span data-ttu-id="7f90b-110">自动化机器学习支持将数据集加载到 [IDataView](xref:Microsoft.ML.IDataView) 中。</span><span class="sxs-lookup"><span data-stu-id="7f90b-110">Automated machine learning supports loading a dataset into an [IDataView](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="7f90b-111">数据可以采用制表符分隔值 (TSV) 文件和逗号分隔值 (CSV) 文件的形式。</span><span class="sxs-lookup"><span data-stu-id="7f90b-111">Data can be in the form of tab-separated value (TSV) files and comma separated value (CSV) files.</span></span>

<span data-ttu-id="7f90b-112">示例：</span><span class="sxs-lookup"><span data-stu-id="7f90b-112">Example:</span></span>

```csharp
using Microsoft.ML;
using Microsoft.ML.AutoML;
    // ...
    MLContext mlContext = new MLContext();
    IDataView trainDataView = mlContext.Data.LoadFromTextFile<SentimentIssue>("my-data-file.csv", hasHeader: true);
```

## <a name="select-the-machine-learning-task-type"></a><span data-ttu-id="7f90b-113">选择机器学习任务类型</span><span class="sxs-lookup"><span data-stu-id="7f90b-113">Select the machine learning task type</span></span>
<span data-ttu-id="7f90b-114">在创建试验之前，请确定想要解决的机器学习问题的类型。</span><span class="sxs-lookup"><span data-stu-id="7f90b-114">Before creating an experiment, determine the kind of machine learning problem you want to solve.</span></span> <span data-ttu-id="7f90b-115">自动化机器学习支持以下 ML 任务：</span><span class="sxs-lookup"><span data-stu-id="7f90b-115">Automated machine learning supports the following ML tasks:</span></span>

* <span data-ttu-id="7f90b-116">二元分类</span><span class="sxs-lookup"><span data-stu-id="7f90b-116">Binary Classification</span></span>
* <span data-ttu-id="7f90b-117">多类分类</span><span class="sxs-lookup"><span data-stu-id="7f90b-117">Multiclass Classification</span></span>
* <span data-ttu-id="7f90b-118">回归测试</span><span class="sxs-lookup"><span data-stu-id="7f90b-118">Regression</span></span>

## <a name="create-experiment-settings"></a><span data-ttu-id="7f90b-119">创建试验设置</span><span class="sxs-lookup"><span data-stu-id="7f90b-119">Create experiment settings</span></span>

<span data-ttu-id="7f90b-120">为确定的 ML 任务类型创建试验设置：</span><span class="sxs-lookup"><span data-stu-id="7f90b-120">Create experiment settings for the determined ML task type:</span></span>

* <span data-ttu-id="7f90b-121">二元分类</span><span class="sxs-lookup"><span data-stu-id="7f90b-121">Binary Classification</span></span>

  ```csharp
  var experimentSettings = new BinaryExperimentSettings();
  ```

* <span data-ttu-id="7f90b-122">多类分类</span><span class="sxs-lookup"><span data-stu-id="7f90b-122">Multiclass Classification</span></span>

  ```csharp
  var experimentSettings = new MulticlassExperimentSettings();
  ```

* <span data-ttu-id="7f90b-123">回归测试</span><span class="sxs-lookup"><span data-stu-id="7f90b-123">Regression</span></span>

  ```csharp
  var experimentSettings = new RegressionExperimentSettings();
  ```

## <a name="configure-experiment-settings"></a><span data-ttu-id="7f90b-124">配置试验设置</span><span class="sxs-lookup"><span data-stu-id="7f90b-124">Configure experiment settings</span></span>

<span data-ttu-id="7f90b-125">试验具有高度可配置性。</span><span class="sxs-lookup"><span data-stu-id="7f90b-125">Experiments are highly configurable.</span></span> <span data-ttu-id="7f90b-126">有关配置设置的完整列表，请参阅 [AutoML API 文档](https://docs.microsoft.com/dotnet/api/?view=automl-dotnet)。</span><span class="sxs-lookup"><span data-stu-id="7f90b-126">See the [AutoML API docs](https://docs.microsoft.com/dotnet/api/?view=automl-dotnet) for a full list of configuration settings.</span></span>

<span data-ttu-id="7f90b-127">一些示例包括：</span><span class="sxs-lookup"><span data-stu-id="7f90b-127">Some examples include:</span></span>

1. <span data-ttu-id="7f90b-128">指定试验的最长允许运行时间。</span><span class="sxs-lookup"><span data-stu-id="7f90b-128">Specify the maximum time that the experiment is allowed to run.</span></span>

    ```csharp
    experimentSettings.MaxExperimentTimeInSeconds = 3600;
    ```

1. <span data-ttu-id="7f90b-129">在试验的计划完成时间之前，使用取消令牌取消试验。</span><span class="sxs-lookup"><span data-stu-id="7f90b-129">Use a cancellation token to cancel the experiment before it is scheduled to finish.</span></span>

    ```csharp
    experimentSettings.CancellationToken = cts.Token;

    // Cancel experiment after the user presses any key
    CancelExperimentAfterAnyKeyPress(cts);
    ```

1. <span data-ttu-id="7f90b-130">指定其他优化指标。</span><span class="sxs-lookup"><span data-stu-id="7f90b-130">Specify a different optimizing metric.</span></span>

    ```csharp
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.OptimizingMetric = RegressionMetric.MeanSquaredError;
    ```

1. <span data-ttu-id="7f90b-131">`CacheDirectory` 设置是指向目录的指针，执行 AutoML 任务期间训练的所有模型都将保存在该目录中。</span><span class="sxs-lookup"><span data-stu-id="7f90b-131">The `CacheDirectory` setting is a pointer to a directory where all models trained during the AutoML task will be saved.</span></span> <span data-ttu-id="7f90b-132">如果 `CacheDirectory` 设置为 null，则模型将保留在内存中，而不是写入磁盘。</span><span class="sxs-lookup"><span data-stu-id="7f90b-132">If `CacheDirectory` is set to null, models will be kept in memory instead of written to disk.</span></span>
 
    ```csharp
    experimentSettings.CacheDirectory = null;
    ```

1. <span data-ttu-id="7f90b-133">指示自动化 ML 不要使用特定训练程序。</span><span class="sxs-lookup"><span data-stu-id="7f90b-133">Instruct automated ML not to use certain trainers.</span></span>

    <span data-ttu-id="7f90b-134">将根据每个任务探索待优化训练程序的默认列表。</span><span class="sxs-lookup"><span data-stu-id="7f90b-134">A default list of trainers to optimize are explored per task.</span></span> <span data-ttu-id="7f90b-135">此列表可以针对每个试验进行修改。</span><span class="sxs-lookup"><span data-stu-id="7f90b-135">This list can be modified for each experiment.</span></span> <span data-ttu-id="7f90b-136">例如，可以从列表中删除在数据集上运行缓慢的训练程序。</span><span class="sxs-lookup"><span data-stu-id="7f90b-136">For instance, trainers that run slowly on your dataset can be removed from the list.</span></span> <span data-ttu-id="7f90b-137">若要优化一个特定的训练程序，请调用 `experimentSettings.Trainers.Clear()`，然后添加想要使用的训练程序。</span><span class="sxs-lookup"><span data-stu-id="7f90b-137">To optimize on one specific trainer call `experimentSettings.Trainers.Clear()`, then add the trainer that you want to use.</span></span>

    ```csharp
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.Trainers.Remove(RegressionTrainer.LbfgsPoissonRegression);
    experimentSettings.Trainers.Remove(RegressionTrainer.OnlineGradientDescent);
    ```

<span data-ttu-id="7f90b-138">每个 ML 任务支持的训练程序的列表可在以下相应链接中找到：</span><span class="sxs-lookup"><span data-stu-id="7f90b-138">The list of supported trainers per ML task can be found at the corresponding link below:</span></span>

* [<span data-ttu-id="7f90b-139">支持的二元分类算法</span><span class="sxs-lookup"><span data-stu-id="7f90b-139">Supported Binary Classification Algorithms</span></span>](xref:Microsoft.ML.AutoML.BinaryClassificationTrainer)
* [<span data-ttu-id="7f90b-140">支持的多类分类算法</span><span class="sxs-lookup"><span data-stu-id="7f90b-140">Supported Multiclass Classification Algorithms</span></span>](xref:Microsoft.ML.AutoML.MulticlassClassificationTrainer)
* [<span data-ttu-id="7f90b-141">支持的回归算法</span><span class="sxs-lookup"><span data-stu-id="7f90b-141">Supported Regression Algorithms</span></span>](xref:Microsoft.ML.AutoML.RegressionTrainer)

## <a name="optimizing-metric"></a><span data-ttu-id="7f90b-142">优化指标</span><span class="sxs-lookup"><span data-stu-id="7f90b-142">Optimizing metric</span></span>

<span data-ttu-id="7f90b-143">如以上示例所示，优化指标可确定在模型训练期间要优化的指标。</span><span class="sxs-lookup"><span data-stu-id="7f90b-143">The optimizing metric, as shown in the example above, determines the metric to be optimized during model training.</span></span> <span data-ttu-id="7f90b-144">可以选择的优化指标由选择的任务类型决定。</span><span class="sxs-lookup"><span data-stu-id="7f90b-144">The optimizing metric you can select is determined by the task type you choose.</span></span> <span data-ttu-id="7f90b-145">以下是可用指标的列表。</span><span class="sxs-lookup"><span data-stu-id="7f90b-145">Below is a list of available metrics.</span></span>

|[<span data-ttu-id="7f90b-146">二元分类</span><span class="sxs-lookup"><span data-stu-id="7f90b-146">Binary Classification</span></span>](xref:Microsoft.ML.AutoML.BinaryClassificationMetric) | [<span data-ttu-id="7f90b-147">多类分类</span><span class="sxs-lookup"><span data-stu-id="7f90b-147">Multiclass Classification</span></span>](xref:Microsoft.ML.AutoML.MulticlassClassificationMetric) |[<span data-ttu-id="7f90b-148">回归</span><span class="sxs-lookup"><span data-stu-id="7f90b-148">Regression</span></span>](xref:Microsoft.ML.AutoML.RegressionMetric)
|-- |-- |--
|<span data-ttu-id="7f90b-149">准确性</span><span class="sxs-lookup"><span data-stu-id="7f90b-149">Accuracy</span></span>| <span data-ttu-id="7f90b-150">LogLoss</span><span class="sxs-lookup"><span data-stu-id="7f90b-150">LogLoss</span></span> | <span data-ttu-id="7f90b-151">RSquared</span><span class="sxs-lookup"><span data-stu-id="7f90b-151">RSquared</span></span>
|<span data-ttu-id="7f90b-152">AreaUnderPrecisionRecallCurve</span><span class="sxs-lookup"><span data-stu-id="7f90b-152">AreaUnderPrecisionRecallCurve</span></span> | <span data-ttu-id="7f90b-153">LogLossReduction</span><span class="sxs-lookup"><span data-stu-id="7f90b-153">LogLossReduction</span></span> | <span data-ttu-id="7f90b-154">MeanAbsoluteError</span><span class="sxs-lookup"><span data-stu-id="7f90b-154">MeanAbsoluteError</span></span>
|<span data-ttu-id="7f90b-155">AreaUnderRocCurve</span><span class="sxs-lookup"><span data-stu-id="7f90b-155">AreaUnderRocCurve</span></span> | <span data-ttu-id="7f90b-156">MacroAccuracy</span><span class="sxs-lookup"><span data-stu-id="7f90b-156">MacroAccuracy</span></span> | <span data-ttu-id="7f90b-157">MeanSquaredError</span><span class="sxs-lookup"><span data-stu-id="7f90b-157">MeanSquaredError</span></span>
|<span data-ttu-id="7f90b-158">F1Score</span><span class="sxs-lookup"><span data-stu-id="7f90b-158">F1Score</span></span> | <span data-ttu-id="7f90b-159">MicroAccuracy</span><span class="sxs-lookup"><span data-stu-id="7f90b-159">MicroAccuracy</span></span> | <span data-ttu-id="7f90b-160">RootMeanSquaredError</span><span class="sxs-lookup"><span data-stu-id="7f90b-160">RootMeanSquaredError</span></span>
|<span data-ttu-id="7f90b-161">NegativePrecision</span><span class="sxs-lookup"><span data-stu-id="7f90b-161">NegativePrecision</span></span> | <span data-ttu-id="7f90b-162">TopKAccuracy</span><span class="sxs-lookup"><span data-stu-id="7f90b-162">TopKAccuracy</span></span>
|<span data-ttu-id="7f90b-163">NegativeRecall</span><span class="sxs-lookup"><span data-stu-id="7f90b-163">NegativeRecall</span></span> |
|<span data-ttu-id="7f90b-164">PositivePrecision</span><span class="sxs-lookup"><span data-stu-id="7f90b-164">PositivePrecision</span></span>
|<span data-ttu-id="7f90b-165">PositiveRecall</span><span class="sxs-lookup"><span data-stu-id="7f90b-165">PositiveRecall</span></span>

## <a name="data-pre-processing-and-featurization"></a><span data-ttu-id="7f90b-166">数据预处理和特征化</span><span class="sxs-lookup"><span data-stu-id="7f90b-166">Data pre-processing and featurization</span></span>

> [!NOTE]
> <span data-ttu-id="7f90b-167">特征列仅支持 [`Boolean`](https://docs.microsoft.com/en-us/dotnet/api/system.boolean)、[`Single`](https://docs.microsoft.com/en-us/dotnet/api/system.single) 和 [`String`](https://docs.microsoft.com/en-us/dotnet/api/system.string) 类型。</span><span class="sxs-lookup"><span data-stu-id="7f90b-167">The feature column only supported types of [`Boolean`](https://docs.microsoft.com/en-us/dotnet/api/system.boolean), [`Single`](https://docs.microsoft.com/en-us/dotnet/api/system.single), and [`String`](https://docs.microsoft.com/en-us/dotnet/api/system.string).</span></span>

<span data-ttu-id="7f90b-168">默认情况下会进行数据预处理，并会自动执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="7f90b-168">Data pre-processing happens by default and the following steps are performed automatically for you:</span></span>

1. <span data-ttu-id="7f90b-169">删除没有有用信息的特征</span><span class="sxs-lookup"><span data-stu-id="7f90b-169">Drop features with no useful information</span></span>

    <span data-ttu-id="7f90b-170">删除没有来自训练集和验证集的有用信息的特征。</span><span class="sxs-lookup"><span data-stu-id="7f90b-170">Drop features with no useful information from training and validation sets.</span></span> <span data-ttu-id="7f90b-171">其中包括缺少所有值的特征、所有行具有相同值的特征或具有极高基数的特征（例如，哈希、ID 或 GUID）。</span><span class="sxs-lookup"><span data-stu-id="7f90b-171">These include features with all values missing, same value across all rows or with extremely high cardinality (e.g., hashes, IDs or GUIDs).</span></span>

1. <span data-ttu-id="7f90b-172">缺少值指示和插补</span><span class="sxs-lookup"><span data-stu-id="7f90b-172">Missing value indication and imputation</span></span>

    <span data-ttu-id="7f90b-173">使用数据类型的默认值填充缺少值的单元格。</span><span class="sxs-lookup"><span data-stu-id="7f90b-173">Fill missing value cells with the default value for the datatype.</span></span> <span data-ttu-id="7f90b-174">使用与输入列数量相同的插槽数追加指示特征。</span><span class="sxs-lookup"><span data-stu-id="7f90b-174">Append indicator features with the same number of slots as the input column.</span></span> <span data-ttu-id="7f90b-175">如果输入列中缺少值，则追加的指示特征中的值为 `1`，否则为 `0`。</span><span class="sxs-lookup"><span data-stu-id="7f90b-175">The value in the appended indicator features is `1` if the value in the input column is missing and `0` otherwise.</span></span>

1. <span data-ttu-id="7f90b-176">生成其他特征</span><span class="sxs-lookup"><span data-stu-id="7f90b-176">Generate additional features</span></span>
    
    <span data-ttu-id="7f90b-177">对于文本特征：使用一元语法和三元语法的词袋特征。</span><span class="sxs-lookup"><span data-stu-id="7f90b-177">For text features: Bag-of-word features using unigrams and tri-character-grams.</span></span>
    
    <span data-ttu-id="7f90b-178">对于分类特征：用于低基数特征的单热编码，以及用于高基数分类特征的单热哈希编码。</span><span class="sxs-lookup"><span data-stu-id="7f90b-178">For categorical features: One-hot encoding for low cardinality features, and one-hot-hash encoding for high cardinality categorical features.</span></span>

1. <span data-ttu-id="7f90b-179">转换和编码</span><span class="sxs-lookup"><span data-stu-id="7f90b-179">Transformations and encodings</span></span>

    <span data-ttu-id="7f90b-180">具有极少唯一值的文本特征转换为分类特征。</span><span class="sxs-lookup"><span data-stu-id="7f90b-180">Text features with very few unique values transformed into categorical features.</span></span> <span data-ttu-id="7f90b-181">根据分类特征的基数，执行单热编码或单热哈希编码。</span><span class="sxs-lookup"><span data-stu-id="7f90b-181">Depending on cardinality of categorical features, perform one-hot encoding or one-hot hash encoding.</span></span>

## <a name="exit-criteria"></a><span data-ttu-id="7f90b-182">退出条件</span><span class="sxs-lookup"><span data-stu-id="7f90b-182">Exit criteria</span></span>

<span data-ttu-id="7f90b-183">定义完成任务的条件：</span><span class="sxs-lookup"><span data-stu-id="7f90b-183">Define the criteria to complete your task:</span></span>

1. <span data-ttu-id="7f90b-184">一段时间后退出 - 通过在试验设置中使用 `MaxExperimentTimeInSeconds`，可以定义任务应持续运行的时长（以秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="7f90b-184">Exit after a length of time - Using `MaxExperimentTimeInSeconds` in your experiment settings you can define how long in seconds that an task should continue to run.</span></span>

1. <span data-ttu-id="7f90b-185">收到取消令牌时退出 - 可以使用取消令牌，以便在任务的计划完成时间之前取消该任务。</span><span class="sxs-lookup"><span data-stu-id="7f90b-185">Exit on a cancellation token -  You can use a cancellation token that lets you cancel the task before it is scheduled to finish.</span></span>

    ```csharp
    var cts = new CancellationTokenSource();
    var experimentSettings = new RegressionExperimentSettings();
    experimentSettings.MaxExperimentTimeInSeconds = 3600;
    experimentSettings.CancellationToken = cts.Token;
    ```

## <a name="create-an-experiment"></a><span data-ttu-id="7f90b-186">创建试验</span><span class="sxs-lookup"><span data-stu-id="7f90b-186">Create an experiment</span></span>

<span data-ttu-id="7f90b-187">配置试验设置后，即可创建试验。</span><span class="sxs-lookup"><span data-stu-id="7f90b-187">Once you have configured the experiment settings, you are ready to create the experiment.</span></span>

```csharp
RegressionExperiment experiment = mlContext.Auto().CreateRegressionExperiment(experimentSettings);
```

## <a name="run-the-experiment"></a><span data-ttu-id="7f90b-188">运行试验</span><span class="sxs-lookup"><span data-stu-id="7f90b-188">Run the experiment</span></span>

<span data-ttu-id="7f90b-189">运行试验会触发数据预处理、学习算法选择和超参数调整。</span><span class="sxs-lookup"><span data-stu-id="7f90b-189">Running the experiment triggers data pre-processing, learning algorithm selection, and hyperparameter tuning.</span></span> <span data-ttu-id="7f90b-190">AutoML 将继续生成特征化、学习算法和超参数的组合，直到达到 `MaxExperimentTimeInSeconds` 或试验终止。</span><span class="sxs-lookup"><span data-stu-id="7f90b-190">AutoML will continue to generate combinations of featurization, learning algorithms, and hyperparameters until the `MaxExperimentTimeInSeconds` is reached or the experiment is terminated.</span></span>

```csharp
ExperimentResult<RegressionMetrics> experimentResult = experiment
    .Execute(trainingDataView, LabelColumnName, progressHandler: progressHandler);
```

<span data-ttu-id="7f90b-191">如果想要传入验证数据、指示列目的的列信息或特征预提取器，请探索 `Execute()` 的其他重载。</span><span class="sxs-lookup"><span data-stu-id="7f90b-191">Explore other overloads for `Execute()` if you want to pass in validation data, column information indicating the column purpose, or prefeaturizers.</span></span>

## <a name="training-modes"></a><span data-ttu-id="7f90b-192">训练模式</span><span class="sxs-lookup"><span data-stu-id="7f90b-192">Training modes</span></span>

### <a name="training-dataset"></a><span data-ttu-id="7f90b-193">训练数据集</span><span class="sxs-lookup"><span data-stu-id="7f90b-193">Training dataset</span></span>

<span data-ttu-id="7f90b-194">AutoML 提供重载试验执行方法，该方法允许提供训练数据。</span><span class="sxs-lookup"><span data-stu-id="7f90b-194">AutoML provides an overloaded experiment execute method which allows you to provide training data.</span></span> <span data-ttu-id="7f90b-195">在内部，自动化 ML 将数据划分为训练-验证拆分。</span><span class="sxs-lookup"><span data-stu-id="7f90b-195">Internally, automated ML divides the data into train-validate splits.</span></span>

```csharp
experiment.Execute(trainDataView);   
```

### <a name="custom-validation-dataset"></a><span data-ttu-id="7f90b-196">自定义验证数据集</span><span class="sxs-lookup"><span data-stu-id="7f90b-196">Custom validation dataset</span></span>

<span data-ttu-id="7f90b-197">如果随机拆分不可接受（时序数据通常如此），则使用自定义验证数据集。</span><span class="sxs-lookup"><span data-stu-id="7f90b-197">Use custom validation dataset if random split is not acceptable, as is usually the case with time series data.</span></span> <span data-ttu-id="7f90b-198">可以指定自己的验证数据集。</span><span class="sxs-lookup"><span data-stu-id="7f90b-198">You can specify your own validation dataset.</span></span> <span data-ttu-id="7f90b-199">将根据指定的验证数据集而不是一个或多个随机数据集评估模型。</span><span class="sxs-lookup"><span data-stu-id="7f90b-199">The model will be evaluated against the validation dataset specified instead of one or more random datasets.</span></span>

```csharp
experiment.Execute(trainDataView, validationDataView);   
```

## <a name="explore-model-metrics"></a><span data-ttu-id="7f90b-200">探索模型指标</span><span class="sxs-lookup"><span data-stu-id="7f90b-200">Explore model metrics</span></span>

<span data-ttu-id="7f90b-201">在 ML 试验的每次迭代后，系统会存储与该任务相关的指标。</span><span class="sxs-lookup"><span data-stu-id="7f90b-201">After each iteration of an ML experiment, metrics relating to that task are stored.</span></span>

<span data-ttu-id="7f90b-202">例如，我们可以从最佳运行中访问验证指标：</span><span class="sxs-lookup"><span data-stu-id="7f90b-202">For example, we can access validation metrics from the best run:</span></span>

```csharp
RegressionMetrics metrics = experimentResult.BestRun.ValidationMetrics;
Console.WriteLine($"R-Squared: {metrics.RSquared:0.##}");
Console.WriteLine($"Root Mean Squared Error: {metrics.RootMeanSquaredError:0.##}");
```

<span data-ttu-id="7f90b-203">以下是每个 ML 任务的所有可用指标：</span><span class="sxs-lookup"><span data-stu-id="7f90b-203">The following are all the available metrics per ML task:</span></span>

* [<span data-ttu-id="7f90b-204">二元分类指标</span><span class="sxs-lookup"><span data-stu-id="7f90b-204">Binary classification metrics</span></span>](xref:Microsoft.ML.AutoML.BinaryClassificationMetric)
* [<span data-ttu-id="7f90b-205">多类分类指标</span><span class="sxs-lookup"><span data-stu-id="7f90b-205">Multiclass classification metrics</span></span>](xref:Microsoft.ML.AutoML.MulticlassClassificationMetric)
* [<span data-ttu-id="7f90b-206">回归指标</span><span class="sxs-lookup"><span data-stu-id="7f90b-206">Regression metrics</span></span>](xref:Microsoft.ML.AutoML.RegressionMetric)

## <a name="see-also"></a><span data-ttu-id="7f90b-207">请参阅</span><span class="sxs-lookup"><span data-stu-id="7f90b-207">See also</span></span>

<span data-ttu-id="7f90b-208">有关完整的代码示例等，请访问 [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master#automate-mlnet-models-generation-preview-state) GitHub 存储库。</span><span class="sxs-lookup"><span data-stu-id="7f90b-208">For full code samples and more visit the [dotnet/machinelearning-samples](https://github.com/dotnet/machinelearning-samples/tree/master#automate-mlnet-models-generation-preview-state) GitHub repository.</span></span>

---
title: 训练和评估模型
description: 了解如何使用 ML.NET 生成机器学习模型、收集指标以及测量性能。 机器学习模型识别训练数据内的模式以使用新数据进行预测。
ms.date: 06/25/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to, title-hack-0625
ms.openlocfilehash: 61cdaf693c417d02da95d1d79ab30eb2d30a057b
ms.sourcegitcommit: bab17fd81bab7886449217356084bf4881d6e7c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2019
ms.locfileid: "67397644"
---
# <a name="train-and-evaluate-a-model"></a><span data-ttu-id="a683b-104">训练和评估模型</span><span class="sxs-lookup"><span data-stu-id="a683b-104">Train and evaluate a model</span></span>

<span data-ttu-id="a683b-105">了解如何使用 ML.NET 生成机器学习模型、收集指标以及测量性能。</span><span class="sxs-lookup"><span data-stu-id="a683b-105">Learn how to build machine learning models, collect metrics, and measure performance with ML.NET.</span></span> <span data-ttu-id="a683b-106">虽然此示例训练回归模型，但这些概念适用于大部分其他算法。</span><span class="sxs-lookup"><span data-stu-id="a683b-106">Although this sample trains a regression model, the concepts are applicable throughout a majority of the other algorithms.</span></span>

## <a name="split-data-for-training-and-testing"></a><span data-ttu-id="a683b-107">拆分数据用于训练和测试</span><span class="sxs-lookup"><span data-stu-id="a683b-107">Split data for training and testing</span></span>

<span data-ttu-id="a683b-108">机器学习模型旨在识别训练数据中的模式。</span><span class="sxs-lookup"><span data-stu-id="a683b-108">The goal of a machine learning model is to identify patterns within training data.</span></span> <span data-ttu-id="a683b-109">这些模式用于使用新数据进行预测。</span><span class="sxs-lookup"><span data-stu-id="a683b-109">These patterns are used to make predictions using new data.</span></span>

<span data-ttu-id="a683b-110">给定以下数据模型：</span><span class="sxs-lookup"><span data-stu-id="a683b-110">Given the following data model:</span></span>

```csharp
public class HousingData
{
    [LoadColumn(0)]
    public float Size { get; set; }

    [LoadColumn(1, 3)]
    [VectorType(3)]
    public float[] HistoricalPrices { get; set; }

    [LoadColumn(4)]
    [ColumnName("Label")]
    public float CurrentPrice { get; set; }
}
```

<span data-ttu-id="a683b-111">将数据加载到 [`IDataView`](xref:Microsoft.ML.IDataView) 中：</span><span class="sxs-lookup"><span data-stu-id="a683b-111">Load the data into an [`IDataView`](xref:Microsoft.ML.IDataView):</span></span>

```csharp
HousingData[] housingData = new HousingData[]
{
    new HousingData
    {
        Size = 600f,
        HistoricalPrices = new float[] { 100000f ,125000f ,122000f },
        CurrentPrice = 170000f
    },
    new HousingData
    {
        Size = 1000f,
        HistoricalPrices = new float[] { 200000f, 250000f, 230000f },
        CurrentPrice = 225000f
    },
    new HousingData
    {
        Size = 1000f,
        HistoricalPrices = new float[] { 126000f, 130000f, 200000f },
        CurrentPrice = 195000f
    },
    new HousingData
    {
        Size = 850f,
        HistoricalPrices = new float[] { 150000f,175000f,210000f },
        CurrentPrice = 205000f
    },
    new HousingData
    {
        Size = 900f,
        HistoricalPrices = new float[] { 155000f, 190000f, 220000f },
        CurrentPrice = 210000f
    },
    new HousingData
    {
        Size = 550f,
        HistoricalPrices = new float[] { 99000f, 98000f, 130000f },
        CurrentPrice = 180000f
    }
};
```

<span data-ttu-id="a683b-112">使用 [`TrainTestSplit`](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit*) 方法将数据拆分为训练集和测试集。</span><span class="sxs-lookup"><span data-stu-id="a683b-112">Use the [`TrainTestSplit`](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit*) method to split the data into train and test sets.</span></span> <span data-ttu-id="a683b-113">结果将是一个 [`TrainTestData`](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData) 对象，其中包含两个 [`IDataView`](xref:Microsoft.ML.IDataView) 成员，一个用于训练集，另一个用于测试集。</span><span class="sxs-lookup"><span data-stu-id="a683b-113">The result will be a [`TrainTestData`](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData) object which contains two [`IDataView`](xref:Microsoft.ML.IDataView) members, one for the train set and the other for the test set.</span></span> <span data-ttu-id="a683b-114">数据拆分百分比由 `testFraction` 参数确定。</span><span class="sxs-lookup"><span data-stu-id="a683b-114">The data split percentage is determined by the `testFraction` parameter.</span></span> <span data-ttu-id="a683b-115">下面的代码片段让测试集占用 20% 的原始数据。</span><span class="sxs-lookup"><span data-stu-id="a683b-115">The snippet below is holding out 20 percent of the original data for the test set.</span></span>

```csharp
DataOperationsCatalog.TrainTestData dataSplit = mlContext.Data.TrainTestSplit(data, testFraction: 0.2);
IDataView trainData = dataSplit.TrainSet;
IDataView testData = dataSplit.TestSet;
```

## <a name="prepare-the-data"></a><span data-ttu-id="a683b-116">准备数据</span><span class="sxs-lookup"><span data-stu-id="a683b-116">Prepare the data</span></span>

<span data-ttu-id="a683b-117">在训练机器学习模型之前，需要对数据进行预处理。</span><span class="sxs-lookup"><span data-stu-id="a683b-117">The data needs to be pre-processed before training a machine learning model.</span></span> <span data-ttu-id="a683b-118">有关数据准备的详细信息，请参阅[数据准备操作说明文章](prepare-data-ml-net.md)以及[`transforms page`](../resources/transforms.md)。</span><span class="sxs-lookup"><span data-stu-id="a683b-118">More information on data preparation can be found on the [data prep how-to article](prepare-data-ml-net.md) as well as the [`transforms page`](../resources/transforms.md).</span></span>

<span data-ttu-id="a683b-119">ML.NET 算法对输入列类型存在约束。</span><span class="sxs-lookup"><span data-stu-id="a683b-119">ML.NET algorithms have constraints on input column types.</span></span> <span data-ttu-id="a683b-120">此外，如果未指定任何值，则默认值会用于输入和输出列名。</span><span class="sxs-lookup"><span data-stu-id="a683b-120">Additionally, default values are used for input and output column names when no values are specified.</span></span>

### <a name="working-with-expected-column-types"></a><span data-ttu-id="a683b-121">使用预期的列类型</span><span class="sxs-lookup"><span data-stu-id="a683b-121">Working with expected column types</span></span>

<span data-ttu-id="a683b-122">ML.NET 中的机器学习算法预期使用大小已知的浮点向量作为输入。</span><span class="sxs-lookup"><span data-stu-id="a683b-122">The machine learning algorithms in ML.NET expect a float vector of known size as input.</span></span> <span data-ttu-id="a683b-123">当所有数据都已经是数字格式并且打算一起处理（即图像像素）时，将 [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) 属性应用于数据模型。</span><span class="sxs-lookup"><span data-stu-id="a683b-123">Apply the [`VectorType`](xref:Microsoft.ML.Data.VectorTypeAttribute) attribute to your data model when all of the data is already in numerical format and is intended to be processed together (i.e. image pixels).</span></span> 

<span data-ttu-id="a683b-124">如果数据不全为数字格式，并且想要单独对每个列应用不同的数据转换，请在处理所有列后使用 [`Concatenate`](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate*) 方法，以将所有单独的列合并为一个特征向量并将特征向量输出到新列。</span><span class="sxs-lookup"><span data-stu-id="a683b-124">If data is not all numerical and you want to apply different data transformations on each of the columns individually, use the [`Concatenate`](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate*) method after all of the columns have been processed to combine all of the individual columns into a single feature vector that is output to a new column.</span></span> 

<span data-ttu-id="a683b-125">以下代码片段将 `Size` 和 `HistoricalPrices` 列合并为一个特征向量，该特征向量输出到名为 `Features` 的新列。</span><span class="sxs-lookup"><span data-stu-id="a683b-125">The following snippet combines the `Size` and `HistoricalPrices` columns into a single feature vector that is output to a new column called `Features`.</span></span> <span data-ttu-id="a683b-126">由于比例存在差异，将 [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax*) 应用于 `Features` 列来规范化数据。</span><span class="sxs-lookup"><span data-stu-id="a683b-126">Because there is a difference in scales, [`NormalizeMinMax`](xref:Microsoft.ML.NormalizationCatalog.NormalizeMinMax*) is applied to the `Features` column to normalize the data.</span></span>

```csharp
// Define Data Prep Estimator
// 1. Concatenate Size and Historical into a single feature vector output to a new column called Features
// 2. Normalize Features vector
IEstimator<ITransformer> dataPrepEstimator =
    mlContext.Transforms.Concatenate("Features", "Size", "HistoricalPrices")
        .Append(mlContext.Transforms.NormalizeMinMax("Features"));

// Create data prep transformer
ITransformer dataPrepTransformer = dataPrepEstimator.Fit(trainData);

// Apply transforms to training data
IDataView transformedTrainingData = dataPrepTransformer.Transform(trainData);
```

### <a name="working-with-default-column-names"></a><span data-ttu-id="a683b-127">使用默认列名</span><span class="sxs-lookup"><span data-stu-id="a683b-127">Working with default column names</span></span>

<span data-ttu-id="a683b-128">未指定列名时，ML.NET 算法会使用默认列名。</span><span class="sxs-lookup"><span data-stu-id="a683b-128">ML.NET algorithms use default column names when none are specified.</span></span> <span data-ttu-id="a683b-129">所有训练程序都有一个名为 `featureColumnName` 的参数可用于算法的输入，并且在适用情况下，它们还有一个用于预期值的名为 `labelColumnName` 的参数。</span><span class="sxs-lookup"><span data-stu-id="a683b-129">All trainers have a parameter called `featureColumnName` for the inputs of the algorithm and when applicable they also have a parameter for the expected value called `labelColumnName`.</span></span> <span data-ttu-id="a683b-130">默认情况下，这些值分别为 `Features` 和 `Label`。</span><span class="sxs-lookup"><span data-stu-id="a683b-130">By default those values are `Features` and `Label` respectively.</span></span> 

<span data-ttu-id="a683b-131">通过在预处理期间使用 [`Concatenate`](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate*) 方法创建名为 `Features` 的新列，无需在算法的参数中指定特征列名，因为它已存在于预处理的 `IDataView` 中。</span><span class="sxs-lookup"><span data-stu-id="a683b-131">By using the [`Concatenate`](xref:Microsoft.ML.TransformExtensionsCatalog.Concatenate*) method during pre-processing to create a new column called `Features`, there is no need to specify the feature column name in the parameters of the algorithm since it already exists in the pre-processed `IDataView`.</span></span> <span data-ttu-id="a683b-132">标签列为 `CurrentPrice`，但由于数据模型中使用了 [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) 属性，ML.NET 将 `CurrentPrice` 列重命名为 `Label`，因而无需向机器学习算法估算器提供 `labelColumnName` 参数。</span><span class="sxs-lookup"><span data-stu-id="a683b-132">The label column is `CurrentPrice`, but since the [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) attribute is used in the data model, ML.NET renames the `CurrentPrice` column to `Label` which removes the need to provide the `labelColumnName` parameter to the machine learning algorithm estimator.</span></span> 

<span data-ttu-id="a683b-133">如果不想使用默认列名，请在定义机器学习算法估算器时将特征和标签列的名称作为参数传入，如以下代码片段所示：</span><span class="sxs-lookup"><span data-stu-id="a683b-133">If you don't want to use the default column names, pass in the names of the feature and label columns as parameters when defining the machine learning algorithm estimator as demonstrated by the subsequent snippet:</span></span>

```csharp
var UserDefinedColumnSdcaEstimator = mlContext.Regression.Trainers.Sdca(labelColumnName: "MyLabelColumnName", featureColumnName: "MyFeatureColumnName");
```

## <a name="train-the-machine-learning-model"></a><span data-ttu-id="a683b-134">训练机器学习模型</span><span class="sxs-lookup"><span data-stu-id="a683b-134">Train the machine learning model</span></span>

<span data-ttu-id="a683b-135">对数据进行预处理后，使用 [`Fit`](xref:Microsoft.ML.Trainers.TrainerEstimatorBase`2.Fit*) 方法通过 [`StochasticDualCoordinateAscent`](xref:Microsoft.ML.Trainers.SdcaRegressionTrainer) 回归算法训练机器学习模型。</span><span class="sxs-lookup"><span data-stu-id="a683b-135">Once the data is pre-processed, use the [`Fit`](xref:Microsoft.ML.Trainers.TrainerEstimatorBase`2.Fit*) method to train the machine learning model with the [`StochasticDualCoordinateAscent`](xref:Microsoft.ML.Trainers.SdcaRegressionTrainer) regression algorithm.</span></span>

```csharp
// Define StochasticDualCoordinateAscent regression algorithm estimator
var sdcaEstimator = mlContext.Regression.Trainers.Sdca();

// Build machine learning model
var trainedModel = sdcaEstimator.Fit(transformedTrainingData);
```

## <a name="extract-model-parameters"></a><span data-ttu-id="a683b-136">提取模型参数</span><span class="sxs-lookup"><span data-stu-id="a683b-136">Extract model parameters</span></span>

<span data-ttu-id="a683b-137">训练模型后，提取已学习的 [`ModelParameters`](xref:Microsoft.ML.Trainers.ModelParametersBase%601) 用于检查或重新训练。</span><span class="sxs-lookup"><span data-stu-id="a683b-137">After the model has been trained, extract the learned [`ModelParameters`](xref:Microsoft.ML.Trainers.ModelParametersBase%601) for inspection or re-training.</span></span> <span data-ttu-id="a683b-138">[`LinearRegressionModelParameters`](xref:Microsoft.ML.Trainers.LinearRegressionModelParameters) 提供经过训练的模型的偏差和已学习的系数或权重。</span><span class="sxs-lookup"><span data-stu-id="a683b-138">The [`LinearRegressionModelParameters`](xref:Microsoft.ML.Trainers.LinearRegressionModelParameters) provide the bias and learned coefficients or weights of the trained model.</span></span> 

```csharp
var trainedModelParameters = trainedModel.Model as LinearRegressionModelParameters;
```

> [!NOTE]
> <span data-ttu-id="a683b-139">其他模型具有特定于其任务的参数。</span><span class="sxs-lookup"><span data-stu-id="a683b-139">Other models have parameters that are specific to their tasks.</span></span> <span data-ttu-id="a683b-140">例如，[K-Means 算法](xref:Microsoft.ML.Trainers.KMeansTrainer)基于形心将数据放入群集中，[`KMeansModelParameters`](xref:Microsoft.ML.Trainers.KMeansModelParameters) 包含存储这些已学习的形心的属性。</span><span class="sxs-lookup"><span data-stu-id="a683b-140">For example, the [K-Means algorithm](xref:Microsoft.ML.Trainers.KMeansTrainer) puts data into cluster based on centroids and the [`KMeansModelParameters`](xref:Microsoft.ML.Trainers.KMeansModelParameters) contains a property that stores these learned centroids.</span></span> <span data-ttu-id="a683b-141">若要了解详细信息，请访问 [`Microsoft.ML.Trainers` API 文档](xref:Microsoft.ML.Trainers)并查找名称中包含 `ModelParameters` 的类。</span><span class="sxs-lookup"><span data-stu-id="a683b-141">To learn more, visit the [`Microsoft.ML.Trainers` API Documentation](xref:Microsoft.ML.Trainers) and look for classes that contain `ModelParameters` in their name.</span></span> 

## <a name="evaluate-model-quality"></a><span data-ttu-id="a683b-142">评估模型质量</span><span class="sxs-lookup"><span data-stu-id="a683b-142">Evaluate model quality</span></span>

<span data-ttu-id="a683b-143">若要帮助选择性能最佳的模型，必须评估其在测试数据中的性能。</span><span class="sxs-lookup"><span data-stu-id="a683b-143">To help choose the best performing model, it is essential to evaluate its performance on test data.</span></span> <span data-ttu-id="a683b-144">使用 [`Evaluate`](xref:Microsoft.ML.RegressionCatalog.Evaluate*) 方法测量经过训练的模型的各种指标。</span><span class="sxs-lookup"><span data-stu-id="a683b-144">Use the [`Evaluate`](xref:Microsoft.ML.RegressionCatalog.Evaluate*) method, to measure various metrics for the trained model.</span></span>

> [!NOTE]
> <span data-ttu-id="a683b-145">`Evaluate` 方法根据执行的机器学习任务生成不同的指标。</span><span class="sxs-lookup"><span data-stu-id="a683b-145">The `Evaluate` method produces different metrics depending on which machine learning task was performed.</span></span> <span data-ttu-id="a683b-146">有关更多详细信息，请访问 [`Microsoft.ML.Data` API 文档](xref:Microsoft.ML.Data)并查找名称中包含 `Metrics` 的类。</span><span class="sxs-lookup"><span data-stu-id="a683b-146">For more details, visit the [`Microsoft.ML.Data` API Documentation](xref:Microsoft.ML.Data) and look for classes that contain `Metrics` in their name.</span></span> 

```csharp
// Measure trained model performance
// Apply data prep transformer to test data
IDataView transformedTestData = dataPrepTransformer.Transform(testData);

// Use trained model to make inferences on test data
IDataView testDataPredictions = trainedModel.Transform(transformedTestData);

// Extract model metrics and get RSquared
RegressionMetrics trainedModelMetrics = mlContext.Regression.Evaluate(testDataPredictions);
double rSquared = trainedModelMetrics.RSquared;
```

<span data-ttu-id="a683b-147">在上一代码示例中：</span><span class="sxs-lookup"><span data-stu-id="a683b-147">In the previous code sample:</span></span>  
1. <span data-ttu-id="a683b-148">测试数据集使用之前定义的数据准备转换进行预处理。</span><span class="sxs-lookup"><span data-stu-id="a683b-148">Test data set is pre-processed using the data preparation transforms previously defined.</span></span> 
2. <span data-ttu-id="a683b-149">经过训练的机器学习模型用于对测试数据进行预测。</span><span class="sxs-lookup"><span data-stu-id="a683b-149">The trained machine learning model is used to make predictions on the test data.</span></span>
3. <span data-ttu-id="a683b-150">在 `Evaluate` 方法中，将测试数据集 `CurrentPrice` 列中的值与新输出预测的 `Score` 列进行比较，以计算回归模型的指标，其中之一是 R 平方，它存储在 `rSquared` 变量中。</span><span class="sxs-lookup"><span data-stu-id="a683b-150">In the `Evaluate` method, the values in the `CurrentPrice` column of the test data set are compared against the `Score` column of the newly output predictions to calculate the metrics for the regression model, one of which, R-Squared is stored in the `rSquared` variable.</span></span>

> [!NOTE]
> <span data-ttu-id="a683b-151">在这一小型示例中，由于数据大小存在限制，R 平方是一个不在 0-1 范围内的数字。</span><span class="sxs-lookup"><span data-stu-id="a683b-151">In this small example, the R-Squared is a number not in the range of 0-1 because of the limited size of the data.</span></span> <span data-ttu-id="a683b-152">在实际方案中，应预期看到介于 0 和 1 之间的值。</span><span class="sxs-lookup"><span data-stu-id="a683b-152">In a real-world scenario, you should expect to see a value between 0 and 1.</span></span>

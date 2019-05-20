---
title: 使用经过训练的模型进行预测
description: 了解如何使用经过训练的模型进行预测
ms.date: 05/03/2019
author: luisquintanilla
ms.author: luquinta
ms.custom: mvc, how-to
ms.openlocfilehash: dac3b3bfa68776975a2e5e762f46db16e39d61fb
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2019
ms.locfileid: "65065600"
---
# <a name="make-predictions-with-a-trained-model"></a>使用经过训练的模型进行预测

了解如何使用经过训练的模型进行预测

## <a name="create-data-models"></a>创建数据模型

### <a name="input-data"></a>输入数据

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

### <a name="output-data"></a>输出数据

与 `Features` 和 `Label` 输入列名一样，ML.NET 为模型生成的预测值列提供默认名称。 名称可能因任务而异。

由于此示例中使用的算法是线性回归算法，输出列的默认名称为 `Score`，它由 `PredictedPrice` 属性上的 [`ColumnName`](xref:Microsoft.ML.Data.ColumnNameAttribute) 特性定义。

```csharp
class HousingPrediction : HousingData
{
    [ColumnName("Score")]
    public float PredictedPrice { get; set; }
}
```

`HousingPrediction` 数据模型继承自 `HousingData`，这让它可以轻松地将原始输入数据与模型生成的输出一起可视化。  

## <a name="set-up-a-prediction-pipeline"></a>设置预测管道

无论是进行单一预测还是批量预测，都需要将预测管道加载到应用程序中。 此管道包含数据预处理转换以及经过训练的模型。 下面的代码片段从名为 `model.zip` 的文件中加载预测管道。

```csharp
//Create MLContext 
MLContext mlContext = new MLContext();

// Load Trained Model
DataViewSchema predictionPipelineSchema;
ITransformer predictionPipeline = mlContext.Model.Load("model.zip", out predictionPipelineSchema);
```

## <a name="single-prediction"></a>单一预测

若要进行单一预测，请使用加载的预测管道创建 [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)。

```csharp
// Create PredictionEngines
PredictionEngine<HousingData, HousingPrediction> predictionEngine = mlContext.Model.CreatePredictionEngine<HousingData, HousingPrediction>(predictionPipeline);
```

然后，使用 [`Predict`](xref:Microsoft.ML.PredictionEngineBase%602.Predict*) 方法并将输入数据作为参数传入。 请注意，使用 [`Predict`](xref:Microsoft.ML.PredictionEngineBase%602.Predict*) 方法不要求输入为 [`IDataView`](xref:Microsoft.ML.IDataView)。 这是因为它可以方便地内在化输入数据类型操作，以便能够传入输入数据类型的对象。 此外，由于 `CurrentPrice` 是尝试使用新数据进行预测的目标或标签，假设此时没有用于它的值。

```csharp
// Input Data
HousingData inputData = new HousingData
{
    Size = 900f,
    HistoricalPrices = new float[] { 155000f, 190000f, 220000f }
};

// Get Prediction
HousingPrediction prediction = predictionEngine.Predict(inputData);
```

如果访问 `prediction` 对象的 `Score` 属性，则应获得类似于 `150079` 的值。

## <a name="batch-prediction"></a>批量预测

给定以下数据，将其加载到 [`IDataView`](xref:Microsoft.ML.IDataView) 中。 因为 `CurrentPrice` 是尝试使用新数据进行预测的目标或标签，所以假设此时没有用于它的值。

```csharp
// Actual data
HousingData[] housingData = new HousingData[]
{
    new HousingData
    {
        Size = 850f,
        HistoricalPrices = new float[] { 150000f,175000f,210000f }
    },
    new HousingData
    {
        Size = 900f,
        HistoricalPrices = new float[] { 155000f, 190000f, 220000f }
    },
    new HousingData
    {
        Size = 550f,
        HistoricalPrices = new float[] { 99000f, 98000f, 130000f }
    }
};
```

然后，使用 [`Transform`](xref:Microsoft.ML.ITransformer.Transform*) 方法应用数据转换并生成预测。

```csharp
// Predicted Data
IDataView predictions = predictionPipeline.Transform(inputData);
```

使用 [`GetColumn`](xref:Microsoft.ML.Data.ColumnCursorExtensions.GetColumn*) 方法检查预测值。

```csharp
// Get Predictions
float[] scoreColumn = predictions.GetColumn<float>("Score").ToArray();
```

分数列中的预测值应如下所示：

| 观测 | 预测 |
|---|---|
| 1 | 144638.2 |
| 2 | 150079.4 |
| 3 | 107789.8 |

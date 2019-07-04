---
title: 将回归与模型生成器配合使用以预测价格
description: 本教程演示如何使用 ML.NET 模型生成器生成回归模型以预测价格，特别是纽约市的出租车费。
author: luisquintanilla
ms.author: luquinta
ms.date: 06/26/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: db9788e3065a0f2f21d712b2d4826efea2d8a829
ms.sourcegitcommit: 52e588dc2ee74d484cd07ac60076be25cbf777ab
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2019
ms.locfileid: "67410575"
---
# <a name="predict-prices-using-regression-with-model-builder"></a>将回归与模型生成器配合使用以预测价格

了解如何使用 ML.NET 模型生成器来生成用于预测价格的[回归模型](../resources/glossary.md#regression)。  在本教程中开发的.NET 控制台应用根据纽约市出租车费的历史数据预测出租车费。

模型生成器价格预测模板可用于任何需要数值预测值的方案。 示例方案包括：房价预测、需求预测和销售额预测。

在本教程中，你将了解：
> [!div class="checklist"]
> * 准备和了解数据
> * 选择方案
> * 加载数据
> * 定型模型
> * 评估模型
> * 使用预测模型

> [!NOTE]
> 模型生成器当前为预览版。

## <a name="pre-requisites"></a>先决条件

请访问[模型生成器安装指南](../how-to-guides/install-model-builder.md)，查看先决条件和安装说明的列表。

## <a name="create-a-console-application"></a>创建控制台应用程序

1. 创建名为“TaxiFarePrediction”的“.NET Core 控制台应用程序”  。

1. 安装“Microsoft.ML”NuGet 包  ：

    在“解决方案资源管理器”中，右键单击“TaxiFarePrediction”项目，然后选择“管理 NuGet 包”    。 选择“nuget.org”作为包源，然后选择“浏览”选项卡并搜索“Microsoft.ML”，在列表中选择包，再选择“安装”按钮    。 选择“预览更改”  对话框上的“确定”  按钮，如果你同意所列包的许可条款，则选择“接受许可”  对话框上的“我接受”  按钮。

## <a name="prepare-and-understand-the-data"></a>准备和了解数据

1. 在项目中创建一个名为“数据”的目录来保存数据集文件  。

1. 下载 [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) 数据集并将其保存至在上一步中创建的“数据”文件夹  。 此数据集用于训练和评估机器学习模型。 该数据集最初来自 [NYC TLC 出租车行程数据集](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml)。

1. 在解决方案资源管理器中，右键单击“taxi-fare-train.csv”文件并选择“属性”    。 在“高级”下，将“复制到输出目录”的值更改为“如果较新则复制”    。

`taxi-fare-train.csv` 数据集中的每一行都包含一辆出租车的详细行程。 

1. 打开“taxi-fare-train.csv”数据集 

    提供的数据集包含以下列：

    * **vendor_id：** 出租车供应商的 ID 是一项特征。
    * **rate_code：** 出租车行程的费率类型是一项特征。
    * **passenger_count：** 行程中的乘客人数是一项特征。
    * **trip_time_in_secs：** 这次行程所花的时间。 希望在行程完成前预测行程费用。 当时并不知道行程有多长。 因此，行程时间不是一项特征，需要从模型删除此列。
    * **trip_distance：** 行程距离是一项特征。
    * **payment_type：** 付款方式（现金或信用卡）是一项特征。
    * **fare_amount：** 支付的总出租车费用是一个标签。

`label` 是要预测的列。 在执行回归任务时，目标是预测一个数字值。 在此价格预测方案中，要预测的是出租车的乘车费用。 所以“fare_amount”是标签  。 标识的 `features` 是为模型提供的用来预测 `label` 的输入。 在这种情况下，剩余的列都用作特征或输入来预测车费金额。

## <a name="choose-a-scenario"></a>选择方案

为了训练模型，需要从模型生成器提供的可用机器学习方案列表中进行选择。 在本例中，选择的方案是 `Price Prediction`。 请访问[模型生成器概述文章](../automate-training-with-model-builder.md#scenarios)，查看更多列表内容。

1. 在“解决方案资源管理器”中，右键单击“TaxiFarePrediction”项目，然后选择“添加” > “机器学习”     。
1. 在模型生成器工具的方案步骤中，选择“价格预测”方案  。

## <a name="load-the-data"></a>加载数据

模型生成器有两个数据源：SQL Server 数据库或者 csv 或 tsv 格式的本地文件。 若要详细了解数据格式要求，请访问以下[链接](../how-to-guides/install-model-builder.md#limitations)。

1. 在模型生成器工具的数据步骤中，选择数据源下拉列表中的“文件”  。
1. 选择“选择文件”文本框旁边的按钮，并使用文件资源管理器浏览到“数据”目录中的“taxi-fare-test.csv”，然后选择该文件   
1. 在“要预测的标签或列”下拉列表中选择“fare_amount”，并浏览到模型生成器工具的训练步骤   。

## <a name="train-the-model"></a>定型模型

在本教程中，用于训练价格预测模型的机器学习任务是回归。 在模型训练过程中，模型生成器使用不同的回归算法和设置训练各个模型，以便为数据集找到性能最佳的模型。

模型训练所需的时间与数据量成正比。 请参考此图表，为 `Time to train (seconds)` 字段选择适当的值：

*数据集大小  | 数据集类型       | 平均训练时间*
------------- | ------------------ | --------------
0 - 10 Mb     | 数值和文本   | 10 秒
10 - 100 Mb   | 数值和文本   | 10 分钟
100 - 500 Mb  | 数值和文本   | 30 分钟
500 - 1 Gb    | 数值和文本   | 60 分钟
1 Gb 以上         | 数值和文本   | 3 小时以上

1. 由于训练用的数据文件超过 10 MB，所以请使用 600 秒（10 分钟）作为“训练时间(秒)”的值  。
2. 选择“开始训练”  。

在训练过程中，进度数据显示在训练步骤中的 `Progress` 部分。

- “状态”显示训练进程的完成状态。
- “最高准确性”显示截至目前由模型生成器找到的性能最佳的模型的准确性。 准确性越高，意味着模型对测试数据的预测越准确。 
- “最佳算法”显示截至目前由模型生成器找到的性能最佳的算法的名称。
- “最新算法”显示模型生成器为了训练模型采用的最新算法名称。

训练完成后，导航到评估步骤。

## <a name="evaluate-the-model"></a>评估模型

训练步骤的成果将是一个模型，该模型具备最佳的性能。 在模型生成器工具的评估步骤中，输出部分将包含“最佳模型”项中性能最佳的模型使用的算法，并包含“最佳模型质量 (RSquared)”中的指标   。 此外还有一个摘要表格，包含性能最佳的前五种模型以及它们的指标信息。 请访问以下链接，了解有关[评估模型指标](https://docs.microsoft.com/dotnet/machine-learning/resources/metrics)的更多信息。

如果对自己的准确性指标不满意，尝试提高模型准确性的简单方法是增加模型的训练时间或使用更多数据。

## <a name="use-the-model-for-predictions"></a>使用预测模型

训练期间会创建两个项目。

- TaxiFarePredictionML.ConsoleApp：包含模型训练和要使用的代码的 .NET 控制台应用程序。
- TaxiFarePredictionML.Model：一个 .NET Standard 类库，包含定义输入和输出模型数据架构的数据模型，以及在训练期间性能最佳的模型的持久版本。

1. 在模型生成器工具的代码部分中，选择“添加项目”以将项目添加到解决方案  。
1. 在“解决方案资源管理器”中，右键单击“TaxiFarePrediction”项目  。 然后选择“添加”>“现有项”  。 在文件类型下拉列表中选择 `All Files`，导航到 TaxiFarePredictionML.Model 项目目录，然后选择 `MLModel.zip` 文件  。 然后右键单击新添加的 `MLModel.zip` 文件，并选择“属性”  。 在“复制到输出目录”处，从下拉列表中选择“如果较新则复制”  。
1. 右键单击“TaxiFarePrediction”项目  。 然后选择“添加”>“引用”  。 选择“项目”>“解决方案”节点，在列表中勾选“TaxiFarePredictionML.Model”项目并选择“确定”   。

4. 打开 TaxiFarePrediction 项目中的 Program.cs 文件   。
5. 添加以下 using 语句：

    ```csharp
    using System;
    using Microsoft.ML;
    using TaxiFarePredictionML.Model.DataModels;
    ```

6. 将 `ConsumeModel` 方法添加到 `Program` 类。 `ConsumeModel` 将基于模型生成器生成的模型创建一个 `PredictionEngine`，对新数据进行预测并将其打印到控制台。

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

7. 将以下代码添加到 `Main` 方法，并运行应用程序。

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

    该程序生成的输出应类似于下面的代码段：

    ```bash
    Predicted Fare: 16.82245
    ```

如果稍后需要在另一个解决方案中引用生成的项目，可以在 `C:\Users\%USERNAME%\AppData\Local\Temp\MLVSTools` 目录中找到它们。

## <a name="next-steps"></a>后续步骤

在本教程中，你将了解：
> [!div class="checklist"]
> * 准备和了解数据
> * 选择方案
> * 加载数据
> * 定型模型
> * 评估模型
> * 使用预测模型

请继续阅读以下操作指南文章，了解如何部署模型。

> [!div class="nextstepaction"]
> [将模型部署到 Azure Functions](../how-to-guides/serve-model-serverless-azure-functions-ml-net.md)
> [!div class="nextstepaction"]
> [将模型部署到 Web API](../how-to-guides/serve-model-web-api-ml-net.md)

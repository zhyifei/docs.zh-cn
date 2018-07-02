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
# <a name="tutorial-use-mlnet-to-predict-new-york-taxi-fares-regression"></a>教程：使用 ML.NET 预测纽约出租车费（回归）

> [!NOTE]
> 本主题引用 ML.NET（目前处于预览状态），且材料可能会更改。 有关详细信息，请访问 [ML.NET 简介](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)。

本教程演示如何使用 ML.NET 构建[回归模型](../resources/glossary.md#regression)来预测纽约市出租车费。

在本教程中，你将了解：
> [!div class="checklist"]
> * 了解问题
> * 选择适当的机器学习任务
> * 准备和了解数据
> * 创建学习管道
> * 加载和转换数据
> * 选择学习算法
> * 定型模型
> * 评估模型
> * 使用预测模型

## <a name="prerequisites"></a>系统必备

* 安装了“.NET Core 跨平台开发”工作负载的 [Visual Studio 2017 15.6 或更高版本](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)。

## <a name="understand-the-problem"></a>了解问题

此问题围绕“预测纽约市的出租车行程费用”展开。 从表面看，似乎只取决于行程距离。 但是，由于其他因素（比如额外的乘客或使用信用卡而非现金付款），纽约的出租车供应商收费不同。

## <a name="select-the-appropriate-machine-learning-task"></a>选择适当的机器学习任务

若要预测出租车费，首先选择适当的机器学习任务。 你希望基于数据集中的其他因素预测实际值（表示价格的双精度值）。 你选择[回归](../resources/glossary.md#regression)任务。

定型模型的过程标识数据集中哪些因素在预测最终车费价格时最具影响力。

## <a name="create-a-console-application"></a>创建控制台应用程序

1. 打开 Visual Studio 2017。 从菜单栏中选择“文件” > “新建” > “项目”。 在“新项目”对话框中，依次选择“Visual C#”和“.NET Core”节点。 然后，选择“控制台应用程序(.NET Core)”项目模板。 在“名称”文本框中，键入“TaxiFarePrediction”，然后选择“确定”按钮。

2. 在项目中创建一个名为“数据”的目录来保存数据集文件：

    在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新文件夹”。 键入“数据”，然后按 Enter。

3. 安装“Microsoft.ML NuGet 包”：

    在“解决方案资源管理器”中，右键单击项目，然后选择“管理 NuGet 包”。 将“nuget.org”选择为“包源”，选择“浏览”选项卡并搜索“Microsoft.ML”，在列表中选择该包，然后选择“安装”按钮。 选择“预览更改”对话框上的“确定”按钮，如果你同意所列包的许可条款，则选择“接受许可”对话框上的“我接受”按钮。

### <a name="prepare-and-understand-your-data"></a>准备和了解数据

1. 下载 [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) 和 [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) 数据集，并将它们保存到先前创建的“数据”文件夹。 “出租车行程”数据集定型机器学习模型，且可用来评估模型的准确度。 这些数据集最初来自 [NYC TLC 出租车行程数据集](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml)。

2. 在“解决方案资源管理器”中，右键单击每个 \*.csv 文件，然后选择“属性”。 在“高级”下，将“复制到输出目录”的值更改为“始终”。

3. 在代码编辑器中打开“taxi-fare-train.csv”数据集并查看第一行中的列标题。 查看每个列。 了解数据并确定哪些列是“特征”以及哪些是“标签”。

“标签”是你尝试预测的列的标识符。 标识的“特征”用于预测标签。

* vendor_id：出租车供应商的 ID 是一项特征。
* rate_code：出租车行程的费率类型是一项特征。
* passenger_count：行程乘客数是一项特征。
* trip_time_in_secs：行程花费的时间量。 在行程完成之前，你不会知道行程花费的时间。 从模型中排除此列。
* trip_distance：行程距离是一项特征。
* payment_type：付款方式（现金或信用卡）是一项特征。
* fare_amount：支付的总出租车费是一个标签。

### <a name="create-classes-and-define-paths"></a>创建类和定义路径

将以下附加的 `using` 语句添加到“Program.cs”文件顶部：

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#1 "Add necessary usings")]

需要创建三个全局变量，来保存最近下载的文件路径和保存模型：

* `_datapath` 具有用于定型模型的数据集路径。
* `_testdatapath` 具有用于评估模型的数据集路径。
* `_modelpath` 具有在其中存储定型模型的路径。

将以下代码添加到上面 `Main` 右侧的行中，以指定将最近下载的文件：

[!code-csharp[InitializePaths](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#2 "Define variables to store the data file paths")]

接下来，创建输入数据和预测类：

1. 在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新项”。
1. 在“添加新项”对话框中，选择“类”并将“名称”字段更改为“TaxiTrip.cs”。 然后，选择“添加”按钮。
1. 将以下 `using` 语句添加到新文件中：

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#1 "Add necessary usings")]

删除现有类定义并向“TaxiTrip.cs”文件添加以下代码，其中有两个类 `TaxiTrip` 和 `TaxiTripFarePrediction`：

[!code-csharp[DefineTaxiTrip](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#2 "Define the taxi trip and fare predictions classes")]

`TaxiTrip` 是输入数据集类且具有针对每个数据集列的定义。 `TaxiTripFarePrediction` 类用于模型定型后的预测。 它应用了单个浮点 (`FareAmount`) 和一个`Score` [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute) 属性。

现在回到“Program.cs”文件。 在 `Main` 中，将 `Console.WriteLine("Hello World!")` 替换为以下代码：

```csharp
PredictionModel<TaxiTrip, TaxiTripFarePrediction> model = Train();
```

`Train` 方法定型模型。 使用以下代码在 `Main` 下创建该函数：

```csharp
public static PredictionModel<TaxiTrip, TaxiTripFarePrediction> Train()
{

}
```

## <a name="create-a-learning-pipeline"></a>创建学习管道

学习管道加载所有数据和所需的算法来定型模型。 将以下代码添加到 `Train()` 方法：

```csharp
var pipeline = new LearningPipeline();
```

## <a name="load-and-transform-your-data"></a>加载和转换数据

接下来，将数据加载到管道。 指向最初创建的 `_datapath` 并指定 .csv 文件的分隔符 (,)。 将下面的代码添加到最后一步下的 `Train()` 方法：

```csharp
pipeline.Add(new TextLoader(_datapath).CreateFrom<TaxiTrip>(separator:','));
```

你将引用列，而无需在代码中创建的下划线。 使用 `ColumnCopier()` 函数将 `FareAmount` 列复制到列名为“标签”的新列。 此列为“标签”。

```csharp
pipeline.Add(new ColumnCopier(("FareAmount", "Label")));
```

执行一些“特征工程”来转换数据，以便可以有效地用于机器学习。 定型模型的算法需要数值特征，需要将分类数据（`VendorId`、`RateCode` 和 `PaymentType`）转换为数字。 `CategoricalOneHotVectorizer()` 函数将数字键指派给每个这些列中的值。 通过添加此代码来转换数据：

```csharp
pipeline.Add(new CategoricalOneHotVectorizer("VendorId",
                                             "RateCode",
                                             "PaymentType"));
```

数据准备的最后一步使用 `ColumnConcatenator()` 函数将所有特征合并到一个向量。 此必要步骤可帮助算法轻松处理特征。 添加以下代码：

```csharp
pipeline.Add(new ColumnConcatenator("Features",
                                    "VendorId",
                                    "RateCode",
                                    "PassengerCount",
                                    "TripDistance",
                                    "PaymentType"));
```

请注意，不包含 `trip_time_in_secs` 列。 你已确定它不是一项有用的预测特征。

> [!NOTE]
> 必须按照上面指定的顺序将这些步骤添加到管道才能成功执行。

## <a name="choose-a-learning-algorithm"></a>选择学习算法

在将数据添加到管道，并将其转换为正确的输入格式之后，可以选择学习算法（学习器）。 学习算法定型模型。 针对此问题选择“回归任务”，以此向管道添加一个名为 `FastTreeRegressor()` 的学习器来利用“梯度提升”。

梯度提升是针对回归问题的一项机器学习技术。 它将以步进方式生成每个回归树。 它使用预定义的损失函数测量每个步骤中的错误，并在下一步中对其进行校正。 其结果是一种预测模型，实际上是一组较弱的预测模型。 有关梯度提升的详细信息，请参阅[提升的决策树回归](https://docs.microsoft.com/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression)。

将下面的代码添加到在上一步中添加的数据处理代码后面的 `Train()` 方法中：

```csharp
pipeline.Add(new FastTreeRegressor());
```

你已将前面所有步骤作为单个语句添加到管道，但 C# 包含可以更轻松地创建和初始化管道的方便集合初始化语法。 将目前添加到 `Train()` 方法的代码替换为以下代码：

[!code-csharp[CreatePipeline](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#3 "Create and initialize the learning pipeline")]

## <a name="train-the-model"></a>定型模型

最后一步是定型模型。 在此之前，管道中未执行任何操作。 `pipeline.Train<T_Input, T_Output>()` 函数采用预定义的 `TaxiTrip` 类类型并输出 `TaxiTripFarePrediction` 类型。 将此最后一段代码添加到 `Train()` 函数：

[!code-csharp[TrainMOdel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#4 "Train your model")]

就是这么简单！ 已成功定型机器学习模型，可以用来预测 NYC 的出租车费。 现在，请观察模型的准确度并了解如何使用它。

## <a name="save-the-model"></a>保存模型

继续下一步之前，通过在 `Train()` 函数的末尾添加以下代码，将模型保存到一个 .zip 文件：

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#5 "Save the model asynchronously and return the model")]

将 `await` 语句添加到 `model.WriteAsync()` 调用中意味着 `Train()` 方法必须更改为返回 `Task` 的异步方法。 修改 `Train` 的签名，如下面的代码所示：

[!code-csharp[AsyncTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#6 "Make the Train method async and return a task.")]

更改 `Train` 方法的返回类型意味着你需要将 `await` 添加到调用 `Main` 方法中的 `Train` 的代码，如下面的代码所示：

[!code-csharp[AwaitTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#7 "Await the Train method")]

在 `Main` 方法中添加 `await` 意味着 `Main` 方法必须具有 `async` 修饰符并返回 `Task`：

[!code-csharp[AsyncMain](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#8 "Make the Main method async and return a task.")]

还需要将下面的 using 语句添加到文件顶部：

[!code-csharp[UsingTasks](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#9 "Add System.Threading.Tasks. to your usings.")]

因为 `async Main` 方法是 C# 7.1 中的新功能，且项目的默认语言版本为 C# 7.0，你需要将语言版本更改为 C# 7.1 或更高版本。
要完成此操作，右键单击“解决方案资源管理器”中的项目节点，然后选择“属性”。 选择**生成**选项卡并选择**高级**按钮。 在下拉列表中，选择“C# 7.1”（或更高版本）。 选择“确定”按钮。

## <a name="evaluate-the-model"></a>评估模型

评估是检查模型工作情况的过程。 务必使模型对它在定型时未使用的数据进行准确预测。 实现此目的的一种方法是将数据拆分为定型和测试数据集，就像在本教程所执行的那样。 你已在定型数据上定型模型，现在可以看到它在测试数据上的表现。

返回到 `Main` 函数，并在调用 `Train()` 方法下添加以下代码：

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#10 "Evaluate the model.")]

`Evaluate()` 函数对模型进行评估。 在 `Train()` 下创建该函数。 添加以下代码：

```csharp
private static void Evaluate(PredictionModel<TaxiTrip, TaxiTripFarePrediction> model)
{

}
```

使用 `TextLoader()` 函数加载测试数据。 将以下代码添加到 `Evaluate()` 方法：

[!code-csharp[LoadTestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#12 "Load the test data.")]

添加以下代码以评估模型并为其生成指标：

[!code-csharp[EvaluateAndMeasure](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#13 "Evaluate the model and its predictions.")]

RMS 是一项用于评估回归问题的指标。 指标越低，模型就越好。 将下面的代码添加到 `Evaluate()` 函数以打印模型的 RMS。

[!code-csharp[DisplayRMS](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#14 "Display the RMS metric.")]

RSquared 是另一项用于评估回归问题的指标。 RSquared 将是介于 0 和 1 之间的值。 越接近 1，模型越好。 将下面的代码添加到 `Evaluate()` 函数以打印模型的 RSquared 值。

[!code-csharp[DisplayRSquared](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#15 "Display the RSquared metric.")]

## <a name="use-the-model-for-predictions"></a>使用预测模型

接下来，创建一个类来存放测试场景，可以使用这些场景来确保模型正常工作：

1. 在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新项”。
1. 在“添加新项”对话框中，选择“类”并将“名称”字段更改为“TestTrips.cs”。 然后，选择“添加”按钮。
1. 将类修改为静态，如下面的示例所示：

[!code-csharp[StaticClass](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#1 "Change class to be a static class.")]

本教程使用此类中的一个测试行程。 稍后可以添加其他方案，以尝试使用此示例。 将下面的代码添加到 `TestTrips` 类中：

[!code-csharp[TestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#2 "Create aq trip to predict its cost.")]

此行程实际费用为 29.5，但使用 0 作为占位符。 机器学习算法将预测费用。

在 `Main` 函数中添加以下代码。 它使用 `TestTrip` 数据测试模型：

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#16 "Try a prediction.")]

运行此程序，查看测试用例的预测出租车费。

祝贺你！ 你已成功生成用于预测出租车费的机器学习模型、评估其准确性，并对其进行了测试。 可以在 [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction) 存储库中找到本教程的源代码。

## <a name="next-steps"></a>后续步骤

在本教程中，你将了解：
> [!div class="checklist"]
> * 了解问题
> * 选择适当的机器学习任务
> * 准备和了解数据
> * 创建学习管道
> * 加载和转换数据
> * 选择学习算法
> * 定型模型
> * 评估模型
> * 使用预测模型

查看我们的 GitHub 存储库以继续学习，并找到更多示例。
> [!div class="nextstepaction"]
> [dotnet/machinelearning GitHub 存储库](https://github.com/dotnet/machinelearning/)

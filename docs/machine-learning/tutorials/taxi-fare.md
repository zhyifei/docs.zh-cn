---
title: 使用 ML.NET 预测纽约出租车费（回归）
description: 了解如何在回归方案中使用 ML.NET。
author: aditidugar
ms.author: johalex
ms.date: 07/02/2018
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 133b7ad17a98e4eea510f1704555b690b98e9091
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2018
ms.locfileid: "44252839"
---
# <a name="tutorial-use-mlnet-to-predict-new-york-taxi-fares-regression"></a>教程：使用 ML.NET 预测纽约出租车费（回归）

> [!NOTE]
> 本主题引用 ML.NET（目前处于预览状态），且材料可能会更改。 有关详细信息，请参阅 [ML.NET 简介](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)。

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

* 安装了“.NET Core 跨平台开发”工作负载的 [Visual Studio 2017 15.6 或更高版本](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)。

## <a name="understand-the-problem"></a>了解问题

此问题是有关“预测纽约市的出租车行程费用”。 从表面看，似乎只取决于行程距离。 但是，由于其他因素（比如额外的乘客或使用信用卡而非现金付款），纽约的出租车供应商收费不同。

## <a name="select-the-appropriate-machine-learning-task"></a>选择适当的机器学习任务

你想要预测价格值，该值是基于数据集中的其他因素的实际值。 要执行此操作，选择[回归](../resources/glossary.md#regression)机器学习任务。

## <a name="create-a-console-application"></a>创建控制台应用程序

1. 打开 Visual Studio 2017。 从菜单栏中选择“文件” > “新建” > “项目”。 在“新项目”对话框中，依次选择“Visual C#”和“.NET Core”节点。 然后，选择“控制台应用程序(.NET Core)”项目模板。 在“名称”文本框中，键入“TaxiFarePrediction”，然后选择“确定”按钮。

1. 在项目中创建一个名为“数据”的目录来保存数据集和模型文件：

    在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新文件夹”。 键入“数据”，然后按 Enter。

1. 安装“Microsoft.ML”NuGet 包：

    在“解决方案资源管理器”中，右键单击项目，然后选择“管理 NuGet 包”。 将“nuget.org”选择为“包源”，选择“浏览”选项卡并搜索“Microsoft.ML”，在列表中选择该包，然后选择“安装”按钮。 选择“预览更改”对话框上的“确定”按钮，如果你同意所列包的许可条款，则选择“接受许可”对话框上的“我接受”按钮。

## <a name="prepare-and-understand-the-data"></a>准备和了解数据

1. 下载 [taxi-fare-train.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-train.csv) 和 [taxi-fare-test.csv](https://github.com/dotnet/machinelearning/blob/master/test/data/taxi-fare-test.csv) 数据集，并将它们保存到先前创建的“数据”文件夹。 我们使用这些数据集定型机器学习模型，然后评估模型的准确性。 这些数据集最初来自 [NYC TLC 出租车行程数据集](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml)。

1. 在“解决方案资源管理器”中，右键单击每个 \*.csv 文件，然后选择“属性”。 在“高级”下，将“复制到输出目录”的值更改为“如果较新则复制”。

1. 打开“taxi-fare-train.csv”数据集并查看第一行中的列标题。 查看每个列。 了解数据并确定哪些列是“特征”以及哪些是“标签”。

“标签”是希望预测的列的标识符。 标识的“特征”用于预测标签。

提供的数据集包含以下列：

* vendor_id：出租车供应商的 ID 是一项特征。
* rate_code：出租车行程的费率类型是一项特征。
* passenger_count：行程乘客数是一项特征。
* trip_time_in_secs：行程花费的时间量。 希望在行程完成前预测行程费用。 当时并不知道行程有多长。 因此，行程时间不是一项特征，需要从模型删除此列。
* trip_distance：行程距离是一项特征。
* payment_type：付款方式（现金或信用卡）是一项特征。
* fare_amount：支付的总出租车费是一个标签。

## <a name="create-data-classes"></a>创建数据类

创建输入数据和预测类：

1. 在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新项”。
1. 在“添加新项”对话框中，选择“类”并将“名称”字段更改为“TaxiTrip.cs”。 然后，选择“添加”按钮。
1. 将以下 `using` 指令添加到新文件：

   [!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#1 "Add necessary usings")]

删除现有类定义并向“TaxiTrip.cs”文件添加以下代码，其中有两个类 `TaxiTrip` 和 `TaxiTripFarePrediction`：

[!code-csharp[DefineTaxiTrip](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TaxiTrip.cs#2 "Define the taxi trip and fare predictions classes")]

`TaxiTrip` 是输入数据类且具有针对每个数据集列的定义。 使用[列](xref:Microsoft.ML.Runtime.Api.ColumnAttribute)属性在数据集中指定源列的索引。

`TaxiTripFarePrediction` 类表示预测的结果。 它应用了单个浮动 `FareAmount` 字段，附带 `Score` [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute) 属性。 对于回归任务，“分数”列包含预测的标签值。

> [!NOTE]
> 使用 `float` 类型来表示输入和预测数据类中的浮点值。

## <a name="define-data-and-model-paths"></a>定义数据和模型路径

返回到 Program.cs 文件并添加三个字段，以保存具有数据集的文件的路径以及用于保存模型的文件的路径：

* `_datapath` 包含具有用于定型模型的数据集的文件的路径。
* `_testdatapath` 包含具有用于评估模型的数据集的文件的路径。
* `_modelpath` 包含用于存储定型模型的文件的路径。

将以下代码添加到 `Main` 方法上方，以指定这些路径：

[!code-csharp[InitializePaths](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#2 "Define variables to store the data file paths")]

要编译前面的代码，请将以下 `using` 指令添加到 Program.cs 文件顶部：

[!code-csharp[AddUsingsForPaths](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#17 "Using statements for path definitions")]

## <a name="create-a-learning-pipeline"></a>创建学习管道

将以下附加 `using` 指令添加到 Program.cs 文件顶部：

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#1 "Add necessary usings")]

将 `Main` 方法中的 `Console.WriteLine("Hello World!")` 替换为以下代码：

```csharp
PredictionModel<TaxiTrip, TaxiTripFarePrediction> model = Train();
```

`Train` 方法定型模型。 使用以下代码在 `Main` 下创建该方法：

```csharp
public static PredictionModel<TaxiTrip, TaxiTripFarePrediction> Train()
{

}
```

学习管道加载所有数据和所需的算法来定型模型。 将以下代码添加到 `Train` 方法：

```csharp
var pipeline = new LearningPipeline();
```

## <a name="load-and-transform-data"></a>加载和转换数据

第一个步骤是从定型数据集加载数据。 在本例中，定型数据集存储在具有 `_datapath` 字段所定义路径的文本文件中。 该文件带有列名的标头，所以加载数据时应忽略第一行。 文件中的列用逗号 (",") 分割。 将以下代码添加到 `Train` 方法：

```csharp
pipeline.Add(new TextLoader(_datapath).CreateFrom<TaxiTrip>(useHeader: true, separator: ','));
```

在后续步骤中，我们按 `TaxiTrip` 类中定义的名称引用列。

定型和评估模型时，默认情况下，将“标签”列中的值视为要预测的正确值。 希望预测出租车费时，将 `FareAmount` 列复制到“标签”列。 为此，请使用 <xref:Microsoft.ML.Transforms.ColumnCopier> 并添加以下代码：

```csharp
pipeline.Add(new ColumnCopier(("FareAmount", "Label")));
```

定型模型的算法需要数值特征，所以必须将分类数据（`VendorId`、`RateCode` 和 `PaymentType`）值转换为数字。 为此，请使用 <xref:Microsoft.ML.Transforms.CategoricalOneHotVectorizer>，它将不同的数字键值分配到每行的不同值，并添加以下代码：

```csharp
pipeline.Add(new CategoricalOneHotVectorizer("VendorId",
                                             "RateCode",
                                             "PaymentType"));
```

数据准备最后一步使用 <xref:Microsoft.ML.Transforms.ColumnConcatenator> 转换类将所有功能列合并到“功能”列。 默认情况下，学习算法仅处理“特征”列的特征。 添加以下代码：

```csharp
pipeline.Add(new ColumnConcatenator("Features",
                                    "VendorId",
                                    "RateCode",
                                    "PassengerCount",
                                    "TripDistance",
                                    "PaymentType"));
```

请注意，不包括 `TripTime` 列（对应数据集文件中的 `trip_time_in_secs` 列）。 你已确定它不是一项有用的预测特征。

> [!NOTE]
> 必须按照上面指定的顺序将这些步骤添加到管道才能成功执行。

## <a name="choose-a-learning-algorithm"></a>选择学习算法

在将数据添加到管道，并将其转换为正确的输入格式之后，可以选择学习算法（学习器）。 学习器定型模型。 为此问题选择了“回归任务”，所以使用 <xref:Microsoft.ML.Trainers.FastTreeRegressor> 学习器（ML.NET 提供的一种回归学习器）。

<xref:Microsoft.ML.Trainers.FastTreeRegressor> 学习器利用梯度提升。 梯度提升是针对回归问题的一项机器学习技术。 它将以步进方式生成每个回归树。 它使用预定义的损失函数测量每个步骤中的错误，并在下一步中对其进行校正。 其结果是一种预测模型，实际上是一组较弱的预测模型。 有关梯度提升的详细信息，请参阅[提升的决策树回归](/azure/machine-learning/studio-module-reference/boosted-decision-tree-regression)。

将下面的代码添加到在上一步中添加的数据处理代码后面的 `Train` 方法中：

```csharp
pipeline.Add(new FastTreeRegressor());
```

你已将前面所有步骤作为单个语句添加到管道，但 C# 包含可以更轻松地创建和初始化管道的方便集合初始化语法。 将目前添加到 `Train` 方法的代码替换为以下代码：

[!code-csharp[CreatePipeline](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#3 "Create and initialize the learning pipeline")]

## <a name="train-the-model"></a>定型模型

最后一步是定型模型。 在此之前，管道中未执行任何操作。 `pipeline.Train<TInput, TOutput>` 方法生成的模型接收 `TInput` 类型实例并输出 `TOutput` 类型实例。 将以下代码添加到 `Train` 方法：

[!code-csharp[TrainMOdel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#4 "Train your model")]

就是这么简单！ 已成功定型机器学习模型，可以用来预测 NYC 的出租车费。 现在，我们看一下模型的精确性并了解如何用它来预测出租车费的值。

### <a name="save-the-model"></a>保存模型

此时，你具有可以集成到任何现有或新 .NET 应用程序的模型。 要将模型保存到 .zip 文件中，请在 `Train` 方法的末尾添加以下代码：

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#5 "Save the model asynchronously and return the model")]

将 `await` 语句添加到 `model.WriteAsync` 调用中意味着 `Train` 方法必须更改为返回任务的异步方法。 修改 `Train` 的签名，如下面的代码所示：

[!code-csharp[AsyncTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#6 "Make the Train method async and return a task.")]

更改 `Train` 方法的返回类型意味着你需要将 `await` 添加到调用 `Main` 方法中的 `Train` 的代码，如下面的代码所示：

[!code-csharp[AwaitTraining](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#7 "Await the Train method")]

在 `Main` 方法中使用 `await` 意味着 `Main` 方法必须具有 `async` 修饰符并返回 `Task`：

[!code-csharp[AsyncMain](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#8 "Make the Main method async and return a task.")]

还需要将以下 `using` 指令添加到文件顶部：

[!code-csharp[UsingTasks](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#9 "Add System.Threading.Tasks. to your usings.")]

由于 `async Main` 方法是 C# 7.1 中的新增功能，且项目的默认语言版本为 C# 7.0，因此需要将语言版本更改为 C# 7.1 或更高版本。 要完成此操作，右键单击“解决方案资源管理器”中的项目节点，然后选择“属性”。 选择**生成**选项卡并选择**高级**按钮。 在下拉列表中，选择“C# 7.1”（或更高版本）。 选择“确定”按钮。

## <a name="evaluate-the-model"></a>评估模型

评估是检查模型预测标签值情况的过程。 模型对定型模型中未使用的数据做出好的预测非常重要。 执行此操作的一种方法是将数据拆分到定型和测试数据集，如此教程中所示。 你已在定型数据上定型模型，现在可以看到它在测试数据上的表现。

返回到 `Main` 方法，并在调用 `Train` 方法下添加以下代码：

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#10 "Evaluate the model.")]

`Evaluate` 方法评估模型。 若要创建该方法，请将以下代码添加到 `Train` 方法下：

```csharp
private static void Evaluate(PredictionModel<TaxiTrip, TaxiTripFarePrediction> model)
{

}
```

将以下代码添加到 `Evaluate` 方法，设置测试数据的加载：

[!code-csharp[LoadTestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#12 "Load the test data.")]

添加以下代码以评估模型并生成评估模型：

[!code-csharp[EvaluateAndMeasure](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#13 "Evaluate the model and its predictions.")]

[RMS](../resources/glossary.md##root-of-mean-squared-error-rmse) 是回归模型的一种评估指标。 指标越低，模型就越好。 将以下代码添加到 `Evaluate` 方法以显示 RMS 值：

[!code-csharp[DisplayRMS](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#14 "Display the RMS metric.")]

[RSquared](../resources/glossary.md#coefficient-of-determination) 是回归模型的另一种评估指标。 RSquared 在 0 和 1 之间取值。 值越接近 1，模型就越好。 将以下代码添加到 `Evaluate` 方法以显示 RSquared 值：

[!code-csharp[DisplayRSquared](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#15 "Display the RSquared metric.")]

## <a name="use-the-model-for-predictions"></a>使用预测模型

将类创建到房屋测试数据实例：

1. 在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新项”。
1. 在“添加新项”对话框中，选择“类”并将“名称”字段更改为“TestTrips.cs”。 然后，选择“添加”按钮。
1. 将类修改为静态，如下面的示例所示：

   [!code-csharp[StaticClass](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#1 "Change class to be a static class.")]

本教程使用此类中的一个测试行程。 稍后可以添加其他方案，以尝试使用此模型。 将下面的代码添加到 `TestTrips` 类中：

[!code-csharp[TestData](../../../samples/machine-learning/tutorials/TaxiFarePrediction/TestTrips.cs#2 "Create aq trip to predict its cost.")]

行程实际费用为 29.5。 使用 0 作为占位符，模型将预测费用。

若要预测指定行程的费用，请返回到 Program.cs 文件并将以下代码添加到 `Main` 方法：

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TaxiFarePrediction/Program.cs#16 "Try a prediction.")]

运行此程序，查看测试用例的预测出租车费。

祝贺你！ 你已成功生成用于预测出租车费的机器学习模型、评估其准确性，并用其进行预测。 可以在 [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TaxiFarePrediction) GitHub 存储库中找到本教程的源代码。

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

进入下一教程了解详细信息。
> [!div class="nextstepaction"]
> [Iris 聚类分析](iris-clustering.md)

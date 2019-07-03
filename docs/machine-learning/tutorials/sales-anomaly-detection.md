---
title: 教程：检测产品销售中的异常
description: 了解如何构建针对产品销售数据的异常检测应用程序。 本教程将使用 Visual Studio 2019 和 C# 创建 .NET Core 控制台应用程序。
ms.date: 06/11/2019
ms.topic: tutorial
ms.custom: mvc, title-hack-0612
ms.openlocfilehash: 3e3e368ed3bcb35e7e2c8bdf08abe71afd4ae87c
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2019
ms.locfileid: "67306230"
---
# <a name="tutorial-detect-anomalies-in-product-sales-with-mlnet"></a>教程：使用 ML.NET 检测产品销售中的异常

了解如何构建针对产品销售数据的异常检测应用程序。 本教程将使用 Visual Studio 和 C# 创建 .NET Core 控制台应用程序。

在本教程中，你将了解：
> [!div class="checklist"]
> * 加载数据
> * 训练模型用于峰值异常情况检测
> * 使用经过训练的模型检测峰值异常情况
> * 训练模型用于更改点异常情况检测
> * 使用经过训练的模型检测更改点异常情况

可以在 [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection) 存储库中找到本教程的源代码。

## <a name="prerequisites"></a>系统必备

* 安装了“.NET Core 跨平台开发”工作负载的 [Visual Studio 2017 15.6 或更高版本](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)。

* [product-sales.csv 数据集](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)

>[!NOTE]
> `product-sales.csv` 中的数据格式基于“Shampoo Sales Over a Three Year Period”数据集，该数据集最初来自 DataMarket，由 Rob Hyndman 创建的 Time Series Data Library (TSDL) 提供。 “Shampoo Sales Over a Three Year Period”数据集根据 DataMarket 默认开放许可进行许可。

## <a name="create-a-console-application"></a>创建控制台应用程序

1. 创建名为“ProductSalesAnomalyDetection”的 **.NET Core 控制台应用程序**。

2. 在项目中创建名为“Data”的目录，用于保存数据集文件  。

3. 安装“Microsoft.ML NuGet 包”  ：

    在“解决方案资源管理器”中，右键单击项目，然后选择“管理 NuGet 包”  。 选择“nuget.org”作为包源，然后选择“浏览”选项卡并搜索“Microsoft.ML”，选择列表中的“v1.0.0”包，再选择“安装”按钮    。 选择“预览更改”  对话框上的“确定”  按钮，如果你同意所列包的许可条款，则选择“接受许可”  对话框上的“我接受”  按钮。 对 **Microsoft.ML.TimeSeries v0.12.0** 重复这些步骤。

4. 在 Program.cs 文件的顶部添加以下 `using` 语句  ：

    [!code-csharp[AddUsings](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddUsings "Add necessary usings")]

### <a name="download-your-data"></a>下载数据

1. 下载数据集并将其保存到之前创建的 *Data* 文件夹中：

   * 右键单击 [*product-sales.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv) 并选择“将链接(或目标)另存为...”

     确保将 \*.csv 文件保存到 *Data* 文件夹，或者在将其保存到其他位置后，将 \*.csv 文件移动到 *Data* 文件夹。

2. 在解决方案资源管理器中，右键单击 \*.csv 文件并选择“属性”  。 在“高级”下，将“复制到输出目录”的值更改为“如果较新则复制”    。

下表是来自 \*.csv 文件的数据预览：

|月份  |ProductSales |
|-------|-------------|
|1-Jan  |    271      |
|2-Jan  |    150.9    |
|.....  |    .....    |
|1-Feb  |    199.3    |
|.....  |    .....    |

### <a name="create-classes-and-define-paths"></a>创建类和定义路径

接下来，定义输入类数据结构。

向项目添加一个新类：

1. 在“解决方案资源管理器”中，右键单击该项目，然后选择“添加”>“新项”   。

2. 在“添加新项”对话框中，选择“类”并将“名称”字段更改为“ProductSalesData.cs”     。 然后，选择“添加”  按钮。

此时，*ProductSalesData.cs* 文件在代码编辑器中打开。 将以下 `using` 语句添加到 *ProductSalesData.cs* 顶部：

```csharp
using Microsoft.ML.Data;
```

删除现有类定义并向 *ProductSalesData.cs* 文件添加以下代码，其中有两个类 `ProductSalesData` 和 `ProductSalesPrediction`：

[!code-csharp[DeclareTypes](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/ProductSalesData.cs#DeclareTypes "Declare data record types")]

`ProductSalesData` 指定输入数据类。 [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) 属性指定应加载数据集中的哪些列（按列索引）。 

将以下附加的 `using` 语句添加到“Program.cs”  文件顶部：

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddUsings "Add necessary usings")]

需要创建两个全局字段来存储最近下载的数据集文件路径和已保存的模型文件路径：

* `_dataPath` 具有用于定型模型的数据集路径。
* `_docsize` 具有数据集文件中记录的数量。 可使用此数据计算 `pvalueHistoryLength`。

将以下代码添加到 `Main` 方法上方的行中，以指定这些路径：

[!code-csharp[Declare global variables](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DeclareGlobalVariables "Declare global variables")]

执行所有 ML.NET 操作都是从 [MLContext 类](xref:Microsoft.ML.MLContext)开始，初始化 `mlContext` 可创建一个新的 ML.NET 环境，可在模型创建工作流对象之间共享该环境。 从概念上讲，它与实体框架中的 `DBContext` 类似。

### <a name="initialize-variables-in-main"></a>在 Main 中初始化变量

使用以下代码替换 `Main` 方法中的 `Console.WriteLine("Hello World!")` 行，以声明和初始化 `mlContext` 变量：

[!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CreateMLContext "Create the ML Context")]

### <a name="load-the-data"></a>加载数据

ML.NET 中的数据表示为 [IDataView 类](xref:Microsoft.ML.IDataView)。 `IDataView` 是用于描述表格数据（数字和文本）的一种灵活且有效的方法。 可从文本文件或实时（例如，SQL 数据库或日志文件）将数据加载到 `IDataView` 对象。 添加以下代码作为 `Main()` 方法的下一行：

[!code-csharp[LoadData](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#LoadData "loading dataset")]

[LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) 用于定义数据架构并读取文件。 它使用数据路径变量并返回 `IDataView`。

## <a name="ml-task---time-series-anomaly-detection"></a>ML 任务 - 时序异常情况检测 

异常情况检测标记意外或异常事件/行为。 它提供寻找问题所在位置的线索，并帮助回答“这是否奇怪？”的问题。

![这是否奇怪](./media/sales-anomaly-detection/anomalydetection.png)

异常情况检测是检测时序数据离群值的过程；在给定的输入时序上指向“怪异”或不是预期行为的行为。

这在很多方面都很有用。 例如：

如果你有一辆车，你可能想要知道：此油量计读数是否正常，或者是否存在漏油现象？
如果正在监视能耗，你需要知道：是否出现了中断？

可以检测到两种类型的时序异常情况： 

* **峰值**指示系统中异常行为的临时突发。 

* **更改点**指示系统中一段时间内持续更改的开始。 

在 ML.NET 中，IID 峰值检测或 IID 更改点检测算法适用于[独立且均匀分布的数据集](https://en.wikipedia.org/wiki/Independent_and_identically_distributed_random_variables)。 

将分析相同的产品销售数据来检测峰值和更改点。 峰值检测和更改点检测的模型生成和训练过程相同；主要区别在于使用的特定检测算法。

## <a name="spike-detection"></a>峰值检测 

峰值检测旨在识别与大部分时序数据值明显不同的突然但临时的突发。 及时检测到这些可疑的罕见项目、事件或观测很重要，这样才能尽量减少其出现。 以下方法可用于检测各种异常情况，例如：中断、网络攻击或病毒式 Web 内容。 下图是时序数据集中峰值的示例：

![SpikeDetection](./media/sales-anomaly-detection/SpikeDetection.png)

### <a name="create-the-detectspike-method"></a>创建 DetectSpike() 方法

将以下调用添加到 `DetectSpike()` 方法作为 `Main()` 方法的下一行代码：

[!code-csharp[CallDetectSpike](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CallDetectSpike)]

`DetectSpike()` 方法执行以下任务：

* 定型模型。
* 根据历史销售数据检测峰值。
* 显示结果。

使用下面的代码紧随 `Main()` 方法后创建 `DetectSpike()` 方法：

```csharp
static void DetectSpike(MLContext mlContext, int docSize, IDataView productSales)
{

}
```

使用 [IidSpikeEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidSpikeEstimator) 训练模型用于峰值检测。 使用以下代码将其添加到 `DetectChangepoint()` 方法中：

[!code-csharp[AddSpikeTrainer](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddSpikeTrainer)]

通过在 `DetectSpike()` 方法中添加以下代码作为下一代码行来使模型适应 `productSales` 数据：

[!code-csharp[TrainModel1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TrainModel1)]

[Fit()](xref:Microsoft.ML.Data.TrivialEstimator%601.Fit%2A) 方法通过转换数据集并应用训练来训练模型。

添加以下代码行将 `productSales` 数据转换为 `DetectSpike()` 方法中的下一行：

[!code-csharp[TransformData1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TransformData1)]

之前的代码使用 [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) 方法对测试数据集提供的多个输入行进行预测。

使用 [CreateEnumerable()](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A) 方法和以下代码将 `transformedData` 转换为强类型 `IEnumerable`，以方便显示：

[!code-csharp[CreateEnumerable1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CreateEnumerable1)]

使用以下 <xref:System.Console.WriteLine?displayProperty=nameWithType> 代码创建显示标头行：

[!code-csharp[DisplayHeader1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayHeader1)]

将在峰值检测结果中显示以下信息：

* `Alert` 指示给定数据点的峰值警报。

* `Score` 是数据集中给定数据点的 `ProductSales` 值。

* `P-Value`“P”代表概率， 其指示此数据点为异常数据点的可能性。 

使用以下代码循环访问 `predictions` `IEnumerable` 并显示结果：

[!code-csharp[DisplayResults1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayResults1)]

## <a name="spike-detection-results"></a>峰值检测结果

结果应如下所示。 处理期间将显示消息。 你可能会看到警告或处理消息。 为清楚起见，已经从下面的结果中删除这些内容。

```console
Detect temporary changes in pattern
=============== Training the model ===============
=============== End of training process ===============
Alert   Score   P-Value
0       271.00  0.50
0       150.90  0.00
0       188.10  0.41
0       124.30  0.13
0       185.30  0.47
0       173.50  0.47
0       236.80  0.19
0       229.50  0.27
0       197.80  0.48
0       127.90  0.13
1       341.50  0.00 <-- Spike detected
0       190.90  0.48
0       199.30  0.48
0       154.50  0.24
0       215.10  0.42
0       278.30  0.19
0       196.40  0.43
0       292.00  0.17
0       231.00  0.45
0       308.60  0.18
0       294.90  0.19
1       426.60  0.00 <-- Spike detected
0       269.50  0.47
0       347.30  0.21
0       344.70  0.27
0       445.40  0.06
0       320.90  0.49
0       444.30  0.12
0       406.30  0.29
0       442.40  0.21
1       580.50  0.00 <-- Spike detected
0       412.60  0.45
1       687.00  0.01 <-- Spike detected
0       480.30  0.40
0       586.30  0.20
0       651.90  0.14
```

## <a name="change-point-detection"></a>更改点检测

`Change points` 是时序事件流值分布的持续更改，例如级别更改和趋势。 这些持续更改的持续时间比 `spikes` 的持续时间长得多，可能指示灾难性事件。 `Change points` 通常对肉眼不可见，但可以使用诸如以下方法的方法在数据中检测到。  下图是更改点检测的示例：

![ChangePointDetection](./media/sales-anomaly-detection/ChangePointDetection.png)

### <a name="create-the-detectchangepoint-method"></a>创建 DetectChangepoint() 方法

将以下调用添加到 `DetectChangepoint()` 方法作为 `Main()` 方法的下一行代码：

[!code-csharp[CallDetectChangepoint](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CallDetectChangepoint)]

`DetectChangepoint()` 方法执行以下任务：

* 定型模型。
* 根据历史销售数据检测更改点。
* 显示结果。

使用下面的代码紧随 `Main()` 方法后创建 `DetectChangepoint()` 方法：

```csharp
static void DetectChangepoint(MLContext mlContext, int docSize, IDataView productSales)
{

}
```

[iidChangePointEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidChangePointEstimator) 用于训练模型来进行更改点检测。 使用以下代码将其添加到 `DetectChangepoint()` 方法中：

[!code-csharp[AddChangepointTrainer](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddChangepointTrainer)]

如之前一样，通过在 `DetectChangePoint()` 方法中添加以下代码作为下一代码行来使模型适应 `productSales` 数据：

[!code-csharp[TrainModel2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TrainModel2)]

使用 `Transform()` 方法通过将以下代码添加到 `DetectChangePoint()` 来转换 `Training` 数据：

[!code-csharp[TransformData2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TransformData2)]

如之前一样，使用 `CreateEnumerable()` 方法和以下代码将 `transformedData` 转换为强类型 `IEnumerable`，以方便显示：

[!code-csharp[CreateEnumerable2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CreateEnumerable2)]

使用以下代码创建显示标头，用作 `DetectChangePoint()` 方法中的下一行：

[!code-csharp[DisplayHeader2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayHeader2)]

将在更改点检测结果中显示以下信息：

* `Alert` 指示给定数据点的更改点警报。
* `Score` 是数据集中给定数据点的 `ProductSales` 值。
* `P-Value`“P”代表概率， 其指示此数据点为异常数据点的可能性。 
* `Martingale value` 用于根据 P 值序列识别数据点的“奇怪”程度。  

使用以下代码循环访问 `predictions` `IEnumerable` 并显示结果：

[!code-csharp[DisplayResults2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayResults2)]

## <a name="change-point-detection-results"></a>更改点检测结果

结果应如下所示。 处理期间将显示消息。 你可能会看到警告或处理消息。 为清楚起见，已经从下面的结果中删除这些内容。

```console
Detect Persistent changes in pattern
=============== Training the model Using Change Point Detection Algorithm===============
=============== End of training process ===============
Alert   Score   P-Value Martingale value
0       271.00  0.50    0.00
0       150.90  0.00    2.33
0       188.10  0.41    2.80
0       124.30  0.13    9.16
0       185.30  0.47    9.77
0       173.50  0.47    10.41
0       236.80  0.19    24.46
0       229.50  0.27    42.38
1       197.80  0.48    44.23 <-- alert is on, predicted changepoint
0       127.90  0.13    145.25
0       341.50  0.00    0.01
0       190.90  0.48    0.01
0       199.30  0.48    0.00
0       154.50  0.24    0.00
0       215.10  0.42    0.00
0       278.30  0.19    0.00
0       196.40  0.43    0.00
0       292.00  0.17    0.01
0       231.00  0.45    0.00
0       308.60  0.18    0.00
0       294.90  0.19    0.00
0       426.60  0.00    0.00
0       269.50  0.47    0.00
0       347.30  0.21    0.00
0       344.70  0.27    0.00
0       445.40  0.06    0.02
0       320.90  0.49    0.01
0       444.30  0.12    0.02
0       406.30  0.29    0.01
0       442.40  0.21    0.01
0       580.50  0.00    0.01
0       412.60  0.45    0.01
0       687.00  0.01    0.12
0       480.30  0.40    0.08
0       586.30  0.20    0.03
0       651.90  0.14    0.09
```

祝贺你！ 现在已成功生成用于检测销售数据中的峰值和更改点异常情况的机器学习模型。

可以在 [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection) 存储库中找到本教程的源代码。

在本教程中，你将了解：
> [!div class="checklist"]
> * 加载数据
> * 训练模型用于峰值异常情况检测
> * 使用经过训练的模型检测峰值异常情况
> * 训练模型用于更改点异常情况检测
> * 使用经过训练的模型检测更改点异常情况

## <a name="next-steps"></a>后续步骤

请查看机器学习示例 GitHub 存储库，以探索能耗异常情况检测示例。
> [!div class="nextstepaction"]
> [dotnet/machinelearning-samples GitHub 存储库](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/AnomalyDetection_PowerMeterReadings)

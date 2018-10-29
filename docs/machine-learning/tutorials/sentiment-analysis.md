---
title: 在情绪分析二元分类方案中使用 ML.NET
description: 了解如何在二元分类方案中使用 ML.NET，以了解如何使用情绪预测来采取相应措施。
ms.date: 06/04/2018
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: fd0a1ad246c6d50db35e3d0f0332a82b256902c1
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/19/2018
ms.locfileid: "49453157"
---
# <a name="tutorial-use-mlnet-in-a-sentiment-analysis-binary-classification-scenario"></a>教程：在情绪分析二元分类方案中使用 ML.NET

> [!NOTE]
> 本主题引用 ML.NET（目前处于预览状态），且材料可能会更改。 有关详细信息，请访问 [ML.NET 简介](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)。

此示例教程通过在 Visual Studio 2017 中使用 C# 的 .NET Core 控制台应用程序，演示如何使用 ML.NET 创建情绪分类器。

在本教程中，你将了解：
> [!div class="checklist"]
> * 了解问题
> * 选择适当的机器学习任务
> * 准备数据
> * 创建学习管道
> * 加载分类器
> * 定型模型
> * 使用不同数据集评估模型
> * 使用模型预测测试数据结果

## <a name="sentiment-analysis-sample-overview"></a>情绪分析示例概述

该示例是使用 ML.NET 定型模型的控制台应用，以将情绪分类和预测为正面或负面。 它还使用第二个数据集对模型进行评估，以进行质量分析。 情绪数据集来自 WikiDetox 项目。

## <a name="prerequisites"></a>系统必备

* 安装了“.NET Core 跨平台开发”工作负载的 [Visual Studio 2017 15.6 或更高版本](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)。

* [Wikipedia detox 行数据制表符分隔文件 (wikiPedia-detox-250-line-data.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv)。
* [Wikipedia detox 行测试制表符分隔文件 (wikipedia-detox-250-line-test.tsv)](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv)。

## <a name="machine-learning-workflow"></a>机器学习工作流

本教程后面介绍了机器学习工作流，使该过程能够有序地进行。

工作流阶段如下所示：

1. **了解问题**
2. **引入数据**
3. **数据预处理和特征工程**
4. **定型和预测模型**
5. **评估模型**
6. **模型操作化**

### <a name="understand-the-problem"></a>了解问题

首先需要了解问题，因此可以将其分解为能够支持构建和定型模型的几个部分。 分解问题可以预测和评估结果。

本教程中的问题是了解传入网站评论情绪以采取相应的措施。

可以将问题分解为你想要对模型进行定型的数据的情绪文本和情绪值，以及可以评估和以操作状态使用的预期情绪值。

然后，需要确定情绪，这将帮助你进行机器学习任务选择。

## <a name="select-the-appropriate-machine-learning-task"></a>选择适当的机器学习任务

通过此问题，你将了解以下情况：

定型数据：网站评论可以是正面或负面（情绪）。
预测新网站评论的情绪，正面或负面，如以下示例所示：

* 请避免向 Wikipedia 添加无意义的内容。
* 他是最棒的，且文章应如此表述。

分类机器学习任务最适合此方案。

### <a name="about-the-classification-task"></a>有关分类任务

分类是一项机器学习任务，它使用数据来确定某个项或数据行的类别、类型或类。 例如，可以使用分类：

* 识别情绪为正面还是负面。
* 将电子邮件分类为垃圾邮件或正常邮件。
* 确定患者的实验室样本是否癌变。
* 根据客户对销售活动的反应倾向对客户进行分类。

分类任务通常为以下类型之一：

* 二元：A 或 B。
* 多类：可以通过使用单个模型来预测多个类别。

## <a name="create-a-console-application"></a>创建控制台应用程序

1. 打开 Visual Studio 2017。 从菜单栏中选择“文件” > “新建” > “项目”。 在“新项目”对话框中，依次选择“Visual C#”和“.NET Core”节点。 然后，选择“控制台应用程序(.NET Core)”项目模板。 在“名称”文本框中，键入“SentimentAnalysis”，然后选择“确定”按钮。

2. 在项目中创建一个名为“数据”的目录来保存数据集文件：

    在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新文件夹”。 键入“数据”，然后按 Enter。

3. 安装“Microsoft.ML NuGet 包”：

    在“解决方案资源管理器”中，右键单击项目，然后选择“管理 NuGet 包”。 将“nuget.org”选择为“包源”，选择“浏览”选项卡并搜索“Microsoft.ML”，在列表中选择该包，然后选择“安装”按钮。 选择“预览更改”对话框上的“确定”按钮，如果你同意所列包的许可条款，则选择“接受许可”对话框上的“我接受”按钮。

### <a name="prepare-your-data"></a>准备数据

1. 下载 [WikiPedia detox-250-line-data.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-data.tsv) 和 [wikipedia-detox-250-line-test.tsv](https://github.com/dotnet/machinelearning/blob/master/test/data/wikipedia-detox-250-line-test.tsv) 数据集并将它们保存到先前创建的“数据”文件夹。 第一个数据集定型机器学习模型，第二个数据集可用来评估模型的准确度。

2. 在“解决方案资源管理器”中，右键单击每个 \*.tsv 文件，然后选择“属性”。 在“高级”下，将“复制到输出目录”的值更改为“如果较新则复制”。

### <a name="create-classes-and-define-paths"></a>创建类和定义路径

将以下附加的 `using` 语句添加到“Program.cs”文件顶部：

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#1 "Add necessary usings")]

需要创建三个全局字段，来保存最近下载的文件的路径：

* `_dataPath` 具有用于定型模型的数据集路径。
* `_testDataPath` 具有用于评估模型的数据集路径。
* `_modelPath` 具有在其中保存定型模型的路径。

将以下代码添加到 `Main` 方法上方的行中，以指定这些路径：

[!code-csharp[Declare file variables](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#2 "Declare variables to store data files")]

需要为输入数据和预测创建一些类。 向项目添加一个新类：

1. 在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新项”。

1. 在“添加新项”对话框中，选择“类”并将“名称”字段更改为“SentimentData.cs”。 然后，选择“添加”按钮。

    “SentimentData.cs”文件随即在代码编辑器中打开。 将下面的 `using` 语句添加到 SentimentData.cs 的顶部：

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#1 "Add necessary usings")]

删除现有类定义并向“SentimentData.cs”文件添加以下代码，其中有两个类 `SentimentData` 和 `SentimentPrediction`：

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#2 "Declare data record types")]

`SentimentData` 是输入数据集类，且具有带正或负情绪值的 `float` (`Sentiment`) 和评论字符串 (`SentimentText`)。 这两个字段均有随附的 `Column` 属性。 此属性描述数据文件中每个字段的顺序，以及哪个是 `Label` 字段。 `SentimentPrediction` 是在定型模型后用于预测的类。 它有一个布尔值 (`Sentiment`) 和一个 `PredictedLabel` `ColumnName` 属性。 `Label` 用于创建和定型模型，并且与第二个数据集结合使用来评估模型。 `PredictedLabel` 在预测和评估过程中使用。 对于计算，将使用带定型数据的输入、预测值和模型。

在“Program.cs”文件中，通过将 `void` 替换为 `async Task` 来更改 `Main` 方法签名，如以下示例所示：

```csharp
static async Task Main(string[] args) 
{

}
```

将 `async` 添加到带有 <xref:System.Threading.Tasks.Task> 返回类型的 `Main`，因为稍后你会将模型保存到一个 zip 文件，且该过程需要等待，直到此外部任务完成。

> [!NOTE]
> *异步 Main* 方法使你能够在 `Main` 方法中使用 `await` 关键字。 有关详细信息，请参阅 C# 编程指南中的[异步 Main](../../../docs/csharp/programming-guide/main-and-command-args/index.md) 主题。

用下面 `Main` 方法中的代码替换 `Console.WriteLine("Hello World!")` 行：

[!code-csharp[Train](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#3 "Train your model")]

`Train` 方法执行以下任务：

* 加载或引入数据。
* 预处理和特征化数据。
* 定型模型。
* 根据测试数据预测情绪。

使用下面的代码紧随 `Main` 方法后创建 `Train` 方法：

```csharp
public static async Task<PredictionModel<SentimentData, SentimentPrediction>> Train()
{

}
```

## <a name="ingest-the-data"></a>引入数据

初始化 <xref:Microsoft.ML.Legacy.LearningPipeline> 的新实例以包含数据加载、数据处理/特征化和模型。 将以下代码添加为 `Train` 方法的首行：

[!code-csharp[LearningPipeline](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#5 "Create a learning pipeline")]

<xref:Microsoft.ML.Legacy.Data.TextLoader> 对象是管道的第一部分，并加载定型文件数据。

[!code-csharp[TextLoader](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#6 "Add a text loader to the pipeline")]

## <a name="data-preprocess-and-feature-engineering"></a>数据预处理和特征工程

预处理和清除数据任务至关重要，需要首先执行才能将数据集有效地用于机器学习。 原始数据通常嘈杂不可靠，并且可能缺少值。 在没有这些建模任务的情况下使用数据会产生误导性结果。 可以通过 ML.NET 的转换管道撰写一组自定义转换，在定型或测试数据之前将其应用到数据。 转换的主要目的是为了特征化数据。 转换管道的优点是，在转换管道定义之后，保存管道以将其应用于测试数据。

应用 <xref:Microsoft.ML.Legacy.Transforms.TextFeaturizer> 将 `SentimentText` 列转换为机器学习算法使用的名为 `Features` 的[数值向量](../resources/glossary.md#numerical-feature-vector)。 这是预处理/特征化步骤。 使用 ML.NET 中可用的其他组件可以在使用模型时生成更佳结果。 将 `TextFeaturizer` 添加到管道作为下一行代码：

[!code-csharp[TextFeaturizer](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#7 "Add a TextFeaturizer to the pipeline")]

## <a name="choose-a-learning-algorithm"></a>选择学习算法

<xref:Microsoft.ML.Legacy.Trainers.FastTreeBinaryClassifier> 对象是一个将在此管道中使用的决策树学习器。 与特征化步骤类似，尝试使用 ML.NET 中提供的其他学习器和更改其参数会导致不同结果。 对于优化，可以设置[超参数](../resources/glossary.md#hyperparameter)，如 <xref:Microsoft.ML.Legacy.Trainers.FastTreeBinaryClassifier.NumTrees>、<xref:Microsoft.ML.Legacy.Trainers.FastTreeBinaryClassifier.NumLeaves> 和 <xref:Microsoft.ML.Legacy.Trainers.FastTreeBinaryClassifier.MinDocumentsInLeafs>。 这些超参数是在任何影响模型的情况下设置的，并且特定于模型。 它们用于优化决策树的性能，因此较大的值可以会对性能产生负面影响。

将以下代码添加到 `Train` 方法中：

[!code-csharp[BinaryClassifier](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#8 "Add a fast binary tree classifier")]

## <a name="train-the-model"></a>定型模型

根据已加载和转换的数据集定型模型 <xref:Microsoft.ML.Legacy.PredictionModel%602>。 `pipeline.Train<SentimentData, SentimentPrediction>()` 定型管道（加载数据、定型特征化程序和学习器）。 在发生这种情况之前不会执行此试验。

将以下代码添加到 `Train` 方法中：

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#9 "Train the model")]

### <a name="save-and-return-the-model-trained-to-use-for-evaluation"></a>保存并返回定型模型以用于评估

此时，你具有可以集成到任何现有或新 .NET 应用程序的模型。 若要在返回之前将模型保存到 .zip 文件，请将下面的代码添加到 `Train` 中的下一行：

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#10 "Save the model")]

在 `Train` 方法末尾返回模型。

[!code-csharp[ReturnModel](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#11 "Return the model")]

## <a name="evaluate-the-model"></a>评估模型

你已经创建和定型模型，现在需要使用不同的数据集对其进行评估以保证质量和进行验证。 在 `Evaluate` 方法中，将传入在 `Train` 中创建的模型以进行评估。 紧随 `Train` 后创建 `Evaluate` 方法，如以下代码所示：

```csharp
public static void Evaluate(PredictionModel<SentimentData, SentimentPrediction> model)
{

}
```

`Evaluate` 方法执行以下任务：

* 加载测试数据集。
* 创建二进制计算器。
* 评估模型并创建指标。
* 显示指标。

使用下面的代码，在 `Train` 方法调用的正下方，从 `Main` 方法中添加对新方法的调用：

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#12 "Call the Evaluate method")]

<xref:Microsoft.ML.Legacy.Data.TextLoader> 类使用相同的架构加载新的测试数据集。 可以将此数据集作为质量检查来评估模型。 将以下代码添加到 `Evaluate` 方法中：

[!code-csharp[LoadText](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#13 "Load the test dataset")]

<xref:Microsoft.ML.Legacy.Models.BinaryClassificationEvaluator> 对象使用指定数据集计算 `PredictionModel` 的质量指标。 要查看这些指标，使用以下代码将计算器添加为 `Evaluate` 方法中的下一行：

[!code-csharp[BinaryEvaluator](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#14 "Create the binary evaluator")]

<xref:Microsoft.ML.Legacy.Models.BinaryClassificationMetrics> 包含由二元分类计算器计算出的总体指标。 若要显示这些指标来确定模型质量，需要先获取指标。 添加以下代码：

[!code-csharp[CreateMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#15 "Evaluate the model and create metrics")]

### <a name="displaying-the-metrics-for-model-validation"></a>显示用于模型验证的指标

使用下面的代码显示指标、共享结果，然后处理它们：

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#16 "Display selected metrics")]

## <a name="predict-the-test-data-outcomes-with-the-model"></a>使用模型预测测试数据结果

使用下面的代码紧随 `Evaluate` 方法后创建 `Predict` 方法：

```csharp
public static void Predict(PredictionModel<SentimentData, SentimentPrediction> model)
{

}
```

`Predict` 方法执行以下任务：

* 创建测试数据。
* 根据测试数据预测情绪。
* 结合测试数据和预测进行报告。
* 显示预测结果。

使用下面的代码，在 `Evaluate` 方法调用的正下方，从 `Main` 方法中添加对新方法的调用：

[!code-csharp[CallEvaluate](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#17 "Call the Predict method")]

添加一些评论，以测试 `Predict` 方法中的定型模型预测：

[!code-csharp[PredictionData](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#18 "Create test data for predictions")]

现在你有一个模型，可以使用它来预测使用 <xref:Microsoft.ML.Legacy.PredictionModel.Predict%2A?displayProperty=nameWithType> 方法的评论数据的正面或负面情绪。 要获得预测，请使用新数据上的 `Predict`。 请注意，输入数据是一个字符串，且模型包含特征化。 管道在定型和预测期间同步。 不必专门为预测编写预处理/特征化代码，并且相同 API 负责批处理和一次性预测。

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#19 "Create predictions of sentiments")]

### <a name="model-operationalization-prediction"></a>模型操作化：预测

显示 `SentimentText` 和相应的情绪预测以便共享结果，并采取相应措施。 这称为操作化，使用返回的数据作为操作策略的一部分。 使用以下 <xref:System.Console.WriteLine?displayProperty=nameWithType> 代码创建结果标头：

[!code-csharp[OutputHeaders](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#20 "Display prediction outputs")]

在显示预测结果之前，将情绪和预测结合在一起以查看原始评论及其预测情绪。 下面的代码使用 <xref:System.Linq.Enumerable.Zip%2A> 方法来实现此目的，因此请在下一步添加以下代码：

[!code-csharp[BuildTuples](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#21 "Build the pairs of sentiment data and predictions")]

将 `SentimentText` 和 `Sentiment` 合并到一个类后，现在可以使用 <xref:System.Console.WriteLine?displayProperty=nameWithType> 方法来显示结果：

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#22 "Display the predictions")]

因为推测的元组元素名称是 C# 7.1 中的新功能，且项目的默认语言版本为 C# 7.0，你需要将语言版本更改为 C# 7.1 或更高版本。
要完成此操作，右键单击“解决方案资源管理器”中的项目节点，然后选择“属性”。 选择**生成**选项卡并选择**高级**按钮。 在下拉列表中，选择“C# 7.1”（或更高版本）。 选择“确定”按钮。

## <a name="results"></a>结果

结果应如下所示。 管道处理期间，会显示消息。 你可能会看到警告或处理消息。 为清楚起见，已经从下面的结果中删除这些内容。

```

PredictionModel quality metrics evaluation
------------------------------------------
Accuracy: 66.67%
Auc: 94.44%
F1Score: 75.00%

Sentiment Predictions
---------------------
Sentiment: Please refrain from adding nonsense to Wikipedia. | Prediction: Negative
Sentiment: He is the best, and the article should say that. | Prediction: Positive

```

祝贺你！ 现在，你已成功生成用于分类和预测消息情绪的机器学习模型。 可以在 [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) 存储库中找到本教程的源代码。

## <a name="next-steps"></a>后续步骤

在本教程中，你将了解：
> [!div class="checklist"]
> * 了解问题
> * 选择适当的机器学习任务
> * 准备数据
> * 创建学习管道
> * 加载分类器
> * 定型模型
> * 使用不同数据集评估模型
> * 使用模型预测测试数据结果

进入下一教程了解详细信息
> [!div class="nextstepaction"]
> [出租车费预测器](taxi-fare.md)

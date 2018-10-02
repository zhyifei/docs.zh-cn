---
title: 使用 ML.NET 生成鸢尾花数据群集（聚类分析）
description: 了解如何在聚类分析方案中使用 ML.NET
author: pkulikov
ms.author: johalex
ms.date: 07/02/2018
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: 46db9dc7ff425c483f1a9f61da5e806e598b16d5
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2018
ms.locfileid: "37937162"
---
# <a name="tutorial-use-mlnet-to-cluster-iris-flowers-clustering"></a>教程：使用 ML.NET 生成鸢尾花数据群集（聚类分析）

> [!NOTE]
> 本主题引用 ML.NET（目前处于预览状态），且材料可能会更改。 有关详细信息，请参阅 [ML.NET 简介](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)。

本教程演示如何使用 ML.NET 为[鸢尾花数据集](https://en.wikipedia.org/wiki/Iris_flower_data_set)构建[聚类分析模型](../resources/tasks.md#clustering)。

在本教程中，你将了解：
> [!div class="checklist"]
> - 了解问题
> - 选择适当的机器学习任务
> - 准备数据
> - 加载和转换数据
> - 选择学习算法
> - 定型模型
> - 使用预测模型

## <a name="prerequisites"></a>系统必备

- 安装了“.NET Core 跨平台开发”工作负载的 [Visual Studio 2017 15.6 或更高版本](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)。

## <a name="understand-the-problem"></a>了解问题

此问题的本质即基于花卉特征将鸢尾花数据归入不同的组。 这些特征包括：花萼的长度和宽度以及花瓣的长度和宽度。 此教程假设每朵花的类型都是未知的。 需通过这些特征了解数据集的结构，并预测数据实例与此结构的拟合程度。

## <a name="select-the-appropriate-machine-learning-task"></a>选择适当的机器学习任务

鉴于不知道每朵花属于哪个分组，应选择[非监管式机器学习](../resources/glossary.md#unsupervised-machine-learning)任务。 为将数据归入不同的组，并使同一组中的元素互相之间更为相似（与其他组中的元素相比），应使用[聚类分析](../resources/tasks.md#clustering)机器学习任务。

## <a name="create-a-console-application"></a>创建控制台应用程序

1. 打开 Visual Studio 2017。 从菜单栏中选择“文件” > “新建” > “项目”。 在“新项目”对话框中，依次选择“Visual C#”和“.NET Core”节点。 然后，选择“控制台应用程序(.NET Core)”项目模板。 在“名称”文本框中，键入“IrisClustering”，然后选择“确定”按钮。

1. 在项目中创建一个名为“数据”的目录来保存数据集和模型文件：

    在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新文件夹”。 键入“数据”，然后按 Enter。

1. 安装“Microsoft.ML NuGet”包：

    在“解决方案资源管理器”中，右键单击项目，然后选择“管理 NuGet 包”。 将“nuget.org”选择为“包源”，选择“浏览”选项卡并搜索“Microsoft.ML”，在列表中选择该包，然后选择“安装”按钮。 选择“预览更改”对话框上的“确定”按钮，如果你同意所列包的许可条款，则选择“接受许可”对话框上的“我接受”按钮。

## <a name="prepare-the-data"></a>准备数据

1. 下载 [](https://github.com/dotnet/machinelearning/blob/master/test/data/iris.data) 数据集并将其保存至在上一步中创建的“数据”文件夹。 若要详细了解鸢尾花数据集，请参阅[鸢尾花数据集](https://en.wikipedia.org/wiki/Iris_flower_data_set)维基百科页面，以及该数据集的源[鸢尾花数据集](http://archive.ics.uci.edu/ml/datasets/Iris)页面。

1. 在“解决方案资源管理器”中，右键单击“iris.data”文件并选择“属性”。 在“高级”下，将“复制到输出目录”的值更改为“如果较新则复制”。

该 iris.data 文件包含五列，分别代表以下内容：

- 花萼长度（厘米）
- 花萼宽度（厘米）
- 花瓣长度（厘米）
- 花瓣宽度（厘米）
- 鸢尾花类型

考虑到聚类分析示例，本教程忽略最后一列。

## <a name="create-data-classes"></a>创建数据类

创建输入数据和预测类：

1. 在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新项”。
1. 在“添加新项”对话框中，选择“类”并将“名称”字段更改为“IrisData.cs”。 然后，选择“添加”按钮。
1. 将以下 `using` 指令添加到新文件：

   [!code-csharp[Add necessary usings](../../../samples/machine-learning/tutorials/IrisClustering/IrisData.cs#1)]

删除现有类定义并向“IrisData.cs”文件添加以下代码，其中定义了两个类 `IrisData` 和 `ClusterPrediction`：

[!code-csharp[Define data classes](../../../samples/machine-learning/tutorials/IrisClustering/IrisData.cs#2)]

`IrisData` 是输入数据类，并且具有针对数据集每个特征的定义。 使用 [Column](xref:Microsoft.ML.Runtime.Api.ColumnAttribute) 属性在数据集文件中指定源列的索引。

`ClusterPrediction` 类表示应用到 `IrisData` 实例的聚类分析模型的输出。 使用 [ColumnName](xref:Microsoft.ML.Runtime.Api.ColumnNameAttribute) 属性将 `PredictedClusterId` 和 `Distances` 字段分别绑定至 PredictedLabel 和 Score 列。 在聚类分析任务中，这些列具有以下含义：

- **PredictedLabel** 列包含所预测的群集的 ID。
- **Score** 列包含一个数组，该数组中的数与群集形心之间的距离为欧氏距离的平方。 该数组的长度等于群集数。

> [!NOTE]
> 使用 `float` 类型来表示输入和预测数据类中的浮点值。

## <a name="define-data-and-model-paths"></a>定义数据和模型路径

返回到 Program.cs 文件并添加两个字段，以保存数据集文件以及用于保存模型的文件的路径：

- `_dataPath` 包含具有用于定型模型的数据集的文件的路径。
- `_modelPath` 包含用于存储定型模型的文件的路径。

将以下代码添加到 `Main` 方法上方，以指定这些路径：

[!code-csharp[Initialize paths](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#1)]

要编译前面的代码，请将以下 `using` 指令添加到 Program.cs 文件顶部：

[!code-csharp[Add usings for paths](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#2)]

## <a name="create-a-learning-pipeline"></a>创建学习管道

将以下附加 `using` 指令添加到 Program.cs 文件顶部：

[!code-csharp[Add Microsoft.ML usings](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#3)]

将 `Main` 方法中的 `Console.WriteLine("Hello World!")` 替换为以下代码：

[!code-csharp[Call the Train method](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#4)]

`Train` 方法定型模型。 使用以下代码在 `Main` 方法下创建该方法：

```csharp
private static PredictionModel<IrisData, ClusterPrediction> Train()
{

}
```

学习管道加载所有数据和所需的算法来定型模型。 将以下代码添加到 `Train` 方法：

[!code-csharp[Initialize pipeline](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#5)]

## <a name="load-and-transform-data"></a>加载和转换数据

第一个步骤是加载定型数据集。 在本例中，定型数据集存储在具有 `_dataPath` 字段所定义路径的文本文件中。 文件中的列用逗号 (",") 分割。 将以下代码添加到 `Train` 方法：

[!code-csharp[Add step to load data](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#6)]

下一步是使用 <xref:Microsoft.ML.Transforms.ColumnConcatenator> 转换类将所有特征列合并到“特征”列。 默认情况下，学习算法仅处理“特征”列的特征。 添加以下代码：

[!code-csharp[Add step to concatenate columns](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#7)]

## <a name="choose-a-learning-algorithm"></a>选择学习算法

在将数据添加到管道，并将其转换为正确的输入格式之后，可以选择学习算法（学习器）。 学习器定型模型。 ML.NET 提供一种 <xref:Microsoft.ML.Trainers.KMeansPlusPlusClusterer> 学习器，该学习器通过一种经过改进的、用于选择初始群集形心的方法来实现 [k-means 算法](https://en.wikipedia.org/wiki/K-means_clustering)。

将下面的代码添加到在上一步中添加的数据处理代码后面的 `Train` 方法中：

[!code-csharp[Add a learner step](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#8)]

使用 <xref:Microsoft.ML.Trainers.KMeansPlusPlusClusterer.K?displayProperty=nameWithType> 属性指定群集数。 上述代码指定该数据集应拆分为三个群集。

## <a name="train-the-model"></a>定型模型

前述部分中添加的步骤准备了用于定型的管道，但尚未执行。 `pipeline.Train<TInput, TOutput>` 方法生成的模型接收 `TInput` 类型实例并输出 `TOutput` 类型实例。 将以下代码添加到 `Train` 方法：

[!code-csharp[Train the model and return](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#9)]

### <a name="save-the-model"></a>保存模型

此时，你具有可以集成到任何现有或新 .NET 应用程序的模型。 若要将模型保存到 .zip 文件，请将下面的代码添加到调用 `Train` 方法下的 `Main` 方法中：

[!code-csharp[Save the model](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#10)]

在 `Main` 方法中使用 `await` 意味着 `Main` 方法必须具有 `async` 修饰符并返回 `Task`：

[!code-csharp[Make the Main method async](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#11)]

还需要将以下 `using` 指令添加到 Program.cs 文件顶部：

[!code-csharp[Add System.Threading.Tasks using](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#12)]

由于 `async Main` 方法是 C# 7.1 中的新增功能，且项目的默认语言版本为 C# 7.0，因此需要将语言版本更改为 C# 7.1 或更高版本。 要完成此操作，右键单击“解决方案资源管理器”中的项目节点，然后选择“属性”。 选择**生成**选项卡并选择**高级**按钮。 在下拉列表中，选择“C# 7.1”（或更高版本）。 选择“确定”按钮。

## <a name="use-the-model-for-predictions"></a>使用预测模型

将 `TestIrisData` 类创建到房屋测试数据实例：

1. 在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新项”。
1. 在“添加新项”对话框中，选择“类”并将“名称”字段更改为“TestIrisData.cs”。 然后，选择“添加”按钮。
1. 将类修改为静态，如下面的示例所示：

   [!code-csharp[Make class static](../../../samples/machine-learning/tutorials/IrisClustering/TestIrisData.cs#1)]

本教程引入此类中的一个鸢尾花数据实例。 可以添加其他方案来体验此模型。 将下面的代码添加到 `TestIrisData` 类中：

[!code-csharp[Test data](../../../samples/machine-learning/tutorials/IrisClustering/TestIrisData.cs#2)]

若要查找指定项所属的群集，请返回至 Program.cs 文件并将以下代码添加进 `Main` 方法：

[!code-csharp[Predict and output results](../../../samples/machine-learning/tutorials/IrisClustering/Program.cs#13)]

运行该程序以查看哪个群集包含所指定的数据实例，以及从该实例到群集形心的距离的平方值。 结果应如下所示。 在进行管道处理时，可能会显示警告或处理消息。 为清楚起见，已经从下面的输出中删除这些内容。

```text
Cluster: 2
Distances: 0.4192338 0.0008847713 0.9660053
```

祝贺你！ 现已成功地生成用于鸢尾花聚类分析的机器学习模型并将其用于预测。 可以在 [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/IrisClustering) GitHub 存储库中找到本教程的源代码。

## <a name="next-steps"></a>后续步骤

在本教程中，你将了解：
> [!div class="checklist"]
> - 了解问题
> - 选择适当的机器学习任务
> - 准备数据
> - 加载和转换数据
> - 选择学习算法
> - 定型模型
> - 使用预测模型

查看我们的 GitHub 存储库以继续学习，并找到更多示例。
> [!div class="nextstepaction"]
> [dotnet/machinelearning GitHub 存储库](https://github.com/dotnet/machinelearning/)

---
title: 教程：使用 TensorFlow 生成 ML.NET 自定义图像分类器
description: 了解如何通过重用预定型 TensorFlow 模型，在 TensorFlow 迁移学习方案中生成 ML.NET 自定义图像分类器来分类图像。
ms.date: 05/06/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: e248c5ae73281ed6cd492592ba4a51791db75aa2
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2019
ms.locfileid: "65593432"
---
# <a name="tutorial-build-an-mlnet-custom-image-classifier-with-tensorflow"></a>教程：使用 TensorFlow 生成 ML.NET 自定义图像分类器

本示例教程展示了如何使用已定型的图像分类器 `TensorFlow` 模型来生成新的自定义模型，以将图像分类为若干类别。

如果可以重用已预定型的模型来解决类似问题，并重新定型此模型的所有层或部分层来解决问题，那该有多好！ 重用部分已定型的模型来生成新模型的技术称为[迁移学习](https://en.wikipedia.org/wiki/Transfer_learning)。

从头开始定型[图像分类](https://en.wikipedia.org/wiki/Outline_of_object_recognition)模型需要设置数百万个参数、大量已标记的定型数据和海量计算资源（数百个 GPU 小时）。 虽然不如从头开始定型自定义模型有效，但借助迁移学习，可以通过处理数千张图像（与数百万张已标记的图像相比）来简化此过程，并非常快速地生成自定义模型（在没有 GPU 的计算机上一小时内完成）。

在本教程中，你将了解：
> [!div class="checklist"]
> * 了解问题
> * 重用和优化预定型模型
> * 分类图像

## <a name="image-classification-sample-overview"></a>图像分类示例概述

此示例是一个控制台应用，使用 ML.NET 并通过重用预定型模型来生成图像分类器，以对定型数据很少的图像进行分类。

可以在 [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) 存储库中找到本教程的源代码。

## <a name="prerequisites"></a>系统必备

* 安装了“.NET Core 跨平台开发”工作负载的 [Visual Studio 2017 15.6 或更高版本](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017)。

* Microsoft.ML 1.0.0 Nuget 包
* Microsoft.ML.ImageAnalytics 1.0.0 Nuget 包
* Microsoft.ML.TensorFlow 0.12.0 Nuget 包

* [教程资产目录 .ZIP 文件](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip)

* [InceptionV3 机器学习模型](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip)

## <a name="select-the-appropriate-machine-learning-task"></a>选择适当的机器学习任务

[深度学习](https://en.wikipedia.org/wiki/Deep_learning)是机器学习的一部分，颠覆了计算机视觉和语音识别等领域。

深度学习模型是使用包含多个学习层的大量[已标记的数据](https://en.wikipedia.org/wiki/Labeled_data)和[神经网络](https://en.wikipedia.org/wiki/Artificial_neural_network)来定型。 深度学习：

* 执行计算机视觉等一些任务的效果更好。

* 处理大量数据的效果好。

图像分类是常见的机器学习任务，可便于自动将图像分类为多个类别，比如：

* 检测图像中是否有人脸。
* 检测是猫还是狗。

 或者在以下图像中，确定图像是食物、玩具还是家用电器：

![披萨图像](./media/image-classification/220px-Pepperoni_pizza.jpg)
![泰迪熊图像](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![烤面包机图像](./media/image-classification/193px-Broodrooster.jpg)

>[!Note]
> 上面的图像属于维基共享资源，并按如下方式进行属性化：
>
> * “220px-Pepperoni_pizza.jpg”公有领域，https://commons.wikimedia.org/w/index.php?curid=79505
> * “119px-Nalle_-_a_small_brown_teddy_bear.jpg”作者为 [Jonik](https://commons.wikimedia.org/wiki/User:Jonik) - 独自拍摄，CC BY-SA 2.0，https://commons.wikimedia.org/w/index.php?curid=48166。
> * “193px-Broodrooster.jpg”作者为 [M.Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972) - 自有作品，CC BY-SA 3.0，https://commons.wikimedia.org/w/index.php?curid=27403

迁移学习包括多种策略，如重新定型所有层策略和倒数第二层策略。 本教程将介绍并展示如何使用倒数第二层策略。 倒数第二层策略重用已预定型的模型来解决具体问题。 然后，此策略重新定型这个模型的最后一层来解决新问题。 重用预定型模型作为新模型的一部分将节省大量时间和资源。

图像分类模型重用 [Inception 模型](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip)，这是对 `ImageNet` 数据集定型的热门图像识别模型，其中 TensorFlow 模型尝试将所有图像分类为 1000 个类别，如“雨伞”、“针织衫”和“洗碗机”。

`Inception v3 model` 可以分类为[深度卷积神经网络](https://en.wikipedia.org/wiki/Convolutional_neural_network)，执行艰难视觉识别任务的效果合理，在一些领域中匹敌或超过人为绩效。 此模型/算法是由多个研究人员根据以下原始文章开发的：[“重新思考计算机视觉的 Inception 体系结构”，作者为 Szegedy 以及其他人](https://arxiv.org/abs/1512.00567)

由于 `Inception model` 已对数千个不同图像进行过预定型，因此其中包含图像识别所需的[图像特征](https://en.wikipedia.org/wiki/Feature_(computer_vision))。 较低图像特征层识别简单特征（如边缘），较高层识别更复杂的特征（如形状）。 最后一层对更小的数据集进行定型，因为你是从已了解如何分类图像的预定型模型入手。 由于模型允许分类为超过两个类别，因此这是[多类别分类器](../resources/tasks.md#multiclass-classification)示例。 

`TensorFlow` 是热门深度学习和机器学习工具包，可用于定型深度神经网络（和常规数值计算），并在 ML.NET 中实现为 `transformer`。 在本教程中，它用于重用 `Inception model`。

如下图中所示，在 .NET Core 或 .NET Framework 应用中添加对 ML.NET NuGet 包的引用。 实际上，ML.NET 包含并引用本机 `TensorFlow` 库，可用于编写代码来加载已定型的现有 `TensorFlow` 模型文件以进行评分。  

![TensorFlow 转换 ML.NET 体系结构图](./media/image-classification/tensorflow-mlnet.png)

`Inception model` 定型为将图像分类为 1000 个类别，但你只需要在更小的类别集中分类图像。 输入 `transfer learning` 的 `transfer` 部分。 可以将 `Inception model` 的识别和分类图像功能迁移到自定义图像分类器的新受限类别。  

 你将使用以下三个类别来重新定型此模型中的最后一层：

* 食物
* 玩具
* 家用电器

你的层使用[多项逻辑回归算法](https://en.wikipedia.org/wiki/Multinomial_logistic_regression)尽可能快地找到正确的类别。 此算法使用概率来确定答案，向正确类别提供值 1，向其他类别提供值 0，从而进行分类。  

### <a name="dataset"></a>数据集

数据源有两个：`.tsv` 文件和图像文件。  `tags.tsv` 文件包含两个列：第一列定义为 `ImagePath`，第二列是与图像对应的 `Label`。 下面的示例文件没有标题行，如下所示：

<!-- markdownlint-disable MD010 -->
```tsv
broccoli.jpg    food
pizza.jpg   food
pizza2.jpg  food
teddy2.jpg  toy
teddy3.jpg  toy
teddy4.jpg  toy
toaster.jpg appliance
toaster2.png    appliance
```
<!-- markdownlint-enable MD010 -->

定型图像和测试图像位于下载 zip 文件的资产文件夹中。 这些图像属于维基共享资源。
> [维基共享资源](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208)，免费媒体存储库。 检索时间：2018 年 10 月 17 日 10:48 检索位置：  
> https://commons.wikimedia.org/wiki/Pizza  
> https://commons.wikimedia.org/wiki/Toaster  
> https://commons.wikimedia.org/wiki/Teddy_bear  

## <a name="create-a-console-application"></a>创建控制台应用程序

### <a name="create-a-project"></a>创建项目

1. 创建名为“TransferLearningTF”的 **.NET Core 控制台应用程序**。

2. 安装“Microsoft.ML NuGet 包”：

    在“解决方案资源管理器”中，右键单击项目，然后选择“管理 NuGet 包”。 选择“nuget.org”作为“包源”，选择“浏览”选项卡，再搜索“Microsoft.ML”。 单击“版本”下拉列表，选择列表中的“1.0.0”包，然后选择“安装”按钮。 选择“预览更改”对话框上的“确定”按钮，如果你同意所列包的许可条款，则选择“接受许可”对话框上的“我接受”按钮。 对 **Microsoft.ML.ImageAnalytics v1.0.0** 和 **Microsoft.ML.TensorFlow v0.12.0** 重复这些步骤。

### <a name="prepare-your-data"></a>准备数据

1. 下载并解压缩[项目资产目录 zip 文件](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip)。

2. 将“`assets`”目录复制到“TransferLearningTF”项目目录中。 此目录及其子目录包含本教程所需的数据和支持文件（Inception 模型除外，将在下一步中下载并添加此模型）。

3. 下载并解压缩 [Inception 模型](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip)。

4. 将刚刚解压缩的“`inception5h`”目录的内容复制到 TransferLearningTF 项目的“`assets\inputs-train\inception`”目录中。 此目录包含本教程所需的模型和其他支持文件，如下图所示：

   ![Inception 目录内容](./media/image-classification/inception-files.png)

5. 在“解决方案资源管理器”中，右键单击资产目录和子目录中的每个文件，再选择“属性”。 在“高级”下，将“复制到输出目录”的值更改为“如果较新则复制”。

### <a name="create-classes-and-define-paths"></a>创建类和定义路径

将以下附加的 `using` 语句添加到“Program.cs”文件顶部：

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddUsings)]

创建全局字段，用于保留各种资产的路径，以及 `LabelTokey`、`ImageReal` 和 `PredictedLabelValue` 的全局变量：

* `_assetsPath` 包含资产的路径。
* `_trainTagsTsv` 包含定型图像数据标记 tsv 文件的路径。
* `_predictTagsTsv` 包含预测图像数据标记 tsv 文件的路径。
* `_trainImagesFolder` 包含用于定型模型的图像的路径。
* `_predictImagesFolder` 包含已定型的模型要分类的图像的路径。
* `_inceptionPb` 包含要重用于重新定型模型的预定型 Inception 模型的路径。
* `_inputImageClassifierZip` 包含从中加载已定型的模型的路径。
* `_outputImageClassifierZip` 具有在其中保存定型模型的路径。
* `LabelTokey` 是映射到键的 `Label` 值。
* `ImageReal` 是包含预测出的图像值的列。
* `PredictedLabelValue` 是包含预测出的标签值的列。

将以下代码添加到 `Main` 方法正上方的行中以指定这些路径和其他变量：

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DeclareGlobalVariables)]

为输入数据和预测结果创建一些类。 向项目添加一个新类：

1. 在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新项”。

1. 在“添加新项”对话框中，选择“类”，并将“名称”字段更改为“ImageData.cs”。 然后，选择“添加”按钮。

    此时，ImageData.cs 文件在代码编辑器中打开。 将下面的 `using` 语句添加到 ImageData.cs 顶部：

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TransferLearningTF/ImageData.cs#AddUsings)]

删除现有类定义，并将 `ImageData` 类的以下代码添加到 ImageData.cs 文件中：

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/TransferLearningTF/ImageData.cs#DeclareTypes)]

`ImageData` 是输入图像数据类，包含以下 <xref:System.String> 字段：

* `ImagePath` 包含图像文件名。
* `Label` 包含图像标签值。

向项目添加 `ImagePrediction` 的新类：

1. 在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新项”。

1. 在“添加新项”对话框中，选择“类”，并将“名称”字段更改为“ImagePrediction.cs”。 然后，选择“添加”按钮。

    此时，ImagePrediction.cs 文件在代码编辑器中打开。 删除 ImagePrediction.cs 顶部的 `System.Collections.Generic` 和 `System.Text` `using` 语句：

删除现有类定义，并将包含 `ImagePrediction` 类的以下代码添加到 ImagePrediction.cs 文件中：

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TransferLearningTF/ImagePrediction.cs#DeclareTypes)]

`ImagePrediction` 是图像预测类，包含以下字段：

* `Score` 包含给定图像分类的置信度百分比。
* `PredictedLabelValue` 包含预测出的图像分类标签的值。

`ImagePrediction` 是在定型模型后用于预测的类。 它包含图像路径的 `string` (`ImagePath`)。 `Label` 用于重用和重新定型模型。 `PredictedLabelValue` 在预测和评估过程中使用。 对于计算，将使用带定型数据的输入、预测值和模型。

执行所有 ML.NET 操作都是从 [MLContext 类](xref:Microsoft.ML.MLContext)开始，初始化 `mlContext` 可创建一个新的 ML.NET 环境，可在模型创建工作流对象之间共享该环境。 从概念上讲，它与实体框架中的 `DBContext` 类似。

### <a name="initialize-variables-in-main"></a>在 Main 中初始化变量

使用 `MLContext` 的新实例初始化 `mlContext` 变量。  用下面 `Main` 方法中的代码替换 `Console.WriteLine("Hello World!")` 行：

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CreateMLContext)]

### <a name="create-a-struct-for-default-parameters"></a>创建默认参数的结构

需要传入 Inception 模型的多个默认参数。 紧跟在 `Main()` 方法后面，使用以下代码创建结构，以将默认参数值映射到易记名称：

[!code-csharp[InceptionSettings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#InceptionSettings)]

### <a name="create-a-display-utility-method"></a>创建显示实用工具方法

由于将多次显示图像数据和相关预测，请创建显示实用工具方法，用于处理图像和预测结果的显示。

`DisplayResults()` 方法执行以下任务：

* 显示预测结果。

紧跟在 `InceptionSettings` 结构后面，使用下面的代码创建 `DisplayResults()` 方法：

```csharp
private static void DisplayResults(IEnumerable<ImagePrediction> imagePredictionData)
{

}
```

`Transform()` 方法在 `ImagePrediction` 中填充 `ImagePath` 以及预测的字段。 随着 ML.NET 进程继续执行，每个组件会添加列，这让显示结果变得轻松：

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPredictions)]

将在两个图像分类方法中调用 `DisplayResults()` 方法。

### <a name="create-a-tsv-file-utility-method"></a>创建 .tsv 文件实用工具方法

`ReadFromTsv()` 方法执行以下任务：

* 读取图像数据 `tags.tsv` 文件。
* 将文件路径添加到图像文件名中。
* 将文件数据加载到 IEnumerable`ImageData` 对象中。

使用下面的代码紧随 `PairAndDisplayResults()` 方法后创建 `ReadFromTsv()` 方法：

```csharp
public static IEnumerable<ImageData> ReadFromTsv(string file, string folder)
{

}
```

下面的代码分析整个 `tags.tsv` 文件，以将文件路径添加到 `ImagePath` 属性的图像文件名中，并将它和 `Label` 加载到 `ImageData` 对象中。 将它添加为 `ReadFromTsv()` 方法的第一行。  必须有完全限定的文件路径，才能显示预测结果。

[!code-csharp[ReadFromTsv](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReadFromTsv)]
ML.NET 中包含三个主要概念：[数据](../resources/glossary.md#data)、[转换器](../resources/glossary.md#transformer)和[估算器](../resources/glossary.md#estimator)。

## <a name="reuse-and-tune-pre-trained-model"></a>重用和优化预定型模型

将以下调用添加到 `ReuseAndTuneInceptionModel()` 方法作为 `Main()` 方法的下一行代码：

[!code-csharp[CallReuseAndTuneInceptionModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallReuseAndTuneInceptionModel)]

`ReuseAndTuneInceptionModel()` 方法执行以下任务：

* 加载数据
* 提取并转换数据。
* 对 TensorFlow 模型评分。
* 优化（重新定型）模型。
* 显示模型结果。
* 评估模型。
* 返回模型。

紧跟在 `InceptionSettings` 结构后面且恰好在 `DisplayResults()` 方法前面，使用以下代码创建 `ReuseAndTuneInceptionModel()` 方法：

```csharp
public static ITransformer ReuseAndTuneInceptionModel(MLContext mlContext, string dataLocation, string imagesFolder, string inputModelLocation, string outputModelLocation)
{

}
```

### <a name="load-the-data"></a>加载数据

ML.NET 中的数据表示为 [IDataView 类](xref:Microsoft.ML.IDataView)。 `IDataView` 是用于描述表格数据（数字和文本）的一种灵活且有效的方法。 可从文本文件或实时（例如，SQL 数据库或日志文件）将数据加载到 `IDataView` 对象。

使用 `MLContext.Data.LoadFromTextFile` 包装器加载数据。 将以下代码作为下一行添加到 `ReuseAndTuneInceptionModel()` 方法中：

[!code-csharp[LoadData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadData "Load the data")]

### <a name="extract-features-and-transform-the-data"></a>提取功能和转换数据

预处理和清除数据任务至关重要，需要首先执行才能将数据集有效地用于机器学习。  在没有这些建模任务的情况下使用数据会产生误导性结果。

机器学习算法理解[特征化](../resources/glossary.md#feature)数据，因此在处理深度神经网络时，必须将图像调整为网络所需的格式。 该格式是[数值向量](../resources/glossary.md#numerical-feature-vector)。

定型和评估后，预测“标签”列值。 由于使用的是预定型模型，因此使用 [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) 方法将字段映射到新模型。 此方法会将 `Label` 转换为数值键类型 (`LabelTokey`) 列，并将它添加为新数据集列：将此命名为 `estimator`，因为还会向它添加定型程序。 添加下一个代码行：

[!code-csharp[MapValueToKey1](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapValueToKey1)]

图像处理估算器使用预定型[深度神经网络 (DNN)](https://en.wikipedia.org/wiki/Deep_learning#Deep_neural_networks) 特征提取器来提取特征。 处理深度神经网络时，将图像调整为所需的网络格式。 正因为此，你使用多个图像转换将图像数据转换为模型所需的格式：

1. `LoadImages` 转换图像作为位图类型加载到内存中。
2. `ResizeImages` 转换可重设图像大小，因为预定型模型有已定义的输入图像宽度和高度。
3. `ExtractPixels` 转换可提取输入图像中的像素，并将它们转换为数值向量。

将这些图像转换添加为接下来的几行代码：

[!code-csharp[ImageTransforms](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ImageTransforms)]

`LoadTensorFlowModel` 是一种便捷方法，允许加载一次 `TensorFlow` 模型，然后使用 `ScoreTensorFlowModel` 创建 `TensorFlowEstimator`。 `ScoreTensorFlowModel` 提取指定输出（`Inception model` 的图像特征 `softmax2_pre_activation`），并使用预定型 `TensorFlow` 模型对数据集进行评分。

`softmax2_pre_activation` 协助模型确定图像属于哪个类别。 `softmax2_pre_activation` 返回图像每个类别的概率，所有这些概率的总和必须为 1。 它假设图像仅属于一个类别，如下面的示例所示：

| 类         | 概率   |
| ------------- | ------------- |
| `Food`        |  0.001        |
| `Toy`         |  0.95         |
| `Appliance`   |  0.06         |

使用以下代码行将 `TensorFlowTransform` 追加到 `estimator`：

[!code-csharp[ScoreTensorFlowModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ScoreTensorFlowModel)]

### <a name="choose-a-training-algorithm"></a>选择定型算法

若要添加定型算法，请调用 `mlContext.MulticlassClassification.Trainers.LbfgsMaximumEntropy()` 包装器方法。  [LbfgsMaximumEntropy](xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer) 追加到 `estimator` 中，并接受 Inception 图像特征 (`softmax2_pre_activation`) 和 `Label` 输入参数，以便从历史数据中学习。  使用以下代码添加定型程序：

[!code-csharp[AddTrainer](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddTrainer)]

还需要将 `predictedlabel` 映射到 `predictedlabelvalue`：

[!code-csharp[MapValueToKey2](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapValueToKey2)]

`Fit()` 方法通过转换数据集并应用训练来训练模型。 在 `ReuseAndTuneInceptionModel()` 方法中添加以下代码作为下一行代码，使模型拟合训练数据集，并返回经过训练的模型：

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#TrainModel)]

[Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) 方法对测试数据集的多个提供的输入行进行预测。  将以下代码添加到 `ReuseAndTuneInceptionModel()` 以转换 `Training` 数据：

[!code-csharp[TransformData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#TransformData)]

为了更方便显示，将图像数据和预测 `DataViews` 转换为强类型 `IEnumerables`，以供配对。 为此，通过下面的代码使用 `MLContext.CreateEnumerable()` 方法：

[!code-csharp[EnumerateDataViews](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#EnumerateDataViews)]

作为 `ReuseAndTuneInceptionModel()` 方法的下一行，调用 `DisplayResults()` 方法来显示数据和预测结果：

[!code-csharp[CallDisplayResults1](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallDisplayResults1)]

在你设置预测后，[Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) 方法便能：

* 评估模型（将预测出的值与实际数据集 `Labels` 进行比较）。

* 返回模型性能指标。

将以下代码作为下一行添加到 `ReuseAndTuneInceptionModel()` 方法中：

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#Evaluate)]

下面是图像分类评估指标：

* `Log-loss` - 请参阅[对数损失](../resources/glossary.md#log-loss)。 通常会希望对数损失尽可能接近 0。

* `Per class Log-loss`。 建议每类别的对数损失尽可能接近 0。

使用下面的代码显示指标、共享结果，然后处理它们：

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayMetrics)]

 添加以下代码，将经过训练的模型作为下一行代码返回：

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReturnModel)]

## <a name="classify-images-with-a-loaded-model"></a>使用已加载的模型来分类图像

将以下 `ClassifyImages()` 方法调用添加为 `Main` 方法的下一行代码：

[!code-csharp[CallClassifyImages](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallClassifyImages)]

`ClassifyImages()` 方法执行以下任务：

* 将 .TSV 文件读取到 `IEnumerable` 中。
* 根据测试数据预测图像分类。

紧跟在 `ReuseAndTuneInceptionModel()` 方法后面且恰好在 `PairAndDisplayResults()` 方法前面，使用以下代码创建 `ClassifyImages()` 方法：

```csharp
public static void ClassifyImages(MLContext mlContext, string dataLocation, string imagesFolder, string outputModelLocation, ITransformer model)
{

}
```

首先，调用 `ReadFromTsv()` 方法来创建 `IEnumerable<ImageData>` 类，其中包含每个 `ImagePath` 的完全限定的路径。 必须有此文件路径，才能配对数据和预测结果。 还需要将 `IEnumerable<ImageData>` 类转换为将用于预测的 `IDataView`。 将以下代码添加为 `ClassifyImages()` 方法的接下来两行代码：

[!code-csharp[CallReadFromTSV](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallReadFromTSV)]

如同之前处理训练图像数据一样，使用传入模型的 [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) 方法预测测试图像数据的类别。 将以下代码添加到预测结果的 `ClassifyImages()` 方法，并将 `predictions` `IDataView` 转换为 `IEnumerable` 以供配对和显示：

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#Predict)]

若要配对和显示测试图像数据和预测结果，请将以下代码添加为 `ClassifyImages()` 方法的下一行，以调用之前创建的 `DisplayResults()` 方法：

[!code-csharp[CallDisplayResults2](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallDisplayResults2)]

## <a name="classify-a-single-image-with-a-loaded-model"></a>使用已加载的模型来分类单张图像

将以下 `ClassifySingleImage()` 方法调用添加为 `Main` 方法的下一行代码：

[!code-csharp[CallClassifySingleImage](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallClassifySingleImage)]

`ClassifySingleImage()` 方法执行以下任务：

* 加载 `ImageData` 实例。
* 根据测试数据预测图像分类。

紧跟在 `ClassifyImages()` 方法后面且恰好在 `PairAndDisplayResults()` 方法前面，使用以下代码创建 `ClassifySingleImage()` 方法：

```csharp
public static void ClassifySingleImage(MLContext mlContext, string imagePath, string outputModelLocation, ITransformer model)
{

}
```

首先，创建 `ImageData` 类，其中包含单个 `ImagePath` 的完全限定的路径和图像文件名。 将以下代码添加为 `ClassifySingleImage()` 方法的接下来几行：

[!code-csharp[LoadImageData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadImageData)]

[PredictionEngine 类](xref:Microsoft.ML.PredictionEngine%602)是对单个数据实例执行预测的简便 API。 [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) 函数对单列数据进行预测。 通过将以下代码添加到 `ClassifySingleImage()`，将 `imageData` 传递到 `PredictionEngine` 来预测图像类别：

[!code-csharp[PredictSingle](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#PredictSingle)]

`ClassifySingleImage()` 方法的下一行代码用于显示预测结果：

[!code-csharp[DisplayPrediction](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPrediction)]

## <a name="results"></a>结果

按照上述步骤操作后，运行控制台应用 (Ctrl + F5)。 结果应如以下输出所示。  你可能会看到警告或处理消息，为清楚起见，这些消息已从以下结果中删除。

```console
=============== Training classification model ===============
Image: broccoli.jpg predicted as: food with score: 0.976743
Image: pizza.jpg predicted as: food with score: 0.9751652
Image: pizza2.jpg predicted as: food with score: 0.9660203
Image: teddy2.jpg predicted as: toy with score: 0.9748783
Image: teddy3.jpg predicted as: toy with score: 0.9829691
Image: teddy4.jpg predicted as: toy with score: 0.9868168
Image: toaster.jpg predicted as: appliance with score: 0.9769174
Image: toaster2.png predicted as: appliance with score: 0.9800823
=============== Classification metrics ===============
LogLoss is: 0.0228266745633507
PerClassLogLoss is: 0.0277501705149937 , 0.0186303530571291 , 0.0217359128952187
=============== Making classifications ===============
Image: broccoli.png predicted as: food with score: 0.905548
Image: pizza3.jpg predicted as: food with score: 0.9709008
Image: teddy6.jpg predicted as: toy with score: 0.9750155
=============== Making single image classification ===============
Image: toaster3.jpg predicted as: appliance with score: 0.9625379

C:\Program Files\dotnet\dotnet.exe (process 4304) exited with code 0.
Press any key to close this window . . .
```

祝贺你！ 现已通过重用 ML.NET 中的预定型 `TensorFlow` 模型，成功生成图像分类机器学习模型。

可以在 [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) 存储库中找到本教程的源代码。

在本教程中，你将了解：
> [!div class="checklist"]
> * 了解问题
> * 重用和优化预定型模型
> * 使用已加载的模型来分类图像

请查看机器学习示例 GitHub 存储库，以探索扩展的图像分类示例。
> [!div class="nextstepaction"]
> [dotnet/machinelearning-samples GitHub 存储库](https://github.com/dotnet/machinelearning-samples/)

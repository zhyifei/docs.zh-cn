---
title: ML.NET CLI 工具中的 auto-train 命令
description: ML.NET CLI 工具中 auto-train 命令的概述、示例和参考。
ms.date: 04/16/2019
ms.custom: ''
ms.openlocfilehash: ce5994f392c492e80676b9e65ce54fe010cf03ab
ms.sourcegitcommit: 90f0bee0e8a416e45c78fa3ad4c91ef00e5228d5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/06/2019
ms.locfileid: "66722611"
---
# <a name="the-auto-train-command-in-mlnet-cli"></a>ML.NET CLI 中的“auto-train”命令

> [!NOTE]
> 本主题涉及目前处于预览状态的 ML.NET CLI 和 ML.NET AutoML，且材料可能会有所变化。

`auto-train` 命令是 ML.NET CLI 工具提供的主要命令。 该命令允许生成高质量的 ML.NET 模型（序列化模型 .zip 文件）以及用于运行该模型/对该模型评分的示例 C# 代码。 此外，还会生成用于创建/训练该模型的 C# 代码，以便研究用于该生成的“最佳模型”的算法和设置。

可以从自己的数据集生成这些资产而无需自行编码，因此，即使已经了解 ML.NET，它也可以提高工作效率。

目前，ML.NET CLI 支持的 ML 任务包括：

- `binary-classification`
- `multiclass-classification`
- `regression`

- 未来：其他机器学习任务，例如
  - `recommendation`
  - `anomaly-detection`
  - `clustering`

命令提示符上的用法示例：

```console
> mlnet auto-train --task regression --dataset "cars.csv" --label-column-name price
```

`mlnet auto-train` 命令生成以下资产：

- 可供使用的序列化模型 .zip 文件（“最佳模型”）。
- 用于运行生成的模型/对生成的模型评分的 C# 代码（使用该模型在最终用户应用中进行预测）。
- C# 代码，其中包含用于生成该模型的训练代码（学习目的）。

前两个资产可以直接用于最终用户应用（ASP.NET Core Web 应用、服务、桌面应用等），以使用生成的 ML 模型进行预测。

第三个资产（训练代码）显示 CLI 用于训练生成的模型的 ML.NET API 代码，因此可以研究 CLI 和 ML.NET AutoML 引擎选择的特定训练程序/算法和超参数。

## <a name="the-auto-train-command-uses-the-automl-engine"></a>“auto-train”命令使用 AutoML 引擎

CLI 使用 ML.NET AutoML 引擎（NuGet 包）智能搜索最佳质量模型，如以下关系图所示：

![图像](./media/ml-net-automl-working-diagram.png "在 ML.NET CLI 内部工作的 AutoML 引擎")

使用 `auto-train- 命令运行 ML.NET CLI 工具时，将看到该工具尝试使用不同的算法和配置组合进行多次迭代。

## <a name="reference-for-auto-train-command"></a>“auto-train”命令参考

## <a name="examples"></a>示例

用于二元分类问题的最简单的 CLI 命令（AutoML 将需要从提供的数据中推断出大部分配置）：

```console
> mlnet auto-train --task binary-classification --dataset "customer-feedback.tsv" --label-column-name Sentiment
```

另一个用于回归问题的简单 CLI 命令：

``` console
> mlnet auto-train --task regression --dataset "cars.csv" --label-column-name Price
```

使用训练数据集、测试数据集和进一步的自定义显式参数创建和训练二元分类模型：

```console
> mlnet auto-train --task binary-classification --dataset "/MyDataSets/Population-Training.csv" --test-dataset "/MyDataSets/Population-Test.csv" --label-column-name "InsuranceRisk" --cache on --max-exploration-time 600
```

## <a name="name"></a>name

`mlnet auto-train` - 根据提供的数据集训练多个模型（“n”次迭代）并最终选择最佳模型，然后将其作为序列化 .zip 文件保存，并生成相关 C# 代码用于评分和训练。

## <a name="synopsis"></a>摘要

```console
> mlnet auto-train

--task | --mltask | -T <value>

--dataset | -d <value>

[
 [--validation-dataset | -v <value>]
  --test-dataset | -t <value>
]

--label-column-name | -n <value>
|
--label-column-index | -i <value>

[--ignore-columns | -I <value>]

[--has-header | -h <value>]

[--max-exploration-time | -x <value>]

[--verbosity | -V <value>]

[--cache | -c <value>]

[--name | -N <value>]

[--output-path | -o <value>]

[--help | -h]

```

无效的输入选项应该使 CLI 工具发出有效输入的列表和说明缺少的参数的错误消息（如果缺少参数）。

## <a name="options"></a>选项

 ----------------------------------------------------------

`--task | --mltask | -T`（字符串）

提供要解决的 ML 问题的单个字符串。 例如，以下任何任务（CLI 最终将支持 AutoML 支持的所有任务）：

- `regression` - 如果 ML 模型将用于预测数字值，则选择。
- `binary-classification` - 如果 ML 模型结果有两个可能的分类布尔值（0 或 1），则选择。
- `multiclass-classification` - 如果 ML 模型结果有多个分类可能值，则选择。

在未来的版本中，将支持其他 ML 任务和方案，例如 `recommendations`、`clustering` 和 `ranking`。

 仅应在此参数中提供一个 ML 任务。

 ----------------------------------------------------------

`--dataset | -d`（字符串）

此参数向以下任一选项提供文件路径：

- *A：整个数据集文件：* 如果使用此选项且用户未提供 `--test-dataset` 和 `--validation-dataset`，则将在内部使用交叉验证（K 折等）或自动数据拆分方法来验证模型。 在这种情况下，用户将只需要提供数据集文件路径。

- *B：训练数据集文件：* 如果用户还提供用于模型验证的数据集（使用 `--test-dataset` 和可选的 `--validation-dataset`），则 `--dataset` 参数意味着仅拥有“训练数据集”。 例如，当使用 80%-20% 方法来验证模型的质量以及获取准确性指标时，“训练数据集”将拥有 80% 的数据，而“测试数据集”将拥有 20% 的数据。

----------------------------------------------------------

`--test-dataset | -t`（字符串）

指向测试数据集文件的文件路径，例如，在进行常规验证以获取准确性指标时使用 80%-20% 方法的情况。

如果使用 `--test-dataset`，则还需要 `--dataset`。

除非使用 --validation-dataset，否则 `--test-dataset` 参数是可选的。 在这种情况下，用户必须使用三个参数。

----------------------------------------------------------

`--validation-dataset | -v`（字符串）

指向验证数据集文件的文件路径。 验证数据集在任何情况下都是可选的。

如果使用 `validation dataset`，则行为应为：

- `test-dataset` 和 `--dataset` 参数也是必需的。

- `validation-dataset` 数据集用于估算模型选择的预测误差。

- `test-dataset` 用于评估最终选定模型的泛化误差。 理想情况下，测试集应保存在“保管库”中，并仅在数据分析结束时显示。

一般来说，使用 `validation dataset` 以及 `test dataset` 时，验证阶段拆分为两部分：

1. 在第一部分中，只需查看模型并使用验证数据选择性能最佳的方法即可（= 验证）
2. 然后，估算选定方法的准确性（= 测试）。

因此，数据分离可以是 80/10/10 或 75/15/10。 例如:

- `training-dataset` 文件应拥有 75% 的数据。
- `validation-dataset` 文件应拥有 15% 的数据。
- `test-dataset` 文件应拥有 10% 的数据。

在任何情况下，这些百分比都将由使用 CLI 的用户决定，用户将提供已经拆分的文件。

----------------------------------------------------------

`--label-column-name | -n`（字符串）

借助此参数，可以使用数据集标头中设置的列名来指定特定的目的/目标列（想要预测的变量）。

此参数仅用于受监管的 ML 任务，例如*分类问题*。 它不能用于不受监管的 ML 任务，例如*聚类分析*。

----------------------------------------------------------

`--label-column-index | -i`（整数）

借助此参数，可以使用数据集文件中列的数字索引（列索引值从 1 开始）来指定特定的目的/目标列（想要预测的变量）。

*注意：* 如果用户还使用 `--label-column-name`，则应使用 `--label-column-name`。

此参数仅用于受监管的 ML 任务，例如*分类问题*。 它不能用于不受监管的 ML 任务，例如*聚类分析*。

----------------------------------------------------------

`--ignore-columns | -I`（字符串）

借助此参数，可以忽略数据集文件中的现有列，这样一来，训练过程便不会加载和使用它们。

指定想要忽略的列名。 使用“, ”（逗号加空格）或“ ”（空格）分隔多个列名。 可以对包含空格的列名使用引号（例如，“logged in”）。

示例:

`--ignore-columns email, address, id, logged_in`

----------------------------------------------------------

`--has-header | -h`（布尔值）

指定数据集文件是否拥有标头行。
可能的值有：
- `true`
- `false`

如果用户未指定此参数，则默认值为 `true`。

若要使用 `--label-column-name` 参数，需要在数据集文件中包含标头，并将 `--has-header` 设置为 `true`（默认值）。

----------------------------------------------------------

`--max-exploration-time | -x`（字符串）

默认情况下，最大浏览时间为 30 分钟。

此参数设置探索多个训练程序和配置的过程的最长持续时间（以秒为单位）。 如果提供的时间对于单次迭代来说太短（例如 2 秒），则可能会超出配置的时间。 在这种情况下，实际时间是在单次迭代中生成一个模型配置所需的时间。

迭代所需的时间可能因数据集的大小而异。

----------------------------------------------------------

`--cache | -c`（字符串）

如果使用缓存，则整个训练数据集将在内存中加载。

对于中小型数据集，使用缓存可以大幅提高训练性能，这意味着训练时间可以比不使用缓存时更短。

但是，对于大型数据集，在内存中加载所有数据可能会产生负面影响，因为可能会出现内存不足的情况。 如果使用大型数据集文件进行训练而不使用缓存，ML.NET 将在训练期间需要加载更多数据时从驱动器中流式传输数据块。

你可以指定以下值：

`on`：强制在训练时使用缓存。
`off`：强制在训练时不使用缓存。
`auto`：是否使用缓存取决于 AutoML 试探法。 通常情况下，如果使用 `auto` 选项，小型/中型数据集将使用缓存，而大型数据集将不使用缓存。

如果未指定 `--cache` 参数，则默认情况下将使用缓存 `auto` 配置。

----------------------------------------------------------

`--name | -N`（字符串）

创建的输出项目或解决方案的名称。 如果未指定名称，则使用名称 `sample-{mltask}`。

ML.NET 模型文件（.zip 文件）也将获得相同的名称。

----------------------------------------------------------

`--output-path | -o`（字符串）

用于放置生成的输出的根位置/文件夹。 默认为当前目录。

----------------------------------------------------------

`--verbosity | -V`（字符串）

设置标准输出的详细级别。

允许的值包括：

- `q[uiet]`
- `m[inimal]`（默认情况）
- `diag[nostic]`（日志记录信息级别）

默认情况下，CLI 工具应在运行时应显示一些最低限度的反馈（最小值），例如提及它正在运行以及剩余多少时间或已完成时间的百分比（如果可能）。

----------------------------------------------------------

`-h|--help`

打印命令帮助，其中包含对每个命令的参数的描述。

----------------------------------------------------------

## <a name="see-also"></a>请参阅

- [如何安装 ML.NET CLI 工具](../how-to-guides/install-ml-net-cli.md)
- [使用 ML.NET CLI 自动进行模型训练](../automate-training-with-cli.md)
- [教程：使用 ML.NET CLI 自动生成二元分类器](../tutorials/mlnet-cli.md)
- [ML.NET CLI 中的遥测](../resources/ml-net-cli-telemetry.md)

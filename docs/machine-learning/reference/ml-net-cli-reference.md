---
title: ML.NET CLI 工具中的 auto-train 命令
description: ML.NET CLI 工具中 auto-train 命令的概述、示例和参考。
ms.date: 04/16/2019
ms.custom: ''
ms.openlocfilehash: 28eb56eb018e3d1cc76f300ee78c298af77c9b91
ms.sourcegitcommit: 682c64df0322c7bda016f8bfea8954e9b31f1990
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2019
ms.locfileid: "65557941"
---
# <a name="the-auto-train-command-in-mlnet-cli"></a><span data-ttu-id="52fc3-103">ML.NET CLI 中的“auto-train”命令</span><span class="sxs-lookup"><span data-stu-id="52fc3-103">The 'auto-train' command in ML.NET CLI</span></span>

> [!NOTE]
> <span data-ttu-id="52fc3-104">本主题涉及目前处于预览状态的 ML.NET CLI 和 ML.NET AutoML，且材料可能会有所变化。</span><span class="sxs-lookup"><span data-stu-id="52fc3-104">This topic refers to ML.NET CLI and ML.NET AutoML, which are currently in Preview, and material may be subject to change.</span></span>

<span data-ttu-id="52fc3-105">`auto-train` 命令是 ML.NET CLI 工具提供的主要命令。</span><span class="sxs-lookup"><span data-stu-id="52fc3-105">The `auto-train` command is the main command provided by the ML.NET CLI tool.</span></span> <span data-ttu-id="52fc3-106">该命令允许生成高质量的 ML.NET 模型（序列化模型 .zip 文件）以及用于运行该模型/对该模型评分的示例 C# 代码。</span><span class="sxs-lookup"><span data-stu-id="52fc3-106">The command allows you to generate a good quality ML.NET model (serialized model .zip file) plus the example C# code to run/score that model.</span></span> <span data-ttu-id="52fc3-107">此外，还会生成用于创建/训练该模型的 C# 代码，以便研究用于该生成的“最佳模型”的算法和设置。</span><span class="sxs-lookup"><span data-stu-id="52fc3-107">In addition, the C# code to create/train that model is also generated for you to research what algorithm and settings it is using for that generated "best model".</span></span>

<span data-ttu-id="52fc3-108">可以从自己的数据集生成这些资产而无需自行编码，因此，即使已经了解 ML.NET，它也可以提高工作效率。</span><span class="sxs-lookup"><span data-stu-id="52fc3-108">You can generate those assets from your own datasets without coding by yourself, so it also improves your productivity even if you already know ML.NET.</span></span>

<span data-ttu-id="52fc3-109">目前，ML.NET CLI 支持的 ML 任务包括：</span><span class="sxs-lookup"><span data-stu-id="52fc3-109">Currently, the ML Tasks supported by the ML.NET CLI are:</span></span>

- `binary-classification`
- `multiclass-classification`
- `regression`

- <span data-ttu-id="52fc3-110">未来：其他机器学习任务，例如</span><span class="sxs-lookup"><span data-stu-id="52fc3-110">Future: Other machine learning tasks, such as</span></span>
  - `recommendation`
  - `anomaly-detection`
  - `clustering`

<span data-ttu-id="52fc3-111">命令提示符上的用法示例：</span><span class="sxs-lookup"><span data-stu-id="52fc3-111">Example of usage on the command prompt:</span></span>

```console
> mlnet auto-train --task regression --dataset "cars.csv" --label-column-name price
```

<span data-ttu-id="52fc3-112">`mlnet auto-train` 命令生成以下资产：</span><span class="sxs-lookup"><span data-stu-id="52fc3-112">The `mlnet auto-train` command generates the following assets:</span></span>

- <span data-ttu-id="52fc3-113">可供使用的序列化模型 .zip 文件（“最佳模型”）。</span><span class="sxs-lookup"><span data-stu-id="52fc3-113">A serialized model .zip ("best model") ready to use.</span></span>
- <span data-ttu-id="52fc3-114">用于运行生成的模型/对生成的模型评分的 C# 代码（使用该模型在最终用户应用中进行预测）。</span><span class="sxs-lookup"><span data-stu-id="52fc3-114">C# code to run/score that generated model (To make predictions in your end-user apps with that model).</span></span>
- <span data-ttu-id="52fc3-115">C# 代码，其中包含用于生成该模型的训练代码（学习目的）。</span><span class="sxs-lookup"><span data-stu-id="52fc3-115">C# code with the training code used to generate that model (Learning purposes).</span></span>

<span data-ttu-id="52fc3-116">前两个资产可以直接用于最终用户应用（ASP.NET Core Web 应用、服务、桌面应用等），以使用生成的 ML 模型进行预测。</span><span class="sxs-lookup"><span data-stu-id="52fc3-116">The first two assets can directly be used in your end-user apps (ASP.NET Core web app, services, desktop app, etc.) to make predictions with that generated ML model.</span></span>

<span data-ttu-id="52fc3-117">第三个资产（训练代码）显示 CLI 用于训练生成的模型的 ML.NET API 代码，因此可以研究 CLI 和 ML.NET AutoML 引擎选择的特定训练程序/算法和超参数。</span><span class="sxs-lookup"><span data-stu-id="52fc3-117">The third asset, the training code, shows you what ML.NET API code was used by the CLI to train the generated model, so you can investigate what specific trainer/algorithm and hyper-paramenters were selected by the CLI and the ML.NET AutoML engine.</span></span>

## <a name="the-auto-train-command-uses-the-automl-engine"></a><span data-ttu-id="52fc3-118">“auto-train”命令使用 AutoML 引擎</span><span class="sxs-lookup"><span data-stu-id="52fc3-118">The 'auto-train' command uses the AutoML engine</span></span>

<span data-ttu-id="52fc3-119">CLI 使用 ML.NET AutoML 引擎（NuGet 包）智能搜索最佳质量模型，如以下关系图所示：</span><span class="sxs-lookup"><span data-stu-id="52fc3-119">The CLI uses the ML.NET AutoML engine (NuGet package) to intelligently search for the best quality models, as shown in the following diagram:</span></span>

<span data-ttu-id="52fc3-120">![图像](./media/ml-net-automl-working-diagram.png "在 ML.NET CLI 内部工作的 AutoML 引擎")</span><span class="sxs-lookup"><span data-stu-id="52fc3-120">![image](./media/ml-net-automl-working-diagram.png "AutoML engine working inside the ML.NET CLI")</span></span>

<span data-ttu-id="52fc3-121">使用 \`auto-train- 命令运行 ML.NET CLI 工具时，将看到该工具尝试使用不同的算法和配置组合进行多次迭代。</span><span class="sxs-lookup"><span data-stu-id="52fc3-121">When running the ML.NET CLI tool with the \`auto-train- command, you'll see the tool trying many iterations with different algorithms and combinations of configuration.</span></span>

## <a name="reference-for-auto-train-command"></a><span data-ttu-id="52fc3-122">“auto-train”命令参考</span><span class="sxs-lookup"><span data-stu-id="52fc3-122">Reference for 'auto-train' command</span></span>

## <a name="examples"></a><span data-ttu-id="52fc3-123">示例</span><span class="sxs-lookup"><span data-stu-id="52fc3-123">Examples</span></span>

<span data-ttu-id="52fc3-124">用于二元分类问题的最简单的 CLI 命令（AutoML 将需要从提供的数据中推断出大部分配置）：</span><span class="sxs-lookup"><span data-stu-id="52fc3-124">Simplest CLI command for a binary classification problem (AutoML will need to infer most of the configuration from the provided data):</span></span>

```console
> mlnet auto-train --task binary-classification --dataset "customer-feedback.tsv" --label-column-name Sentiment
```

<span data-ttu-id="52fc3-125">另一个用于回归问题的简单 CLI 命令：</span><span class="sxs-lookup"><span data-stu-id="52fc3-125">Another simple CLI command for a regression problem:</span></span>

``` console
> mlnet auto-train --task regression --dataset "cars.csv" --label-column-name Price
```

<span data-ttu-id="52fc3-126">使用训练数据集、测试数据集和进一步的自定义显式参数创建和训练二元分类模型：</span><span class="sxs-lookup"><span data-stu-id="52fc3-126">Create and train a binary-classification model with a train dataset, a test dataset, and further customization explicit arguments:</span></span>

```console
> mlnet auto-train --task binary-classification --dataset "/MyDataSets/Population-Training.csv" --test-dataset "/MyDataSets/Population-Test.csv" --label-column-name "InsuranceRisk" --cache on --max-exploration-time 600
```

## <a name="name"></a><span data-ttu-id="52fc3-127">name</span><span class="sxs-lookup"><span data-stu-id="52fc3-127">Name</span></span>

<span data-ttu-id="52fc3-128">`mlnet auto-train` - 根据提供的数据集训练多个模型（“n”次迭代）并最终选择最佳模型，然后将其作为序列化 .zip 文件保存，并生成相关 C# 代码用于评分和训练。</span><span class="sxs-lookup"><span data-stu-id="52fc3-128">`mlnet auto-train` - Trains multiple models ('n' iterations) based on the provided dataset and finally selects the best model, saves it as a serialized .zip file plus generates related C# code for scoring and training.</span></span>

## <a name="synopsis"></a><span data-ttu-id="52fc3-129">摘要</span><span class="sxs-lookup"><span data-stu-id="52fc3-129">Synopsis</span></span>

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

<span data-ttu-id="52fc3-130">无效的输入选项应该使 CLI 工具发出有效输入的列表和说明缺少的参数的错误消息（如果缺少参数）。</span><span class="sxs-lookup"><span data-stu-id="52fc3-130">Invalid input options should cause the CLI tool to emit a list of valid inputs and an error message explaining which arg is missing, if that is the case.</span></span>

## <a name="options"></a><span data-ttu-id="52fc3-131">选项</span><span class="sxs-lookup"><span data-stu-id="52fc3-131">Options</span></span>

 ----------------------------------------------------------

<span data-ttu-id="52fc3-132">`--task | --mltask | -T`（字符串）</span><span class="sxs-lookup"><span data-stu-id="52fc3-132">`--task | --mltask | -T` (string)</span></span>

<span data-ttu-id="52fc3-133">提供要解决的 ML 问题的单个字符串。</span><span class="sxs-lookup"><span data-stu-id="52fc3-133">A single string providing the ML problem to solve.</span></span> <span data-ttu-id="52fc3-134">例如，以下任何任务（CLI 最终将支持 AutoML 支持的所有任务）：</span><span class="sxs-lookup"><span data-stu-id="52fc3-134">For instance, any of the following tasks (The CLI will eventually support all tasks supported in AutoML):</span></span>

- <span data-ttu-id="52fc3-135">`regression` - 如果 ML 模型将用于预测数字值，则选择。</span><span class="sxs-lookup"><span data-stu-id="52fc3-135">`regression` - Choose if the ML Model will be used to predict a numeric value</span></span>
- <span data-ttu-id="52fc3-136">`binary-classification` - 如果 ML 模型结果有两个可能的分类布尔值（0 或 1），则选择。</span><span class="sxs-lookup"><span data-stu-id="52fc3-136">`binary-classification` - Choose if the ML Model result has two possible categorical boolean values (0 or 1).</span></span>
- <span data-ttu-id="52fc3-137">`multiclass-classification` - 如果 ML 模型结果有多个分类可能值，则选择。</span><span class="sxs-lookup"><span data-stu-id="52fc3-137">`multiclass-classification` - Choose if the ML Model result has multiple categorical possible values.</span></span>

<span data-ttu-id="52fc3-138">在未来的版本中，将支持其他 ML 任务和方案，例如 `recommendations`、`clustering` 和 `ranking`。</span><span class="sxs-lookup"><span data-stu-id="52fc3-138">In future releases additional ML Tasks and scenarios such as `recommendations`, `clustering` and `ranking` will be supported.</span></span>

 <span data-ttu-id="52fc3-139">仅应在此参数中提供一个 ML 任务。</span><span class="sxs-lookup"><span data-stu-id="52fc3-139">Only one ML task should be provided in this argument.</span></span>

 ----------------------------------------------------------

<span data-ttu-id="52fc3-140">`--dataset | -d`（字符串）</span><span class="sxs-lookup"><span data-stu-id="52fc3-140">`--dataset | -d` (string)</span></span>

<span data-ttu-id="52fc3-141">此参数向以下任一选项提供文件路径：</span><span class="sxs-lookup"><span data-stu-id="52fc3-141">This argument provides the filepath to either one of the following options:</span></span>

- <span data-ttu-id="52fc3-142">*A：整个数据集文件：* 如果使用此选项且用户未提供 `--test-dataset` 和 `--validation-dataset`，则将在内部使用交叉验证（K 折等）或自动数据拆分方法来验证模型。</span><span class="sxs-lookup"><span data-stu-id="52fc3-142">*A: The whole dataset file:* If using this option and the user is not providing `--test-dataset` and `--validation-dataset`, then cross-validation (k-fold, etc.) or automated data split approaches will be used internally for validating the model.</span></span> <span data-ttu-id="52fc3-143">在这种情况下，用户将只需要提供数据集文件路径。</span><span class="sxs-lookup"><span data-stu-id="52fc3-143">In that case, the user will just need to provide the dataset filepath.</span></span>

- <span data-ttu-id="52fc3-144">*B：训练数据集文件：* 如果用户还提供用于模型验证的数据集（使用 `--test-dataset` 和可选的 `--validation-dataset`），则 `--dataset` 参数意味着仅拥有“训练数据集”。</span><span class="sxs-lookup"><span data-stu-id="52fc3-144">*B: The training dataset file:* If the user is also providing datasets for model validation (using `--test-dataset` and optionally `--validation-dataset`), then the `--dataset` argument means to only have the "training dataset".</span></span> <span data-ttu-id="52fc3-145">例如，当使用 80%-20% 方法来验证模型的质量以及获取准确性指标时，“训练数据集”将拥有 80% 的数据，而“测试数据集”将拥有 20% 的数据。</span><span class="sxs-lookup"><span data-stu-id="52fc3-145">For example, when using an 80% - 20% approach to validate the quality of the model and to obtain accuracy metrics, the "training dataset" will have 80% of the data and the "test dataset" would have 20% of the data.</span></span>

----------------------------------------------------------

<span data-ttu-id="52fc3-146">`--test-dataset | -t`（字符串）</span><span class="sxs-lookup"><span data-stu-id="52fc3-146">`--test-dataset | -t` (string)</span></span>

<span data-ttu-id="52fc3-147">指向测试数据集文件的文件路径，例如，在进行常规验证以获取准确性指标时使用 80%-20% 方法的情况。</span><span class="sxs-lookup"><span data-stu-id="52fc3-147">File path pointing to the test dataset file, for example when using an 80% - 20% approach when making regular validations to obtain accuracy metrics.</span></span>

<span data-ttu-id="52fc3-148">如果使用 `--test-dataset`，则还需要 `--dataset`。</span><span class="sxs-lookup"><span data-stu-id="52fc3-148">If using `--test-dataset`, then `--dataset` is also required.</span></span>

<span data-ttu-id="52fc3-149">除非使用 --validation-dataset，否则 `--test-dataset` 参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="52fc3-149">The `--test-dataset` argument is optional unless the --validation-dataset is used.</span></span> <span data-ttu-id="52fc3-150">在这种情况下，用户必须使用三个参数。</span><span class="sxs-lookup"><span data-stu-id="52fc3-150">In that case, the user must use the three arguments.</span></span>

----------------------------------------------------------

<span data-ttu-id="52fc3-151">`--validation-dataset | -v`（字符串）</span><span class="sxs-lookup"><span data-stu-id="52fc3-151">`--validation-dataset | -v` (string)</span></span>

<span data-ttu-id="52fc3-152">指向验证数据集文件的文件路径。</span><span class="sxs-lookup"><span data-stu-id="52fc3-152">File path pointing to the validation dataset file.</span></span> <span data-ttu-id="52fc3-153">验证数据集在任何情况下都是可选的。</span><span class="sxs-lookup"><span data-stu-id="52fc3-153">The validation dataset is optional, in any case.</span></span>

<span data-ttu-id="52fc3-154">如果使用 `validation dataset`，则行为应为：</span><span class="sxs-lookup"><span data-stu-id="52fc3-154">If using a `validation dataset`, the behavior should be:</span></span>

- <span data-ttu-id="52fc3-155">`test-dataset` 和 `--dataset` 参数也是必需的。</span><span class="sxs-lookup"><span data-stu-id="52fc3-155">The `test-dataset` and `--dataset` arguments are also required.</span></span>

- <span data-ttu-id="52fc3-156">`validation-dataset` 数据集用于估算模型选择的预测误差。</span><span class="sxs-lookup"><span data-stu-id="52fc3-156">The `validation-dataset` dataset is used to estimate prediction error for model selection.</span></span>

- <span data-ttu-id="52fc3-157">`test-dataset` 用于评估最终选定模型的泛化误差。</span><span class="sxs-lookup"><span data-stu-id="52fc3-157">The `test-dataset` is used for assessment of the generalization error of the final chosen model.</span></span> <span data-ttu-id="52fc3-158">理想情况下，测试集应保存在“保管库”中，并仅在数据分析结束时显示。</span><span class="sxs-lookup"><span data-stu-id="52fc3-158">Ideally, the test set should be kept in a “vault,” and be brought out only at the end of the data analysis.</span></span>

<span data-ttu-id="52fc3-159">一般来说，使用 `validation dataset` 以及 `test dataset` 时，验证阶段拆分为两部分：</span><span class="sxs-lookup"><span data-stu-id="52fc3-159">Basically, when using a `validation dataset` plus the `test dataset`, the validation phase is split into two parts:</span></span>

1. <span data-ttu-id="52fc3-160">在第一部分中，只需查看模型并使用验证数据选择性能最佳的方法即可（= 验证）</span><span class="sxs-lookup"><span data-stu-id="52fc3-160">In the first part, you just look at your models and select the best performing approach using the validation data (=validation)</span></span>
2. <span data-ttu-id="52fc3-161">然后，估算选定方法的准确性（= 测试）。</span><span class="sxs-lookup"><span data-stu-id="52fc3-161">Then you estimate the accuracy of the selected approach (=test).</span></span>

<span data-ttu-id="52fc3-162">因此，数据分离可以是 80/10/10 或 75/15/10。</span><span class="sxs-lookup"><span data-stu-id="52fc3-162">Hence, the separation of data could be 80/10/10 or 75/15/10.</span></span> <span data-ttu-id="52fc3-163">例如:</span><span class="sxs-lookup"><span data-stu-id="52fc3-163">For example:</span></span>

- <span data-ttu-id="52fc3-164">`training-dataset` 文件应拥有 75% 的数据。</span><span class="sxs-lookup"><span data-stu-id="52fc3-164">`training-dataset` file should have 75% of the data.</span></span>
- <span data-ttu-id="52fc3-165">`validation-dataset` 文件应拥有 15% 的数据。</span><span class="sxs-lookup"><span data-stu-id="52fc3-165">`validation-dataset` file should have 15% of the data.</span></span>
- <span data-ttu-id="52fc3-166">`test-dataset` 文件应拥有 10% 的数据。</span><span class="sxs-lookup"><span data-stu-id="52fc3-166">`test-dataset` file should have 10% of the data.</span></span>

<span data-ttu-id="52fc3-167">在任何情况下，这些百分比都将由使用 CLI 的用户决定，用户将提供已经拆分的文件。</span><span class="sxs-lookup"><span data-stu-id="52fc3-167">In any case, those percentages will be decided by the user using the CLI who will provide the files already split.</span></span>

----------------------------------------------------------

<span data-ttu-id="52fc3-168">`--label-column-name | -n`（字符串）</span><span class="sxs-lookup"><span data-stu-id="52fc3-168">`--label-column-name | -n` (string)</span></span>

<span data-ttu-id="52fc3-169">借助此参数，可以使用数据集标头中设置的列名来指定特定的目的/目标列（想要预测的变量）。</span><span class="sxs-lookup"><span data-stu-id="52fc3-169">With this argument, a specific objective/target column (the variable that you want to predict) can be specified by using the column's name set in the dataset's header.</span></span>

<span data-ttu-id="52fc3-170">此参数仅用于受监管的 ML 任务，例如*分类问题*。</span><span class="sxs-lookup"><span data-stu-id="52fc3-170">This argument is used only for supervised ML tasks such as a *classification problem*.</span></span> <span data-ttu-id="52fc3-171">它不能用于不受监管的 ML 任务，例如*聚类分析*。</span><span class="sxs-lookup"><span data-stu-id="52fc3-171">It cannot be used for unsupervised ML Tasks such as *clustering*.</span></span>

----------------------------------------------------------

<span data-ttu-id="52fc3-172">`--label-column-index | -i`（整数）</span><span class="sxs-lookup"><span data-stu-id="52fc3-172">`--label-column-index | -i` (int)</span></span>

<span data-ttu-id="52fc3-173">借助此参数，可以使用数据集文件中列的数字索引（列索引值从 1 开始）来指定特定的目的/目标列（想要预测的变量）。</span><span class="sxs-lookup"><span data-stu-id="52fc3-173">With this argument, a specific objective/target column (the variable that you want to predict) can be specified by using the column's numeric index in the dataset's file (The column index values start at 1).</span></span>

<span data-ttu-id="52fc3-174">*注意：* 如果用户还使用 `--label-column-name`，则应使用 `--label-column-name`。</span><span class="sxs-lookup"><span data-stu-id="52fc3-174">*Note:* If the user is also using the `--label-column-name`, the `--label-column-name` is the one being used.</span></span>

<span data-ttu-id="52fc3-175">此参数仅用于受监管的 ML 任务，例如*分类问题*。</span><span class="sxs-lookup"><span data-stu-id="52fc3-175">This argument is used only for supervised ML task such as a *classification problem*.</span></span> <span data-ttu-id="52fc3-176">它不能用于不受监管的 ML 任务，例如*聚类分析*。</span><span class="sxs-lookup"><span data-stu-id="52fc3-176">It cannot be used for unsupervised ML Tasks such as *clustering*.</span></span>

----------------------------------------------------------

<span data-ttu-id="52fc3-177">`--ignore-columns | -I`（字符串）</span><span class="sxs-lookup"><span data-stu-id="52fc3-177">`--ignore-columns | -I` (string)</span></span>

<span data-ttu-id="52fc3-178">借助此参数，可以忽略数据集文件中的现有列，这样一来，训练过程便不会加载和使用它们。</span><span class="sxs-lookup"><span data-stu-id="52fc3-178">With this argument, you can ignore existing columns in the dataset file so they are not loaded and used by the training processes.</span></span>

<span data-ttu-id="52fc3-179">指定想要忽略的列名。</span><span class="sxs-lookup"><span data-stu-id="52fc3-179">Specify the columns names that you want to ignore.</span></span> <span data-ttu-id="52fc3-180">使用“, ”（逗号加空格）或“ ”（空格）分隔多个列名。</span><span class="sxs-lookup"><span data-stu-id="52fc3-180">Use ', ' (comma with space) or ' ' (space) to separate multiple column names.</span></span> <span data-ttu-id="52fc3-181">可以对包含空格的列名使用引号（例如，“logged in”）。</span><span class="sxs-lookup"><span data-stu-id="52fc3-181">You can use quotes for column names containing whitespace (e.g. "logged in").</span></span>

<span data-ttu-id="52fc3-182">示例:</span><span class="sxs-lookup"><span data-stu-id="52fc3-182">Example:</span></span>

`--ignore-columns email, address, id, logged_in`

----------------------------------------------------------

<span data-ttu-id="52fc3-183">`--has-header | -h`（布尔值）</span><span class="sxs-lookup"><span data-stu-id="52fc3-183">`--has-header | -h` (bool)</span></span>

<span data-ttu-id="52fc3-184">指定数据集文件是否拥有标头行。</span><span class="sxs-lookup"><span data-stu-id="52fc3-184">Specify if the dataset file(s) have a header row.</span></span>
<span data-ttu-id="52fc3-185">可能的值有：</span><span class="sxs-lookup"><span data-stu-id="52fc3-185">Possible values are:</span></span>
- `true`
- `false`

<span data-ttu-id="52fc3-186">如果用户未指定此参数，则默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="52fc3-186">The by default value is `true` if this argument is not specified by the user.</span></span>

<span data-ttu-id="52fc3-187">若要使用 `--label-column-name` 参数，需要在数据集文件中包含标头，并将 `--has-header` 设置为 `true`（默认值）。</span><span class="sxs-lookup"><span data-stu-id="52fc3-187">In order to use the `--label-column-name` argument, you need to have a header in the dataset file and `--has-header` set to `true` (which is by default).</span></span>

----------------------------------------------------------

<span data-ttu-id="52fc3-188">`--max-exploration-time | -x`（字符串）</span><span class="sxs-lookup"><span data-stu-id="52fc3-188">`--max-exploration-time | -x` (string)</span></span>

<span data-ttu-id="52fc3-189">默认情况下，最长探索时间为 10 秒。</span><span class="sxs-lookup"><span data-stu-id="52fc3-189">By default, the maximum exploration time is 10 seconds.</span></span>

<span data-ttu-id="52fc3-190">此参数设置探索多个训练程序和配置的过程的最长持续时间（以秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="52fc3-190">This argument sets the maximum time (in seconds) for the process to explore multiple trainers and configurations.</span></span> <span data-ttu-id="52fc3-191">如果提供的时间对于单次迭代来说太短（例如 2 秒），则可能会超出配置的时间。</span><span class="sxs-lookup"><span data-stu-id="52fc3-191">The configured time may be exceeded if the provided time is too short (say 2 seconds) for a single iteration.</span></span> <span data-ttu-id="52fc3-192">在这种情况下，实际时间是在单次迭代中生成一个模型配置所需的时间。</span><span class="sxs-lookup"><span data-stu-id="52fc3-192">In this case, the actual time is the required time to produce one model configuration in a single iteration.</span></span>

<span data-ttu-id="52fc3-193">迭代所需的时间可能因数据集的大小而异。</span><span class="sxs-lookup"><span data-stu-id="52fc3-193">The needed time for iterations can vary depending on the size of the dataset.</span></span>

----------------------------------------------------------

<span data-ttu-id="52fc3-194">`--cache | -c`（字符串）</span><span class="sxs-lookup"><span data-stu-id="52fc3-194">`--cache | -c` (string)</span></span>

<span data-ttu-id="52fc3-195">如果使用缓存，则整个训练数据集将在内存中加载。</span><span class="sxs-lookup"><span data-stu-id="52fc3-195">If you use caching, the whole training dataset will be loaded in-memory.</span></span>

<span data-ttu-id="52fc3-196">对于中小型数据集，使用缓存可以大幅提高训练性能，这意味着训练时间可以比不使用缓存时更短。</span><span class="sxs-lookup"><span data-stu-id="52fc3-196">For small and medium datasets, using cache can drastically improve the training performance, meaning the training time can be shorter than when you don't use cache.</span></span>

<span data-ttu-id="52fc3-197">但是，对于大型数据集，在内存中加载所有数据可能会产生负面影响，因为可能会出现内存不足的情况。</span><span class="sxs-lookup"><span data-stu-id="52fc3-197">However, for large datasets, loading all the data in memory can impact negatively since you might get out of memory.</span></span> <span data-ttu-id="52fc3-198">如果使用大型数据集文件进行训练而不使用缓存，ML.NET 将在训练期间需要加载更多数据时从驱动器中流式传输数据块。</span><span class="sxs-lookup"><span data-stu-id="52fc3-198">When training with large dataset files and not using cache, ML.NET will be streaming chunks of data from the drive when it needs to load more data while training.</span></span>

<span data-ttu-id="52fc3-199">你可以指定以下值：</span><span class="sxs-lookup"><span data-stu-id="52fc3-199">You can specify the following values:</span></span>

<span data-ttu-id="52fc3-200">`on`：强制在训练时使用缓存。</span><span class="sxs-lookup"><span data-stu-id="52fc3-200">`on`: Forces cache to be used when training.</span></span>
<span data-ttu-id="52fc3-201">`off`：强制在训练时不使用缓存。</span><span class="sxs-lookup"><span data-stu-id="52fc3-201">`off`: Forces cache not to be used when training.</span></span>
<span data-ttu-id="52fc3-202">`auto`：是否使用缓存取决于 AutoML 试探法。</span><span class="sxs-lookup"><span data-stu-id="52fc3-202">`auto`: Depending on AutoML heuristics, the cache will be used or not.</span></span> <span data-ttu-id="52fc3-203">通常情况下，如果使用 `auto` 选项，小型/中型数据集将使用缓存，而大型数据集将不使用缓存。</span><span class="sxs-lookup"><span data-stu-id="52fc3-203">Usually, small/medium datasets will use cache and large datasets won't use cache if you use the `auto` choice.</span></span>

<span data-ttu-id="52fc3-204">如果未指定 `--cache` 参数，则默认情况下将使用缓存 `auto` 配置。</span><span class="sxs-lookup"><span data-stu-id="52fc3-204">If you don't specify the `--cache` parameter, then the cache `auto` configuration will be used by default.</span></span>

----------------------------------------------------------

<span data-ttu-id="52fc3-205">`--name | -N`（字符串）</span><span class="sxs-lookup"><span data-stu-id="52fc3-205">`--name | -N` (string)</span></span>

<span data-ttu-id="52fc3-206">创建的输出项目或解决方案的名称。</span><span class="sxs-lookup"><span data-stu-id="52fc3-206">The name for the created output project or solution.</span></span> <span data-ttu-id="52fc3-207">如果未指定名称，则使用名称 `sample-{mltask}`。</span><span class="sxs-lookup"><span data-stu-id="52fc3-207">If no name is specified, the name `sample-{mltask}` is used.</span></span>

<span data-ttu-id="52fc3-208">ML.NET 模型文件（.zip 文件）也将获得相同的名称。</span><span class="sxs-lookup"><span data-stu-id="52fc3-208">The ML.NET model file (.ZIP file) will get the same name, as well.</span></span>

----------------------------------------------------------

<span data-ttu-id="52fc3-209">`--output-path | -o`（字符串）</span><span class="sxs-lookup"><span data-stu-id="52fc3-209">`--output-path | -o` (string)</span></span>

<span data-ttu-id="52fc3-210">用于放置生成的输出的根位置/文件夹。</span><span class="sxs-lookup"><span data-stu-id="52fc3-210">Root location/folder to place the generated output.</span></span> <span data-ttu-id="52fc3-211">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="52fc3-211">The default is the current directory.</span></span>

----------------------------------------------------------

<span data-ttu-id="52fc3-212">`--verbosity | -V`（字符串）</span><span class="sxs-lookup"><span data-stu-id="52fc3-212">`--verbosity | -V` (string)</span></span>

<span data-ttu-id="52fc3-213">设置标准输出的详细级别。</span><span class="sxs-lookup"><span data-stu-id="52fc3-213">Sets the verbosity level of the standard output.</span></span>

<span data-ttu-id="52fc3-214">允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="52fc3-214">Allowed values are:</span></span>

- `q[uiet]`
- <span data-ttu-id="52fc3-215">`m[inimal]`（默认情况）</span><span class="sxs-lookup"><span data-stu-id="52fc3-215">`m[inimal]`  (by default)</span></span>
- <span data-ttu-id="52fc3-216">`diag[nostic]`（日志记录信息级别）</span><span class="sxs-lookup"><span data-stu-id="52fc3-216">`diag[nostic]` (logging information level)</span></span>

<span data-ttu-id="52fc3-217">默认情况下，CLI 工具应在运行时应显示一些最低限度的反馈（最小值），例如提及它正在运行以及剩余多少时间或已完成时间的百分比（如果可能）。</span><span class="sxs-lookup"><span data-stu-id="52fc3-217">By default, the CLI tool should show some minimum feedback (minimal) when working, such as mentioning that it is working and if possible how much time is left or what % of the time is completed.</span></span>

----------------------------------------------------------

`-h|--help`

<span data-ttu-id="52fc3-218">打印命令帮助，其中包含对每个命令的参数的描述。</span><span class="sxs-lookup"><span data-stu-id="52fc3-218">Prints out help for the command with a description for each command's parameter.</span></span>

----------------------------------------------------------

## <a name="see-also"></a><span data-ttu-id="52fc3-219">请参阅</span><span class="sxs-lookup"><span data-stu-id="52fc3-219">See also</span></span>

- [<span data-ttu-id="52fc3-220">如何安装 ML.NET CLI 工具</span><span class="sxs-lookup"><span data-stu-id="52fc3-220">How to install the ML.NET CLI tool</span></span>](../how-to-guides/install-ml-net-cli.md)
- [<span data-ttu-id="52fc3-221">使用 ML.NET CLI 自动进行模型训练</span><span class="sxs-lookup"><span data-stu-id="52fc3-221">Automate model training with the ML.NET CLI</span></span>](../automate-training-with-cli.md)
- [<span data-ttu-id="52fc3-222">教程：使用 ML.NET CLI 自动生成二元分类器</span><span class="sxs-lookup"><span data-stu-id="52fc3-222">Tutorial: Auto generate a binary classifier using the ML.NET CLI</span></span>](../tutorials/mlnet-cli.md)
- [<span data-ttu-id="52fc3-223">ML.NET CLI 中的遥测</span><span class="sxs-lookup"><span data-stu-id="52fc3-223">Telemetry in ML.NET CLI</span></span>](../resources/ml-net-cli-telemetry.md)

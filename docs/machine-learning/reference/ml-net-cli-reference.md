---
title: ML.NET CLI 命令参考
description: ML.NET CLI 工具中 auto-train 命令的概述、示例和参考。
ms.date: 12/18/2019
ms.custom: mlnet-tooling
ms.openlocfilehash: bb161c596a76134876ee2bf0a6229bc551e0dad2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "78848920"
---
# <a name="the-mlnet-cli-command-reference"></a><span data-ttu-id="830aa-103">ML.NET CLI 命令参考</span><span class="sxs-lookup"><span data-stu-id="830aa-103">The ML.NET CLI command reference</span></span>

<span data-ttu-id="830aa-104">`auto-train` 命令是 ML.NET CLI 工具提供的主要命令。</span><span class="sxs-lookup"><span data-stu-id="830aa-104">The `auto-train` command is the main command provided by the ML.NET CLI tool.</span></span> <span data-ttu-id="830aa-105">该命令允许使用自动化机器学习 (AutoML) 生成高质量的 ML.NET 模型以及用于运行该模型/对该模型评分的示例 C# 代码。</span><span class="sxs-lookup"><span data-stu-id="830aa-105">The command allows you to generate a good quality ML.NET model using automated machine learning (AutoML) as well as the example C# code to run/score that model.</span></span> <span data-ttu-id="830aa-106">此外，还会生成用于训练模型的 C# 代码，以便你可以研究模型的算法和设置。</span><span class="sxs-lookup"><span data-stu-id="830aa-106">In addition, the C# code to train the model is generated for you to research the algorithm and settings of the model.</span></span>

> [!NOTE]
> <span data-ttu-id="830aa-107">本主题涉及目前处于预览状态的 ML.NET CLI 和 ML.NET AutoML，且材料可能会有所变化。</span><span class="sxs-lookup"><span data-stu-id="830aa-107">This topic refers to ML.NET CLI and ML.NET AutoML, which are currently in Preview, and material may be subject to change.</span></span>

## <a name="overview"></a><span data-ttu-id="830aa-108">概述</span><span class="sxs-lookup"><span data-stu-id="830aa-108">Overview</span></span>

<span data-ttu-id="830aa-109">示例用法：</span><span class="sxs-lookup"><span data-stu-id="830aa-109">Example usage:</span></span>

```console
mlnet auto-train --task regression --dataset "cars.csv" --label-column-name price
```

<span data-ttu-id="830aa-110">`mlnet auto-train` 命令生成以下资产：</span><span class="sxs-lookup"><span data-stu-id="830aa-110">The `mlnet auto-train` command generates the following assets:</span></span>

- <span data-ttu-id="830aa-111">可供使用的序列化模型 .zip 文件（“最佳模型”）。</span><span class="sxs-lookup"><span data-stu-id="830aa-111">A serialized model .zip ("best model") ready to use.</span></span>
- <span data-ttu-id="830aa-112">用于运行生成的模型和对其进行评分的 C# 代码。</span><span class="sxs-lookup"><span data-stu-id="830aa-112">C# code to run/score that generated model.</span></span>
- <span data-ttu-id="830aa-113">包含用于生成该模型的训练代码的 C# 代码。</span><span class="sxs-lookup"><span data-stu-id="830aa-113">C# code with the training code used to generate that model.</span></span>

<span data-ttu-id="830aa-114">前两个资产可以直接用于最终用户应用（ASP.NET Core Web 应用、服务、桌面应用等），以使用模型进行预测。</span><span class="sxs-lookup"><span data-stu-id="830aa-114">The first two assets can directly be used in your end-user apps (ASP.NET Core web app, services, desktop app and more) to make predictions with the model.</span></span>

<span data-ttu-id="830aa-115">第三个资产（训练代码）显示 CLI 用于训练生成的模型的 ML.NET API 代码，因此可以研究模型的特定算法和设置。</span><span class="sxs-lookup"><span data-stu-id="830aa-115">The third asset, the training code, shows you what ML.NET API code was used by the CLI to train the generated model, so you can investigate the specific algorithm and settings of the model.</span></span>

## <a name="examples"></a><span data-ttu-id="830aa-116">示例</span><span class="sxs-lookup"><span data-stu-id="830aa-116">Examples</span></span>

<span data-ttu-id="830aa-117">用于二元分类问题的最简单的 CLI 命令（AutoML 从提供的数据中推断出大部分配置）：</span><span class="sxs-lookup"><span data-stu-id="830aa-117">The simplest CLI command for a binary classification problem (AutoML infers most of the configuration from the provided data):</span></span>

```console
mlnet auto-train --task binary-classification --dataset "customer-feedback.tsv" --label-column-name Sentiment
```

<span data-ttu-id="830aa-118">另一个用于回归问题的简单 CLI 命令：</span><span class="sxs-lookup"><span data-stu-id="830aa-118">Another simple CLI command for a regression problem:</span></span>

``` console
mlnet auto-train --task regression --dataset "cars.csv" --label-column-name Price
```

<span data-ttu-id="830aa-119">使用训练数据集、测试数据集和进一步的自定义显式参数创建和训练二元分类模型：</span><span class="sxs-lookup"><span data-stu-id="830aa-119">Create and train a binary-classification model with a train dataset, a test dataset, and further customization explicit arguments:</span></span>

```console
mlnet auto-train --task binary-classification --dataset "/MyDataSets/Population-Training.csv" --test-dataset "/MyDataSets/Population-Test.csv" --label-column-name "InsuranceRisk" --cache on --max-exploration-time 600
```

## <a name="command-options"></a><span data-ttu-id="830aa-120">命令选项</span><span class="sxs-lookup"><span data-stu-id="830aa-120">Command options</span></span>

<span data-ttu-id="830aa-121">`mlnet auto-train` 根据提供的数据集训练多个模型并最终选择最佳模型，然后将其作为序列化 .zip 文件保存，并生成相关 C# 代码用于评分和训练。</span><span class="sxs-lookup"><span data-stu-id="830aa-121">`mlnet auto-train` trains multiple models based on the provided dataset and finally selects the best model, saves it as a serialized .zip file plus generates related C# code for scoring and training.</span></span>

```console
mlnet auto-train

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

<span data-ttu-id="830aa-122">无效输入选项会导致 CLI 工具发出有效输入和错误消息列表。</span><span class="sxs-lookup"><span data-stu-id="830aa-122">Invalid input options cause the CLI tool to emit a list of valid inputs and an error message.</span></span>

## <a name="task"></a><span data-ttu-id="830aa-123">任务</span><span class="sxs-lookup"><span data-stu-id="830aa-123">Task</span></span>

<span data-ttu-id="830aa-124">`--task | --mltask | -T`（字符串）</span><span class="sxs-lookup"><span data-stu-id="830aa-124">`--task | --mltask | -T` (string)</span></span>

<span data-ttu-id="830aa-125">提供要解决的 ML 问题的单个字符串。</span><span class="sxs-lookup"><span data-stu-id="830aa-125">A single string providing the ML problem to solve.</span></span> <span data-ttu-id="830aa-126">例如，以下任何任务（CLI 最终将支持 AutoML 支持的所有任务）：</span><span class="sxs-lookup"><span data-stu-id="830aa-126">For instance, any of the following tasks (The CLI will eventually support all tasks supported in AutoML):</span></span>

- <span data-ttu-id="830aa-127">`regression` - 如果 ML 模型将用于预测数字值，则选择。</span><span class="sxs-lookup"><span data-stu-id="830aa-127">`regression` - Choose if the ML Model will be used to predict a numeric value</span></span>
- <span data-ttu-id="830aa-128">`binary-classification` - 如果 ML 模型结果有两个可能的分类布尔值（0 或 1），则选择。</span><span class="sxs-lookup"><span data-stu-id="830aa-128">`binary-classification` - Choose if the ML Model result has two possible categorical boolean values (0 or 1).</span></span>
- <span data-ttu-id="830aa-129">`multiclass-classification` - 如果 ML 模型结果有多个分类可能值，则选择。</span><span class="sxs-lookup"><span data-stu-id="830aa-129">`multiclass-classification` - Choose if the ML Model result has multiple categorical possible values.</span></span>

<span data-ttu-id="830aa-130">仅应在此参数中提供一个 ML 任务。</span><span class="sxs-lookup"><span data-stu-id="830aa-130">Only one ML task should be provided in this argument.</span></span>

## <a name="dataset"></a><span data-ttu-id="830aa-131">数据集</span><span class="sxs-lookup"><span data-stu-id="830aa-131">Dataset</span></span>

<span data-ttu-id="830aa-132">`--dataset | -d`（字符串）</span><span class="sxs-lookup"><span data-stu-id="830aa-132">`--dataset | -d` (string)</span></span>

<span data-ttu-id="830aa-133">此参数向以下任一选项提供文件路径：</span><span class="sxs-lookup"><span data-stu-id="830aa-133">This argument provides the filepath to either one of the following options:</span></span>

- <span data-ttu-id="830aa-134">*A：整个数据集文件：* 如果使用此选项且用户未提供 `--test-dataset` 和 `--validation-dataset`，则将在内部使用交叉验证（K 折等）或自动数据拆分方法来验证模型。</span><span class="sxs-lookup"><span data-stu-id="830aa-134">*A: The whole dataset file:* If using this option and the user is not providing `--test-dataset` and `--validation-dataset`, then cross-validation (k-fold, etc.) or automated data split approaches will be used internally for validating the model.</span></span> <span data-ttu-id="830aa-135">在这种情况下，用户将只需要提供数据集文件路径。</span><span class="sxs-lookup"><span data-stu-id="830aa-135">In that case, the user will just need to provide the dataset filepath.</span></span>

- <span data-ttu-id="830aa-136">*B：训练数据集文件：* 如果用户还提供用于模型验证的数据集（使用 `--test-dataset` 和可选的 `--validation-dataset`），则 `--dataset` 参数意味着仅拥有“训练数据集”。</span><span class="sxs-lookup"><span data-stu-id="830aa-136">*B: The training dataset file:* If the user is also providing datasets for model validation (using `--test-dataset` and optionally `--validation-dataset`), then the `--dataset` argument means to only have the "training dataset".</span></span> <span data-ttu-id="830aa-137">例如，当使用 80%-20% 方法来验证模型的质量以及获取准确性指标时，“训练数据集”将拥有 80% 的数据，而“测试数据集”将拥有 20% 的数据。</span><span class="sxs-lookup"><span data-stu-id="830aa-137">For example, when using an 80% - 20% approach to validate the quality of the model and to obtain accuracy metrics, the "training dataset" will have 80% of the data and the "test dataset" would have 20% of the data.</span></span>

## <a name="test-dataset"></a><span data-ttu-id="830aa-138">测试数据集</span><span class="sxs-lookup"><span data-stu-id="830aa-138">Test dataset</span></span>

<span data-ttu-id="830aa-139">`--test-dataset | -t`（字符串）</span><span class="sxs-lookup"><span data-stu-id="830aa-139">`--test-dataset | -t` (string)</span></span>

<span data-ttu-id="830aa-140">指向测试数据集文件的文件路径，例如，在进行常规验证以获取准确性指标时使用 80%-20% 方法的情况。</span><span class="sxs-lookup"><span data-stu-id="830aa-140">File path pointing to the test dataset file, for example when using an 80% - 20% approach when making regular validations to obtain accuracy metrics.</span></span>

<span data-ttu-id="830aa-141">如果使用 `--test-dataset`，则还需要 `--dataset`。</span><span class="sxs-lookup"><span data-stu-id="830aa-141">If using `--test-dataset`, then `--dataset` is also required.</span></span>

<span data-ttu-id="830aa-142">除非使用 --validation-dataset，否则 `--test-dataset` 参数是可选的。</span><span class="sxs-lookup"><span data-stu-id="830aa-142">The `--test-dataset` argument is optional unless the --validation-dataset is used.</span></span> <span data-ttu-id="830aa-143">在这种情况下，用户必须使用三个参数。</span><span class="sxs-lookup"><span data-stu-id="830aa-143">In that case, the user must use the three arguments.</span></span>

## <a name="validation-dataset"></a><span data-ttu-id="830aa-144">验证数据集</span><span class="sxs-lookup"><span data-stu-id="830aa-144">Validation dataset</span></span>

<span data-ttu-id="830aa-145">`--validation-dataset | -v`（字符串）</span><span class="sxs-lookup"><span data-stu-id="830aa-145">`--validation-dataset | -v` (string)</span></span>

<span data-ttu-id="830aa-146">指向验证数据集文件的文件路径。</span><span class="sxs-lookup"><span data-stu-id="830aa-146">File path pointing to the validation dataset file.</span></span> <span data-ttu-id="830aa-147">验证数据集在任何情况下都是可选的。</span><span class="sxs-lookup"><span data-stu-id="830aa-147">The validation dataset is optional, in any case.</span></span>

<span data-ttu-id="830aa-148">如果使用 `validation dataset`，则行为应为：</span><span class="sxs-lookup"><span data-stu-id="830aa-148">If using a `validation dataset`, the behavior should be:</span></span>

- <span data-ttu-id="830aa-149">`test-dataset` 和 `--dataset` 参数也是必需的。</span><span class="sxs-lookup"><span data-stu-id="830aa-149">The `test-dataset` and `--dataset` arguments are also required.</span></span>

- <span data-ttu-id="830aa-150">`validation-dataset` 数据集用于估算模型选择的预测误差。</span><span class="sxs-lookup"><span data-stu-id="830aa-150">The `validation-dataset` dataset is used to estimate prediction error for model selection.</span></span>

- <span data-ttu-id="830aa-151">`test-dataset` 用于评估最终选定模型的泛化误差。</span><span class="sxs-lookup"><span data-stu-id="830aa-151">The `test-dataset` is used for assessment of the generalization error of the final chosen model.</span></span> <span data-ttu-id="830aa-152">理想情况下，测试集应保存在“保管库”中，并仅在数据分析结束时显示。</span><span class="sxs-lookup"><span data-stu-id="830aa-152">Ideally, the test set should be kept in a “vault,” and be brought out only at the end of the data analysis.</span></span>

<span data-ttu-id="830aa-153">一般来说，使用 `validation dataset` 以及 `test dataset` 时，验证阶段拆分为两部分：</span><span class="sxs-lookup"><span data-stu-id="830aa-153">Basically, when using a `validation dataset` plus the `test dataset`, the validation phase is split into two parts:</span></span>

1. <span data-ttu-id="830aa-154">在第一部分中，只需查看模型并使用验证数据选择性能最佳的方法即可（= 验证）</span><span class="sxs-lookup"><span data-stu-id="830aa-154">In the first part, you just look at your models and select the best performing approach using the validation data (=validation)</span></span>
2. <span data-ttu-id="830aa-155">然后，估算选定方法的准确性（= 测试）。</span><span class="sxs-lookup"><span data-stu-id="830aa-155">Then you estimate the accuracy of the selected approach (=test).</span></span>

<span data-ttu-id="830aa-156">因此，数据分离可以是 80/10/10 或 75/15/10。</span><span class="sxs-lookup"><span data-stu-id="830aa-156">Hence, the separation of data could be 80/10/10 or 75/15/10.</span></span> <span data-ttu-id="830aa-157">例如：</span><span class="sxs-lookup"><span data-stu-id="830aa-157">For example:</span></span>

- <span data-ttu-id="830aa-158">`training-dataset` 文件应拥有 75% 的数据。</span><span class="sxs-lookup"><span data-stu-id="830aa-158">`training-dataset` file should have 75% of the data.</span></span>
- <span data-ttu-id="830aa-159">`validation-dataset` 文件应拥有 15% 的数据。</span><span class="sxs-lookup"><span data-stu-id="830aa-159">`validation-dataset` file should have 15% of the data.</span></span>
- <span data-ttu-id="830aa-160">`test-dataset` 文件应拥有 10% 的数据。</span><span class="sxs-lookup"><span data-stu-id="830aa-160">`test-dataset` file should have 10% of the data.</span></span>

<span data-ttu-id="830aa-161">在任何情况下，这些百分比都将由使用 CLI 的用户决定，用户将提供已经拆分的文件。</span><span class="sxs-lookup"><span data-stu-id="830aa-161">In any case, those percentages will be decided by the user using the CLI who will provide the files already split.</span></span>

## <a name="label-column-name"></a><span data-ttu-id="830aa-162">标签列名称</span><span class="sxs-lookup"><span data-stu-id="830aa-162">Label column name</span></span>

<span data-ttu-id="830aa-163">`--label-column-name | -n`（字符串）</span><span class="sxs-lookup"><span data-stu-id="830aa-163">`--label-column-name | -n` (string)</span></span>

<span data-ttu-id="830aa-164">借助此参数，可以使用数据集标头中设置的列名来指定特定的目的/目标列（想要预测的变量）。</span><span class="sxs-lookup"><span data-stu-id="830aa-164">With this argument, a specific objective/target column (the variable that you want to predict) can be specified by using the column's name set in the dataset's header.</span></span>

<span data-ttu-id="830aa-165">此参数仅用于受监管的 ML 任务，例如*分类问题*。</span><span class="sxs-lookup"><span data-stu-id="830aa-165">This argument is used only for supervised ML tasks such as a *classification problem*.</span></span> <span data-ttu-id="830aa-166">它不能用于不受监管的 ML 任务，例如*聚类分析*。</span><span class="sxs-lookup"><span data-stu-id="830aa-166">It cannot be used for unsupervised ML Tasks such as *clustering*.</span></span>

## <a name="label-column-index"></a><span data-ttu-id="830aa-167">标签列索引</span><span class="sxs-lookup"><span data-stu-id="830aa-167">Label column index</span></span>

<span data-ttu-id="830aa-168">`--label-column-index | -i`（整数）</span><span class="sxs-lookup"><span data-stu-id="830aa-168">`--label-column-index | -i` (int)</span></span>

<span data-ttu-id="830aa-169">借助此参数，可以使用数据集文件中列的数字索引（列索引值从 1 开始）来指定特定的目的/目标列（想要预测的变量）。</span><span class="sxs-lookup"><span data-stu-id="830aa-169">With this argument, a specific objective/target column (the variable that you want to predict) can be specified by using the column's numeric index in the dataset's file (The column index values start at 1).</span></span>

<span data-ttu-id="830aa-170">*注意：* 如果用户还使用 `--label-column-name`，则应使用 `--label-column-name`。</span><span class="sxs-lookup"><span data-stu-id="830aa-170">*Note:* If the user is also using the `--label-column-name`, the `--label-column-name` is the one being used.</span></span>

<span data-ttu-id="830aa-171">此参数仅用于受监管的 ML 任务，例如*分类问题*。</span><span class="sxs-lookup"><span data-stu-id="830aa-171">This argument is used only for supervised ML task such as a *classification problem*.</span></span> <span data-ttu-id="830aa-172">它不能用于不受监管的 ML 任务，例如*聚类分析*。</span><span class="sxs-lookup"><span data-stu-id="830aa-172">It cannot be used for unsupervised ML Tasks such as *clustering*.</span></span>

## <a name="ignore-columns"></a><span data-ttu-id="830aa-173">忽略列</span><span class="sxs-lookup"><span data-stu-id="830aa-173">Ignore columns</span></span>

<span data-ttu-id="830aa-174">`--ignore-columns | -I`（字符串）</span><span class="sxs-lookup"><span data-stu-id="830aa-174">`--ignore-columns | -I` (string)</span></span>

<span data-ttu-id="830aa-175">借助此参数，可以忽略数据集文件中的现有列，这样一来，训练过程便不会加载和使用它们。</span><span class="sxs-lookup"><span data-stu-id="830aa-175">With this argument, you can ignore existing columns in the dataset file so they are not loaded and used by the training processes.</span></span>

<span data-ttu-id="830aa-176">指定想要忽略的列名。</span><span class="sxs-lookup"><span data-stu-id="830aa-176">Specify the columns names that you want to ignore.</span></span> <span data-ttu-id="830aa-177">使用“, ”（逗号加空格）或“ ”（空格）分隔多个列名。</span><span class="sxs-lookup"><span data-stu-id="830aa-177">Use ', ' (comma with space) or ' ' (space) to separate multiple column names.</span></span> <span data-ttu-id="830aa-178">可以对包含空格的列名使用引号（例如，“logged in”）。</span><span class="sxs-lookup"><span data-stu-id="830aa-178">You can use quotes for column names containing whitespace (e.g. "logged in").</span></span>

<span data-ttu-id="830aa-179">示例：</span><span class="sxs-lookup"><span data-stu-id="830aa-179">Example:</span></span>

`--ignore-columns email, address, id, logged_in`

## <a name="has-header"></a><span data-ttu-id="830aa-180">具有标头</span><span class="sxs-lookup"><span data-stu-id="830aa-180">Has header</span></span>

<span data-ttu-id="830aa-181">`--has-header | -h`（布尔值）</span><span class="sxs-lookup"><span data-stu-id="830aa-181">`--has-header | -h` (bool)</span></span>

<span data-ttu-id="830aa-182">指定数据集文件是否拥有标头行。</span><span class="sxs-lookup"><span data-stu-id="830aa-182">Specify if the dataset file(s) have a header row.</span></span>
<span data-ttu-id="830aa-183">可能的值有：</span><span class="sxs-lookup"><span data-stu-id="830aa-183">Possible values are:</span></span>

- `true`
- `false`

<span data-ttu-id="830aa-184">如果用户未指定此参数，则默认值为 `true`。</span><span class="sxs-lookup"><span data-stu-id="830aa-184">The by default value is `true` if this argument is not specified by the user.</span></span>

<span data-ttu-id="830aa-185">若要使用 `--label-column-name` 参数，需要在数据集文件中包含标头，并将 `--has-header` 设置为 `true`（默认值）。</span><span class="sxs-lookup"><span data-stu-id="830aa-185">In order to use the `--label-column-name` argument, you need to have a header in the dataset file and `--has-header` set to `true` (which is by default).</span></span>

## <a name="max-exploration-time"></a><span data-ttu-id="830aa-186">最长探索时间</span><span class="sxs-lookup"><span data-stu-id="830aa-186">Max exploration time</span></span>

<span data-ttu-id="830aa-187">`--max-exploration-time | -x`（字符串）</span><span class="sxs-lookup"><span data-stu-id="830aa-187">`--max-exploration-time | -x` (string)</span></span>

<span data-ttu-id="830aa-188">默认情况下，最长探索时间为 30 分钟。</span><span class="sxs-lookup"><span data-stu-id="830aa-188">By default, the maximum exploration time is 30 minutes.</span></span>

<span data-ttu-id="830aa-189">此参数设置探索多个训练程序和配置的过程的最长持续时间（以秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="830aa-189">This argument sets the maximum time (in seconds) for the process to explore multiple trainers and configurations.</span></span> <span data-ttu-id="830aa-190">如果提供的时间对于单次迭代来说太短（例如 2 秒），则可能会超出配置的时间。</span><span class="sxs-lookup"><span data-stu-id="830aa-190">The configured time may be exceeded if the provided time is too short (say 2 seconds) for a single iteration.</span></span> <span data-ttu-id="830aa-191">在这种情况下，实际时间是在单次迭代中生成一个模型配置所需的时间。</span><span class="sxs-lookup"><span data-stu-id="830aa-191">In this case, the actual time is the required time to produce one model configuration in a single iteration.</span></span>

<span data-ttu-id="830aa-192">迭代所需的时间可能因数据集的大小而异。</span><span class="sxs-lookup"><span data-stu-id="830aa-192">The needed time for iterations can vary depending on the size of the dataset.</span></span>

## <a name="cache"></a><span data-ttu-id="830aa-193">缓存</span><span class="sxs-lookup"><span data-stu-id="830aa-193">Cache</span></span>

<span data-ttu-id="830aa-194">`--cache | -c`（字符串）</span><span class="sxs-lookup"><span data-stu-id="830aa-194">`--cache | -c` (string)</span></span>

<span data-ttu-id="830aa-195">如果使用缓存，则整个训练数据集将在内存中加载。</span><span class="sxs-lookup"><span data-stu-id="830aa-195">If you use caching, the whole training dataset will be loaded in-memory.</span></span>

<span data-ttu-id="830aa-196">对于中小型数据集，使用缓存可以大幅提高训练性能，这意味着训练时间可以比不使用缓存时更短。</span><span class="sxs-lookup"><span data-stu-id="830aa-196">For small and medium datasets, using cache can drastically improve the training performance, meaning the training time can be shorter than when you don't use cache.</span></span>

<span data-ttu-id="830aa-197">但是，对于大型数据集，在内存中加载所有数据可能会产生负面影响，因为可能会出现内存不足的情况。</span><span class="sxs-lookup"><span data-stu-id="830aa-197">However, for large datasets, loading all the data in memory can impact negatively since you might get out of memory.</span></span> <span data-ttu-id="830aa-198">如果使用大型数据集文件进行训练而不使用缓存，ML.NET 将在训练期间需要加载更多数据时从驱动器中流式传输数据块。</span><span class="sxs-lookup"><span data-stu-id="830aa-198">When training with large dataset files and not using cache, ML.NET will be streaming chunks of data from the drive when it needs to load more data while training.</span></span>

<span data-ttu-id="830aa-199">你可以指定以下值：</span><span class="sxs-lookup"><span data-stu-id="830aa-199">You can specify the following values:</span></span>

<span data-ttu-id="830aa-200">`on`：强制在训练时使用缓存。</span><span class="sxs-lookup"><span data-stu-id="830aa-200">`on`: Forces cache to be used when training.</span></span>
<span data-ttu-id="830aa-201">`off`：强制在训练时不使用缓存。</span><span class="sxs-lookup"><span data-stu-id="830aa-201">`off`: Forces cache not to be used when training.</span></span>
<span data-ttu-id="830aa-202">`auto`：是否使用缓存取决于 AutoML 试探法。</span><span class="sxs-lookup"><span data-stu-id="830aa-202">`auto`: Depending on AutoML heuristics, the cache will be used or not.</span></span> <span data-ttu-id="830aa-203">通常情况下，如果使用 `auto` 选项，小型/中型数据集将使用缓存，而大型数据集将不使用缓存。</span><span class="sxs-lookup"><span data-stu-id="830aa-203">Usually, small/medium datasets will use cache and large datasets won't use cache if you use the `auto` choice.</span></span>

<span data-ttu-id="830aa-204">如果未指定 `--cache` 参数，则默认情况下将使用缓存 `auto` 配置。</span><span class="sxs-lookup"><span data-stu-id="830aa-204">If you don't specify the `--cache` parameter, then the cache `auto` configuration will be used by default.</span></span>

## <a name="name"></a><span data-ttu-id="830aa-205">“属性”</span><span class="sxs-lookup"><span data-stu-id="830aa-205">Name</span></span>

<span data-ttu-id="830aa-206">`--name | -N`（字符串）</span><span class="sxs-lookup"><span data-stu-id="830aa-206">`--name | -N` (string)</span></span>

<span data-ttu-id="830aa-207">创建的输出项目或解决方案的名称。</span><span class="sxs-lookup"><span data-stu-id="830aa-207">The name for the created output project or solution.</span></span> <span data-ttu-id="830aa-208">如果未指定名称，则使用名称 `sample-{mltask}`。</span><span class="sxs-lookup"><span data-stu-id="830aa-208">If no name is specified, the name `sample-{mltask}` is used.</span></span>

<span data-ttu-id="830aa-209">ML.NET 模型文件（.zip 文件）也将获得相同的名称。</span><span class="sxs-lookup"><span data-stu-id="830aa-209">The ML.NET model file (.ZIP file) will get the same name, as well.</span></span>

## <a name="output-path"></a><span data-ttu-id="830aa-210">输出路径</span><span class="sxs-lookup"><span data-stu-id="830aa-210">Output path</span></span>

<span data-ttu-id="830aa-211">`--output-path | -o`（字符串）</span><span class="sxs-lookup"><span data-stu-id="830aa-211">`--output-path | -o` (string)</span></span>

<span data-ttu-id="830aa-212">用于放置生成的输出的根位置/文件夹。</span><span class="sxs-lookup"><span data-stu-id="830aa-212">Root location/folder to place the generated output.</span></span> <span data-ttu-id="830aa-213">默认为当前目录。</span><span class="sxs-lookup"><span data-stu-id="830aa-213">The default is the current directory.</span></span>

## <a name="verbosity"></a><span data-ttu-id="830aa-214">详细级别</span><span class="sxs-lookup"><span data-stu-id="830aa-214">Verbosity</span></span>

<span data-ttu-id="830aa-215">`--verbosity | -V`（字符串）</span><span class="sxs-lookup"><span data-stu-id="830aa-215">`--verbosity | -V` (string)</span></span>

<span data-ttu-id="830aa-216">设置标准输出的详细级别。</span><span class="sxs-lookup"><span data-stu-id="830aa-216">Sets the verbosity level of the standard output.</span></span>

<span data-ttu-id="830aa-217">允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="830aa-217">Allowed values are:</span></span>

- `q[uiet]`
- <span data-ttu-id="830aa-218">`m[inimal]`（默认情况）</span><span class="sxs-lookup"><span data-stu-id="830aa-218">`m[inimal]`  (by default)</span></span>
- <span data-ttu-id="830aa-219">`diag[nostic]`（日志记录信息级别）</span><span class="sxs-lookup"><span data-stu-id="830aa-219">`diag[nostic]` (logging information level)</span></span>

<span data-ttu-id="830aa-220">默认情况下，CLI 工具应在运行时应显示一些最低限度的反馈（最小值），例如提及它正在运行以及剩余多少时间或已完成时间的百分比（如果可能）。</span><span class="sxs-lookup"><span data-stu-id="830aa-220">By default, the CLI tool should show some minimum feedback (minimal) when working, such as mentioning that it is working and if possible how much time is left or what % of the time is completed.</span></span>

## <a name="help"></a><span data-ttu-id="830aa-221">帮助</span><span class="sxs-lookup"><span data-stu-id="830aa-221">Help</span></span>

`-h|--help`

<span data-ttu-id="830aa-222">打印命令帮助，其中包含对每个命令的参数的描述。</span><span class="sxs-lookup"><span data-stu-id="830aa-222">Prints out help for the command with a description for each command's parameter.</span></span>

## <a name="see-also"></a><span data-ttu-id="830aa-223">请参阅</span><span class="sxs-lookup"><span data-stu-id="830aa-223">See also</span></span>

- [<span data-ttu-id="830aa-224">如何安装 ML.NET CLI 工具</span><span class="sxs-lookup"><span data-stu-id="830aa-224">How to install the ML.NET CLI tool</span></span>](../how-to-guides/install-ml-net-cli.md)
- [<span data-ttu-id="830aa-225">ML.NET CLI 概述</span><span class="sxs-lookup"><span data-stu-id="830aa-225">Overview of the ML.NET CLI</span></span>](../automate-training-with-cli.md)
- [<span data-ttu-id="830aa-226">教程：使用 ML.NET CLI 分析情绪</span><span class="sxs-lookup"><span data-stu-id="830aa-226">Tutorial: Analyze sentiment using the ML.NET CLI</span></span>](../tutorials/sentiment-analysis-cli.md)
- [<span data-ttu-id="830aa-227">ML.NET CLI 中的遥测</span><span class="sxs-lookup"><span data-stu-id="830aa-227">Telemetry in ML.NET CLI</span></span>](../resources/ml-net-cli-telemetry.md)

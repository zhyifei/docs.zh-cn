---
title: 使用 ML.NET CLI 自动进行模型训练
description: 了解如何使用 ML.NET CLI 工具通过命令行自动训练最佳模型。
author: CESARDELATORRE
ms.date: 04/17/2019
ms.custom: how-to
ms.openlocfilehash: 33383582140d9df4290a0bbf30659301af837d1d
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2019
ms.locfileid: "65065890"
---
# <a name="automate-model-training-with-the-mlnet-cli"></a><span data-ttu-id="4bc8c-103">使用 ML.NET CLI 自动进行模型训练</span><span class="sxs-lookup"><span data-stu-id="4bc8c-103">Automate model training with the ML.NET CLI</span></span>

<span data-ttu-id="4bc8c-104">在学习 ML.NET 时，ML.NET CLI 为 .NET 开发人员“普及”ML.NET。</span><span class="sxs-lookup"><span data-stu-id="4bc8c-104">The ML.NET CLI "democratizes" ML.NET for .NET developers when learning ML.NET.</span></span>

<span data-ttu-id="4bc8c-105">若要单独使用 ML.NET API（不使用 ML.NET AutoML CLI），需要选择训练程序（针对特定任务的机器学习算法的实现），以及要应用到数据的数据转换集（特征工程）。</span><span class="sxs-lookup"><span data-stu-id="4bc8c-105">To use the ML.NET API by itself, (without the ML.NET AutoML CLI) you need to choose a trainer (implementation of a machine learning algorithm for a particular task), and the set of data transformations (feature engineering) to apply to your data.</span></span> <span data-ttu-id="4bc8c-106">每个数据集的最佳管道各不相同，从所有选择中选择最佳算法增加了复杂性。</span><span class="sxs-lookup"><span data-stu-id="4bc8c-106">The optimal pipeline will vary for each dataset and selecting the optimal algorithm from all the choices adds to the complexity.</span></span> <span data-ttu-id="4bc8c-107">此外，每个算法都有一组要调整的超参数。</span><span class="sxs-lookup"><span data-stu-id="4bc8c-107">Even further, each algorithm has a set of hyperparameters to be tuned.</span></span> <span data-ttu-id="4bc8c-108">因此，可能会花费数周甚至数月时间进行机器学习模型优化，以尝试找到特征工程、学习算法和超参数的最佳组合。</span><span class="sxs-lookup"><span data-stu-id="4bc8c-108">Hence, you can spend weeks and sometimes months on machine learning model optimization trying to find the best combinations of feature engineering, learning algorithms, and hyperparameters.</span></span>

<span data-ttu-id="4bc8c-109">此过程可使用 ML.NET CLI 自动化，其实现 ML.NET AutoML 智能引擎。</span><span class="sxs-lookup"><span data-stu-id="4bc8c-109">This process can be automated with the ML.NET CLI, which implements the ML.NET AutoML intelligent engine.</span></span> 

> [!NOTE]
> <span data-ttu-id="4bc8c-110">本主题涉及目前处于预览状态的 ML.NET **CLI** 和 ML.NET **AutoML**，且材料可能会有所变化。</span><span class="sxs-lookup"><span data-stu-id="4bc8c-110">This topic refers to ML.NET **CLI** and ML.NET **AutoML**, which are currently in Preview, and material may be subject to change.</span></span> 

## <a name="what-is-the-mlnet-command-line-interface-cli"></a><span data-ttu-id="4bc8c-111">什么是 ML.NET 命令行接口 (CLI)？</span><span class="sxs-lookup"><span data-stu-id="4bc8c-111">What is the ML.NET Command-line Interface (CLI)?</span></span>

<span data-ttu-id="4bc8c-112">可以在任何命令提示符（Windows、Mac 或 Linux）上运行 ML.NET CLI，以根据训练数据集生成高质量的 ML.NET 模型和源代码。</span><span class="sxs-lookup"><span data-stu-id="4bc8c-112">You can run the ML.NET CLI on any command-prompt (Windows, Mac, or Linux) for generating good quality ML.NET models and source code based on your training dataset.</span></span>

<span data-ttu-id="4bc8c-113">如下图所示，生成高质量的 ML.NET 模型（序列化模型 .zip 文件）以及用于运行该模型/对该模型评分的示例 C# 代码非常简单。</span><span class="sxs-lookup"><span data-stu-id="4bc8c-113">As shown in the figure below, it is simple to generate a high quality ML.NET model (serialized model .zip file) plus the sample C# code to run/score that model.</span></span> <span data-ttu-id="4bc8c-114">此外，还会生成用于创建/训练该模型的 C# 代码，以便可以研究和迭代用于该生成的“最佳模型”的算法和设置。</span><span class="sxs-lookup"><span data-stu-id="4bc8c-114">In addition, the C# code to create/train that model is also generated, so that you can research and iterate on the algorithm and settings used for that generated "best model".</span></span> 

<span data-ttu-id="4bc8c-115">![图像](media/automate-training-with-cli/cli-high-level-process.png "在 ML.NET CLI 内部工作的 AutoML 引擎")</span><span class="sxs-lookup"><span data-stu-id="4bc8c-115">![image](media/automate-training-with-cli/cli-high-level-process.png "AutoML engine working inside the ML.NET CLI")</span></span>

<span data-ttu-id="4bc8c-116">可以从自己的数据集生成这些资产而无需自行编码，因此，即使已经了解 ML.NET，它也可以提高工作效率。</span><span class="sxs-lookup"><span data-stu-id="4bc8c-116">You can generate those assets from your own datasets without coding by yourself, so it also improves your productivity even if you already know ML.NET.</span></span>

<span data-ttu-id="4bc8c-117">目前，ML.NET CLI 支持的 ML 任务包括：</span><span class="sxs-lookup"><span data-stu-id="4bc8c-117">Currently, the ML Tasks supported by the ML.NET CLI are:</span></span>

- `binary-classification`
- `multiclass-classification` 
- `regression`
- <span data-ttu-id="4bc8c-118">未来：其他机器学习任务，例如 `recommendation`、`ranking`、`anomaly-detection`、`clustering`</span><span class="sxs-lookup"><span data-stu-id="4bc8c-118">Future: other machine learning tasks such as `recommendation`, `ranking`, `anomaly-detection`, `clustering`</span></span>

<span data-ttu-id="4bc8c-119">用法示例：</span><span class="sxs-lookup"><span data-stu-id="4bc8c-119">Example of usage:</span></span>

```console
> mlnet auto-train --task binary-classification --dataset "customer-feedback.tsv" --label-column-name Sentiment
```

![图像](media/automate-training-with-cli/cli-model-generation.gif)

<span data-ttu-id="4bc8c-121">可以在 *Windows PowerShell*、\*macOS/Linux bash 或 *Windows CMD* 上以相同的方式运行它。</span><span class="sxs-lookup"><span data-stu-id="4bc8c-121">You can run it the same way on *Windows PowerShell*, \*macOS/Linux bash, or *Windows CMD*.</span></span> <span data-ttu-id="4bc8c-122">但是，表格自动填写（参数建议）不适用于 *Windows CMD*。</span><span class="sxs-lookup"><span data-stu-id="4bc8c-122">However, tabular auto-completion (parameter suggestions) won't work on *Windows CMD*.</span></span>

## <a name="output-assets-generated"></a><span data-ttu-id="4bc8c-123">生成的输出资产</span><span class="sxs-lookup"><span data-stu-id="4bc8c-123">Output assets generated</span></span>

<span data-ttu-id="4bc8c-124">CLI `auto-train` 命令在输出文件夹中生成以下资产：</span><span class="sxs-lookup"><span data-stu-id="4bc8c-124">The CLI `auto-train` command generates the following assets in the output folder:</span></span>

- <span data-ttu-id="4bc8c-125">可供用于运行预测的序列化模型 .zip 文件（“最佳模型”）。</span><span class="sxs-lookup"><span data-stu-id="4bc8c-125">A serialized model .zip ("best model") ready to use for running predictions.</span></span> 
- <span data-ttu-id="4bc8c-126">C# 解决方案以及：</span><span class="sxs-lookup"><span data-stu-id="4bc8c-126">C# solution with:</span></span>
    - <span data-ttu-id="4bc8c-127">用于运行生成的模型/对生成的模型评分的 C# 代码（使用该模型在最终用户应用中进行预测）。</span><span class="sxs-lookup"><span data-stu-id="4bc8c-127">C# code to run/score that generated model (to make predictions in your end-user apps with that model).</span></span>
    - <span data-ttu-id="4bc8c-128">包含用于生成该模型的训练代码的 C# 代码（用于学习目的或模型重新训练）。</span><span class="sxs-lookup"><span data-stu-id="4bc8c-128">C# code with the training code used to generate that model (for learning purposes or model retraining).</span></span>
- <span data-ttu-id="4bc8c-129">日志文件，包含有关评估的多种算法的所有迭代/扫描的信息（包括其详细配置/管道）。</span><span class="sxs-lookup"><span data-stu-id="4bc8c-129">Log file with information of all iterations/sweeps across the multiple algorithms evaluated, including their detailed configuration/pipeline.</span></span>

<span data-ttu-id="4bc8c-130">前两个资产可以直接用于最终用户应用（ASP.NET Core Web 应用、服务、桌面应用等），以使用生成的 ML 模型进行预测。</span><span class="sxs-lookup"><span data-stu-id="4bc8c-130">The first two assets can directly be used in your end-user apps (ASP.NET Core web app, services, desktop app, etc.) to make predictions with that generated ML model.</span></span>

<span data-ttu-id="4bc8c-131">第三个资产（训练代码）显示 CLI 用于训练生成的模型的 ML.NET API 代码，因此，可以在后台重新训练模型并调查和迭代 CLI 和 AutoML 选择的特定训练程序/算法及超参数。</span><span class="sxs-lookup"><span data-stu-id="4bc8c-131">The third asset, the training code, shows you what ML.NET API code was used by the CLI to train the generated model, so you can retrain your model and investigate and iterate on which specific trainer/algorithm and hyperparameters were selected by the CLI and AutoML under the covers.</span></span> 

## <a name="understanding-the-quality-of-the-model"></a><span data-ttu-id="4bc8c-132">了解模型的质量</span><span class="sxs-lookup"><span data-stu-id="4bc8c-132">Understanding the quality of the model</span></span>

<span data-ttu-id="4bc8c-133">使用 CLI 工具生成“最佳模型”时，可看到适用于所针对的 ML 任务的质量指标（例如准确性和 R 平方）。</span><span class="sxs-lookup"><span data-stu-id="4bc8c-133">When you generate a 'best model' with the CLI tool, you see quality metrics (such as accuracy, and R-Squared) as appropriate for the ML task you are targeting.</span></span>

<span data-ttu-id="4bc8c-134">在这里，我们总结了按 ML 任务分组的指标，以便于了解自动生成的“最佳模型”的质量。</span><span class="sxs-lookup"><span data-stu-id="4bc8c-134">Here we summarize those metrics grouped by ML task so you can understand the quality of your auto-generated 'best model'.</span></span>

### <a name="metrics-for-binary-classification-models"></a><span data-ttu-id="4bc8c-135">二元分类模型指标</span><span class="sxs-lookup"><span data-stu-id="4bc8c-135">Metrics for Binary Classification models</span></span>

 <span data-ttu-id="4bc8c-136">以下显示 CLI 找到的排名前五的模型的二元分类 ML 任务指标列表：</span><span class="sxs-lookup"><span data-stu-id="4bc8c-136">The following displays the binary classification ML task metrics list for the top five models found by the CLI:</span></span> 

![图像](media/automate-training-with-cli/cli-binary-classification-metrics.png)

<span data-ttu-id="4bc8c-138">准确性是分类问题的常用指标，但准确性并不总是用于选择最佳模型的最佳指标，如下文参考中所述。</span><span class="sxs-lookup"><span data-stu-id="4bc8c-138">Accuracy is a popular metric for classification problems, however accuracy is not always the best metric to select the best model from as explained in the references below.</span></span> <span data-ttu-id="4bc8c-139">在某些情况下，需要使用其他指标评估模型的质量。</span><span class="sxs-lookup"><span data-stu-id="4bc8c-139">There are cases where you need to evaluate the quality of your model with additional metrics.</span></span>

<span data-ttu-id="4bc8c-140">若要探索和了解 CLI 输出的指标，请参阅[二元分类指标](resources/metrics.md#metrics-for-binary-classification)。</span><span class="sxs-lookup"><span data-stu-id="4bc8c-140">To explore and understand the metrics that are output by the CLI, see [Metrics for binary classification](resources/metrics.md#metrics-for-binary-classification).</span></span>

### <a name="metrics-for-multi-class-classification-models"></a><span data-ttu-id="4bc8c-141">多类分类模型指标</span><span class="sxs-lookup"><span data-stu-id="4bc8c-141">Metrics for Multi-class Classification models</span></span>

 <span data-ttu-id="4bc8c-142">以下显示 CLI 找到的排名前五的模型的多类分类 ML 任务指标列表：</span><span class="sxs-lookup"><span data-stu-id="4bc8c-142">The following displays the multi-class classification ML task metrics list for the top five models found by the CLI:</span></span> 

![图像](media/automate-training-with-cli/cli-multiclass-classification-metrics.png)

<span data-ttu-id="4bc8c-144">若要探索和了解 CLI 输出的指标，请参阅[多类分类指标](resources/metrics.md#metrics-for-multi-class-classification)。</span><span class="sxs-lookup"><span data-stu-id="4bc8c-144">To explore and understand the metrics that are output by the CLI, see [Metrics for multiclass classification](resources/metrics.md#metrics-for-multi-class-classification).</span></span>

### <a name="metrics-for-regression-models"></a><span data-ttu-id="4bc8c-145">回归模型指标</span><span class="sxs-lookup"><span data-stu-id="4bc8c-145">Metrics for Regression models</span></span>

<span data-ttu-id="4bc8c-146">如果观测值与模型预测值之间的差异很小且无偏差，则回归模型能够很好地拟合数据。</span><span class="sxs-lookup"><span data-stu-id="4bc8c-146">A regression model fits the data well if the differences between the observed values and the model's predicted values are small and unbiased.</span></span> <span data-ttu-id="4bc8c-147">可以使用特定指标评估回归。</span><span class="sxs-lookup"><span data-stu-id="4bc8c-147">Regression can be evaluated with certain metrics.</span></span>

<span data-ttu-id="4bc8c-148">将看到 CLI 找到的排名前五的最佳质量模型的类似指标列表。</span><span class="sxs-lookup"><span data-stu-id="4bc8c-148">You will see a similar list of metrics for the best top five quality models found by the CLI.</span></span> <span data-ttu-id="4bc8c-149">在与回归 ML 任务相关的这一特定案例中：</span><span class="sxs-lookup"><span data-stu-id="4bc8c-149">In this particular case related to a regression ML task:</span></span>

![图像](media/automate-training-with-cli/cli-regression-metrics.png)

<span data-ttu-id="4bc8c-151">若要探索和了解 CLI 输出的指标，请参阅[回归指标](resources/metrics.md#metrics-for-regression)。</span><span class="sxs-lookup"><span data-stu-id="4bc8c-151">To explore and understand the metrics that are output by the CLI, see [Metrics for regression](resources/metrics.md#metrics-for-regression).</span></span>

## <a name="see-also"></a><span data-ttu-id="4bc8c-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="4bc8c-152">See also</span></span>

- [<span data-ttu-id="4bc8c-153">如何安装 ML.NET CLI 工具</span><span class="sxs-lookup"><span data-stu-id="4bc8c-153">How to install the ML.NET CLI tool</span></span>](how-to-guides/install-ml-net-cli.md)
- [<span data-ttu-id="4bc8c-154">教程：使用 ML.NET CLI 自动生成二元分类器</span><span class="sxs-lookup"><span data-stu-id="4bc8c-154">Tutorial: Auto generate a binary classifier using the ML.NET CLI</span></span>](tutorials/mlnet-cli.md)
- [<span data-ttu-id="4bc8c-155">ML.NET CLI 命令参考</span><span class="sxs-lookup"><span data-stu-id="4bc8c-155">ML.NET CLI command reference</span></span>](reference/ml-net-cli-reference.md)
- [<span data-ttu-id="4bc8c-156">ML.NET CLI 中的遥测</span><span class="sxs-lookup"><span data-stu-id="4bc8c-156">Telemetry in ML.NET CLI</span></span>](resources/ml-net-cli-telemetry.md)

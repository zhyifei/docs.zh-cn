---
title: 什么是模型生成器，它的工作原理是怎样的？
description: 如何使用 ML.NET 模型生成器自动训练机器学习模型
author: natke
ms.date: 08/07/2019
ms.custom: overview
ms.openlocfilehash: 77fe56dba3532617ad9fb0c89bfaac7c8e031ce7
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73971523"
---
# <a name="what-is-model-builder-and-how-does-it-work"></a><span data-ttu-id="2a941-103">什么是模型生成器，它的工作原理是怎样的？</span><span class="sxs-lookup"><span data-stu-id="2a941-103">What is Model Builder and how does it work?</span></span>

<span data-ttu-id="2a941-104">ML.NET 模型生成器是一个直观的图形化 Visual Studio 扩展，用于生成、训练和部署自定义机器学习模型。</span><span class="sxs-lookup"><span data-stu-id="2a941-104">ML.NET Model Builder is an intuitive graphical Visual Studio extension to build, train, and deploy custom machine learning models.</span></span>

<span data-ttu-id="2a941-105">模型生成器使用自动化的机器学习 (AutoML) 来探索不同的机器学习算法和设置，以帮助找到最合适的方案。</span><span class="sxs-lookup"><span data-stu-id="2a941-105">Model Builder uses automated machine learning (AutoML) to explore different machine learning algorithms and settings to help you find the one that best suits your scenario.</span></span>

<span data-ttu-id="2a941-106">使用模型生成器不需要具备机器学习的专业知识。</span><span class="sxs-lookup"><span data-stu-id="2a941-106">You don't need machine learning expertise to use Model Builder.</span></span> <span data-ttu-id="2a941-107">只需要一些数据，和确定要解决的问题。</span><span class="sxs-lookup"><span data-stu-id="2a941-107">All you need is some data, and a problem to solve.</span></span> <span data-ttu-id="2a941-108">模型生成器会生成将模型添加到 .NET 应用程序的代码。</span><span class="sxs-lookup"><span data-stu-id="2a941-108">Model Builder generates the code to add the model to your .NET application.</span></span>

![模型生成器 Visual Studio 扩展用户界面动画](media/ml-dotnet-model-builder.gif)

> [!NOTE]
> <span data-ttu-id="2a941-110">模型生成器当前为预览版。</span><span class="sxs-lookup"><span data-stu-id="2a941-110">Model Builder is currently in Preview.</span></span>

## <a name="scenarios"></a><span data-ttu-id="2a941-111">方案</span><span class="sxs-lookup"><span data-stu-id="2a941-111">Scenarios</span></span>

<span data-ttu-id="2a941-112">可以为模型生成器提供许多不同的方案，从而为应用程序生成一个机器学习模型。</span><span class="sxs-lookup"><span data-stu-id="2a941-112">You can bring many different scenarios to Model Builder, to generate a machine learning model for your application.</span></span>

<span data-ttu-id="2a941-113">方案就是要使用数据进行预测类型的描述。</span><span class="sxs-lookup"><span data-stu-id="2a941-113">A scenario is a description of the type of prediction you want to make using your data.</span></span> <span data-ttu-id="2a941-114">例如:</span><span class="sxs-lookup"><span data-stu-id="2a941-114">For example:</span></span>

- <span data-ttu-id="2a941-115">根据历史销售数据预测未来的产品销量</span><span class="sxs-lookup"><span data-stu-id="2a941-115">predict future product sales volume based on historical sales data</span></span>
- <span data-ttu-id="2a941-116">根据客户评价将情绪分类为正面或负面</span><span class="sxs-lookup"><span data-stu-id="2a941-116">classify sentiments as positive or negative based on customer reviews</span></span>
- <span data-ttu-id="2a941-117">检测某项银行交易是否存在欺诈性</span><span class="sxs-lookup"><span data-stu-id="2a941-117">detect whether a banking transaction is fraudulent</span></span>
- <span data-ttu-id="2a941-118">将客户反馈问题传递至公司中合适的团队</span><span class="sxs-lookup"><span data-stu-id="2a941-118">route customer feedback issues to the correct team in your company</span></span>

## <a name="choose-a-model-type"></a><span data-ttu-id="2a941-119">选择模型类型</span><span class="sxs-lookup"><span data-stu-id="2a941-119">Choose a model type</span></span>

<span data-ttu-id="2a941-120">在模型生成器中，需要选择机器学习模型类型。</span><span class="sxs-lookup"><span data-stu-id="2a941-120">In Model Builder, you need to select a machine learning model type.</span></span> <span data-ttu-id="2a941-121">模型类型取决于尝试进行的预测类型。</span><span class="sxs-lookup"><span data-stu-id="2a941-121">The type of model depends on what sort of prediction you are trying to make.</span></span>

<span data-ttu-id="2a941-122">对于预测数字的方案，机器学习模型称为 `regression`。</span><span class="sxs-lookup"><span data-stu-id="2a941-122">For scenarios that predict a number, the machine learning model type is called `regression`.</span></span>

<span data-ttu-id="2a941-123">对于预测类别的方案，模型类型为 `classification`。</span><span class="sxs-lookup"><span data-stu-id="2a941-123">For scenarios that predict a category, the model type is `classification`.</span></span> <span data-ttu-id="2a941-124">有两种类型的分类：</span><span class="sxs-lookup"><span data-stu-id="2a941-124">There are two types of classification:</span></span>

- <span data-ttu-id="2a941-125">其中只有两个类别：`binary classification`。</span><span class="sxs-lookup"><span data-stu-id="2a941-125">where there are only 2 categories: `binary classification`.</span></span>
- <span data-ttu-id="2a941-126">其中有三个或更多个类别：`multiclass classification`。</span><span class="sxs-lookup"><span data-stu-id="2a941-126">where there are three or more categories: `multiclass classification`.</span></span>

### <a name="which-model-type-is-right-for-me"></a><span data-ttu-id="2a941-127">哪种模型类型适合我？</span><span class="sxs-lookup"><span data-stu-id="2a941-127">Which model type is right for me?</span></span>

#### <a name="predict-a-category-when-there-are-only-two-categories"></a><span data-ttu-id="2a941-128">预测类别（只有两个类别时）</span><span class="sxs-lookup"><span data-stu-id="2a941-128">Predict a category (when there are only two categories)</span></span>

<span data-ttu-id="2a941-129">二元分类用于将数据分为两个类别（是/否；通过/失败；true/false；正面/负面）。</span><span class="sxs-lookup"><span data-stu-id="2a941-129">Binary classification is used to categorize data into two categories (yes/no; pass/fail; true/false; positive/negative).</span></span>

![显示二元分类示例（包括欺诈检测、风险环节和应用程序屏蔽）的图示](media/binary-classification-examples.png)

<span data-ttu-id="2a941-131">情绪分析可用于预测的客户反馈中的正面情绪或负面情绪。</span><span class="sxs-lookup"><span data-stu-id="2a941-131">Sentiment analysis can be used to predict positive or negative sentiment of customer feedback.</span></span> <span data-ttu-id="2a941-132">它是一个二元分类模型类型的例子。</span><span class="sxs-lookup"><span data-stu-id="2a941-132">It is an example of a binary classification model type.</span></span>

<span data-ttu-id="2a941-133">如果方案需要将数据分为两类，可以将该模板与自己的数据集配合使用。</span><span class="sxs-lookup"><span data-stu-id="2a941-133">If your scenario requires classification into two categories, you can use this template with your own dataset.</span></span>

#### <a name="predict-a-category-when-there-are-three-or-more-categories"></a><span data-ttu-id="2a941-134">预测类别（有三个或更多个类别时）</span><span class="sxs-lookup"><span data-stu-id="2a941-134">Predict a category (when there are three or more categories)</span></span>

<span data-ttu-id="2a941-135">多类分类可用于将数据分为三类或更多类。</span><span class="sxs-lookup"><span data-stu-id="2a941-135">Multiclass classification can be used to categorize data into three or more classes.</span></span>

![多类分类示例，包括文档和产品分类、支持票证路由以及客户问题优先级](media/multiclass-classification-examples.png)

<span data-ttu-id="2a941-137">问题分类可用于使用问题标题和描述对客户反馈（例如 GitHub 上的反馈）问题进行分类。</span><span class="sxs-lookup"><span data-stu-id="2a941-137">Issue classification can be used to categorize customer feedback (for example, on GitHub) issues using the issue title and description.</span></span> <span data-ttu-id="2a941-138">它是一个多类分类模型类型的例子。</span><span class="sxs-lookup"><span data-stu-id="2a941-138">It is an example of the multi-class classification model type.</span></span>

<span data-ttu-id="2a941-139">如果需要将数据分为三类或更多类，可以使用问题分类模板。</span><span class="sxs-lookup"><span data-stu-id="2a941-139">You can use the issue classification template for your scenario if you want to categorize data into three or more categories.</span></span>

#### <a name="predict-a-number"></a><span data-ttu-id="2a941-140">预测数字</span><span class="sxs-lookup"><span data-stu-id="2a941-140">Predict a number</span></span>

<span data-ttu-id="2a941-141">回归用于预测数字。</span><span class="sxs-lookup"><span data-stu-id="2a941-141">Regression is used to predict numbers.</span></span>

![显示回归示例（如价格预测、销售预测和预测性维护）的图示](media/regression-examples.png)

<span data-ttu-id="2a941-143">价格预测可以通过房屋的位置、大小等特点来预测房价。</span><span class="sxs-lookup"><span data-stu-id="2a941-143">Price prediction can be used to predict house prices using location, size, and other characteristics of the house.</span></span> <span data-ttu-id="2a941-144">它是一个回归模型类型的例子。</span><span class="sxs-lookup"><span data-stu-id="2a941-144">It is an example of a regression model type.</span></span>

<span data-ttu-id="2a941-145">如果要使用自己的数据集预测数字值，可以使用价格预测模板。</span><span class="sxs-lookup"><span data-stu-id="2a941-145">You can use the price prediction template for your scenario if you want to predict a numerical value with your own dataset.</span></span>

#### <a name="custom-scenario-choose-your-model-type"></a><span data-ttu-id="2a941-146">自定义方案（选择自己的模型类型）</span><span class="sxs-lookup"><span data-stu-id="2a941-146">Custom scenario (choose your model type)</span></span>

<span data-ttu-id="2a941-147">使用自定义方案，可以手动选择自己的模型类型。</span><span class="sxs-lookup"><span data-stu-id="2a941-147">The custom scenario allows you to manually choose your model type.</span></span>

## <a name="data"></a><span data-ttu-id="2a941-148">数据</span><span class="sxs-lookup"><span data-stu-id="2a941-148">Data</span></span>

<span data-ttu-id="2a941-149">选择模型类型后，模型生成器会要求你提供数据集。</span><span class="sxs-lookup"><span data-stu-id="2a941-149">Once you have chosen your model type, Model Builder asks you to provide a dataset.</span></span> <span data-ttu-id="2a941-150">这些数据用于训练、评估和选择最适合方案的的模型。</span><span class="sxs-lookup"><span data-stu-id="2a941-150">The data is used to train, evaluate, and choose the best model for your scenario.</span></span>

![显示模型生成器步骤的图示](media/model-builder-steps.png)

### <a name="choose-the-output-to-predict-label"></a><span data-ttu-id="2a941-152">选择要预测的输出（标签）</span><span class="sxs-lookup"><span data-stu-id="2a941-152">Choose the output to predict (label)</span></span>

<span data-ttu-id="2a941-153">数据集是一个表格，其中，行中含训练示例，列中含特性。</span><span class="sxs-lookup"><span data-stu-id="2a941-153">A dataset is a table of rows of training examples, and columns of attributes.</span></span> <span data-ttu-id="2a941-154">每一行都具有：</span><span class="sxs-lookup"><span data-stu-id="2a941-154">Each row has:</span></span>

- <span data-ttu-id="2a941-155">一个标签，即要预测的特性 </span><span class="sxs-lookup"><span data-stu-id="2a941-155">a **label** (the attribute that you want to predict)</span></span>
- <span data-ttu-id="2a941-156">特征（为预测标签而用作输入的特性）  。</span><span class="sxs-lookup"><span data-stu-id="2a941-156">**features** (attributes that are used as inputs to predict the label).</span></span>

<span data-ttu-id="2a941-157">在房价预测方案中，特性可能是：</span><span class="sxs-lookup"><span data-stu-id="2a941-157">For the house-price prediction scenario, the features could be:</span></span>

- <span data-ttu-id="2a941-158">房屋的面积</span><span class="sxs-lookup"><span data-stu-id="2a941-158">the square footage of the house</span></span>
- <span data-ttu-id="2a941-159">卧室和卫生间的数量</span><span class="sxs-lookup"><span data-stu-id="2a941-159">the number of bedrooms and bathrooms</span></span>
- <span data-ttu-id="2a941-160">邮政编码</span><span class="sxs-lookup"><span data-stu-id="2a941-160">the zip code</span></span>

<span data-ttu-id="2a941-161">标签是与其所属行（包含面积、卧室和卫生间值以及邮政编码信息）对应的历史房价。</span><span class="sxs-lookup"><span data-stu-id="2a941-161">The label is the historical house price for that row of square footage, bedroom, and bathroom values and zip code.</span></span>

![表显示房价数据的行和列，其中包含由大小、房间数、邮政编码和价格标签组成的特征](media/model-builder-data.png)

### <a name="example-datasets"></a><span data-ttu-id="2a941-163">示例数据集</span><span class="sxs-lookup"><span data-stu-id="2a941-163">Example datasets</span></span>

<span data-ttu-id="2a941-164">如果还没有自己的数据，请试用以下数据集之一：</span><span class="sxs-lookup"><span data-stu-id="2a941-164">If you don't have your own data yet, try out one of these datasets:</span></span>

|<span data-ttu-id="2a941-165">方案</span><span class="sxs-lookup"><span data-stu-id="2a941-165">Scenario</span></span>|<span data-ttu-id="2a941-166">模型类型</span><span class="sxs-lookup"><span data-stu-id="2a941-166">Model Type</span></span>|<span data-ttu-id="2a941-167">数据</span><span class="sxs-lookup"><span data-stu-id="2a941-167">Data</span></span>|<span data-ttu-id="2a941-168">Label</span><span class="sxs-lookup"><span data-stu-id="2a941-168">Label</span></span>|<span data-ttu-id="2a941-169">特征</span><span class="sxs-lookup"><span data-stu-id="2a941-169">Features</span></span>|
|-|-|-|-|-|
|<span data-ttu-id="2a941-170">价格预测</span><span class="sxs-lookup"><span data-stu-id="2a941-170">Price prediction</span></span>|<span data-ttu-id="2a941-171">回归</span><span class="sxs-lookup"><span data-stu-id="2a941-171">regression</span></span>|[<span data-ttu-id="2a941-172">出租车费数据</span><span class="sxs-lookup"><span data-stu-id="2a941-172">taxi fare data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/datasets/taxi-fare-train.csv)|<span data-ttu-id="2a941-173">车费</span><span class="sxs-lookup"><span data-stu-id="2a941-173">Fare</span></span>|<span data-ttu-id="2a941-174">行程时间、距离</span><span class="sxs-lookup"><span data-stu-id="2a941-174">Trip time, distance</span></span>|
|<span data-ttu-id="2a941-175">异常情况检测</span><span class="sxs-lookup"><span data-stu-id="2a941-175">Anomaly detection</span></span>|<span data-ttu-id="2a941-176">二元分类</span><span class="sxs-lookup"><span data-stu-id="2a941-176">binary classification</span></span>|[<span data-ttu-id="2a941-177">产品销售数据</span><span class="sxs-lookup"><span data-stu-id="2a941-177">product sales data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)|<span data-ttu-id="2a941-178">产品销售额</span><span class="sxs-lookup"><span data-stu-id="2a941-178">Product Sales</span></span>|<span data-ttu-id="2a941-179">月份</span><span class="sxs-lookup"><span data-stu-id="2a941-179">Month</span></span>|
|<span data-ttu-id="2a941-180">情绪分析</span><span class="sxs-lookup"><span data-stu-id="2a941-180">Sentiment analysis</span></span>|<span data-ttu-id="2a941-181">二元分类</span><span class="sxs-lookup"><span data-stu-id="2a941-181">binary classification</span></span>|[<span data-ttu-id="2a941-182">网站评论数据</span><span class="sxs-lookup"><span data-stu-id="2a941-182">website comment data</span></span>](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv)|<span data-ttu-id="2a941-183">标签（负面情绪为 0，正面情绪为 1）</span><span class="sxs-lookup"><span data-stu-id="2a941-183">Label (0 when negative sentiment, 1 when positive)</span></span>|<span data-ttu-id="2a941-184">评论、年份</span><span class="sxs-lookup"><span data-stu-id="2a941-184">Comment, Year</span></span>|
|<span data-ttu-id="2a941-185">欺诈检测</span><span class="sxs-lookup"><span data-stu-id="2a941-185">Fraud detection</span></span>|<span data-ttu-id="2a941-186">二元分类</span><span class="sxs-lookup"><span data-stu-id="2a941-186">binary classification</span></span>|[<span data-ttu-id="2a941-187">信用卡数据</span><span class="sxs-lookup"><span data-stu-id="2a941-187">credit card data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/BinaryClassification_CreditCardFraudDetection/CreditCardFraudDetection.Trainer/assets/input/creditcardfraud-dataset.zip)|<span data-ttu-id="2a941-188">类（存在欺诈性为 1，否则为 0）</span><span class="sxs-lookup"><span data-stu-id="2a941-188">Class (1 when fraudulent, 0 otherwise)</span></span>|<span data-ttu-id="2a941-189">金额，V1-V28（匿名处理后的特征）</span><span class="sxs-lookup"><span data-stu-id="2a941-189">Amount, V1-V28 (anonymized features)</span></span>|
|<span data-ttu-id="2a941-190">文本分类</span><span class="sxs-lookup"><span data-stu-id="2a941-190">Text classification</span></span>|<span data-ttu-id="2a941-191">多类分类</span><span class="sxs-lookup"><span data-stu-id="2a941-191">multiclass classification</span></span>|[<span data-ttu-id="2a941-192">GitHub 问题数据</span><span class="sxs-lookup"><span data-stu-id="2a941-192">GitHub issue data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/end-to-end-apps/MulticlassClassification-GitHubLabeler/GitHubLabeler/Data/corefx-issues-train.tsv)|<span data-ttu-id="2a941-193">区域</span><span class="sxs-lookup"><span data-stu-id="2a941-193">Area</span></span>|<span data-ttu-id="2a941-194">标题、描述</span><span class="sxs-lookup"><span data-stu-id="2a941-194">Title, Description</span></span>|

## <a name="train"></a><span data-ttu-id="2a941-195">定型</span><span class="sxs-lookup"><span data-stu-id="2a941-195">Train</span></span>

<span data-ttu-id="2a941-196">选择方案、数据和标签后，模型生成器会训练该模型。</span><span class="sxs-lookup"><span data-stu-id="2a941-196">Once you select your scenario, data, and label, Model Builder trains the model.</span></span>

### <a name="what-is-training"></a><span data-ttu-id="2a941-197">什么是训练？</span><span class="sxs-lookup"><span data-stu-id="2a941-197">What is training?</span></span>

<span data-ttu-id="2a941-198">训练是一个自动的过程，模型生成器通过该过程教模型如何回答方案相关的问题。</span><span class="sxs-lookup"><span data-stu-id="2a941-198">Training is an automatic process by which Model Builder teaches your model how to answer questions for your scenario.</span></span> <span data-ttu-id="2a941-199">训练后，模型可以对其没有见过的输入数据进行预测。</span><span class="sxs-lookup"><span data-stu-id="2a941-199">Once trained, your model can make predictions with input data that it has not seen before.</span></span> <span data-ttu-id="2a941-200">例如，在预测房价时，可以预测新上市的房屋销售价。</span><span class="sxs-lookup"><span data-stu-id="2a941-200">For example, if you are predicting house prices and a new house comes on the market, you can predict its sale price.</span></span>

<span data-ttu-id="2a941-201">因为模型生成器使用自动机器学习 (AutoML)，所以在训练期间不需要任何人工输入或微调操作。</span><span class="sxs-lookup"><span data-stu-id="2a941-201">Because Model Builder uses automated machine learning (AutoML), it does not require any input or tuning from you during training.</span></span>

## <a name="evaluate"></a><span data-ttu-id="2a941-202">评估</span><span class="sxs-lookup"><span data-stu-id="2a941-202">Evaluate</span></span>

<span data-ttu-id="2a941-203">评估是让经过训练的模型对新的测试数据进行预测，然后度量预测效果的过程。</span><span class="sxs-lookup"><span data-stu-id="2a941-203">Evaluation is the process of using the trained model to make predictions with new test data, and then measuring how good the predictions are.</span></span>

<span data-ttu-id="2a941-204">模型生成器将训练数据拆分为训练集和测试集。</span><span class="sxs-lookup"><span data-stu-id="2a941-204">Model Builder splits the training data into a training set and a test set.</span></span> <span data-ttu-id="2a941-205">训练数据 (80%) 用于训练模型，测试数据 (20%) 用于评估模型。</span><span class="sxs-lookup"><span data-stu-id="2a941-205">The training data (80%) is used to train your model and the test data (20%) is held back to evaluate your model.</span></span> <span data-ttu-id="2a941-206">模型生成器使用指标来衡量模型的优秀程度。</span><span class="sxs-lookup"><span data-stu-id="2a941-206">Model Builder uses metrics to measure how good the model is.</span></span> <span data-ttu-id="2a941-207">所使用的具体指标取决于模型类型。</span><span class="sxs-lookup"><span data-stu-id="2a941-207">The specific metrics used are dependent on the type of model.</span></span> <span data-ttu-id="2a941-208">有关详细信息，请参阅[模型评估指标](resources/metrics.md)。</span><span class="sxs-lookup"><span data-stu-id="2a941-208">For more information, see [model evaluation metrics](resources/metrics.md).</span></span>

## <a name="improve"></a><span data-ttu-id="2a941-209">改进</span><span class="sxs-lookup"><span data-stu-id="2a941-209">Improve</span></span>

<span data-ttu-id="2a941-210">如果模型性能评分不符合预期，可以：</span><span class="sxs-lookup"><span data-stu-id="2a941-210">If your model performance score is not as good as you want it to be, you can:</span></span>

- <span data-ttu-id="2a941-211">延长训练时间。</span><span class="sxs-lookup"><span data-stu-id="2a941-211">Train for a longer period of time.</span></span> <span data-ttu-id="2a941-212">有了更多时间，自动机器学习引擎可以尝试更多算法和设置。</span><span class="sxs-lookup"><span data-stu-id="2a941-212">With more time, the automated machine learning engine to try more algorithms and settings.</span></span>

- <span data-ttu-id="2a941-213">添加更多数据。</span><span class="sxs-lookup"><span data-stu-id="2a941-213">Add more data.</span></span> <span data-ttu-id="2a941-214">有时候可能是数据量不足，无法训练出高质量的机器学习模型。</span><span class="sxs-lookup"><span data-stu-id="2a941-214">Sometimes the amount of data is not sufficient to train a high-quality machine learning model.</span></span>

- <span data-ttu-id="2a941-215">均衡分配数据。</span><span class="sxs-lookup"><span data-stu-id="2a941-215">Balance your data.</span></span> <span data-ttu-id="2a941-216">对于分类任务，请确保在各个类别间均匀分配训练集。</span><span class="sxs-lookup"><span data-stu-id="2a941-216">For classification tasks, make sure that the training set is balanced across the categories.</span></span> <span data-ttu-id="2a941-217">例如，若有四个类别和 100 个训练示例，前两类（标记 1 和标记 2）包含 90 个记录，而剩下两类（标记 3 和标记 4）只包含 10 个记录，这就存在数据不均衡的问题，可能会导致模型很难正确预测标记 3 或标记 4。</span><span class="sxs-lookup"><span data-stu-id="2a941-217">For example, if you have four classes for 100 training examples, and the two first classes (tag1 and tag2) are used for 90 records, but the other two (tag3 and tag4) are only used on the remaining 10 records, the lack of balanced data may cause your model to struggle to correctly predict tag3 or tag4.</span></span>

## <a name="code"></a><span data-ttu-id="2a941-218">代码</span><span class="sxs-lookup"><span data-stu-id="2a941-218">Code</span></span>

<span data-ttu-id="2a941-219">完成评估阶段后，模型生成器会输出一份模型文件和代码，可以使用该代码将模型添加到应用程序。</span><span class="sxs-lookup"><span data-stu-id="2a941-219">After the evaluation phase, Model Builder outputs a model file, and code that you can use to add the model to your application.</span></span> <span data-ttu-id="2a941-220">ML.NET 模型保存为 zip 文件。</span><span class="sxs-lookup"><span data-stu-id="2a941-220">ML.NET models are saved as a zip file.</span></span> <span data-ttu-id="2a941-221">用于加载和使用模型的代码会以新项目的形式添加到解决方案中。</span><span class="sxs-lookup"><span data-stu-id="2a941-221">The code to load and use your model is added as a new project in your solution.</span></span> <span data-ttu-id="2a941-222">模型生成器还会添加一个示例控制台应用，可以运行该应用来查看工作状态下的模型。</span><span class="sxs-lookup"><span data-stu-id="2a941-222">Model Builder also adds a sample console app that you can run to see your model in action.</span></span>

<span data-ttu-id="2a941-223">此外，模型生成器还会输出生成模型的代码，以便你能了解生成模型所使用的步骤。</span><span class="sxs-lookup"><span data-stu-id="2a941-223">In addition, Model Builder outputs the code that generated the model, so that you can understand the steps used to generate the model.</span></span> <span data-ttu-id="2a941-224">还可以通过模型训练代码使用新的数据重新训练模型。</span><span class="sxs-lookup"><span data-stu-id="2a941-224">You can also use the model training code to retrain your model with new data.</span></span>

## <a name="whats-next"></a><span data-ttu-id="2a941-225">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2a941-225">What's next?</span></span>

<span data-ttu-id="2a941-226">[安装](how-to-guides/install-model-builder.md)模型生成器 Visual Studio 扩展</span><span class="sxs-lookup"><span data-stu-id="2a941-226">[Install](how-to-guides/install-model-builder.md) the Model Builder Visual Studio extension</span></span>

<span data-ttu-id="2a941-227">请尝试[价格预测或任何回归方案](tutorials/predict-prices-with-model-builder.md)</span><span class="sxs-lookup"><span data-stu-id="2a941-227">Try [price prediction or any regression scenario](tutorials/predict-prices-with-model-builder.md)</span></span>

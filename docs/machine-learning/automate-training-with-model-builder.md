---
title: 什么是模型生成器，它的工作原理是怎样的？
description: 如何使用 ML.NET 模型生成器自动训练机器学习模型
ms.date: 01/07/2020
ms.custom: overview
ms.openlocfilehash: ac704b7961a8442a9174cdef5a4cd2a619236a4e
ms.sourcegitcommit: cbdc0f4fd39172b5191a35200c33d5030774463c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2020
ms.locfileid: "75777395"
---
# <a name="what-is-model-builder-and-how-does-it-work"></a><span data-ttu-id="0d6d4-103">什么是模型生成器，它的工作原理是怎样的？</span><span class="sxs-lookup"><span data-stu-id="0d6d4-103">What is Model Builder and how does it work?</span></span>

<span data-ttu-id="0d6d4-104">ML.NET 模型生成器是一个直观的图形化 Visual Studio 扩展，用于生成、训练和部署自定义机器学习模型。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-104">ML.NET Model Builder is an intuitive graphical Visual Studio extension to build, train, and deploy custom machine learning models.</span></span>

<span data-ttu-id="0d6d4-105">模型生成器使用自动化的机器学习 (AutoML) 来探索不同的机器学习算法和设置，以帮助找到最合适的方案。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-105">Model Builder uses automated machine learning (AutoML) to explore different machine learning algorithms and settings to help you find the one that best suits your scenario.</span></span>

<span data-ttu-id="0d6d4-106">使用模型生成器不需要具备机器学习的专业知识。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-106">You don't need machine learning expertise to use Model Builder.</span></span> <span data-ttu-id="0d6d4-107">只需要一些数据，和确定要解决的问题。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-107">All you need is some data, and a problem to solve.</span></span> <span data-ttu-id="0d6d4-108">模型生成器会生成将模型添加到 .NET 应用程序的代码。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-108">Model Builder generates the code to add the model to your .NET application.</span></span>

![模型生成器 Visual Studio 扩展用户界面动画](media/ml-dotnet-model-builder.gif)

> [!NOTE]
> <span data-ttu-id="0d6d4-110">模型生成器当前为预览版。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-110">Model Builder is currently in Preview.</span></span>

## <a name="scenarios"></a><span data-ttu-id="0d6d4-111">方案</span><span class="sxs-lookup"><span data-stu-id="0d6d4-111">Scenarios</span></span>

<span data-ttu-id="0d6d4-112">可以为模型生成器提供许多不同的方案，从而为应用程序生成一个机器学习模型。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-112">You can bring many different scenarios to Model Builder, to generate a machine learning model for your application.</span></span>

<span data-ttu-id="0d6d4-113">方案就是要使用数据进行预测类型的描述。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-113">A scenario is a description of the type of prediction you want to make using your data.</span></span> <span data-ttu-id="0d6d4-114">例如：</span><span class="sxs-lookup"><span data-stu-id="0d6d4-114">For example:</span></span>

- <span data-ttu-id="0d6d4-115">根据历史销售数据预测未来的产品销量</span><span class="sxs-lookup"><span data-stu-id="0d6d4-115">predict future product sales volume based on historical sales data</span></span>
- <span data-ttu-id="0d6d4-116">根据客户评价将情绪分类为正面或负面</span><span class="sxs-lookup"><span data-stu-id="0d6d4-116">classify sentiments as positive or negative based on customer reviews</span></span>
- <span data-ttu-id="0d6d4-117">检测某项银行交易是否存在欺诈性</span><span class="sxs-lookup"><span data-stu-id="0d6d4-117">detect whether a banking transaction is fraudulent</span></span>
- <span data-ttu-id="0d6d4-118">将客户反馈问题传递至公司中合适的团队</span><span class="sxs-lookup"><span data-stu-id="0d6d4-118">route customer feedback issues to the correct team in your company</span></span>

### <a name="which-machine-learning-scenario-is-right-for-me"></a><span data-ttu-id="0d6d4-119">哪个机器学习方案最适合我？</span><span class="sxs-lookup"><span data-stu-id="0d6d4-119">Which machine learning scenario is right for me?</span></span>

<span data-ttu-id="0d6d4-120">在模型生成器中，你需要选择一个方案。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-120">In Model Builder, you need to select a scenario.</span></span> <span data-ttu-id="0d6d4-121">方案类型取决于尝试进行的预测类型。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-121">The type of scenario depends on what type of prediction you are trying to make.</span></span>

#### <a name="predict-a-category-when-there-are-only-two-categories"></a><span data-ttu-id="0d6d4-122">预测类别（只有两个类别时）</span><span class="sxs-lookup"><span data-stu-id="0d6d4-122">Predict a category (when there are only two categories)</span></span>

<span data-ttu-id="0d6d4-123">二元分类用于将数据分为两个类别（是/否；通过/失败；true/false；正面/负面）。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-123">Binary classification is used to categorize data into two categories (yes/no; pass/fail; true/false; positive/negative).</span></span>

![显示二元分类示例（包括欺诈检测、风险环节和应用程序屏蔽）的图示](media/binary-classification-examples.png)

<span data-ttu-id="0d6d4-125">情绪分析可用于预测的客户反馈中的正面情绪或负面情绪。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-125">Sentiment analysis can be used to predict positive or negative sentiment of customer feedback.</span></span> <span data-ttu-id="0d6d4-126">这是一个二元分类机器学习任务的示例。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-126">It is an example of the binary classification machine learning task.</span></span>

<span data-ttu-id="0d6d4-127">如果方案需要将数据分为两类，可以将该模板与自己的数据集配合使用。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-127">If your scenario requires classification into two categories, you can use this template with your own dataset.</span></span>

#### <a name="predict-a-category-when-there-are-three-or-more-categories"></a><span data-ttu-id="0d6d4-128">预测类别（有三个或更多个类别时）</span><span class="sxs-lookup"><span data-stu-id="0d6d4-128">Predict a category (when there are three or more categories)</span></span>

<span data-ttu-id="0d6d4-129">多类分类可用于将数据分为三类或更多类。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-129">Multiclass classification can be used to categorize data into three or more classes.</span></span>

![多类分类示例，包括文档和产品分类、支持票证路由以及客户问题优先级](media/multiclass-classification-examples.png)

<span data-ttu-id="0d6d4-131">问题分类可用于使用问题标题和描述对客户反馈（例如 GitHub 上的反馈）问题进行分类。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-131">Issue classification can be used to categorize customer feedback (for example, on GitHub) issues using the issue title and description.</span></span> <span data-ttu-id="0d6d4-132">这是一个多类分类机器学习任务的示例。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-132">It is an example of the multi-class classification machine learning task.</span></span>

<span data-ttu-id="0d6d4-133">如果需要将数据分为三类或更多类，可以使用问题分类模板。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-133">You can use the issue classification template for your scenario if you want to categorize data into three or more categories.</span></span>

#### <a name="predict-a-number"></a><span data-ttu-id="0d6d4-134">预测数字</span><span class="sxs-lookup"><span data-stu-id="0d6d4-134">Predict a number</span></span>

<span data-ttu-id="0d6d4-135">回归用于预测数字。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-135">Regression is used to predict numbers.</span></span>

![显示回归示例（如价格预测、销售预测和预测性维护）的图示](media/regression-examples.png)

<span data-ttu-id="0d6d4-137">价格预测可以通过房屋的位置、大小等特点来预测房价。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-137">Price prediction can be used to predict house prices using location, size, and other characteristics of the house.</span></span> <span data-ttu-id="0d6d4-138">这是一个回归机器学习任务的示例。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-138">It is an example of the regression machine learning task.</span></span>

<span data-ttu-id="0d6d4-139">如果要使用自己的数据集预测数字值，可以使用价格预测模板。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-139">You can use the price prediction template for your scenario if you want to predict a numerical value with your own dataset.</span></span>

#### <a name="classify-images-into-categories"></a><span data-ttu-id="0d6d4-140">将图像分类为类别</span><span class="sxs-lookup"><span data-stu-id="0d6d4-140">Classify images into categories</span></span>

<span data-ttu-id="0d6d4-141">此方案是多类分类的一种特殊情况，其中分类的输入数据是一组图像。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-141">This scenario is a special case of multiclass classification, where the input data to be categorized is a set of images.</span></span>

<span data-ttu-id="0d6d4-142">图像分类可用于标识不同类别的图像。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-142">Image classification can be used to identify images of different categories.</span></span> <span data-ttu-id="0d6d4-143">例如，不同类型的地形或动物或制造缺陷。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-143">For example, different types of terrain or animals or manufacturing defects.</span></span>

<span data-ttu-id="0d6d4-144">如果你有一组图像，并且想要将图像分为不同的类别，则可以使用适用于你的方案的图像分类模板。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-144">You can use the image classification template for your scenario if you have a set of images, and you want to classify the images into different categories.</span></span>

#### <a name="custom-scenario"></a><span data-ttu-id="0d6d4-145">自定义方案</span><span class="sxs-lookup"><span data-stu-id="0d6d4-145">Custom scenario</span></span>

<span data-ttu-id="0d6d4-146">使用自定义方案，可以手动选择自己的方案。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-146">The custom scenario allows you to manually choose your scenario.</span></span>

## <a name="data"></a><span data-ttu-id="0d6d4-147">数据</span><span class="sxs-lookup"><span data-stu-id="0d6d4-147">Data</span></span>

<span data-ttu-id="0d6d4-148">选择方案后，模型生成器会要求你提供数据集。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-148">Once you have chosen your scenario, Model Builder asks you to provide a dataset.</span></span> <span data-ttu-id="0d6d4-149">这些数据用于训练、评估和选择最适合方案的的模型。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-149">The data is used to train, evaluate, and choose the best model for your scenario.</span></span>

![显示模型生成器步骤的图示](media/model-builder-steps.png)

<span data-ttu-id="0d6d4-151">模型生成器支持 .tsv、.csv、.txt 格式以及 SQL 数据库格式的数据集。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-151">Model Builder supports datasets in .tsv, .csv, .txt formats, as well as SQL database format.</span></span> <span data-ttu-id="0d6d4-152">如果你有一个 .txt 文件，则应使用 `,`、`;` 或 `/t` 分隔列，并且该文件必须具有标题行。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-152">If you have a .txt file, columns should be separated with `,`, `;` or `/t` and the file must have a header row.</span></span>

<span data-ttu-id="0d6d4-153">如果数据集由图像组成，则支持的文件类型为 `.jpg` 和 `.png`。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-153">If the dataset is made up of images, the supported file types are `.jpg` and `.png`.</span></span>

<span data-ttu-id="0d6d4-154">有关详细信息，请参阅[将训练数据加载到模型生成器](how-to-guides/load-data-model-builder.md)。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-154">For more information, see [Load training data into Model Builder](how-to-guides/load-data-model-builder.md).</span></span>

### <a name="choose-the-output-to-predict-label"></a><span data-ttu-id="0d6d4-155">选择要预测的输出（标签）</span><span class="sxs-lookup"><span data-stu-id="0d6d4-155">Choose the output to predict (label)</span></span>

<span data-ttu-id="0d6d4-156">数据集是一个表格，其中，行中含训练示例，列中含特性。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-156">A dataset is a table of rows of training examples, and columns of attributes.</span></span> <span data-ttu-id="0d6d4-157">每一行都具有：</span><span class="sxs-lookup"><span data-stu-id="0d6d4-157">Each row has:</span></span>

- <span data-ttu-id="0d6d4-158">一个标签，即要预测的特性 </span><span class="sxs-lookup"><span data-stu-id="0d6d4-158">a **label** (the attribute that you want to predict)</span></span>
- <span data-ttu-id="0d6d4-159">特征（为预测标签而用作输入的特性）  。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-159">**features** (attributes that are used as inputs to predict the label).</span></span>

<span data-ttu-id="0d6d4-160">在房价预测方案中，特性可能是：</span><span class="sxs-lookup"><span data-stu-id="0d6d4-160">For the house-price prediction scenario, the features could be:</span></span>

- <span data-ttu-id="0d6d4-161">房屋的面积</span><span class="sxs-lookup"><span data-stu-id="0d6d4-161">the square footage of the house</span></span>
- <span data-ttu-id="0d6d4-162">卧室和卫生间的数量</span><span class="sxs-lookup"><span data-stu-id="0d6d4-162">the number of bedrooms and bathrooms</span></span>
- <span data-ttu-id="0d6d4-163">邮政编码</span><span class="sxs-lookup"><span data-stu-id="0d6d4-163">the zip code</span></span>

<span data-ttu-id="0d6d4-164">标签是与其所属行（包含面积、卧室和卫生间值以及邮政编码信息）对应的历史房价。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-164">The label is the historical house price for that row of square footage, bedroom, and bathroom values and zip code.</span></span>

![表显示房价数据的行和列，其中包含由大小、房间数、邮政编码和价格标签组成的特征](media/model-builder-data.png)

### <a name="example-datasets"></a><span data-ttu-id="0d6d4-166">示例数据集</span><span class="sxs-lookup"><span data-stu-id="0d6d4-166">Example datasets</span></span>

<span data-ttu-id="0d6d4-167">如果还没有自己的数据，请试用以下数据集之一：</span><span class="sxs-lookup"><span data-stu-id="0d6d4-167">If you don't have your own data yet, try out one of these datasets:</span></span>

|<span data-ttu-id="0d6d4-168">方案</span><span class="sxs-lookup"><span data-stu-id="0d6d4-168">Scenario</span></span>|<span data-ttu-id="0d6d4-169">ML 任务</span><span class="sxs-lookup"><span data-stu-id="0d6d4-169">ML task</span></span>|<span data-ttu-id="0d6d4-170">数据</span><span class="sxs-lookup"><span data-stu-id="0d6d4-170">Data</span></span>|<span data-ttu-id="0d6d4-171">Label</span><span class="sxs-lookup"><span data-stu-id="0d6d4-171">Label</span></span>|<span data-ttu-id="0d6d4-172">特征</span><span class="sxs-lookup"><span data-stu-id="0d6d4-172">Features</span></span>|
|-|-|-|-|-|
|<span data-ttu-id="0d6d4-173">价格预测</span><span class="sxs-lookup"><span data-stu-id="0d6d4-173">Price prediction</span></span>|<span data-ttu-id="0d6d4-174">回归</span><span class="sxs-lookup"><span data-stu-id="0d6d4-174">regression</span></span>|[<span data-ttu-id="0d6d4-175">出租车费数据</span><span class="sxs-lookup"><span data-stu-id="0d6d4-175">taxi fare data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/datasets/taxi-fare-train.csv)|<span data-ttu-id="0d6d4-176">车费</span><span class="sxs-lookup"><span data-stu-id="0d6d4-176">Fare</span></span>|<span data-ttu-id="0d6d4-177">行程时间、距离</span><span class="sxs-lookup"><span data-stu-id="0d6d4-177">Trip time, distance</span></span>|
|<span data-ttu-id="0d6d4-178">异常情况检测</span><span class="sxs-lookup"><span data-stu-id="0d6d4-178">Anomaly detection</span></span>|<span data-ttu-id="0d6d4-179">二元分类</span><span class="sxs-lookup"><span data-stu-id="0d6d4-179">binary classification</span></span>|[<span data-ttu-id="0d6d4-180">产品销售数据</span><span class="sxs-lookup"><span data-stu-id="0d6d4-180">product sales data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)|<span data-ttu-id="0d6d4-181">产品销售额</span><span class="sxs-lookup"><span data-stu-id="0d6d4-181">Product Sales</span></span>|<span data-ttu-id="0d6d4-182">月份</span><span class="sxs-lookup"><span data-stu-id="0d6d4-182">Month</span></span>|
|<span data-ttu-id="0d6d4-183">情绪分析</span><span class="sxs-lookup"><span data-stu-id="0d6d4-183">Sentiment analysis</span></span>|<span data-ttu-id="0d6d4-184">二元分类</span><span class="sxs-lookup"><span data-stu-id="0d6d4-184">binary classification</span></span>|[<span data-ttu-id="0d6d4-185">网站评论数据</span><span class="sxs-lookup"><span data-stu-id="0d6d4-185">website comment data</span></span>](https://raw.githubusercontent.com/dotnet/machinelearning/master/test/data/wikipedia-detox-250-line-data.tsv)|<span data-ttu-id="0d6d4-186">标签（负面情绪为 0，正面情绪为 1）</span><span class="sxs-lookup"><span data-stu-id="0d6d4-186">Label (0 when negative sentiment, 1 when positive)</span></span>|<span data-ttu-id="0d6d4-187">评论、年份</span><span class="sxs-lookup"><span data-stu-id="0d6d4-187">Comment, Year</span></span>|
|<span data-ttu-id="0d6d4-188">欺诈检测</span><span class="sxs-lookup"><span data-stu-id="0d6d4-188">Fraud detection</span></span>|<span data-ttu-id="0d6d4-189">二元分类</span><span class="sxs-lookup"><span data-stu-id="0d6d4-189">binary classification</span></span>|[<span data-ttu-id="0d6d4-190">信用卡数据</span><span class="sxs-lookup"><span data-stu-id="0d6d4-190">credit card data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/BinaryClassification_CreditCardFraudDetection/CreditCardFraudDetection.Trainer/assets/input/creditcardfraud-dataset.zip)|<span data-ttu-id="0d6d4-191">类（存在欺诈性为 1，否则为 0）</span><span class="sxs-lookup"><span data-stu-id="0d6d4-191">Class (1 when fraudulent, 0 otherwise)</span></span>|<span data-ttu-id="0d6d4-192">金额，V1-V28（匿名处理后的特征）</span><span class="sxs-lookup"><span data-stu-id="0d6d4-192">Amount, V1-V28 (anonymized features)</span></span>|
|<span data-ttu-id="0d6d4-193">文本分类</span><span class="sxs-lookup"><span data-stu-id="0d6d4-193">Text classification</span></span>|<span data-ttu-id="0d6d4-194">多类分类</span><span class="sxs-lookup"><span data-stu-id="0d6d4-194">multiclass classification</span></span>|[<span data-ttu-id="0d6d4-195">GitHub 问题数据</span><span class="sxs-lookup"><span data-stu-id="0d6d4-195">GitHub issue data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/end-to-end-apps/MulticlassClassification-GitHubLabeler/GitHubLabeler/Data/corefx-issues-train.tsv)|<span data-ttu-id="0d6d4-196">区域</span><span class="sxs-lookup"><span data-stu-id="0d6d4-196">Area</span></span>|<span data-ttu-id="0d6d4-197">标题、描述</span><span class="sxs-lookup"><span data-stu-id="0d6d4-197">Title, Description</span></span>|
|<span data-ttu-id="0d6d4-198">图像分类</span><span class="sxs-lookup"><span data-stu-id="0d6d4-198">Image classification</span></span>|<span data-ttu-id="0d6d4-199">多类分类</span><span class="sxs-lookup"><span data-stu-id="0d6d4-199">multiclass classification</span></span>|[<span data-ttu-id="0d6d4-200">花卉图像</span><span class="sxs-lookup"><span data-stu-id="0d6d4-200">Flowers images</span></span>](http://download.tensorflow.org/example_images/flower_photos.tgz)|<span data-ttu-id="0d6d4-201">花卉类型：雏菊、蒲公英、玫瑰、向日葵、郁金香</span><span class="sxs-lookup"><span data-stu-id="0d6d4-201">The type of flower: daisy, dandelion, roses, sunflowers, tulips</span></span>|<span data-ttu-id="0d6d4-202">图像数据本身</span><span class="sxs-lookup"><span data-stu-id="0d6d4-202">The image data itself</span></span>|

## <a name="train"></a><span data-ttu-id="0d6d4-203">训练</span><span class="sxs-lookup"><span data-stu-id="0d6d4-203">Train</span></span>

<span data-ttu-id="0d6d4-204">选择方案、数据和标签后，模型生成器会训练该模型。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-204">Once you select your scenario, data, and label, Model Builder trains the model.</span></span>

### <a name="what-is-training"></a><span data-ttu-id="0d6d4-205">什么是训练？</span><span class="sxs-lookup"><span data-stu-id="0d6d4-205">What is training?</span></span>

<span data-ttu-id="0d6d4-206">训练是一个自动的过程，模型生成器通过该过程教模型如何回答方案相关的问题。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-206">Training is an automatic process by which Model Builder teaches your model how to answer questions for your scenario.</span></span> <span data-ttu-id="0d6d4-207">训练后，模型可以对其没有见过的输入数据进行预测。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-207">Once trained, your model can make predictions with input data that it has not seen before.</span></span> <span data-ttu-id="0d6d4-208">例如，在预测房价时，可以预测新上市的房屋销售价。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-208">For example, if you are predicting house prices and a new house comes on the market, you can predict its sale price.</span></span>

<span data-ttu-id="0d6d4-209">因为模型生成器使用自动机器学习 (AutoML)，所以在训练期间不需要任何人工输入或微调操作。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-209">Because Model Builder uses automated machine learning (AutoML), it does not require any input or tuning from you during training.</span></span>

### <a name="how-long-should-i-train-for"></a><span data-ttu-id="0d6d4-210">训练时长应为多长时间？</span><span class="sxs-lookup"><span data-stu-id="0d6d4-210">How long should I train for?</span></span>

<span data-ttu-id="0d6d4-211">模型生成器使用 AutoML 浏览多个模型，以查找性能最佳的模型。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-211">Model Builder uses AutoML to explore multiple models to find you the best performing model.</span></span>

<span data-ttu-id="0d6d4-212">更长的训练周期允许 AutoML 通过更多设置来浏览更多模型。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-212">Longer training periods allow AutoML to explore more models with a wider range of settings.</span></span>

<span data-ttu-id="0d6d4-213">下表汇总了在本地计算机上为一组示例数据集获取良好性能所花的平均时间。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-213">The table below summarizes the average time taken to get good performance for a suite of example datasets, on a local machine.</span></span>

|<span data-ttu-id="0d6d4-214">数据集大小</span><span class="sxs-lookup"><span data-stu-id="0d6d4-214">Dataset size</span></span>|<span data-ttu-id="0d6d4-215">训练的平均时间</span><span class="sxs-lookup"><span data-stu-id="0d6d4-215">Average time to train</span></span>|
|------------|---------------------|
|<span data-ttu-id="0d6d4-216">0 - 10 MB</span><span class="sxs-lookup"><span data-stu-id="0d6d4-216">0 - 10 MB</span></span>|<span data-ttu-id="0d6d4-217">10 秒</span><span class="sxs-lookup"><span data-stu-id="0d6d4-217">10 sec</span></span>|
|<span data-ttu-id="0d6d4-218">10 - 100 MB</span><span class="sxs-lookup"><span data-stu-id="0d6d4-218">10 - 100 MB</span></span>|<span data-ttu-id="0d6d4-219">10 分钟</span><span class="sxs-lookup"><span data-stu-id="0d6d4-219">10 min</span></span>|
|<span data-ttu-id="0d6d4-220">100 - 500 MB</span><span class="sxs-lookup"><span data-stu-id="0d6d4-220">100 - 500 MB</span></span>|<span data-ttu-id="0d6d4-221">30 分钟</span><span class="sxs-lookup"><span data-stu-id="0d6d4-221">30 min</span></span>|
|<span data-ttu-id="0d6d4-222">500 - 1 GB</span><span class="sxs-lookup"><span data-stu-id="0d6d4-222">500 - 1 GB</span></span>|<span data-ttu-id="0d6d4-223">60 分钟</span><span class="sxs-lookup"><span data-stu-id="0d6d4-223">60 min</span></span>|
|<span data-ttu-id="0d6d4-224">1 GB 以上</span><span class="sxs-lookup"><span data-stu-id="0d6d4-224">1 GB+</span></span>|<span data-ttu-id="0d6d4-225">3 小时以上</span><span class="sxs-lookup"><span data-stu-id="0d6d4-225">3+ hours</span></span>|

<span data-ttu-id="0d6d4-226">这些数字仅用于指南。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-226">These numbers are a guide only.</span></span> <span data-ttu-id="0d6d4-227">训练的确切长度取决于：</span><span class="sxs-lookup"><span data-stu-id="0d6d4-227">The exact length of training is dependent on:</span></span>

- <span data-ttu-id="0d6d4-228">用作模型输入的特征（列）数</span><span class="sxs-lookup"><span data-stu-id="0d6d4-228">the number of features (columns) being used to as input to the model</span></span>
- <span data-ttu-id="0d6d4-229">列的类型</span><span class="sxs-lookup"><span data-stu-id="0d6d4-229">the type of columns</span></span>
- <span data-ttu-id="0d6d4-230">ML 任务</span><span class="sxs-lookup"><span data-stu-id="0d6d4-230">the ML task</span></span>
- <span data-ttu-id="0d6d4-231">用于训练的计算机的 CPU、磁盘和内存性能</span><span class="sxs-lookup"><span data-stu-id="0d6d4-231">the CPU, disk and memory performance of the machine used for training</span></span>

## <a name="evaluate"></a><span data-ttu-id="0d6d4-232">评估</span><span class="sxs-lookup"><span data-stu-id="0d6d4-232">Evaluate</span></span>

<span data-ttu-id="0d6d4-233">评估是衡量模型品质的过程。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-233">Evaluation is the process of measuring how good your model is.</span></span> <span data-ttu-id="0d6d4-234">模型生成器使用经过训练的模型对新的测试数据进行预测，然后度量预测效果的过程。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-234">Model Builder uses the trained model to make predictions with new test data, and then measures how good the predictions are.</span></span>

<span data-ttu-id="0d6d4-235">模型生成器将训练数据拆分为训练集和测试集。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-235">Model Builder splits the training data into a training set and a test set.</span></span> <span data-ttu-id="0d6d4-236">训练数据 (80%) 用于训练模型，测试数据 (20%) 用于评估模型。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-236">The training data (80%) is used to train your model and the test data (20%) is held back to evaluate your model.</span></span> 

### <a name="how-do-i-understand-my-model-performance"></a><span data-ttu-id="0d6d4-237">如何了解模型性能？</span><span class="sxs-lookup"><span data-stu-id="0d6d4-237">How do I understand my model performance?</span></span>

<span data-ttu-id="0d6d4-238">方案映射到机器学习任务。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-238">A scenario maps to a machine learning task.</span></span> <span data-ttu-id="0d6d4-239">每个 ML 任务都有其自己的一组评估指标。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-239">Each ML task has its own set of evaluation metrics.</span></span>

#### <a name="regression-for-example-price-prediction"></a><span data-ttu-id="0d6d4-240">回归（例如，价格预测）</span><span class="sxs-lookup"><span data-stu-id="0d6d4-240">Regression (for example, Price Prediction)</span></span>

<span data-ttu-id="0d6d4-241">回归问题的默认指标为 RSquared，RSquared 值的范围介于 0 和 1 之间。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-241">The default metric for regression problems is RSquared, the value of RSquared ranges between 0 and 1.</span></span> <span data-ttu-id="0d6d4-242">1 是可能的最大值，换句话说，RSquared 的值越接近 1，模型的性能就越好。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-242">1 is the best possible value or in other words the closer the value of RSquared to 1 the better your model is performing.</span></span>

<span data-ttu-id="0d6d4-243">报告的其他指标（如绝对损失、平方损失和 RMS 损失）为附加指标，可以用来理解模型的性能，并将其与其他回归模型进行比较。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-243">Other metrics reported such as absolute-loss, squared-loss, and RMS loss are additional metrics, which can be used to understand how your model is performing and comparing it against other regression models.</span></span>

#### <a name="binary-classification-for-example-sentiment-analysis"></a><span data-ttu-id="0d6d4-244">二元分类（例如情绪分析）</span><span class="sxs-lookup"><span data-stu-id="0d6d4-244">Binary Classification (for example, Sentiment Analysis)</span></span>

<span data-ttu-id="0d6d4-245">分类问题的默认指标是“准确性”。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-245">The default metric for classification problems is accuracy.</span></span> <span data-ttu-id="0d6d4-246">准确性定义的是模型对测试数据集做出的正确预测的比例。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-246">Accuracy defines the proportion of correct predictions your model is making over the test dataset.</span></span> <span data-ttu-id="0d6d4-247">越接近 100% 或 1.0 越好。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-247">The closer to 100% or 1.0 the better it is.</span></span>

<span data-ttu-id="0d6d4-248">报告的其他指标，如 AUC（曲线下面积），用于度量真正率和假正率之间的比例，在高于 0.50 时，才是可以接受的模型。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-248">Other metrics reported such as AUC (Area under the curve), which measures the true positive rate vs. the false positive rate should be greater than 0.50 for models to be acceptable.</span></span>

<span data-ttu-id="0d6d4-249">F1 分数等其他指标可用于控制精准率与召回率之间的平衡。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-249">Additional metrics like F1 score can be used to control the balance between Precision and Recall.</span></span>

#### <a name="multi-class-classification-for-example-issue-classification-image-classification"></a><span data-ttu-id="0d6d4-250">多类分类（例如，问题分类、映像分类）</span><span class="sxs-lookup"><span data-stu-id="0d6d4-250">Multi-Class Classification (for example, Issue Classification, Image Classification)</span></span>

<span data-ttu-id="0d6d4-251">多类分类问题的默认指标是微观准确性。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-251">The default metric for Multi-class classification is Micro Accuracy.</span></span> <span data-ttu-id="0d6d4-252">微观准确性越接近 100% 或 1.0 越好。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-252">The closer the Micro Accuracy to 100% or 1.0 the better it is.</span></span>

<span data-ttu-id="0d6d4-253">多类分类的另一个重要指标是宏观准确性，类似于微观准确性，越接近 1.0 越好。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-253">Another important metric for Multi-class classification is Macro-accuracy, similar to Micro-accuracy the closer to 1.0 the better it is.</span></span> <span data-ttu-id="0d6d4-254">考虑这两种准确性类型的一种好方法是：</span><span class="sxs-lookup"><span data-stu-id="0d6d4-254">A good way to think about these two types of accuracy is:</span></span>

- <span data-ttu-id="0d6d4-255">微观准确性：传入票证分类给正确团队的频率如何？</span><span class="sxs-lookup"><span data-stu-id="0d6d4-255">Micro-accuracy: How often does an incoming ticket get classified to the right team?</span></span>
- <span data-ttu-id="0d6d4-256">宏观准确性：对于普通团队而言，传入票证符合其业务范围的频率如何？</span><span class="sxs-lookup"><span data-stu-id="0d6d4-256">Macro-accuracy: For an average team, how often is an incoming ticket correct for their team?</span></span>

### <a name="more-information-on-evaluation-metrics"></a><span data-ttu-id="0d6d4-257">有关评估指标的详细信息</span><span class="sxs-lookup"><span data-stu-id="0d6d4-257">More information on evaluation metrics</span></span>

<span data-ttu-id="0d6d4-258">有关详细信息，请参阅[模型评估指标](resources/metrics.md)。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-258">For more information, see [model evaluation metrics](resources/metrics.md).</span></span>

## <a name="improve"></a><span data-ttu-id="0d6d4-259">改进</span><span class="sxs-lookup"><span data-stu-id="0d6d4-259">Improve</span></span>

<span data-ttu-id="0d6d4-260">如果模型性能评分不符合预期，可以：</span><span class="sxs-lookup"><span data-stu-id="0d6d4-260">If your model performance score is not as good as you want it to be, you can:</span></span>

- <span data-ttu-id="0d6d4-261">延长训练时间。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-261">Train for a longer period of time.</span></span> <span data-ttu-id="0d6d4-262">有了更多时间，自动机器学习引擎可以尝试更多算法和设置。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-262">With more time, the automated machine learning engine to try more algorithms and settings.</span></span>

- <span data-ttu-id="0d6d4-263">添加更多数据。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-263">Add more data.</span></span> <span data-ttu-id="0d6d4-264">有时候可能是数据量不足，无法训练出高质量的机器学习模型。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-264">Sometimes the amount of data is not sufficient to train a high-quality machine learning model.</span></span>

- <span data-ttu-id="0d6d4-265">均衡分配数据。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-265">Balance your data.</span></span> <span data-ttu-id="0d6d4-266">对于分类任务，请确保在各个类别间均匀分配训练集。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-266">For classification tasks, make sure that the training set is balanced across the categories.</span></span> <span data-ttu-id="0d6d4-267">例如，若有四个类别和 100 个训练示例，前两类（标记 1 和标记 2）包含 90 个记录，而剩下两类（标记 3 和标记 4）只包含 10 个记录，这就存在数据不均衡的问题，可能会导致模型很难正确预测标记 3 或标记 4。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-267">For example, if you have four classes for 100 training examples, and the two first classes (tag1 and tag2) are used for 90 records, but the other two (tag3 and tag4) are only used on the remaining 10 records, the lack of balanced data may cause your model to struggle to correctly predict tag3 or tag4.</span></span>

## <a name="code"></a><span data-ttu-id="0d6d4-268">代码</span><span class="sxs-lookup"><span data-stu-id="0d6d4-268">Code</span></span>

<span data-ttu-id="0d6d4-269">完成评估阶段后，模型生成器会输出一份模型文件和代码，可以使用该代码将模型添加到应用程序。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-269">After the evaluation phase, Model Builder outputs a model file, and code that you can use to add the model to your application.</span></span> <span data-ttu-id="0d6d4-270">ML.NET 模型保存为 zip 文件。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-270">ML.NET models are saved as a zip file.</span></span> <span data-ttu-id="0d6d4-271">用于加载和使用模型的代码会以新项目的形式添加到解决方案中。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-271">The code to load and use your model is added as a new project in your solution.</span></span> <span data-ttu-id="0d6d4-272">模型生成器还会添加一个示例控制台应用，可以运行该应用来查看工作状态下的模型。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-272">Model Builder also adds a sample console app that you can run to see your model in action.</span></span>

<span data-ttu-id="0d6d4-273">此外，模型生成器还会输出生成模型的代码，以便你能了解生成模型所使用的步骤。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-273">In addition, Model Builder outputs the code that generated the model, so that you can understand the steps used to generate the model.</span></span> <span data-ttu-id="0d6d4-274">还可以通过模型训练代码使用新的数据重新训练模型。</span><span class="sxs-lookup"><span data-stu-id="0d6d4-274">You can also use the model training code to retrain your model with new data.</span></span>

## <a name="whats-next"></a><span data-ttu-id="0d6d4-275">后续步骤</span><span class="sxs-lookup"><span data-stu-id="0d6d4-275">What's next?</span></span>

<span data-ttu-id="0d6d4-276">[安装](how-to-guides/install-model-builder.md)模型生成器 Visual Studio 扩展</span><span class="sxs-lookup"><span data-stu-id="0d6d4-276">[Install](how-to-guides/install-model-builder.md) the Model Builder Visual Studio extension</span></span>

<span data-ttu-id="0d6d4-277">请尝试[价格预测或任何回归方案](tutorials/predict-prices-with-model-builder.md)</span><span class="sxs-lookup"><span data-stu-id="0d6d4-277">Try [price prediction or any regression scenario](tutorials/predict-prices-with-model-builder.md)</span></span>

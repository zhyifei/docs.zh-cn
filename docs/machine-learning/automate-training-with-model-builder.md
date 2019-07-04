---
title: 什么是模型生成器，它的工作原理是怎样的？
description: 如何使用 ML.NET 模型生成器自动训练机器学习模型
author: natke
ms.date: 06/26/2019
ms.custom: overview
ms.openlocfilehash: 6f5bbe3c389e3ca42550a48ef3e6edbc963ac2e9
ms.sourcegitcommit: 52e588dc2ee74d484cd07ac60076be25cbf777ab
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2019
ms.locfileid: "67410585"
---
# <a name="what-is-model-builder-and-how-does-it-work"></a><span data-ttu-id="e75d9-103">什么是模型生成器，它的工作原理是怎样的？</span><span class="sxs-lookup"><span data-stu-id="e75d9-103">What is Model Builder and how does it work?</span></span>

<span data-ttu-id="e75d9-104">ML.NET 模型生成器是一个易于理解的图形化 Visual Studio 扩展，用于生成、训练和部署自定义机器学习模型。</span><span class="sxs-lookup"><span data-stu-id="e75d9-104">ML.NET Model Builder is an easy-to-understand graphical Visual Studio extension to build, train, and deploy custom machine learning models.</span></span> 

<span data-ttu-id="e75d9-105">模型生成器使用自动化的机器学习 (AutoML) 来探索不同的机器学习算法和设置，以帮助找到最合适的方案。</span><span class="sxs-lookup"><span data-stu-id="e75d9-105">Model Builder uses automated machine learning (AutoML) to explore different machine learning algorithms and settings to help you find the one that best suits your scenario.</span></span>

<span data-ttu-id="e75d9-106">使用模型生成器不需要具备机器学习的专业知识。</span><span class="sxs-lookup"><span data-stu-id="e75d9-106">You don't need machine learning expertise to use Model Builder.</span></span> <span data-ttu-id="e75d9-107">只需要一些数据，和确定要解决的问题。</span><span class="sxs-lookup"><span data-stu-id="e75d9-107">All you need is some data, and a problem to solve.</span></span> <span data-ttu-id="e75d9-108">模型生成器会生成将模型添加到 .NET 应用程序的代码。</span><span class="sxs-lookup"><span data-stu-id="e75d9-108">Model Builder generates the code to add the model to your .NET application.</span></span>

![模型生成器 Visual Studio 扩展用户界面动画](media/ml-dotnet-model-builder.gif)

> [!NOTE]
> <span data-ttu-id="e75d9-110">模型生成器当前为预览版。</span><span class="sxs-lookup"><span data-stu-id="e75d9-110">Model Builder is currently in Preview.</span></span>

## <a name="scenarios"></a><span data-ttu-id="e75d9-111">方案</span><span class="sxs-lookup"><span data-stu-id="e75d9-111">Scenarios</span></span>

<span data-ttu-id="e75d9-112">可以为模型生成器提供许多不同的方案，从而为应用程序生成一个机器学习模型。</span><span class="sxs-lookup"><span data-stu-id="e75d9-112">You can bring many different scenarios to Model Builder, to generate a machine learning model for your application.</span></span>

<span data-ttu-id="e75d9-113">方案就是要对数据进行的预测类型的描述。</span><span class="sxs-lookup"><span data-stu-id="e75d9-113">A scenario is a description of the type of prediction you want to make on your data.</span></span> <span data-ttu-id="e75d9-114">例如:</span><span class="sxs-lookup"><span data-stu-id="e75d9-114">For example:</span></span>
- <span data-ttu-id="e75d9-115">根据历史销售数据预测未来的产品销量</span><span class="sxs-lookup"><span data-stu-id="e75d9-115">predict future product sales volume based on historical sales data</span></span>
- <span data-ttu-id="e75d9-116">根据客户评价将情绪分类为正面或负面</span><span class="sxs-lookup"><span data-stu-id="e75d9-116">classify sentiments as positive or negative based on customer reviews</span></span>
- <span data-ttu-id="e75d9-117">检测某项银行交易是否存在欺诈性</span><span class="sxs-lookup"><span data-stu-id="e75d9-117">detect whether a banking transaction is fraudulent</span></span>
- <span data-ttu-id="e75d9-118">将客户反馈问题传递至公司中合适的团队</span><span class="sxs-lookup"><span data-stu-id="e75d9-118">route customer feedback issues to the correct team in your company</span></span>

<span data-ttu-id="e75d9-119">在模型生成器中，需要将方案映射到 [ML.NET 任务](resources/tasks.md)上。</span><span class="sxs-lookup"><span data-stu-id="e75d9-119">In Model Builder, you need to map your scenario onto an [ML.NET task](resources/tasks.md).</span></span> <span data-ttu-id="e75d9-120">可以使用模型生成器进行回归（预测数字）和分类（预测类别）   。</span><span class="sxs-lookup"><span data-stu-id="e75d9-120">You can use Model Builder for **regression** (predicting numbers) and **classification** (predicting categories).</span></span>

### <a name="which-machine-learning-scenario-is-right-for-me"></a><span data-ttu-id="e75d9-121">哪个机器学习方案最适合我？</span><span class="sxs-lookup"><span data-stu-id="e75d9-121">Which machine learning scenario is right for me?</span></span>

<span data-ttu-id="e75d9-122">模型生成器带有用于情绪分析、问题分类、价格预测和自定义方案的模板。</span><span class="sxs-lookup"><span data-stu-id="e75d9-122">Model Builder comes with templates for sentiment analysis, issue classification, price prediction, and custom scenarios.</span></span> <span data-ttu-id="e75d9-123">这些模板可以作为特定 ML.NET 方案的起点。</span><span class="sxs-lookup"><span data-stu-id="e75d9-123">These templates can be used as a starting point for your specific ML.NET scenario.</span></span>

#### <a name="sentiment-analysis-binary-classification"></a><span data-ttu-id="e75d9-124">情绪分析（二元分类）</span><span class="sxs-lookup"><span data-stu-id="e75d9-124">Sentiment analysis (binary classification)</span></span>

<span data-ttu-id="e75d9-125">情绪分析可用于预测的客户反馈中的正面情绪或负面情绪。</span><span class="sxs-lookup"><span data-stu-id="e75d9-125">Sentiment analysis can be used to predict positive or negative sentiment of customer feedback.</span></span> <span data-ttu-id="e75d9-126">它是一个二元分类任务的例子。</span><span class="sxs-lookup"><span data-stu-id="e75d9-126">It is an example of the binary classification task.</span></span>

<span data-ttu-id="e75d9-127">二元分类用于将数据分为两类（是/否；通过/失败；true/false；正面/负面）。</span><span class="sxs-lookup"><span data-stu-id="e75d9-127">Binary classification is used to categorize data into two classes (yes/no; pass/fail; true/false; positive/negative).</span></span> <span data-ttu-id="e75d9-128">该分类可回答类似于以下的问题：</span><span class="sxs-lookup"><span data-stu-id="e75d9-128">It can be used to answer questions such as:</span></span>

- <span data-ttu-id="e75d9-129">该电子邮件是否是垃圾邮件？</span><span class="sxs-lookup"><span data-stu-id="e75d9-129">Is this email spam?</span></span> <span data-ttu-id="e75d9-130">（垃圾邮件检测）</span><span class="sxs-lookup"><span data-stu-id="e75d9-130">(spam detection)</span></span>
- <span data-ttu-id="e75d9-131">哪些申请者有资格得到成员身份？</span><span class="sxs-lookup"><span data-stu-id="e75d9-131">Which applicants may be eligible for membership?</span></span> <span data-ttu-id="e75d9-132">（申请筛选）</span><span class="sxs-lookup"><span data-stu-id="e75d9-132">(application screening)</span></span>
- <span data-ttu-id="e75d9-133">哪些帐户可能不会按时支付发票？</span><span class="sxs-lookup"><span data-stu-id="e75d9-133">Which accounts may not pay their invoices on time?</span></span> <span data-ttu-id="e75d9-134">（风险缓解）</span><span class="sxs-lookup"><span data-stu-id="e75d9-134">(risk mitigation)</span></span>
- <span data-ttu-id="e75d9-135">此信用卡交易是否存在欺诈性？</span><span class="sxs-lookup"><span data-stu-id="e75d9-135">Is this credit card transaction fraudulent?</span></span> <span data-ttu-id="e75d9-136">（欺诈检测）</span><span class="sxs-lookup"><span data-stu-id="e75d9-136">(fraud detection)</span></span>

<span data-ttu-id="e75d9-137">如果方案需要将数据分为两类，可以将该模板与自己的数据集配合使用。</span><span class="sxs-lookup"><span data-stu-id="e75d9-137">If your scenario requires classification into two categories, you can use this template with your own dataset.</span></span>
 
#### <a name="issue-classification-multiclass-classification"></a><span data-ttu-id="e75d9-138">问题分类（多类分类）</span><span class="sxs-lookup"><span data-stu-id="e75d9-138">Issue classification (multiclass classification)</span></span>

<span data-ttu-id="e75d9-139">问题分类可用于使用问题标题和描述对客户反馈（例如 GitHub 上的反馈）问题进行分类。</span><span class="sxs-lookup"><span data-stu-id="e75d9-139">Issue classification can be used to categorize customer feedback (for example, on GitHub) issues using the issue title and description.</span></span> <span data-ttu-id="e75d9-140">它是一个多类分类任务的例子。</span><span class="sxs-lookup"><span data-stu-id="e75d9-140">It is an example of the multi-class classification task.</span></span>

<span data-ttu-id="e75d9-141">多类分类可用于将数据分为三类或更多类。</span><span class="sxs-lookup"><span data-stu-id="e75d9-141">Multiclass classification can be used to categorize data into three or more classes.</span></span> <span data-ttu-id="e75d9-142">该分类可回答类似于以下的问题：</span><span class="sxs-lookup"><span data-stu-id="e75d9-142">It can be used to answer questions such as:</span></span>

- <span data-ttu-id="e75d9-143">我应向哪个部门传递支持票证？</span><span class="sxs-lookup"><span data-stu-id="e75d9-143">To which department should I route a support ticket?</span></span> <span data-ttu-id="e75d9-144">（支持票证传递）</span><span class="sxs-lookup"><span data-stu-id="e75d9-144">(support ticket routing)</span></span>
- <span data-ttu-id="e75d9-145">客户问题的优先级是什么？</span><span class="sxs-lookup"><span data-stu-id="e75d9-145">What is the priority of a customer issue?</span></span> <span data-ttu-id="e75d9-146">（客户问题优先级）</span><span class="sxs-lookup"><span data-stu-id="e75d9-146">(customer issue prioritization)</span></span>
- <span data-ttu-id="e75d9-147">产品属于什么类别？</span><span class="sxs-lookup"><span data-stu-id="e75d9-147">What category does a product belong to?</span></span> <span data-ttu-id="e75d9-148">（产品分类）</span><span class="sxs-lookup"><span data-stu-id="e75d9-148">(product classification)</span></span>
- <span data-ttu-id="e75d9-149">文档是什么类型？</span><span class="sxs-lookup"><span data-stu-id="e75d9-149">What type of document?</span></span> <span data-ttu-id="e75d9-150">（文档/电子邮件分类）</span><span class="sxs-lookup"><span data-stu-id="e75d9-150">(document/email classification)</span></span>

<span data-ttu-id="e75d9-151">如果需要将数据分为三类或更多类，可以使用问题分类模板。</span><span class="sxs-lookup"><span data-stu-id="e75d9-151">You can use the issue classification template for your scenario if you want to categorize data into three or more categories.</span></span>

#### <a name="price-prediction-regression"></a><span data-ttu-id="e75d9-152">价格预测（回归）</span><span class="sxs-lookup"><span data-stu-id="e75d9-152">Price prediction (regression)</span></span>

<span data-ttu-id="e75d9-153">价格预测可以通过房屋的位置、大小等特点来预测房价。</span><span class="sxs-lookup"><span data-stu-id="e75d9-153">Price prediction can be used to predict house prices using location, size, and other characteristics of the house.</span></span> <span data-ttu-id="e75d9-154">它是一个回归任务的例子。</span><span class="sxs-lookup"><span data-stu-id="e75d9-154">It is an example of the regression task.</span></span>

<span data-ttu-id="e75d9-155">回归用于预测数字。</span><span class="sxs-lookup"><span data-stu-id="e75d9-155">Regression is used to predict numbers.</span></span> <span data-ttu-id="e75d9-156">该分类可回答类似于以下的问题：</span><span class="sxs-lookup"><span data-stu-id="e75d9-156">It can be used to answer questions such as:</span></span>

- <span data-ttu-id="e75d9-157">一套房屋的售价会是多少？</span><span class="sxs-lookup"><span data-stu-id="e75d9-157">What price will a house sell for?</span></span> <span data-ttu-id="e75d9-158">（价格预测）</span><span class="sxs-lookup"><span data-stu-id="e75d9-158">(price prediction)</span></span>
- <span data-ttu-id="e75d9-159">机械部件将在多长时间以后需要维修？</span><span class="sxs-lookup"><span data-stu-id="e75d9-159">After how much time will a mechanical part require maintenance?</span></span> <span data-ttu-id="e75d9-160">（预测性维护）</span><span class="sxs-lookup"><span data-stu-id="e75d9-160">(predictive maintenance)</span></span>
- <span data-ttu-id="e75d9-161">这台烘干机的含水量是多少？</span><span class="sxs-lookup"><span data-stu-id="e75d9-161">What is the moisture content in this dryer?</span></span> <span data-ttu-id="e75d9-162">（机器监控）</span><span class="sxs-lookup"><span data-stu-id="e75d9-162">(machine monitoring)</span></span>
- <span data-ttu-id="e75d9-163">此区域的年度销售总额将是多少？</span><span class="sxs-lookup"><span data-stu-id="e75d9-163">What will the total annual sales for this region be?</span></span> <span data-ttu-id="e75d9-164">（销售预测）</span><span class="sxs-lookup"><span data-stu-id="e75d9-164">(sales forecasting)</span></span>

<span data-ttu-id="e75d9-165">如果要使用自己的数据集预测数字值，可以使用价格预测模板。</span><span class="sxs-lookup"><span data-stu-id="e75d9-165">You can use the price prediction template for your scenario if you want to predict a numerical value with your own dataset.</span></span>

#### <a name="custom-scenario-choose-your-task"></a><span data-ttu-id="e75d9-166">自定义方案（选择自己的任务）</span><span class="sxs-lookup"><span data-stu-id="e75d9-166">Custom scenario (choose your task)</span></span>

<span data-ttu-id="e75d9-167">使用自定义方案，可以选择自己的任务。</span><span class="sxs-lookup"><span data-stu-id="e75d9-167">The custom scenario allows you to choose your own task.</span></span> <span data-ttu-id="e75d9-168">选择对问题最有帮助的方案。</span><span class="sxs-lookup"><span data-stu-id="e75d9-168">Pick the scenario that makes the most sense for your problem.</span></span>

<span data-ttu-id="e75d9-169">使用自定义方案，可以选择自己的机器学习任务。</span><span class="sxs-lookup"><span data-stu-id="e75d9-169">The custom scenario allows you to choose your own machine learning task.</span></span> <span data-ttu-id="e75d9-170">在之前介绍的各类模板中，机器学习任务仅限于二元分类、多类分类或回归这三种方案。</span><span class="sxs-lookup"><span data-stu-id="e75d9-170">In the previous templates, the machine learning task was fixed to the scenario: binary classification, multi-class classification, or regression.</span></span> <span data-ttu-id="e75d9-171">在此模板中，可以选择要对自己的数据使用的 ML 任务。</span><span class="sxs-lookup"><span data-stu-id="e75d9-171">In this template, you can choose the ML task you want to use on your data.</span></span>

## <a name="data"></a><span data-ttu-id="e75d9-172">数据</span><span class="sxs-lookup"><span data-stu-id="e75d9-172">Data</span></span>

<span data-ttu-id="e75d9-173">在将方案映射到任务上后，模型生成器会要求你提供数据集。</span><span class="sxs-lookup"><span data-stu-id="e75d9-173">Once you have mapped your scenario onto a task, Model Builder asks you to provide a dataset.</span></span> <span data-ttu-id="e75d9-174">这些数据用于训练、评估和选择最适合方案的的模型。</span><span class="sxs-lookup"><span data-stu-id="e75d9-174">The data is used to train, evaluate, and choose the best model for your scenario.</span></span> <span data-ttu-id="e75d9-175">还需要选择想预测的输出。</span><span class="sxs-lookup"><span data-stu-id="e75d9-175">You also need to choose the output you want to predict.</span></span>

### <a name="choose-the-output-to-predict-label"></a><span data-ttu-id="e75d9-176">选择要预测的输出（标签）</span><span class="sxs-lookup"><span data-stu-id="e75d9-176">Choose the output to predict (label)</span></span>

<span data-ttu-id="e75d9-177">数据集是一个表格，其中，行中含训练示例，列中含特性。</span><span class="sxs-lookup"><span data-stu-id="e75d9-177">A dataset is a table of rows of training examples, and columns of attributes.</span></span> <span data-ttu-id="e75d9-178">每一行都具有：</span><span class="sxs-lookup"><span data-stu-id="e75d9-178">Each row has:</span></span>
- <span data-ttu-id="e75d9-179">一个标签，即要预测的特性 </span><span class="sxs-lookup"><span data-stu-id="e75d9-179">a **label** (the attribute that you want to predict)</span></span>
- <span data-ttu-id="e75d9-180">特征（为预测标签而用作输入的特性）  。</span><span class="sxs-lookup"><span data-stu-id="e75d9-180">**features** (attributes that are used as inputs to predict the label).</span></span>

<span data-ttu-id="e75d9-181">在房价预测方案中，特性可能是：</span><span class="sxs-lookup"><span data-stu-id="e75d9-181">For the house-price prediction scenario, the features could be:</span></span>
- <span data-ttu-id="e75d9-182">房屋的面积</span><span class="sxs-lookup"><span data-stu-id="e75d9-182">the square footage of the house</span></span>
- <span data-ttu-id="e75d9-183">卧室和卫生间的数量</span><span class="sxs-lookup"><span data-stu-id="e75d9-183">the number of bedrooms and bathrooms</span></span>
- <span data-ttu-id="e75d9-184">邮政编码</span><span class="sxs-lookup"><span data-stu-id="e75d9-184">the zip code</span></span>

<span data-ttu-id="e75d9-185">标签是与其所属行（包含面积、卧室和卫生间值以及邮政编码信息）对应的历史房价。</span><span class="sxs-lookup"><span data-stu-id="e75d9-185">The label is the historical house price for that row of square footage, bedroom, and bathroom values and zip code.</span></span>

![表显示房价数据的行和列，其中包含由大小、房间数、邮政编码和价格标签组成的特征](media/model-builder-data.png)

### <a name="data-formats"></a><span data-ttu-id="e75d9-187">数据格式</span><span class="sxs-lookup"><span data-stu-id="e75d9-187">Data formats</span></span>

<span data-ttu-id="e75d9-188">模型生成器对数据设有以下限制：</span><span class="sxs-lookup"><span data-stu-id="e75d9-188">Model Builder places the following limitations on the data:</span></span>

- <span data-ttu-id="e75d9-189">数据必须存储在文件（具有标题行的 .csv 或.tsv 文件）或 SQL server 数据库中。</span><span class="sxs-lookup"><span data-stu-id="e75d9-189">Data must be stored in a file (.csv or .tsv with a header row), or in a SQL server database.</span></span>
- <span data-ttu-id="e75d9-190">训练数据集不能超过 1 GB</span><span class="sxs-lookup"><span data-stu-id="e75d9-190">A limit of 1 GB on the training dataset</span></span>
- <span data-ttu-id="e75d9-191">SQL Server 在训练用途上有 100,000 行的限制</span><span class="sxs-lookup"><span data-stu-id="e75d9-191">SQL server has a limit of 100,000 rows for training</span></span>
- <span data-ttu-id="e75d9-192">在训练之前，将 SQL server 中的数据从服务器复制到本地计算机</span><span class="sxs-lookup"><span data-stu-id="e75d9-192">Data from SQL server is copied from the server to your local machine before training</span></span>

### <a name="example-datasets"></a><span data-ttu-id="e75d9-193">示例数据集</span><span class="sxs-lookup"><span data-stu-id="e75d9-193">Example datasets</span></span>

<span data-ttu-id="e75d9-194">如果还没有自己的数据，请试用以下数据集之一：</span><span class="sxs-lookup"><span data-stu-id="e75d9-194">If you don't have your own data yet, try out one of these datasets:</span></span>

|<span data-ttu-id="e75d9-195">方案</span><span class="sxs-lookup"><span data-stu-id="e75d9-195">Scenario</span></span>|<span data-ttu-id="e75d9-196">ML 任务</span><span class="sxs-lookup"><span data-stu-id="e75d9-196">ML Task</span></span>|<span data-ttu-id="e75d9-197">数据</span><span class="sxs-lookup"><span data-stu-id="e75d9-197">Data</span></span>|<span data-ttu-id="e75d9-198">Label</span><span class="sxs-lookup"><span data-stu-id="e75d9-198">Label</span></span>|<span data-ttu-id="e75d9-199">功能</span><span class="sxs-lookup"><span data-stu-id="e75d9-199">Features</span></span>|
|-|-|-|-|-|
|<span data-ttu-id="e75d9-200">价格预测</span><span class="sxs-lookup"><span data-stu-id="e75d9-200">Price prediction</span></span>|<span data-ttu-id="e75d9-201">回归</span><span class="sxs-lookup"><span data-stu-id="e75d9-201">regression</span></span>|[<span data-ttu-id="e75d9-202">出租车费数据</span><span class="sxs-lookup"><span data-stu-id="e75d9-202">taxi fare data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/datasets/taxi-fare-train.csv)|<span data-ttu-id="e75d9-203">车费</span><span class="sxs-lookup"><span data-stu-id="e75d9-203">Fare</span></span>|<span data-ttu-id="e75d9-204">行程时间、距离</span><span class="sxs-lookup"><span data-stu-id="e75d9-204">Trip time, distance</span></span>|
|<span data-ttu-id="e75d9-205">异常情况检测</span><span class="sxs-lookup"><span data-stu-id="e75d9-205">Anomaly detection</span></span>|<span data-ttu-id="e75d9-206">二元分类</span><span class="sxs-lookup"><span data-stu-id="e75d9-206">binary classification</span></span>|[<span data-ttu-id="e75d9-207">产品销售数据</span><span class="sxs-lookup"><span data-stu-id="e75d9-207">product sales data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)|<span data-ttu-id="e75d9-208">产品销售额</span><span class="sxs-lookup"><span data-stu-id="e75d9-208">Product Sales</span></span>|<span data-ttu-id="e75d9-209">月份</span><span class="sxs-lookup"><span data-stu-id="e75d9-209">Month</span></span>|
|<span data-ttu-id="e75d9-210">情绪分析</span><span class="sxs-lookup"><span data-stu-id="e75d9-210">Sentiment analysis</span></span>|<span data-ttu-id="e75d9-211">二元分类</span><span class="sxs-lookup"><span data-stu-id="e75d9-211">binary classification</span></span>|[<span data-ttu-id="e75d9-212">网站评论数据</span><span class="sxs-lookup"><span data-stu-id="e75d9-212">website comment data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/BinaryClassification_SentimentAnalysis/SentimentAnalysis/Data/wikiDetoxAnnotated40kRows.tsv)|<span data-ttu-id="e75d9-213">标签（负面情绪为 0，正面情绪为 1）</span><span class="sxs-lookup"><span data-stu-id="e75d9-213">Label (0 when negative sentiment, 1 when positive)</span></span>|<span data-ttu-id="e75d9-214">评论、年份</span><span class="sxs-lookup"><span data-stu-id="e75d9-214">Comment, Year</span></span>|
|<span data-ttu-id="e75d9-215">欺诈检测</span><span class="sxs-lookup"><span data-stu-id="e75d9-215">Fraud detection</span></span>|<span data-ttu-id="e75d9-216">二元分类</span><span class="sxs-lookup"><span data-stu-id="e75d9-216">binary classification</span></span>|[<span data-ttu-id="e75d9-217">信用卡数据</span><span class="sxs-lookup"><span data-stu-id="e75d9-217">credit card data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/getting-started/BinaryClassification_CreditCardFraudDetection/CreditCardFraudDetection.Trainer/assets/input/creditcardfraud-dataset.zip)|<span data-ttu-id="e75d9-218">类（存在欺诈性为 1，否则为 0）</span><span class="sxs-lookup"><span data-stu-id="e75d9-218">Class (1 when fraudulent, 0 otherwise)</span></span>|<span data-ttu-id="e75d9-219">金额，V1-V28（匿名处理后的特征）</span><span class="sxs-lookup"><span data-stu-id="e75d9-219">Amount, V1-V28 (anonymized features)</span></span>|
|<span data-ttu-id="e75d9-220">文本分类</span><span class="sxs-lookup"><span data-stu-id="e75d9-220">Text classification</span></span>|<span data-ttu-id="e75d9-221">多类分类</span><span class="sxs-lookup"><span data-stu-id="e75d9-221">multiclass classification</span></span>|[<span data-ttu-id="e75d9-222">GitHub 问题数据</span><span class="sxs-lookup"><span data-stu-id="e75d9-222">GitHub issue data</span></span>](https://github.com/dotnet/machinelearning-samples/blob/master/samples/csharp/end-to-end-apps/MulticlassClassification-GitHubLabeler/GitHubLabeler/Data/corefx-issues-train.tsv)|<span data-ttu-id="e75d9-223">区域</span><span class="sxs-lookup"><span data-stu-id="e75d9-223">Area</span></span>|<span data-ttu-id="e75d9-224">标题、描述</span><span class="sxs-lookup"><span data-stu-id="e75d9-224">Title, Description</span></span>|

## <a name="train"></a><span data-ttu-id="e75d9-225">定型</span><span class="sxs-lookup"><span data-stu-id="e75d9-225">Train</span></span>

<span data-ttu-id="e75d9-226">选择方案、数据和标签后，模型生成器会训练该模型。</span><span class="sxs-lookup"><span data-stu-id="e75d9-226">Once you select your scenario, data, and label, Model Builder trains the model.</span></span>

### <a name="what-is-training"></a><span data-ttu-id="e75d9-227">什么是训练？</span><span class="sxs-lookup"><span data-stu-id="e75d9-227">What is training?</span></span>

<span data-ttu-id="e75d9-228">训练是一个自动的过程，模型生成器通过该过程教模型如何回答方案相关的问题。</span><span class="sxs-lookup"><span data-stu-id="e75d9-228">Training is an automatic process by which Model Builder teaches your model how to answer questions for your scenario.</span></span> <span data-ttu-id="e75d9-229">训练后，模型可以对其没有见过的输入数据进行预测。</span><span class="sxs-lookup"><span data-stu-id="e75d9-229">Once trained, your model can make predictions with input data that it has not seen before.</span></span> <span data-ttu-id="e75d9-230">例如，在预测房价时，可以预测新上市的房屋销售价。</span><span class="sxs-lookup"><span data-stu-id="e75d9-230">For example, if you are predicting house prices and a new house comes on the market, you can predict its sale price.</span></span>

<span data-ttu-id="e75d9-231">因为模型生成器使用自动机器学习 (AutoML)，所以在训练期间不需要任何人工输入或微调操作。</span><span class="sxs-lookup"><span data-stu-id="e75d9-231">Because Model Builder uses automated machine learning (AutoML), it does not require any input or tuning from you during training.</span></span>

### <a name="how-long-should-i-train-for"></a><span data-ttu-id="e75d9-232">训练时长应为多长时间？</span><span class="sxs-lookup"><span data-stu-id="e75d9-232">How long should I train for?</span></span>

<span data-ttu-id="e75d9-233">你可以提供一个训练时长。</span><span class="sxs-lookup"><span data-stu-id="e75d9-233">You can provide a training time.</span></span> <span data-ttu-id="e75d9-234">一般情况下，训练时间越长，生成的模型就越准确。</span><span class="sxs-lookup"><span data-stu-id="e75d9-234">In general, training for a longer time produces a more accurate model.</span></span> <span data-ttu-id="e75d9-235">如果训练用的数据集增大，训练时间也会变长。</span><span class="sxs-lookup"><span data-stu-id="e75d9-235">More training time is also required as the size of the training dataset increases.</span></span> <span data-ttu-id="e75d9-236">关于数据集大小增加和训练时间之间的关系，请参考下表。</span><span class="sxs-lookup"><span data-stu-id="e75d9-236">The following table gives some training time guidelines for datasets of increasing size.</span></span>

<span data-ttu-id="e75d9-237">数据集大小</span><span class="sxs-lookup"><span data-stu-id="e75d9-237">Dataset Size</span></span>  | <span data-ttu-id="e75d9-238">数据集类型</span><span class="sxs-lookup"><span data-stu-id="e75d9-238">Dataset Type</span></span>       | <span data-ttu-id="e75d9-239">平均训练时间</span><span class="sxs-lookup"><span data-stu-id="e75d9-239">Avg. Time to train</span></span>
------------- | ------------------ | --------------
<span data-ttu-id="e75d9-240">0 - 10 Mb</span><span class="sxs-lookup"><span data-stu-id="e75d9-240">0 - 10 Mb</span></span>     | <span data-ttu-id="e75d9-241">数值和文本</span><span class="sxs-lookup"><span data-stu-id="e75d9-241">Numeric and Text</span></span>   | <span data-ttu-id="e75d9-242">10 秒</span><span class="sxs-lookup"><span data-stu-id="e75d9-242">10 sec</span></span>
<span data-ttu-id="e75d9-243">10 - 100 Mb</span><span class="sxs-lookup"><span data-stu-id="e75d9-243">10 - 100 Mb</span></span>   | <span data-ttu-id="e75d9-244">数值和文本</span><span class="sxs-lookup"><span data-stu-id="e75d9-244">Numeric and Text</span></span>   | <span data-ttu-id="e75d9-245">10 分钟</span><span class="sxs-lookup"><span data-stu-id="e75d9-245">10 min</span></span> 
<span data-ttu-id="e75d9-246">100 - 500 Mb</span><span class="sxs-lookup"><span data-stu-id="e75d9-246">100 - 500 Mb</span></span>  | <span data-ttu-id="e75d9-247">数值和文本</span><span class="sxs-lookup"><span data-stu-id="e75d9-247">Numeric and Text</span></span>   | <span data-ttu-id="e75d9-248">30 分钟</span><span class="sxs-lookup"><span data-stu-id="e75d9-248">30 min</span></span> 
<span data-ttu-id="e75d9-249">500 - 1 Gb</span><span class="sxs-lookup"><span data-stu-id="e75d9-249">500 - 1 Gb</span></span>    | <span data-ttu-id="e75d9-250">数值和文本</span><span class="sxs-lookup"><span data-stu-id="e75d9-250">Numeric and Text</span></span>   | <span data-ttu-id="e75d9-251">60 分钟</span><span class="sxs-lookup"><span data-stu-id="e75d9-251">60 min</span></span> 
<span data-ttu-id="e75d9-252">1 Gb 以上</span><span class="sxs-lookup"><span data-stu-id="e75d9-252">1 Gb+</span></span>         | <span data-ttu-id="e75d9-253">数值和文本</span><span class="sxs-lookup"><span data-stu-id="e75d9-253">Numeric and Text</span></span>   | <span data-ttu-id="e75d9-254">3 小时以上</span><span class="sxs-lookup"><span data-stu-id="e75d9-254">3 hour+</span></span> 

<span data-ttu-id="e75d9-255">训练的确切时间还取决于：</span><span class="sxs-lookup"><span data-stu-id="e75d9-255">The exact time to train also depends on:</span></span>

- <span data-ttu-id="e75d9-256">列的类型（文本还是数值）</span><span class="sxs-lookup"><span data-stu-id="e75d9-256">the type of columns that is, text vs numeric</span></span>
- <span data-ttu-id="e75d9-257">机器学习任务的类型（回归还是分类）</span><span class="sxs-lookup"><span data-stu-id="e75d9-257">the type of machine learning task (regression or classification)</span></span>
- <span data-ttu-id="e75d9-258">用于训练的行数</span><span class="sxs-lookup"><span data-stu-id="e75d9-258">the number of rows used for training</span></span>
- <span data-ttu-id="e75d9-259">用于训练的特征列数</span><span class="sxs-lookup"><span data-stu-id="e75d9-259">the number of feature columns used for training</span></span>

<span data-ttu-id="e75d9-260">模型生成器已使用 1 TB 的数据集进行了大规模的测试，但为这么大的数据集生成高质量的模型可能需要多达 4 天的时间！</span><span class="sxs-lookup"><span data-stu-id="e75d9-260">Model Builder has been tested for scale with a 1-TB dataset, but building a high-quality model for that size of dataset can take up to four days!</span></span>

## <a name="evaluate"></a><span data-ttu-id="e75d9-261">评估</span><span class="sxs-lookup"><span data-stu-id="e75d9-261">Evaluate</span></span>

<span data-ttu-id="e75d9-262">评估是让经过训练的模型对新的测试数据进行预测，然后度量预测效果的过程。</span><span class="sxs-lookup"><span data-stu-id="e75d9-262">Evaluation is the process of using the trained model to make predictions with new test data, and then measuring how good the predictions are.</span></span>

<span data-ttu-id="e75d9-263">模型生成器将训练数据拆分为训练集和测试集。</span><span class="sxs-lookup"><span data-stu-id="e75d9-263">Model Builder splits the training data into a training set and a test set.</span></span> <span data-ttu-id="e75d9-264">训练数据 (80%) 用于训练模型，测试数据 (20%) 用于评估模型。</span><span class="sxs-lookup"><span data-stu-id="e75d9-264">The training data (80%) is used to train your model and the test data (20%) is held back to evaluate your model.</span></span>  <span data-ttu-id="e75d9-265">用于评估的指标取决于 ML 任务。</span><span class="sxs-lookup"><span data-stu-id="e75d9-265">The metrics used for evaluation depend on the ML task.</span></span> <span data-ttu-id="e75d9-266">有关详细信息，请参阅[模型评估指标](resources/metrics.md)。</span><span class="sxs-lookup"><span data-stu-id="e75d9-266">For more information, see [model evaluation metrics](resources/metrics.md).</span></span>  

### <a name="sentiment-analysis-binary-classification"></a><span data-ttu-id="e75d9-267">情绪分析（二元分类）</span><span class="sxs-lookup"><span data-stu-id="e75d9-267">Sentiment analysis (binary classification)</span></span>

<span data-ttu-id="e75d9-268">二元分类问题的默认指标是“准确性”  。</span><span class="sxs-lookup"><span data-stu-id="e75d9-268">The default metric for binary classification problems is **accuracy**.</span></span> <span data-ttu-id="e75d9-269">准确性定义的是模型对测试数据集做出的正确预测的比例。</span><span class="sxs-lookup"><span data-stu-id="e75d9-269">Accuracy defines the proportion of correct predictions your model makes over the test dataset.</span></span> <span data-ttu-id="e75d9-270">越接近 100% 越好  。</span><span class="sxs-lookup"><span data-stu-id="e75d9-270">The **closer to 100%, the better it is**.</span></span>

<span data-ttu-id="e75d9-271">报告的其他指标，如 AUC（曲线下面积），用于度量真正例率和假正例率之间的比例，在高于 0.50 时，才是可以接受的模型。</span><span class="sxs-lookup"><span data-stu-id="e75d9-271">Other metrics reported such as AUC (Area under the curve), which measures the true positive rate vs. the false positive rate, should be greater than 0.50 for models to be acceptable.</span></span> 

<span data-ttu-id="e75d9-272">此外还有一些其他指标，如 F1 分数，可以用来控制检准率（正确的预测占该类总预测数的比例）和检全率（正确预测占该类总实际成员的比例）之间的平衡。</span><span class="sxs-lookup"><span data-stu-id="e75d9-272">Additional metrics such as F1 score can be used to control the balance between precision (ratio of correct predictions to the total predictions of that class) and recall (proportion of correct predictions to the total actual members of that class).</span></span>

### <a name="issue-classification-multiclass-classification"></a><span data-ttu-id="e75d9-273">问题分类（多类分类）</span><span class="sxs-lookup"><span data-stu-id="e75d9-273">Issue classification (multiclass classification)</span></span>

<span data-ttu-id="e75d9-274">多类分类问题的默认指标是“微观准确性”  。</span><span class="sxs-lookup"><span data-stu-id="e75d9-274">The default metric for multiclass classification problems is **micro accuracy**.</span></span> <span data-ttu-id="e75d9-275">越接近 100% 越好  。</span><span class="sxs-lookup"><span data-stu-id="e75d9-275">The **closer to 100%, the better it is**.</span></span>

<span data-ttu-id="e75d9-276">在将数据分为多个类的问题中，有两种类型的准确性：</span><span class="sxs-lookup"><span data-stu-id="e75d9-276">For problems where data is categorized into multiple classes there are two types of accuracy:</span></span>

- <span data-ttu-id="e75d9-277">微观准确性：所有实例中正确预测的百分比。</span><span class="sxs-lookup"><span data-stu-id="e75d9-277">Micro-accuracy: the fraction of predictions that are correct across all instances.</span></span> <span data-ttu-id="e75d9-278">在问题分类方案中，微观准确性是分配到正确类别的传入问题的比例。</span><span class="sxs-lookup"><span data-stu-id="e75d9-278">In the issue classification scenario, micro-accuracy is the proportion of incoming issues that get assigned to the correct category.</span></span> 
- <span data-ttu-id="e75d9-279">宏观准确性：在类级别上得出的平均准确性。</span><span class="sxs-lookup"><span data-stu-id="e75d9-279">Macro-accuracy: the average accuracy at the class level.</span></span> <span data-ttu-id="e75d9-280">在问题分类方案中，会为每个类别测量准确性，然后对各个类别的准确性求平均值。</span><span class="sxs-lookup"><span data-stu-id="e75d9-280">In the issue classification scenario, the accuracy is measured for each category, and then the category accuracies are averaged.</span></span> <span data-ttu-id="e75d9-281">对于此指标，所有类得到的权重都是相等的。</span><span class="sxs-lookup"><span data-stu-id="e75d9-281">For this metric, all classes are given equal weight.</span></span> <span data-ttu-id="e75d9-282">如果是完全均匀的数据集（即每个类别中的示例数量相等），微观准确性和宏观准确性就是相同的。</span><span class="sxs-lookup"><span data-stu-id="e75d9-282">For perfectly balanced datasets (where there are an equal number of examples of each category), micro-accuracy and macro-accuracy are the same.</span></span>


### <a name="price-prediction-regression"></a><span data-ttu-id="e75d9-283">价格预测（回归）</span><span class="sxs-lookup"><span data-stu-id="e75d9-283">Price prediction (regression)</span></span>

<span data-ttu-id="e75d9-284">回归问题的默认指标是“RSquared”  。</span><span class="sxs-lookup"><span data-stu-id="e75d9-284">The default metric for regression problems is **RSquared**.</span></span> <span data-ttu-id="e75d9-285">1 是可能达到的最佳值。</span><span class="sxs-lookup"><span data-stu-id="e75d9-285">1 is the best possible value.</span></span> <span data-ttu-id="e75d9-286">RSquared 越接近 1，模型就越好。</span><span class="sxs-lookup"><span data-stu-id="e75d9-286">The closer RSquared is to 1, the better your model is.</span></span>

<span data-ttu-id="e75d9-287">报告的其他指标，如绝对损失、平方损失和 RMS 损失，可以用来理解模型，并将其与其他回归模型进行比较。</span><span class="sxs-lookup"><span data-stu-id="e75d9-287">Other metrics reported, such as absolute-loss, squared-loss, and RMS loss can be used to understand your model, and compare it with other regression models.</span></span> 

## <a name="improve"></a><span data-ttu-id="e75d9-288">改进</span><span class="sxs-lookup"><span data-stu-id="e75d9-288">Improve</span></span>

<span data-ttu-id="e75d9-289">如果模型性能评分不符合预期，可以：</span><span class="sxs-lookup"><span data-stu-id="e75d9-289">If your model performance score is not as good as you want it to be, you can:</span></span>

* <span data-ttu-id="e75d9-290">延长训练时间。</span><span class="sxs-lookup"><span data-stu-id="e75d9-290">Train for a longer period of time.</span></span> <span data-ttu-id="e75d9-291">有了更多时间，自动机器学习引擎可以尝试更多算法和设置。</span><span class="sxs-lookup"><span data-stu-id="e75d9-291">With more time, the automated machine learning engine to try more algorithms and settings.</span></span>

* <span data-ttu-id="e75d9-292">添加更多数据。</span><span class="sxs-lookup"><span data-stu-id="e75d9-292">Add more data.</span></span> <span data-ttu-id="e75d9-293">有时候可能是数据量不足，无法训练出高质量的机器学习模型。</span><span class="sxs-lookup"><span data-stu-id="e75d9-293">Sometimes the amount of data is not sufficient to train a high-quality machine learning model.</span></span> 

* <span data-ttu-id="e75d9-294">均衡分配数据。</span><span class="sxs-lookup"><span data-stu-id="e75d9-294">Balance your data.</span></span> <span data-ttu-id="e75d9-295">对于分类任务，请确保在各个类别间均匀分配训练集。</span><span class="sxs-lookup"><span data-stu-id="e75d9-295">For classification tasks, make sure that the training set is balanced across the categories.</span></span> <span data-ttu-id="e75d9-296">例如，若有四个类别和 100 个训练示例，前两类（标记 1 和标记 2）包含 90 个记录，而剩下两类（标记 3 和标记 4）只包含 10 个记录，这就存在数据不均衡的问题，可能会导致模型很难正确预测标记 3 或标记 4。</span><span class="sxs-lookup"><span data-stu-id="e75d9-296">For example, if you have four classes for 100 training examples, and the two first classes (tag1 and tag2) are used for 90 records, but the other two (tag3 and tag4) are only used on the remaining 10 records, the lack of balanced data may cause your model to struggle to correctly predict tag3 or tag4.</span></span>

## <a name="code"></a><span data-ttu-id="e75d9-297">代码</span><span class="sxs-lookup"><span data-stu-id="e75d9-297">Code</span></span>

<span data-ttu-id="e75d9-298">完成评估阶段后，模型生成器会输出一份模型文件和代码，可以使用该代码将模型添加到应用程序。</span><span class="sxs-lookup"><span data-stu-id="e75d9-298">After the evaluation phase, Model Builder outputs a model file, and code that you can use to add the model to your application.</span></span> <span data-ttu-id="e75d9-299">ML.NET 模型保存为 zip 文件。</span><span class="sxs-lookup"><span data-stu-id="e75d9-299">ML.NET models are saved as a zip file.</span></span> <span data-ttu-id="e75d9-300">用于加载和使用模型的代码会以新项目的形式添加到解决方案中。</span><span class="sxs-lookup"><span data-stu-id="e75d9-300">The code to load and use your model is added as a new project in your solution.</span></span> <span data-ttu-id="e75d9-301">模型生成器还会添加一个示例控制台应用，可以运行该应用来查看工作状态下的模型。</span><span class="sxs-lookup"><span data-stu-id="e75d9-301">Model Builder also adds a sample console app that you can run to see your model in action.</span></span>

<span data-ttu-id="e75d9-302">此外，模型生成器还会输出生成模型的代码，以便你能了解生成模型所使用的步骤。</span><span class="sxs-lookup"><span data-stu-id="e75d9-302">In addition, Model Builder outputs the code that generated the model, so that you can understand the steps used to generate the model.</span></span> <span data-ttu-id="e75d9-303">还可以通过模型训练代码使用新的数据重新训练模型。</span><span class="sxs-lookup"><span data-stu-id="e75d9-303">You can also use the model training code to retrain your model with new data.</span></span>

## <a name="whats-next"></a><span data-ttu-id="e75d9-304">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e75d9-304">What's next?</span></span>

<span data-ttu-id="e75d9-305">请尝试[价格预测或任何回归方案](tutorials/predict-prices-with-model-builder.md)</span><span class="sxs-lookup"><span data-stu-id="e75d9-305">Try [price prediction or any regression scenario](tutorials/predict-prices-with-model-builder.md)</span></span>

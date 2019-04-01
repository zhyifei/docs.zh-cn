---
title: 在影片推荐方案中使用 ML.NET
description: 了解如何在推荐方案中使用 ML.NET 向用户推荐影片。
author: briacht
ms.author: johalex
ms.date: 03/08/2019
ms.custom: mvc
ms.topic: tutorial
ms.openlocfilehash: e78772df1cf7e5f8999305a1b726a7085f94601b
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2019
ms.locfileid: "58410064"
---
# <a name="tutorial-create-a-movie-recommender-with-mlnet"></a><span data-ttu-id="d980f-103">教程：使用 ML.NET 创建影片推荐系统</span><span class="sxs-lookup"><span data-stu-id="d980f-103">Tutorial: Create a Movie Recommender with ML.NET</span></span>

<span data-ttu-id="d980f-104">此示例教程通过在 Visual Studio 2017 中使用 C# 的 .NET Core 控制台应用程序，演示如何使用 ML.NET 创建影片推荐系统。</span><span class="sxs-lookup"><span data-stu-id="d980f-104">This sample tutorial illustrates using ML.NET to build a movie recommender via a .NET Core console application using C# in Visual Studio 2017.</span></span>

<span data-ttu-id="d980f-105">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="d980f-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="d980f-106">选择机器学习算法</span><span class="sxs-lookup"><span data-stu-id="d980f-106">Select a machine learning algorithm</span></span>
> * <span data-ttu-id="d980f-107">准备并加载数据</span><span class="sxs-lookup"><span data-stu-id="d980f-107">Prepare and load your data</span></span>
> * <span data-ttu-id="d980f-108">生成并训练模型</span><span class="sxs-lookup"><span data-stu-id="d980f-108">Build and train a model</span></span>
> * <span data-ttu-id="d980f-109">评估模型</span><span class="sxs-lookup"><span data-stu-id="d980f-109">Evaluate a model</span></span>
> * <span data-ttu-id="d980f-110">部署和使用模型</span><span class="sxs-lookup"><span data-stu-id="d980f-110">Deploy and consume a model</span></span>

> [!NOTE]
> <span data-ttu-id="d980f-111">本主题引用 ML.NET（目前处于预览状态），且材料可能会更改。</span><span class="sxs-lookup"><span data-stu-id="d980f-111">This topic refers to ML.NET, which is currently in Preview, and material may be subject to change.</span></span> <span data-ttu-id="d980f-112">有关详细信息，请访问 [ML.NET 简介](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet)。</span><span class="sxs-lookup"><span data-stu-id="d980f-112">For more information, visit [the ML.NET introduction](https://www.microsoft.com/net/learn/apps/machine-learning-and-ai/ml-dotnet).</span></span>

<span data-ttu-id="d980f-113">此教程和相关示例目前使用的是 ML.NET 版本 0.11。</span><span class="sxs-lookup"><span data-stu-id="d980f-113">This tutorial and related sample are currently using **ML.NET version 0.11**.</span></span> <span data-ttu-id="d980f-114">有关详细信息，请参阅 [dotnet/machinelearning GitHub 存储库](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes)上的发行说明。</span><span class="sxs-lookup"><span data-stu-id="d980f-114">For more information, see the release notes at the [dotnet/machinelearning GitHub repo](https://github.com/dotnet/machinelearning/tree/master/docs/release-notes).</span></span>

<span data-ttu-id="d980f-115">可以在 [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/MovieRecommendation) 存储库中找到本教程的源代码。</span><span class="sxs-lookup"><span data-stu-id="d980f-115">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/MovieRecommendation) repository.</span></span>

## <a name="machine-learning-workflow"></a><span data-ttu-id="d980f-116">机器学习工作流</span><span class="sxs-lookup"><span data-stu-id="d980f-116">Machine learning workflow</span></span>
<span data-ttu-id="d980f-117">你将使用以下步骤完成任务，以及任何其他 ML.NET 任务：</span><span class="sxs-lookup"><span data-stu-id="d980f-117">You will use the following steps to accomplish your task, as well as any other ML.NET task:</span></span>

1. [<span data-ttu-id="d980f-118">加载数据</span><span class="sxs-lookup"><span data-stu-id="d980f-118">Load your data</span></span>](#load-your-data)
2. [<span data-ttu-id="d980f-119">生成并训练模型</span><span class="sxs-lookup"><span data-stu-id="d980f-119">Build and train your model</span></span>](#build-and-train-your-model)
3. [<span data-ttu-id="d980f-120">评估模型</span><span class="sxs-lookup"><span data-stu-id="d980f-120">Evaluate your model</span></span>](#evaluate-your-model)
4. [<span data-ttu-id="d980f-121">使用模型</span><span class="sxs-lookup"><span data-stu-id="d980f-121">Use your model</span></span>](#use-your-model)

## <a name="prerequisites"></a><span data-ttu-id="d980f-122">系统必备</span><span class="sxs-lookup"><span data-stu-id="d980f-122">Prerequisites</span></span>

* <span data-ttu-id="d980f-123">安装了“.NET Core 跨平台开发”工作负载的 [Visual Studio 2017 15.6 或更高版本](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)。</span><span class="sxs-lookup"><span data-stu-id="d980f-123">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="d980f-124">选择适当的机器学习任务</span><span class="sxs-lookup"><span data-stu-id="d980f-124">Select the appropriate machine learning task</span></span>

<span data-ttu-id="d980f-125">有几种方法可以解决推荐问题，如推荐影片列表或推荐相关产品列表，但此示例中将预测用户给予特定影片的评分 (1-5) 并在评分高于定义的阈值时推荐该影片（评分越高，用户喜欢特定电影的可能性就越大）。</span><span class="sxs-lookup"><span data-stu-id="d980f-125">There are several ways to approach recommendation problems, such as recommending a list of movies or recommending a list of related products, but in this case you will predict what rating (1-5) a user will give to a particular movie and recommend that movie if it's higher than a defined threshold (the higher the rating, the higher the likelihood of a user liking a particular movie).</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="d980f-126">创建控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="d980f-126">Create a console application</span></span>

### <a name="create-a-project"></a><span data-ttu-id="d980f-127">创建项目</span><span class="sxs-lookup"><span data-stu-id="d980f-127">Create a project</span></span>

1. <span data-ttu-id="d980f-128">打开 Visual Studio 2017。</span><span class="sxs-lookup"><span data-stu-id="d980f-128">Open Visual Studio 2017.</span></span> <span data-ttu-id="d980f-129">从菜单栏中选择“文件” > “新建” > “项目”。</span><span class="sxs-lookup"><span data-stu-id="d980f-129">Select **File** > **New** > **Project** from the menu bar.</span></span> <span data-ttu-id="d980f-130">在“新项目”对话框中，依次选择“Visual C#”和“.NET Core”节点。</span><span class="sxs-lookup"><span data-stu-id="d980f-130">In the **New Project** dialog, select the **Visual C#** node followed by the **.NET Core** node.</span></span> <span data-ttu-id="d980f-131">然后，选择“控制台应用程序(.NET Core)”项目模板。</span><span class="sxs-lookup"><span data-stu-id="d980f-131">Then select the **Console App (.NET Core)** project template.</span></span> <span data-ttu-id="d980f-132">在“名称”文本框中，键入“MovieRecommender”，然后选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="d980f-132">In the **Name** text box, type "MovieRecommender" and then select the **OK** button.</span></span>

2. <span data-ttu-id="d980f-133">在项目中创建一个名为“数据”的目录来保存数据集文件：</span><span class="sxs-lookup"><span data-stu-id="d980f-133">Create a directory named *Data* in your project to store the data set:</span></span>

    <span data-ttu-id="d980f-134">在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新文件夹”。</span><span class="sxs-lookup"><span data-stu-id="d980f-134">In **Solution Explorer**, right-click the project and select **Add** > **New Folder**.</span></span> <span data-ttu-id="d980f-135">键入“Data”，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="d980f-135">Type "Data" and hit Enter.</span></span>

3. <span data-ttu-id="d980f-136">安装“Microsoft.ML”和“Microsoft.ML.Recommender”NuGet 包：</span><span class="sxs-lookup"><span data-stu-id="d980f-136">Install the **Microsoft.ML** and **Microsoft.ML.Recommender** NuGet Packages:</span></span>

    <span data-ttu-id="d980f-137">在“解决方案资源管理器”中，右键单击项目，然后选择“管理 NuGet 包”。</span><span class="sxs-lookup"><span data-stu-id="d980f-137">In **Solution Explorer**, right-click the project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="d980f-138">将“nuget.org”选择为“包源”，选择“浏览”选项卡并搜索“Microsoft.ML”，在列表中选择该包，然后选择“安装”按钮。</span><span class="sxs-lookup"><span data-stu-id="d980f-138">Choose "nuget.org" as the Package source, select the **Browse** tab, search for **Microsoft.ML**, select that package in the list, and select the **Install** button.</span></span> <span data-ttu-id="d980f-139">选择“预览更改”对话框上的“确定”按钮，如果你同意所列包的许可条款，则选择“接受许可”对话框上的“我接受”按钮。</span><span class="sxs-lookup"><span data-stu-id="d980f-139">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span> <span data-ttu-id="d980f-140">对“Microsoft.ML.Recommender”重复这些步骤。</span><span class="sxs-lookup"><span data-stu-id="d980f-140">Repeat these steps for **Microsoft.ML.Recommender**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="d980f-141">本教程使用“Microsoft.ML v0.11.0”和“Microsoft.ML.Recommender v0.11.0”。</span><span class="sxs-lookup"><span data-stu-id="d980f-141">This tutorial uses **Microsoft.ML v0.11.0** and **Microsoft.ML.Recommender v0.11.0**.</span></span>
    
4. <span data-ttu-id="d980f-142">在 Program.cs 文件的顶部添加以下 `using` 语句：</span><span class="sxs-lookup"><span data-stu-id="d980f-142">Add the following `using` statements at the top of your *Program.cs* file:</span></span>
    
    [!code-csharp[UsingStatements](../../../samples/machine-learning/tutorials/MovieRecommendation/Program.cs#UsingStatements "Add necessary usings")]

### <a name="download-your-data"></a><span data-ttu-id="d980f-143">下载数据</span><span class="sxs-lookup"><span data-stu-id="d980f-143">Download your data</span></span>

1. <span data-ttu-id="d980f-144">下载两个数据集并将其保存到先前创建的“数据”文件夹中：</span><span class="sxs-lookup"><span data-stu-id="d980f-144">Download the two datasets and save them to the *Data* folder you previously created:</span></span>

*   <span data-ttu-id="d980f-145">右键单击 [recommended-ratings-train.csv](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/MatrixFactorization_MovieRecommendation/Data/recommendation-ratings-train.csv)，然后选择“将链接(或目标)另存为...”</span><span class="sxs-lookup"><span data-stu-id="d980f-145">Right click on [*recommendation-ratings-train.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/MatrixFactorization_MovieRecommendation/Data/recommendation-ratings-train.csv) and select "Save Link (or Target) As..."</span></span>
*   <span data-ttu-id="d980f-146">右键单击 [recommendation-ratings-test.csv](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/MatrixFactorization_MovieRecommendation/Data/recommendation-ratings-test.csv)，然后选择“将链接(或目标)另存为...”</span><span class="sxs-lookup"><span data-stu-id="d980f-146">Right click on [*recommendation-ratings-test.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/MatrixFactorization_MovieRecommendation/Data/recommendation-ratings-test.csv) and select "Save Link (or Target) As..."</span></span>

     <span data-ttu-id="d980f-147">确保将 .csv 文件保存到“数据”文件夹，或者将其保存到其他位置后，将 .csv 文件移动到“数据”文件夹\*\*。</span><span class="sxs-lookup"><span data-stu-id="d980f-147">Make sure you either save the \*.csv files to the *Data* folder, or after you save it elsewhere, move the \*.csv files to the *Data* folder.</span></span>

2. <span data-ttu-id="d980f-148">在“解决方案资源管理器”中，右键单击每个 \*.csv 文件，然后选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="d980f-148">In Solution Explorer, right-click each of the \*.csv files and select **Properties**.</span></span> <span data-ttu-id="d980f-149">在“高级”下，将“复制到输出目录”的值更改为“如果较新则复制”。</span><span class="sxs-lookup"><span data-stu-id="d980f-149">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

   ![如果在 VS 中较新则复制](./media/movie-recommendation/copytoout.gif)

## <a name="load-your-data"></a><span data-ttu-id="d980f-151">加载数据</span><span class="sxs-lookup"><span data-stu-id="d980f-151">Load your data</span></span>

<span data-ttu-id="d980f-152">ML.NET 过程的第一步是准备并加载用于训练和测试数据的模型。</span><span class="sxs-lookup"><span data-stu-id="d980f-152">The first step in the ML.NET process is to prepare and load your model training and testing data.</span></span>

<span data-ttu-id="d980f-153">建议分级数据分为 `Train` 和 `Test` 数据集。</span><span class="sxs-lookup"><span data-stu-id="d980f-153">The recommendation ratings data is split into `Train` and `Test` datasets.</span></span> <span data-ttu-id="d980f-154">`Train` 数据用于适应模型。</span><span class="sxs-lookup"><span data-stu-id="d980f-154">The `Train` data is used to fit your model.</span></span> <span data-ttu-id="d980f-155">`Test` 数据用于使用经过训练的模型进行预测并评估模型性能。</span><span class="sxs-lookup"><span data-stu-id="d980f-155">The `Test` data is used to make predictions with your trained model and evaluate model performance.</span></span> <span data-ttu-id="d980f-156">通常使用 `Train` 和 `Test` 数据进行 80/20 拆分。</span><span class="sxs-lookup"><span data-stu-id="d980f-156">It's common to have an 80/20 split with `Train` and `Test` data.</span></span>

<span data-ttu-id="d980f-157">以下是 .csv 文件中数据的预览：\*</span><span class="sxs-lookup"><span data-stu-id="d980f-157">Below is a preview of the data from your \*.csv files:</span></span>

![数据的预览](./media/movie-recommendation/csv-dataset-preview.png)

<span data-ttu-id="d980f-159">在 .csv 文件中，有四列：\*</span><span class="sxs-lookup"><span data-stu-id="d980f-159">In the \*.csv files, there are four columns:</span></span>

* `userId`
* `movieId`
* `rating`
* `timestamp`

<span data-ttu-id="d980f-160">在机器学习中，用于进行预测的列称为 [Features](../resources/glossary.md#feature)，带有返回预测的列称为 [Label](../resources/glossary.md#label)。</span><span class="sxs-lookup"><span data-stu-id="d980f-160">In machine learning, the columns that are used to make a prediction are called [Features](../resources/glossary.md#feature), and the column with the returned prediction is called the [Label](../resources/glossary.md#label).</span></span>

<span data-ttu-id="d980f-161">想要预测影片评分，因此评分列为 `Label`。</span><span class="sxs-lookup"><span data-stu-id="d980f-161">You want to predict movie ratings, so the rating column is the `Label`.</span></span> <span data-ttu-id="d980f-162">其他三列，`userId``movieId` 和 `timestamp` 都用 `Features` 来预测 `Label`。</span><span class="sxs-lookup"><span data-stu-id="d980f-162">The other three columns, `userId`, `movieId`, and `timestamp` are all `Features` used to predict the `Label`.</span></span>

| <span data-ttu-id="d980f-163">功能</span><span class="sxs-lookup"><span data-stu-id="d980f-163">Features</span></span>      | <span data-ttu-id="d980f-164">Label</span><span class="sxs-lookup"><span data-stu-id="d980f-164">Label</span></span>         |
| ------------- |:-------------:|
| `userId`        |    `rating`     |
| `movieId`      |               |
| `timestamp`     |               |

<span data-ttu-id="d980f-165">由你来决定使用哪个 `Features` 来预测 `Label`。</span><span class="sxs-lookup"><span data-stu-id="d980f-165">It's up to you to decide which `Features` are used to predict the `Label`.</span></span> <span data-ttu-id="d980f-166">你还可以使用[特征排列重要性](../how-to-guides/determine-global-feature-importance-in-model.md)等方法来帮助选择最佳 `Features`。</span><span class="sxs-lookup"><span data-stu-id="d980f-166">You can also use methods like [Feature Permutation Importance](../how-to-guides/determine-global-feature-importance-in-model.md) to help with selecting the best `Features`.</span></span>

<span data-ttu-id="d980f-167">在此示例中，应将 `timestamp` 列排除为 `Feature`，因为时间戳并不会真正影响用户对给定影片的评分方式，因此无法进行更准确的预测：</span><span class="sxs-lookup"><span data-stu-id="d980f-167">In this case, you should eliminate the `timestamp` column as a `Feature` because the timestamp does not really affect how a user rates a given movie and thus would not contribute to making a more accurate prediction:</span></span>

| <span data-ttu-id="d980f-168">功能</span><span class="sxs-lookup"><span data-stu-id="d980f-168">Features</span></span>      | <span data-ttu-id="d980f-169">Label</span><span class="sxs-lookup"><span data-stu-id="d980f-169">Label</span></span>         |
| ------------- |:-------------:|
| `userId`        |    `rating`     |
| `movieId`      |               |

<span data-ttu-id="d980f-170">接下来，必须为输入类定义数据结构。</span><span class="sxs-lookup"><span data-stu-id="d980f-170">Next you must define your data structure for the input class.</span></span>

<span data-ttu-id="d980f-171">向项目添加一个新类：</span><span class="sxs-lookup"><span data-stu-id="d980f-171">Add a new class to your project:</span></span>

1. <span data-ttu-id="d980f-172">在“解决方案资源管理器”中，右键单击该项目，然后选择“添加”>“新项”。</span><span class="sxs-lookup"><span data-stu-id="d980f-172">In **Solution Explorer**, right-click the project, and then select **Add > New Item**.</span></span>

2. <span data-ttu-id="d980f-173">在“添加新项”对话框中，选择“类”并将“名称”字段更改为“MovieRatingData.cs”。</span><span class="sxs-lookup"><span data-stu-id="d980f-173">In the **Add New Item dialog box**, select **Class** and change the **Name** field to *MovieRatingData.cs*.</span></span> <span data-ttu-id="d980f-174">然后，选择“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="d980f-174">Then, select the **Add** button.</span></span>

<span data-ttu-id="d980f-175">“MovieRatingData.cs”文件随即在代码编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="d980f-175">The *MovieRatingData.cs* file opens in the code editor.</span></span> <span data-ttu-id="d980f-176">将下面的 `using` 语句添加到 MovieRatingData.cs 的顶部：</span><span class="sxs-lookup"><span data-stu-id="d980f-176">Add the following `using` statement to the top of *MovieRatingData.cs*:</span></span>

```csharp
using Microsoft.ML.Data;
```

<span data-ttu-id="d980f-177">通过删除现有的类定义并在 MovieRatingData.cs 中添加以下代码，创建一个名为 `MovieRating` 的类：</span><span class="sxs-lookup"><span data-stu-id="d980f-177">Create a class called `MovieRating` by removing the existing class definition and adding the following code in *MovieRatingData.cs*:</span></span>

[!code-csharp[MovieRatingClass](../../../samples/machine-learning/tutorials/MovieRecommendation/MovieRatingData.cs#MovieRatingClass "Add the Movie Rating class")]

<span data-ttu-id="d980f-178">`MovieRating` 指定输入数据类。</span><span class="sxs-lookup"><span data-stu-id="d980f-178">`MovieRating` specifies an input data class.</span></span> <span data-ttu-id="d980f-179">[LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) 属性指定应加载数据集中的哪些列（按列索引）。</span><span class="sxs-lookup"><span data-stu-id="d980f-179">The [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) attribute specifies which columns (by column index) in the dataset should be loaded.</span></span> <span data-ttu-id="d980f-180">`userId` 和 `movieId` 列是你的 `Features`（你将向模型提供预测 `Label` 的输入），而评分列是你将预测的 `Label` 模型的输出）。</span><span class="sxs-lookup"><span data-stu-id="d980f-180">The `userId` and `movieId` columns are your `Features` (the inputs you will give the model to predict the `Label`), and the rating column is the `Label` that you will predict (the output of the model).</span></span>

<span data-ttu-id="d980f-181">创建另一个类 `MovieRatingPrediction`，通过在 MovieRatingData.cs 中的 `MovieRating` 类之后添加以下代码来表示预测结果：</span><span class="sxs-lookup"><span data-stu-id="d980f-181">Create another class, `MovieRatingPrediction`, to represent predicted results by adding the following code after the `MovieRating` class in *MovieRatingData.cs*:</span></span>

[!code-csharp[PredictionClass](../../../samples/machine-learning/tutorials/MovieRecommendation/MovieRatingData.cs#PredictionClass "Add the Movie Prediction Class")]

<span data-ttu-id="d980f-182">在 Program.cs 中，将 `Console.WriteLine("Hello World!")` 替换为 `Main()` 中的以下代码：</span><span class="sxs-lookup"><span data-stu-id="d980f-182">In *Program.cs*, replace the `Console.WriteLine("Hello World!")` with the following code inside `Main()`:</span></span>

[!code-csharp[MLContext](../../../samples/machine-learning/tutorials/MovieRecommendation/Program.cs#MLContext "Add MLContext")]

<span data-ttu-id="d980f-183">执行所有 ML.NET 操作都是从 [MLContext 类](xref:Microsoft.ML.MLContext)开始，初始化 `mlContext` 可创建一个新的 ML.NET 环境，可在模型创建工作流对象之间共享该环境。</span><span class="sxs-lookup"><span data-stu-id="d980f-183">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="d980f-184">从概念上讲，它与实体框架中的 `DBContext` 类似。</span><span class="sxs-lookup"><span data-stu-id="d980f-184">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

<span data-ttu-id="d980f-185">在 `Main()` 之后，创建一个名为 `LoadData()` 的方法：</span><span class="sxs-lookup"><span data-stu-id="d980f-185">After `Main()`, create a method called `LoadData()`:</span></span>
```csharp
public static (IDataView training, IDataView test) LoadData(MLContext mlContext)
{


}
```

> [!NOTE]
> <span data-ttu-id="d980f-186">除非在以下步骤中添加返回语句，否则使用此方法将出错。</span><span class="sxs-lookup"><span data-stu-id="d980f-186">This method will give you an error until you add a return statement in the following steps.</span></span>

<span data-ttu-id="d980f-187">初始化数据路径变量、从 \*.csv 文件加载数据以及将 `Train` 和 `Test` 数据作为 `IDataView` 对象返回，方法是在 `LoadData()` 中添加以下代码作为下一代码行：</span><span class="sxs-lookup"><span data-stu-id="d980f-187">Initialize your data path variables, load the data from the \*.csv files, and return the `Train` and `Test` data as `IDataView` objects by adding the following as the next line of code in `LoadData()`:</span></span>

[!code-csharp[LoadData](../../../samples/machine-learning/tutorials/MovieRecommendation/Program.cs#LoadData "Load data from data paths")]

<span data-ttu-id="d980f-188">ML.NET 中的数据表示为 [IDataView 类](xref:Microsoft.Data.DataView.IDataView)。</span><span class="sxs-lookup"><span data-stu-id="d980f-188">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.Data.DataView.IDataView).</span></span> <span data-ttu-id="d980f-189">`IDataView` 是用于描述表格数据（数字和文本）的一种灵活且有效的方法。</span><span class="sxs-lookup"><span data-stu-id="d980f-189">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="d980f-190">可从文本文件或实时（例如，SQL 数据库或日志文件）将数据加载到 `IDataView` 对象。</span><span class="sxs-lookup"><span data-stu-id="d980f-190">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span>

<span data-ttu-id="d980f-191">[LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) 用于定义数据架构并读取文件。</span><span class="sxs-lookup"><span data-stu-id="d980f-191">The [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) defines the data schema and reads in the file.</span></span> <span data-ttu-id="d980f-192">它使用数据路径变量并返回 `IDataView`。</span><span class="sxs-lookup"><span data-stu-id="d980f-192">It takes in the data path variables and returns an `IDataView`.</span></span> <span data-ttu-id="d980f-193">在这种情况下，需提供 `Test` 和 `Train` 文件的路径，并指示文本文件头（以便正确使用列名称）和逗号字符数据分隔符（默认分隔符是制表符）。</span><span class="sxs-lookup"><span data-stu-id="d980f-193">In this case, you provide the path for your `Test` and `Train` files and indicate both the text file header (so it can use the column names properly) and the comma character data separator (the default separator is a tab).</span></span>

<span data-ttu-id="d980f-194">在 `Main()` 方法中添加以下两个代码行，以调用 `LoadData()` 方法并返回 `Train` 和 `Test` 数据：</span><span class="sxs-lookup"><span data-stu-id="d980f-194">Add the following as the next two lines of code in the `Main()` method to call your `LoadData()` method and return the `Train` and `Test` data:</span></span>

[!code-csharp[LoadDataMain](../../../samples/machine-learning/tutorials/MovieRecommendation/Program.cs#LoadDataMain "Add LoadData method to Main")]


## <a name="build-and-train-your-model"></a><span data-ttu-id="d980f-195">生成并训练模型</span><span class="sxs-lookup"><span data-stu-id="d980f-195">Build and train your model</span></span>

<span data-ttu-id="d980f-196">ML.NET 中包含三个主要概念：[数据](../basic-concepts-model-training-in-mldotnet.md#data)、[转换器](../basic-concepts-model-training-in-mldotnet.md#transformer)和[估算器](../basic-concepts-model-training-in-mldotnet.md#estimator)。</span><span class="sxs-lookup"><span data-stu-id="d980f-196">There are three major concepts in ML.NET: [Data](../basic-concepts-model-training-in-mldotnet.md#data), [Transformers](../basic-concepts-model-training-in-mldotnet.md#transformer), and [Estimators](../basic-concepts-model-training-in-mldotnet.md#estimator).</span></span>

<span data-ttu-id="d980f-197">机器学习训练算法需要特定格式的数据。</span><span class="sxs-lookup"><span data-stu-id="d980f-197">Machine learning training algorithms require data in a certain format.</span></span> <span data-ttu-id="d980f-198">`Transformers` 用于将表格数据转换为兼容格式。</span><span class="sxs-lookup"><span data-stu-id="d980f-198">`Transformers` are used to transform tabular data to a compatible format.</span></span>

![转换器图像](./media/movie-recommendation/transformer.png)

<span data-ttu-id="d980f-200">可以通过创建 `Estimators` 在 ML.NET 中创建 `Transformers`。</span><span class="sxs-lookup"><span data-stu-id="d980f-200">You create `Transformers` in ML.NET by creating `Estimators`.</span></span> <span data-ttu-id="d980f-201">`Estimators` 接收数据并返回 `Transformers`。</span><span class="sxs-lookup"><span data-stu-id="d980f-201">`Estimators` take in data and return `Transformers`.</span></span>

![估算器图像](./media/movie-recommendation/estimator.png)

<span data-ttu-id="d980f-203">将用于训练模型的推荐训练算法就是一个 `Estimator` 示例。</span><span class="sxs-lookup"><span data-stu-id="d980f-203">The recommendation training algorithm you will use for training your model is an example of an `Estimator`.</span></span>

<span data-ttu-id="d980f-204">使用以下步骤生成 `Estimator`：</span><span class="sxs-lookup"><span data-stu-id="d980f-204">Build an `Estimator` with the following steps:</span></span>

<span data-ttu-id="d980f-205">使用下面的代码紧随 `LoadData()` 方法后创建 `BuildAndTrainModel()` 方法：</span><span class="sxs-lookup"><span data-stu-id="d980f-205">Create the `BuildAndTrainModel()` method, just after the `LoadData()` method, using the following code:</span></span>
```csharp
public static ITransformer BuildAndTrainModel(MLContext mlContext, IDataView trainingDataView)
{


}
```
> [!NOTE]
> <span data-ttu-id="d980f-206">除非在以下步骤中添加返回语句，否则使用此方法将出错。</span><span class="sxs-lookup"><span data-stu-id="d980f-206">This method will give you an error until you add a return statement in the following steps.</span></span>

<span data-ttu-id="d980f-207">通过将以下代码添加到 `BuildAndTrainModel()` 来定义数据转换：</span><span class="sxs-lookup"><span data-stu-id="d980f-207">Define the data transformations by adding the following code to `BuildAndTrainModel()`:</span></span>
   
[!code-csharp[DataTransformations](../../../samples/machine-learning/tutorials/MovieRecommendation/Program.cs#DataTransformations "Define data transformations")]

<span data-ttu-id="d980f-208">由于 `userId` 和 `movieId` 代表用户和影片标题，而不是实际值，因此使用 [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) 方法将每个 `userId` 和每个 `movieId` 转换为数字键类型 `Feature` 列（推荐算法接受的格式）并将它们添加为新的数据集列：</span><span class="sxs-lookup"><span data-stu-id="d980f-208">Since `userId` and `movieId` represent users and movie titles, not real values, you use the [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) method to transform each `userId` and each `movieId` into a numeric key type `Feature` column (a format accepted by recommendation algorithms) and add them as new dataset columns:</span></span>

| <span data-ttu-id="d980f-209">userId</span><span class="sxs-lookup"><span data-stu-id="d980f-209">userId</span></span> | <span data-ttu-id="d980f-210">movieId</span><span class="sxs-lookup"><span data-stu-id="d980f-210">movieId</span></span> | <span data-ttu-id="d980f-211">Label</span><span class="sxs-lookup"><span data-stu-id="d980f-211">Label</span></span> | <span data-ttu-id="d980f-212">userIdEncoded</span><span class="sxs-lookup"><span data-stu-id="d980f-212">userIdEncoded</span></span> | <span data-ttu-id="d980f-213">movieIdEncoded</span><span class="sxs-lookup"><span data-stu-id="d980f-213">movieIdEncoded</span></span> |
| ------------- |:-------------:| -----:|-----:|-----:|
| <span data-ttu-id="d980f-214">1</span><span class="sxs-lookup"><span data-stu-id="d980f-214">1</span></span> | <span data-ttu-id="d980f-215">1</span><span class="sxs-lookup"><span data-stu-id="d980f-215">1</span></span> | <span data-ttu-id="d980f-216">4</span><span class="sxs-lookup"><span data-stu-id="d980f-216">4</span></span> | <span data-ttu-id="d980f-217">userKey1</span><span class="sxs-lookup"><span data-stu-id="d980f-217">userKey1</span></span> | <span data-ttu-id="d980f-218">movieKey1</span><span class="sxs-lookup"><span data-stu-id="d980f-218">movieKey1</span></span> |
| <span data-ttu-id="d980f-219">1</span><span class="sxs-lookup"><span data-stu-id="d980f-219">1</span></span> | <span data-ttu-id="d980f-220">3</span><span class="sxs-lookup"><span data-stu-id="d980f-220">3</span></span> | <span data-ttu-id="d980f-221">4</span><span class="sxs-lookup"><span data-stu-id="d980f-221">4</span></span> | <span data-ttu-id="d980f-222">userKey1</span><span class="sxs-lookup"><span data-stu-id="d980f-222">userKey1</span></span> | <span data-ttu-id="d980f-223">movieKey2</span><span class="sxs-lookup"><span data-stu-id="d980f-223">movieKey2</span></span> |
| <span data-ttu-id="d980f-224">1</span><span class="sxs-lookup"><span data-stu-id="d980f-224">1</span></span> | <span data-ttu-id="d980f-225">6</span><span class="sxs-lookup"><span data-stu-id="d980f-225">6</span></span> | <span data-ttu-id="d980f-226">4</span><span class="sxs-lookup"><span data-stu-id="d980f-226">4</span></span> | <span data-ttu-id="d980f-227">userKey1</span><span class="sxs-lookup"><span data-stu-id="d980f-227">userKey1</span></span> | <span data-ttu-id="d980f-228">movieKey3</span><span class="sxs-lookup"><span data-stu-id="d980f-228">movieKey3</span></span> |


<span data-ttu-id="d980f-229">选择机器学习算法并将其添加到数据转换定义中，方法是在 `BuildAndTrainModel()` 中添加以下代码作为下一代码行：</span><span class="sxs-lookup"><span data-stu-id="d980f-229">Choose the machine learning algorithm and append it to the data transformation definitions by adding the following as the next line of code in `BuildAndTrainModel()`:</span></span>

[!code-csharp[AddAlgorithm](../../../samples/machine-learning/tutorials/MovieRecommendation/Program.cs#AddAlgorithm "Add the training algorithm with options")]

<span data-ttu-id="d980f-230">[MatrixFactorizationTrainer](xref:Microsoft.ML.RecommendationCatalog.RecommendationTrainers.MatrixFactorization%28Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options%29) 就是推荐训练算法。</span><span class="sxs-lookup"><span data-stu-id="d980f-230">The [MatrixFactorizationTrainer](xref:Microsoft.ML.RecommendationCatalog.RecommendationTrainers.MatrixFactorization%28Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options%29) is your recommendation training algorithm.</span></span>  <span data-ttu-id="d980f-231">当你掌握用户过去如何评价产品的数据时，通常建议使用[矩阵分解](https://en.wikipedia.org/wiki/Matrix_factorization_(recommender_systems))方法，本教程中的数据集就是这种情况。</span><span class="sxs-lookup"><span data-stu-id="d980f-231">[Matrix Factorization](https://en.wikipedia.org/wiki/Matrix_factorization_(recommender_systems)) is a common approach to recommendation when you have data on how users have rated products in the past, which is the case for the datasets in this tutorial.</span></span> <span data-ttu-id="d980f-232">当你有不同的数据时，还可使用其他推荐算法（请参阅下面的[其他推荐算法](#other-recommendation-algorithms)部分以了解更多信息）。</span><span class="sxs-lookup"><span data-stu-id="d980f-232">There are other recommendation algorithms for when you have different data available (see the [Other recommendation algorithms](#other-recommendation-algorithms) section below to learn more).</span></span> 

<span data-ttu-id="d980f-233">在本例中，`Matrix Factorization` 算法使用了一种称为“协作筛选”的方法，该方法假设如果用户 1 在某个问题上与用户 2 有相同的观点，那么用户 1 更有可能与用户 2 在另一个问题上有相同的看法。</span><span class="sxs-lookup"><span data-stu-id="d980f-233">In this case, the `Matrix Factorization` algorithm uses a method called "collaborative filtering", which assumes that if User 1 has the same opinion as User 2 on a certain issue, then User 1 is more likely to feel the same way as User 2 about a different issue.</span></span>

<span data-ttu-id="d980f-234">例如，如果用户 1 和用户 2 对影片的评分相似，那么用户 2 更有可能欣赏用户 1 已观看并给出很高评分的影片：</span><span class="sxs-lookup"><span data-stu-id="d980f-234">For instance, if User 1 and User 2 rate movies similarly, then User 2 is more likely to enjoy a movie that User 1 has watched and rated highly:</span></span>

| | `Incredibles 2 (2018)` | `The Avengers (2012)` | `Guardians of the Galaxy (2014)` |
| -------------:|-------------:| -----:|-----:|
| <span data-ttu-id="d980f-235">用户 1</span><span class="sxs-lookup"><span data-stu-id="d980f-235">User 1</span></span> | <span data-ttu-id="d980f-236">观看和点赞过的影片</span><span class="sxs-lookup"><span data-stu-id="d980f-236">Watched and liked movie</span></span> | <span data-ttu-id="d980f-237">观看和点赞过的影片</span><span class="sxs-lookup"><span data-stu-id="d980f-237">Watched and liked movie</span></span> | <span data-ttu-id="d980f-238">观看和点赞过的影片</span><span class="sxs-lookup"><span data-stu-id="d980f-238">Watched and liked movie</span></span> |
| <span data-ttu-id="d980f-239">用户 2</span><span class="sxs-lookup"><span data-stu-id="d980f-239">User 2</span></span> | <span data-ttu-id="d980f-240">观看和点赞过的影片</span><span class="sxs-lookup"><span data-stu-id="d980f-240">Watched and liked movie</span></span> | <span data-ttu-id="d980f-241">观看和点赞过的影片</span><span class="sxs-lookup"><span data-stu-id="d980f-241">Watched and liked movie</span></span> | <span data-ttu-id="d980f-242">没有看过 - 推荐影片</span><span class="sxs-lookup"><span data-stu-id="d980f-242">Has not watched -- RECOMMEND movie</span></span> |

<span data-ttu-id="d980f-243">`Matrix Factorization` 训练程序有多个[选项](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options)，可在下面的[算法超参数](#algorithm-hyperparameters)部分中详细了解。</span><span class="sxs-lookup"><span data-stu-id="d980f-243">The `Matrix Factorization` trainer has several [Options](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options), which you can read more about in the [Algorithm hyperparameters](#algorithm-hyperparameters) section below.</span></span>

<span data-ttu-id="d980f-244">在 `BuildAndTrainModel()` 方法中添加以下代码作为下一代码行，使模型适应 `Train` 数据，并返回经过训练的模型：</span><span class="sxs-lookup"><span data-stu-id="d980f-244">Fit the model to the `Train` data and return the trained model by adding the following as the next line of code in the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[FitModel](../../../samples/machine-learning/tutorials/MovieRecommendation/Program.cs#FitModel "Call the Fit method and return back the trained model")]

<span data-ttu-id="d980f-245">[Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.Data.DataView.IDataView,Microsoft.Data.DataView.IDataView%29) 方法使用提供的训练数据集训练模型。</span><span class="sxs-lookup"><span data-stu-id="d980f-245">The [Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.Data.DataView.IDataView,Microsoft.Data.DataView.IDataView%29) method trains your model with the provided training dataset.</span></span> <span data-ttu-id="d980f-246">从技术上讲，该方法通过转换数据并应用训练来执行 `Estimator` 定义，然后返回经过训练的模型，即 `Transformer`。</span><span class="sxs-lookup"><span data-stu-id="d980f-246">Technically, it executes the `Estimator` definitions by transforming the data and applying the training, and it returns back the trained model, which is a `Transformer`.</span></span>

<span data-ttu-id="d980f-247">将以下内容添加为 `Main()` 方法中的下一代码行，以调用 `BuildAndTrainModel()` 方法并返回经过训练的模型：</span><span class="sxs-lookup"><span data-stu-id="d980f-247">Add the following as the next line of code in the `Main()` method to call your `BuildAndTrainModel()` method and return the trained model:</span></span>

[!code-csharp[BuildTrainModelMain](../../../samples/machine-learning/tutorials/MovieRecommendation/Program.cs#BuildTrainModelMain "Add BuildAndTrainModel method in Main")]

## <a name="evaluate-your-model"></a><span data-ttu-id="d980f-248">评估模型</span><span class="sxs-lookup"><span data-stu-id="d980f-248">Evaluate your model</span></span>

<span data-ttu-id="d980f-249">训练模型后，使用测试数据评估模型的执行情况。</span><span class="sxs-lookup"><span data-stu-id="d980f-249">Once you have trained your model, use your test data to evaluate how your model is performing.</span></span> 

<span data-ttu-id="d980f-250">使用下面的代码紧随 `BuildAndTrainModel()` 方法后创建 `EvaluateModel()` 方法：</span><span class="sxs-lookup"><span data-stu-id="d980f-250">Create the `EvaluateModel()` method, just after the `BuildAndTrainModel()` method, using the following code:</span></span>
```csharp
public static void EvaluateModel(MLContext mlContext, IDataView testDataView, ITransformer model)
{


}
```

<span data-ttu-id="d980f-251">将以下代码添加到 `EvaluateModel()`，转换 `Test` 数据：[!code-csharp[Transform](../../../samples/machine-learning/tutorials/MovieRecommendation/Program.cs#Transform "Transform the test data")]</span><span class="sxs-lookup"><span data-stu-id="d980f-251">Transform the `Test` data by adding the following code to `EvaluateModel()`: [!code-csharp[Transform](../../../samples/machine-learning/tutorials/MovieRecommendation/Program.cs#Transform "Transform the test data")]</span></span>

<span data-ttu-id="d980f-252">[Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) 方法对测试数据集的多个提供的输入行进行预测。</span><span class="sxs-lookup"><span data-stu-id="d980f-252">The [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method makes predictions for multiple provided input rows of a test dataset.</span></span>

<span data-ttu-id="d980f-253">通过在 `EvaluateModel()` 方法中添加以下代码作为下一代码行来评估模型：</span><span class="sxs-lookup"><span data-stu-id="d980f-253">Evaluate the model by adding the following as the next line of code in the `EvaluateModel()` method:</span></span>

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/MovieRecommendation/Program.cs#Evaluate "Evaluate the model using predictions from the test data")]

<span data-ttu-id="d980f-254">获得预测集后，[Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) 方法会对模型进行评估，该模型会将预测值与测试数据集中的实际 `Labels` 进行比较，并返回有关模型执行情况的指标。</span><span class="sxs-lookup"><span data-stu-id="d980f-254">Once you have the prediction set, the [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) method assesses the model, which compares the predicted values with the actual `Labels` in the test dataset and returns metrics on how the model is performing.</span></span>

<span data-ttu-id="d980f-255">在 `EvaluateModel()` 方法中添加以下代码作为下一代码行，将评估指标输出到控制台：</span><span class="sxs-lookup"><span data-stu-id="d980f-255">Print your evaluation metrics to the console by adding the following as the next line of code in the `EvaluateModel()` method:</span></span>

[!code-csharp[PrintMetrics](../../../samples/machine-learning/tutorials/MovieRecommendation/Program.cs#PrintMetrics "Print the evaluation metrics")]

<span data-ttu-id="d980f-256">在 `Main()` 方法中添加以下代码作为下一代码行，调用 `EvaluateModel()` 方法：</span><span class="sxs-lookup"><span data-stu-id="d980f-256">Add the following as the next line of code in the `Main()` method to call your `EvaluateModel()` method:</span></span>

[!code-csharp[EvaluateModelMain](../../../samples/machine-learning/tutorials/MovieRecommendation/Program.cs#EvaluateModelMain "Add EvaluateModel method in Main")]

<span data-ttu-id="d980f-257">到目前为止的输出应类似于以下文本：</span><span class="sxs-lookup"><span data-stu-id="d980f-257">The output so far should look similar to the following text:</span></span>

```console
=============== Training the model ===============
iter      tr_rmse          obj
   0       1.5403   3.1262e+05
   1       0.9221   1.6030e+05
   2       0.8687   1.5046e+05
   3       0.8416   1.4584e+05
   4       0.8142   1.4209e+05
   5       0.7849   1.3907e+05
   6       0.7544   1.3594e+05
   7       0.7266   1.3361e+05
   8       0.6987   1.3110e+05
   9       0.6751   1.2948e+05
  10       0.6530   1.2766e+05
  11       0.6350   1.2644e+05
  12       0.6197   1.2541e+05
  13       0.6067   1.2470e+05
  14       0.5953   1.2382e+05
  15       0.5871   1.2342e+05
  16       0.5781   1.2279e+05
  17       0.5713   1.2240e+05
  18       0.5660   1.2230e+05
  19       0.5592   1.2179e+05
=============== Evaluating the model ===============
Rms: 0.994051469730769
RSquared: 0.412556298844873
```

<span data-ttu-id="d980f-258">在此输出中，有 20 次迭代。</span><span class="sxs-lookup"><span data-stu-id="d980f-258">In this output, there are 20 iterations.</span></span> <span data-ttu-id="d980f-259">在每次迭代中，误差测量值均会减小并逐渐趋于最小值 0。</span><span class="sxs-lookup"><span data-stu-id="d980f-259">In each iteration, the measure of error decreases and converges closer and closer to 0.</span></span>

<span data-ttu-id="d980f-260">`root of mean squared error`（RMS 或 RMSE）经常用于测量模型预测的值与测试数据集中观察到的值之间的差异。</span><span class="sxs-lookup"><span data-stu-id="d980f-260">The `root of mean squared error` (RMS or RMSE) is frequently used to measure the differences between values predicted by a model and the values observed in a test dataset.</span></span> <span data-ttu-id="d980f-261">从技术上讲，它是误差的平方的平均值的平方根。</span><span class="sxs-lookup"><span data-stu-id="d980f-261">Technically it's the square root of the average of the squares of the errors.</span></span> <span data-ttu-id="d980f-262">通常会希望你的 RMSE 分数尽可能接近 1。</span><span class="sxs-lookup"><span data-stu-id="d980f-262">You want your RMSE score to be as close to 1 as possible.</span></span>

<span data-ttu-id="d980f-263">`R Squared` 是模型解释的预测值中的变化百分比。</span><span class="sxs-lookup"><span data-stu-id="d980f-263">`R Squared` is the variation percentage in the predicted values explained by your model.</span></span> <span data-ttu-id="d980f-264">它是 0 到 1 之间的值，值越接近 0，模型越好。</span><span class="sxs-lookup"><span data-stu-id="d980f-264">It's a value between 0 and 1, and the closer the value is to 0, the better the model is.</span></span>

## <a name="use-your-model"></a><span data-ttu-id="d980f-265">使用模型</span><span class="sxs-lookup"><span data-stu-id="d980f-265">Use your model</span></span>

<span data-ttu-id="d980f-266">现在，你可以使用经过训练的模型对新数据进行预测。</span><span class="sxs-lookup"><span data-stu-id="d980f-266">Now you can use your trained model to make predictions on new data.</span></span>

<span data-ttu-id="d980f-267">使用下面的代码紧随 `EvaluateModel()` 方法后创建 `UseModelForSinglePrediction()` 方法：</span><span class="sxs-lookup"><span data-stu-id="d980f-267">Create the `UseModelForSinglePrediction()` method, just after the `EvaluateModel()` method, using the following code:</span></span>
```csharp
public static void UseModelForSinglePrediction(MLContext mlContext, ITransformer model)
{


}
```

<span data-ttu-id="d980f-268">使用 `PredictionEngine` 通过将以下代码添加到 `UseModelForSinglePrediction()` 来预测评分：</span><span class="sxs-lookup"><span data-stu-id="d980f-268">Use the `PredictionEngine` to predict the rating by adding the following code to `UseModelForSinglePrediction()`:</span></span>

[!code-csharp[PredictionEngine](../../../samples/machine-learning/tutorials/MovieRecommendation/Program.cs#PredictionEngine "Create Prediction Engine")]

<span data-ttu-id="d980f-269">[PredictionEngine 类](xref:Microsoft.ML.PredictionEngine%602)是一个便利 API，可用于传递单个数据实例，然后对此单个数据实例执行预测。</span><span class="sxs-lookup"><span data-stu-id="d980f-269">The [PredictionEngine class](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to pass a single instance of data and then perform a prediction on this single instance of data.</span></span>

<span data-ttu-id="d980f-270">创建一个名为 `testInput` 的 `MovieRating` 实例，并通过在 `UseModelForSinglePrediction()` 方法中添加以下代码作为下一代码行，将其传递给预测引擎：</span><span class="sxs-lookup"><span data-stu-id="d980f-270">Create an instance of `MovieRating` called `testInput` and pass it to the Prediction Engine by adding the following as the next lines of code in the `UseModelForSinglePrediction()` method:</span></span>

[!code-csharp[MakeSinglePrediction](../../../samples/machine-learning/tutorials/MovieRecommendation/Program.cs#MakeSinglePrediction "Make a single prediction with the Prediction Engine")]

<span data-ttu-id="d980f-271">[Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) 函数对单列数据进行预测。</span><span class="sxs-lookup"><span data-stu-id="d980f-271">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single column of data.</span></span>

<span data-ttu-id="d980f-272">然后，你可以使用 `Score` 或预测评分来确定是否要将 movieId 10 的影片推荐给用户 6。</span><span class="sxs-lookup"><span data-stu-id="d980f-272">You can then use the `Score`, or the predicted rating, to determine whether you want to recommend the movie with movieId 10 to user 6.</span></span> <span data-ttu-id="d980f-273">`Score` 越高，用户喜欢特定电影的可能性就越大。</span><span class="sxs-lookup"><span data-stu-id="d980f-273">The higher the `Score`, the higher the likelihood of a user liking a particular movie.</span></span> <span data-ttu-id="d980f-274">在这种情况下，假设你推荐预测评分大于 3.5 的电影。</span><span class="sxs-lookup"><span data-stu-id="d980f-274">In this case, let’s say that you recommend movies with a predicted rating of > 3.5.</span></span>

<span data-ttu-id="d980f-275">若要输出结果，请在 `UseModelForSinglePrediction()` 方法中添加以下代码作为下一代码行：</span><span class="sxs-lookup"><span data-stu-id="d980f-275">To print the results, add the following as the next lines of code in the `UseModelForSinglePrediction()` method:</span></span>

[!code-csharp[PrintResults](../../../samples/machine-learning/tutorials/MovieRecommendation/Program.cs#PrintResults "Print the recommendation prediction results")]

<span data-ttu-id="d980f-276">在 `Main()` 方法中添加以下代码作为下一代码行，调用 `UseModelForSinglePrediction()` 方法：</span><span class="sxs-lookup"><span data-stu-id="d980f-276">Add the following as the next line of code in the `Main()` method to call your `UseModelForSinglePrediction()` method:</span></span>

[!code-csharp[UseModelMain](../../../samples/machine-learning/tutorials/MovieRecommendation/Program.cs#UseModelMain "Add UseModelForSinglePrediction method in Main")]

<span data-ttu-id="d980f-277">此方法的输出应类似于以下文本：</span><span class="sxs-lookup"><span data-stu-id="d980f-277">The output of this method should look similar to the following text:</span></span>

```console
=============== Making a prediction ===============
Movie 10 is recommended for user 6
```

### <a name="save-your-model"></a><span data-ttu-id="d980f-278">保存模型</span><span class="sxs-lookup"><span data-stu-id="d980f-278">Save your model</span></span>
<span data-ttu-id="d980f-279">若要使用模型在最终用户应用程序中进行预测，必须先保存模型。</span><span class="sxs-lookup"><span data-stu-id="d980f-279">To use your model to make predictions in end-user applications, you must first save the model.</span></span>

<span data-ttu-id="d980f-280">使用下面的代码紧随 `UseModelForSinglePrediction()` 方法后创建 `SaveModel()` 方法：</span><span class="sxs-lookup"><span data-stu-id="d980f-280">Create the `SaveModel()` method, just after the `UseModelForSinglePrediction()` method, using the following code:</span></span>
```csharp
public static void SaveModel(MLContext mlContext, ITransformer model)
{


}
```

<span data-ttu-id="d980f-281">通过在 `SaveModel()` 方法中添加以下代码来保存经过训练的模型：</span><span class="sxs-lookup"><span data-stu-id="d980f-281">Save your trained model by adding the following code in the `SaveModel()` method:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/MovieRecommendation/Program.cs#SaveModel "Save the model to a zip file")]

<span data-ttu-id="d980f-282">此方法会将经过训练的模型保存到 .zip 文件（在“数据”文件夹中），然后可以在其他 .NET 应用程序中使用该文件进行预测。</span><span class="sxs-lookup"><span data-stu-id="d980f-282">This method saves your trained model to a .zip file (in the "Data" folder), which can then be used in other .NET applications to make predictions.</span></span>

<span data-ttu-id="d980f-283">在 `Main()` 方法中添加以下代码作为下一代码行，调用 `SaveModel()` 方法：</span><span class="sxs-lookup"><span data-stu-id="d980f-283">Add the following as the next line of code in the `Main()` method to call your `SaveModel()` method:</span></span>

[!code-csharp[SaveModelMain](../../../samples/machine-learning/tutorials/MovieRecommendation/Program.cs#SaveModelMain "Create SaveModel method in Main")]

### <a name="use-your-saved-model"></a><span data-ttu-id="d980f-284">使用保存的模型</span><span class="sxs-lookup"><span data-stu-id="d980f-284">Use your saved model</span></span>
<span data-ttu-id="d980f-285">保存经过训练的模型后，可以在不同环境中使用模型（请参阅[“操作指南”](../how-to-guides/consuming-model-ml-net.md)，了解如何在应用程序中操作经过训练的机器学习模型）。</span><span class="sxs-lookup"><span data-stu-id="d980f-285">Once you have saved your trained model, you can consume the model in different environments (see the ["How-to guide"](../how-to-guides/consuming-model-ml-net.md) to learn how to operationalize a trained machine learning model in apps).</span></span>

## <a name="results"></a><span data-ttu-id="d980f-286">结果</span><span class="sxs-lookup"><span data-stu-id="d980f-286">Results</span></span>

<span data-ttu-id="d980f-287">按照上述步骤操作后，运行控制台应用程序 (Ctrl + F5)。</span><span class="sxs-lookup"><span data-stu-id="d980f-287">After following the steps above, run your console app (Ctrl + F5).</span></span> <span data-ttu-id="d980f-288">上述单一预测的结果应与以下内容类似。</span><span class="sxs-lookup"><span data-stu-id="d980f-288">Your results from the single prediction above should be similar to the following.</span></span> <span data-ttu-id="d980f-289">你可能会看到警告或处理消息，为清楚起见，这些消息已从以下结果中删除。</span><span class="sxs-lookup"><span data-stu-id="d980f-289">You may see warnings or processing messages, but these messages have been removed from the following results for clarity.</span></span>

```console
=============== Training the model ===============
iter      tr_rmse          obj
   0       1.5382   3.1213e+05
   1       0.9223   1.6051e+05
   2       0.8691   1.5050e+05
   3       0.8413   1.4576e+05
   4       0.8145   1.4208e+05
   5       0.7848   1.3895e+05
   6       0.7552   1.3613e+05
   7       0.7259   1.3357e+05
   8       0.6987   1.3121e+05
   9       0.6747   1.2949e+05
  10       0.6533   1.2766e+05
  11       0.6353   1.2636e+05
  12       0.6209   1.2561e+05
  13       0.6072   1.2462e+05
  14       0.5965   1.2394e+05
  15       0.5868   1.2352e+05
  16       0.5782   1.2279e+05
  17       0.5713   1.2227e+05
  18       0.5637   1.2190e+05
  19       0.5604   1.2178e+05
=============== Evaluating the model ===============
Rms: 0.977175077487166
RSquared: 0.43233349213192
=============== Making a prediction ===============
Movie 10 is recommended for user 6
=============== Saving the model to a file ===============
```

<span data-ttu-id="d980f-290">祝贺你！</span><span class="sxs-lookup"><span data-stu-id="d980f-290">Congratulations!</span></span> <span data-ttu-id="d980f-291">现已成功构建了用于推荐影片的机器学习模型。</span><span class="sxs-lookup"><span data-stu-id="d980f-291">You've now successfully built a machine learning model for recommending movies.</span></span> <span data-ttu-id="d980f-292">可以在 [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/MovieRecommendation) 存储库中找到本教程的源代码。</span><span class="sxs-lookup"><span data-stu-id="d980f-292">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/MovieRecommendation) repository.</span></span>

## <a name="improve-your-model"></a><span data-ttu-id="d980f-293">提升模型</span><span class="sxs-lookup"><span data-stu-id="d980f-293">Improve your model</span></span>

<span data-ttu-id="d980f-294">有几种方法可以提升模型的性能，以便可以获得更准确的预测。</span><span class="sxs-lookup"><span data-stu-id="d980f-294">There are several ways that you can improve the performance of your model so that you can get more accurate predictions.</span></span>

### <a name="data"></a><span data-ttu-id="d980f-295">数据</span><span class="sxs-lookup"><span data-stu-id="d980f-295">Data</span></span> 

<span data-ttu-id="d980f-296">可添加更多训练数据，并在其中包括针对每个用户和影片 ID 的足够样本，以帮助提升推荐模型的质量。</span><span class="sxs-lookup"><span data-stu-id="d980f-296">Adding more training data that has enough samples for each user and movie id can help improve the quality of the recommendation model.</span></span>

<span data-ttu-id="d980f-297">[交叉验证](../how-to-guides/train-cross-validation-ml-net.md)是一种评估模型的方法，它将数据随机分成子集（而不是像你在本教程中那样从数据集中提取测试数据），并将一些组作为训练数据，一些组作为测试数据。</span><span class="sxs-lookup"><span data-stu-id="d980f-297">[Cross validation](../how-to-guides/train-cross-validation-ml-net.md) is a technique for evaluating models that randomly splits up data into subsets (instead of extracting out test data from the dataset like you did in this tutorial) and takes some of the groups as train data and some of the groups as test data.</span></span> <span data-ttu-id="d980f-298">从模型质量方面看，该方法优于进行训练-测试拆分。</span><span class="sxs-lookup"><span data-stu-id="d980f-298">This method outperforms making a train-test split in terms of model quality.</span></span>

### <a name="features"></a><span data-ttu-id="d980f-299">功能</span><span class="sxs-lookup"><span data-stu-id="d980f-299">Features</span></span>

<span data-ttu-id="d980f-300">在本教程中，只使用数据集提供的三个 `Features`（`user id``movie id` 和 `rating`）。</span><span class="sxs-lookup"><span data-stu-id="d980f-300">In this tutorial, you only use the three `Features` (`user id`, `movie id`, and `rating`) that are provided by the dataset.</span></span> 

<span data-ttu-id="d980f-301">虽然这是一个良好的开端，但实际上你可能希望添加其他属性或 `Features`（例如，年龄、性别、地理位置等），如果它们包含在数据集中。</span><span class="sxs-lookup"><span data-stu-id="d980f-301">While this is a good start, in reality you might want to add other attributes or `Features` (for example, age, gender, geo-location, etc.) if they are included in the dataset.</span></span> <span data-ttu-id="d980f-302">添加更相关的 `Features` 有助于提升推荐模型的性能。</span><span class="sxs-lookup"><span data-stu-id="d980f-302">Adding more relevant `Features` can help improve the performance of your recommendation model.</span></span> 

<span data-ttu-id="d980f-303">如果你不确定哪个 `Features` 可能与机器学习任务最相关，还可以使用 ML.NET 提供的特征贡献计算 (FCC) 和[特征排列重要性](../how-to-guides/determine-global-feature-importance-in-model.md)来发现最有影响力的 `Features`。</span><span class="sxs-lookup"><span data-stu-id="d980f-303">If you are unsure about which `Features` might be the most relevant for your machine learning task, you can also make use of Feature Contribution Calculation (FCC) and [Feature Permutation Importance](../how-to-guides/determine-global-feature-importance-in-model.md), which ML.NET provides to discover the most influential `Features`.</span></span>

### <a name="algorithm-hyperparameters"></a><span data-ttu-id="d980f-304">算法超参数</span><span class="sxs-lookup"><span data-stu-id="d980f-304">Algorithm hyperparameters</span></span>

<span data-ttu-id="d980f-305">虽然 ML.NET 提供了良好的默认训练算法，但可以通过更改算法的[超参数](../resources/glossary.md#hyperparameter)来进一步微调性能。</span><span class="sxs-lookup"><span data-stu-id="d980f-305">While ML.NET provides good default training algorithms, you can further fine-tune performance by changing the algorithm's [hyperparameters](../resources/glossary.md#hyperparameter).</span></span>

<span data-ttu-id="d980f-306">对于 `Matrix Factorization`，可尝试使用超参数，例如 [NumberOfIterations](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options.NumberOfIterations) 和 [ApproximationRank](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options.ApproximationRank) 来查看是否可以获得更好的结果。</span><span class="sxs-lookup"><span data-stu-id="d980f-306">For `Matrix Factorization`, you can experiment with hyperparameters such as [NumberOfIterations](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options.NumberOfIterations) and [ApproximationRank](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Options.ApproximationRank) to see if that gives you better results.</span></span>

<span data-ttu-id="d980f-307">例如，在本教程中，算法选项是：</span><span class="sxs-lookup"><span data-stu-id="d980f-307">For instance, in this tutorial the algorithm options are:</span></span>

```csharp
var options = new MatrixFactorizationTrainer.Options
{
    MatrixColumnIndexColumnName = "userIdEncoded",
    MatrixRowIndexColumnName = "movieIdEncoded", 
    LabelColumnName = "Label",
    NumberOfIterations = 20,
    ApproximationRank = 100
};
```

### <a name="other-recommendation-algorithms"></a><span data-ttu-id="d980f-308">其他推荐算法</span><span class="sxs-lookup"><span data-stu-id="d980f-308">Other Recommendation Algorithms</span></span>
<span data-ttu-id="d980f-309">具有协作筛选的矩阵分解算法只是用于执行影片推荐的一种方法。</span><span class="sxs-lookup"><span data-stu-id="d980f-309">The matrix factorization algorithm with collaborative filtering is only one approach for performing movie recommendations.</span></span> <span data-ttu-id="d980f-310">在许多情况下，可能没有可用的评分数据，并且只有用户可以获得影片历史记录。</span><span class="sxs-lookup"><span data-stu-id="d980f-310">In many cases, you may not have the ratings data available and only have movie history available from users.</span></span> <span data-ttu-id="d980f-311">在其他情况下，你可能不仅仅拥有用户的评分数据。</span><span class="sxs-lookup"><span data-stu-id="d980f-311">In other cases, you may have more than just the user’s rating data.</span></span>

| <span data-ttu-id="d980f-312">算法</span><span class="sxs-lookup"><span data-stu-id="d980f-312">Algorithm</span></span>       | <span data-ttu-id="d980f-313">方案</span><span class="sxs-lookup"><span data-stu-id="d980f-313">Scenario</span></span>           | <span data-ttu-id="d980f-314">示例</span><span class="sxs-lookup"><span data-stu-id="d980f-314">Sample</span></span>  |
| ------------- |:-------------:| -----:|
| <span data-ttu-id="d980f-315">一类矩阵分解</span><span class="sxs-lookup"><span data-stu-id="d980f-315">One Class Matrix Factorization</span></span> | <span data-ttu-id="d980f-316">当只有 userId 和 movieId 时使用此选项。</span><span class="sxs-lookup"><span data-stu-id="d980f-316">Use this when you only have userId and movieId.</span></span> <span data-ttu-id="d980f-317">这种推荐方式基于共同购买方案或经常一起购买的产品，这意味着它将根据自己的采购订单历史记录向客户推荐一组产品。</span><span class="sxs-lookup"><span data-stu-id="d980f-317">This style of recommendation is based upon the co-purchase scenario, or products frequently bought together, which means it will recommend to customers a set of products based upon their own purchase order history.</span></span> | [<span data-ttu-id="d980f-318">>试试吧</span><span class="sxs-lookup"><span data-stu-id="d980f-318">>Try it out</span></span>](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/MatrixFactorization_ProductRecommendation) |
| <span data-ttu-id="d980f-319">场感知分解机</span><span class="sxs-lookup"><span data-stu-id="d980f-319">Field Aware Factorization Machines</span></span> | <span data-ttu-id="d980f-320">当拥有的特征不止 userId、productId 和评分（例如产品描述或产品价格）时，可使用此选项进行建议。</span><span class="sxs-lookup"><span data-stu-id="d980f-320">Use this to make recommendations when you have more Features beyond userId, productId, and rating (such as product description or product price).</span></span> <span data-ttu-id="d980f-321">此方法也使用协作筛选法。</span><span class="sxs-lookup"><span data-stu-id="d980f-321">This method also uses a collaborative filtering approach.</span></span> | [<span data-ttu-id="d980f-322">>试试吧</span><span class="sxs-lookup"><span data-stu-id="d980f-322">>Try it out</span></span>](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/end-to-end-apps/Recommendation-MovieRecommender) |

### <a name="new-user-scenario"></a><span data-ttu-id="d980f-323">新用户方案</span><span class="sxs-lookup"><span data-stu-id="d980f-323">New user scenario</span></span>
<span data-ttu-id="d980f-324">协作筛选中的一个常见问题是“冷开始问题”，即有一个新用户，没有用于进行推理的任何旧数据。</span><span class="sxs-lookup"><span data-stu-id="d980f-324">One common problem in collaborative filtering is the cold start problem, which is when you have a new user with no previous data to draw inferences from.</span></span> <span data-ttu-id="d980f-325">该问题通常可通过要求新用户创建个人资料来解决，例如，对他们过去看过的影片评分。</span><span class="sxs-lookup"><span data-stu-id="d980f-325">This problem is often solved by asking new users to create a profile and, for instance, rate movies they have seen in the past.</span></span> <span data-ttu-id="d980f-326">虽然此方法会给用户带来一些负担，但它可为没有评分历史记录的新用户提供一些开始数据。</span><span class="sxs-lookup"><span data-stu-id="d980f-326">While this method puts some burden on the user, it provides some starting data for new users with no rating history.</span></span>

## <a name="resources"></a><span data-ttu-id="d980f-327">资源</span><span class="sxs-lookup"><span data-stu-id="d980f-327">Resources</span></span>
<span data-ttu-id="d980f-328">本教程中使用的数据源自 [MovieLens 数据集](http://files.grouplens.org/datasets/movielens/)。</span><span class="sxs-lookup"><span data-stu-id="d980f-328">The data used in this tutorial is derived from [MovieLens Dataset](http://files.grouplens.org/datasets/movielens/).</span></span>

## <a name="next-steps"></a><span data-ttu-id="d980f-329">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d980f-329">Next steps</span></span>
<span data-ttu-id="d980f-330">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="d980f-330">In this tutorial, you learned how to:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="d980f-331">选择机器学习算法</span><span class="sxs-lookup"><span data-stu-id="d980f-331">Select a machine learning algorithm</span></span>
> * <span data-ttu-id="d980f-332">准备并加载数据</span><span class="sxs-lookup"><span data-stu-id="d980f-332">Prepare and load your data</span></span>
> * <span data-ttu-id="d980f-333">生成并训练模型</span><span class="sxs-lookup"><span data-stu-id="d980f-333">Build and train a model</span></span>
> * <span data-ttu-id="d980f-334">评估模型</span><span class="sxs-lookup"><span data-stu-id="d980f-334">Evaluate a model</span></span>
> * <span data-ttu-id="d980f-335">部署和使用模型</span><span class="sxs-lookup"><span data-stu-id="d980f-335">Deploy and consume a model</span></span>

<span data-ttu-id="d980f-336">进入下一教程了解详细信息</span><span class="sxs-lookup"><span data-stu-id="d980f-336">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="d980f-337">情绪分析</span><span class="sxs-lookup"><span data-stu-id="d980f-337">Sentiment Analysis</span></span>](sentiment-analysis.md)

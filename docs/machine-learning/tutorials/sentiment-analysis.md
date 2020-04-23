---
title: 教程：分析网站评论 - 二元分类
description: 本教程演示如何创建 .NET Core 控制台应用程序，该应用程序对网站评论情绪进行分类并采取适当的措施。 二元情绪分类器在 Visual Studio 中使用 C#。
ms.date: 09/30/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: c6e13cfca93c54648b1a0423c5983013d3e2a1a0
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243292"
---
# <a name="tutorial-analyze-sentiment-of-website-comments-with-binary-classification-in-mlnet"></a><span data-ttu-id="bebb2-104">教程：在 ML.NET 中使用二元分类分析网站评论的情绪</span><span class="sxs-lookup"><span data-stu-id="bebb2-104">Tutorial: Analyze sentiment of website comments with binary classification in ML.NET</span></span>

<span data-ttu-id="bebb2-105">本教程演示如何创建 .NET Core 控制台应用程序，该应用程序对网站评论情绪进行分类并采取适当的措施。</span><span class="sxs-lookup"><span data-stu-id="bebb2-105">This tutorial shows you how to create a .NET Core console application that classifies sentiment from website comments and takes the appropriate action.</span></span> <span data-ttu-id="bebb2-106">二元情绪分类器在 Visual Studio 2017 中使用 C#。</span><span class="sxs-lookup"><span data-stu-id="bebb2-106">The binary sentiment classifier uses C# in Visual Studio 2017.</span></span>

<span data-ttu-id="bebb2-107">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="bebb2-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="bebb2-108">创建控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="bebb2-108">Create a console application</span></span>
> - <span data-ttu-id="bebb2-109">准备数据</span><span class="sxs-lookup"><span data-stu-id="bebb2-109">Prepare data</span></span>
> - <span data-ttu-id="bebb2-110">加载数据</span><span class="sxs-lookup"><span data-stu-id="bebb2-110">Load the data</span></span>
> - <span data-ttu-id="bebb2-111">生成和定型模型</span><span class="sxs-lookup"><span data-stu-id="bebb2-111">Build and train the model</span></span>
> - <span data-ttu-id="bebb2-112">评估模型</span><span class="sxs-lookup"><span data-stu-id="bebb2-112">Evaluate the model</span></span>
> - <span data-ttu-id="bebb2-113">使用模型进行预测</span><span class="sxs-lookup"><span data-stu-id="bebb2-113">Use the model to make a prediction</span></span>
> - <span data-ttu-id="bebb2-114">查看结果</span><span class="sxs-lookup"><span data-stu-id="bebb2-114">See the results</span></span>

<span data-ttu-id="bebb2-115">可以在 [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) 存储库中找到本教程的源代码。</span><span class="sxs-lookup"><span data-stu-id="bebb2-115">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bebb2-116">先决条件</span><span class="sxs-lookup"><span data-stu-id="bebb2-116">Prerequisites</span></span>

- <span data-ttu-id="bebb2-117">安装了“.NET Core 跨平台开发”工作负载的 [Visual Studio 2017 版本 15.6 或更高版本](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)</span><span class="sxs-lookup"><span data-stu-id="bebb2-117">[Visual Studio 2017 version 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the ".NET Core cross-platform development" workload installed</span></span>

- <span data-ttu-id="bebb2-118">[UCI Sentiment Labeled Sentences 数据集](http://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip)（zip 文件）</span><span class="sxs-lookup"><span data-stu-id="bebb2-118">[UCI Sentiment Labeled Sentences dataset](http://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) (ZIP file)</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="bebb2-119">创建控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="bebb2-119">Create a console application</span></span>

1. <span data-ttu-id="bebb2-120">创建名为“SentimentAnalysis”的 **.NET Core 控制台应用程序**。</span><span class="sxs-lookup"><span data-stu-id="bebb2-120">Create a **.NET Core Console Application** called "SentimentAnalysis".</span></span>

2. <span data-ttu-id="bebb2-121">在项目中创建名为“Data”的目录，用于保存数据集文件  。</span><span class="sxs-lookup"><span data-stu-id="bebb2-121">Create a directory named *Data* in your project to save your data set files.</span></span>

3. <span data-ttu-id="bebb2-122">安装“Microsoft.ML NuGet 包”  ：</span><span class="sxs-lookup"><span data-stu-id="bebb2-122">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="bebb2-123">在“解决方案资源管理器”中，右键单击项目，然后选择“管理 NuGet 包”  。</span><span class="sxs-lookup"><span data-stu-id="bebb2-123">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="bebb2-124">选择“nuget.org”作为包源，然后选择“浏览”选项卡  。搜索“Microsoft.ML”，选择所需的包，然后选择“安装”按钮   。</span><span class="sxs-lookup"><span data-stu-id="bebb2-124">Choose "nuget.org" as the package source, and then select the **Browse** tab. Search for **Microsoft.ML**, select the package you want, and then select the **Install** button.</span></span> <span data-ttu-id="bebb2-125">同意所选包的许可条款，继续执行安装。</span><span class="sxs-lookup"><span data-stu-id="bebb2-125">Proceed with the installation by agreeing to the license terms for the package you choose.</span></span> <span data-ttu-id="bebb2-126">对 **Microsoft.ML.FastTree** NuGet 包执行相同操作。</span><span class="sxs-lookup"><span data-stu-id="bebb2-126">Do the same for the **Microsoft.ML.FastTree** NuGet package.</span></span>

## <a name="prepare-your-data"></a><span data-ttu-id="bebb2-127">准备数据</span><span class="sxs-lookup"><span data-stu-id="bebb2-127">Prepare your data</span></span>

> [!NOTE]
> <span data-ttu-id="bebb2-128">本教程的数据集摘自 KDD 2015 中由 Kotzias 等</span><span class="sxs-lookup"><span data-stu-id="bebb2-128">The datasets for this tutorial are from the 'From Group to Individual Labels using Deep Features', Kotzias et.</span></span> <span data-ttu-id="bebb2-129">提出的“From Group to Individual Labels using Deep Features”，</span><span class="sxs-lookup"><span data-stu-id="bebb2-129">al,.</span></span> <span data-ttu-id="bebb2-130">并托管在 UCI 机器学习存储库中（Dua, D. 和 Karra Taniskidou, E.(2017)）。</span><span class="sxs-lookup"><span data-stu-id="bebb2-130">KDD 2015, and hosted at the UCI Machine Learning Repository - Dua, D. and Karra Taniskidou, E. (2017).</span></span> <span data-ttu-id="bebb2-131">UCI 机器学习存储库 [http://archive.ics.uci.edu/ml ]。</span><span class="sxs-lookup"><span data-stu-id="bebb2-131">UCI Machine Learning Repository [http://archive.ics.uci.edu/ml].</span></span> <span data-ttu-id="bebb2-132">加利福尼亚州，加利福尼亚大学：欧文分校，信息与计算机科学学院。</span><span class="sxs-lookup"><span data-stu-id="bebb2-132">Irvine, CA: University of California, School of Information and Computer Science.</span></span>

1. <span data-ttu-id="bebb2-133">下载 [UCI Sentiment Labeled Sentences 数据集 zip 文件](http://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip)并解压缩。</span><span class="sxs-lookup"><span data-stu-id="bebb2-133">Download [UCI Sentiment Labeled Sentences dataset ZIP file](http://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip), and unzip.</span></span>

2. <span data-ttu-id="bebb2-134">将 `yelp_labelled.txt` 文件复制到已创建的“Data”  目录中。</span><span class="sxs-lookup"><span data-stu-id="bebb2-134">Copy the `yelp_labelled.txt` file into the *Data* directory you created.</span></span>

3. <span data-ttu-id="bebb2-135">在“解决方案资源管理器”中，右键单击 `yelp_labeled.txt` 文件并选择“属性”  。</span><span class="sxs-lookup"><span data-stu-id="bebb2-135">In Solution Explorer, right-click the `yelp_labeled.txt` file and select **Properties**.</span></span> <span data-ttu-id="bebb2-136">在“高级”下，将“复制到输出目录”的值更改为“如果较新则复制”    。</span><span class="sxs-lookup"><span data-stu-id="bebb2-136">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="bebb2-137">创建类和定义路径</span><span class="sxs-lookup"><span data-stu-id="bebb2-137">Create classes and define paths</span></span>

1. <span data-ttu-id="bebb2-138">将以下附加的 `using` 语句添加到“Program.cs”  文件顶部：</span><span class="sxs-lookup"><span data-stu-id="bebb2-138">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

    [!code-csharp[AddUsings](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#AddUsings "Add necessary usings")]

1. <span data-ttu-id="bebb2-139">将以下代码添加到 `Main` 方法正上方的行中，以创建字段来保存最近下载的数据集文件路径：</span><span class="sxs-lookup"><span data-stu-id="bebb2-139">Add the following code to the line right above the `Main` method, to create a field to hold the recently downloaded dataset file path:</span></span>

    [!code-csharp[Declare global variables](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#DeclareGlobalVariables "Declare global variables")]

1. <span data-ttu-id="bebb2-140">接下来，为输入数据和预测结果创建类。</span><span class="sxs-lookup"><span data-stu-id="bebb2-140">Next, create classes for your input data and predictions.</span></span> <span data-ttu-id="bebb2-141">向项目添加一个新类：</span><span class="sxs-lookup"><span data-stu-id="bebb2-141">Add a new class to your project:</span></span>

    - <span data-ttu-id="bebb2-142">在“解决方案资源管理器”  中，右键单击项目，然后选择“添加”   > “新项”  。</span><span class="sxs-lookup"><span data-stu-id="bebb2-142">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

    - <span data-ttu-id="bebb2-143">在“添加新项”  对话框中，选择“类”  并将“名称”  字段更改为“SentimentData.cs”  。</span><span class="sxs-lookup"><span data-stu-id="bebb2-143">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="bebb2-144">然后，选择“添加”  按钮。</span><span class="sxs-lookup"><span data-stu-id="bebb2-144">Then, select the **Add** button.</span></span>

1. <span data-ttu-id="bebb2-145">“SentimentData.cs”  文件随即在代码编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="bebb2-145">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="bebb2-146">将下面的 `using` 语句添加到 SentimentData.cs  的顶部：</span><span class="sxs-lookup"><span data-stu-id="bebb2-146">Add the following `using` statement to the top of *SentimentData.cs*:</span></span>

    [!code-csharp[AddUsings](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/SentimentData.cs#AddUsings "Add necessary usings")]

1. <span data-ttu-id="bebb2-147">删除现有类定义并向“SentimentData.cs”  文件添加以下代码，其中有两个类 `SentimentData` 和 `SentimentPrediction`：</span><span class="sxs-lookup"><span data-stu-id="bebb2-147">Remove the existing class definition and add the following code, which has two classes `SentimentData` and `SentimentPrediction`, to the *SentimentData.cs* file:</span></span>

    [!code-csharp[DeclareTypes](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/SentimentData.cs#DeclareTypes "Declare data record types")]

### <a name="how-the-data-was-prepared"></a><span data-ttu-id="bebb2-148">如何准备数据</span><span class="sxs-lookup"><span data-stu-id="bebb2-148">How the data was prepared</span></span>

<span data-ttu-id="bebb2-149">输入数据集类 `SentimentData` 拥有一个用于用户评论 (`SentimentText`) 的 `string`，以及一个用于情绪的 `bool` (`Sentiment`)，值为 1（正面）或 0（负面）。</span><span class="sxs-lookup"><span data-stu-id="bebb2-149">The input dataset class, `SentimentData`, has a `string` for user comments (`SentimentText`) and a `bool` (`Sentiment`) value of either 1 (positive) or 0 (negative) for sentiment.</span></span> <span data-ttu-id="bebb2-150">这两个字段都附加了 [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) 特性，其描述了每个字段的数据文件顺序。</span><span class="sxs-lookup"><span data-stu-id="bebb2-150">Both fields have [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) attributes attached to them, which describes the data file order of each field.</span></span>  <span data-ttu-id="bebb2-151">此外，`Sentiment` 属性具有 [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A) 特性，以将其指定为 `Label` 字段。</span><span class="sxs-lookup"><span data-stu-id="bebb2-151">In addition, the `Sentiment` property has a [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A) attribute to designate it as the `Label` field.</span></span> <span data-ttu-id="bebb2-152">下面的示例文件没有标题行，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bebb2-152">The following example file doesn't have a header row, and looks like this:</span></span>

|<span data-ttu-id="bebb2-153">情绪文本</span><span class="sxs-lookup"><span data-stu-id="bebb2-153">SentimentText</span></span>                         |<span data-ttu-id="bebb2-154">情绪（标签）</span><span class="sxs-lookup"><span data-stu-id="bebb2-154">Sentiment (Label)</span></span> |
|--------------------------------------|----------|
|<span data-ttu-id="bebb2-155">女服务员的服务速度有点慢。</span><span class="sxs-lookup"><span data-stu-id="bebb2-155">Waitress was a little slow in service.</span></span>|    <span data-ttu-id="bebb2-156">0</span><span class="sxs-lookup"><span data-stu-id="bebb2-156">0</span></span>     |
|<span data-ttu-id="bebb2-157">酥皮不行。</span><span class="sxs-lookup"><span data-stu-id="bebb2-157">Crust is not good.</span></span>                    |    <span data-ttu-id="bebb2-158">0</span><span class="sxs-lookup"><span data-stu-id="bebb2-158">0</span></span>     |
|<span data-ttu-id="bebb2-159">哇...喜欢这个地方。</span><span class="sxs-lookup"><span data-stu-id="bebb2-159">Wow... Loved this place.</span></span>              |    <span data-ttu-id="bebb2-160">1</span><span class="sxs-lookup"><span data-stu-id="bebb2-160">1</span></span>     |
|<span data-ttu-id="bebb2-161">服务很及时。</span><span class="sxs-lookup"><span data-stu-id="bebb2-161">Service was very prompt.</span></span>              |    <span data-ttu-id="bebb2-162">1</span><span class="sxs-lookup"><span data-stu-id="bebb2-162">1</span></span>     |

<span data-ttu-id="bebb2-163">`SentimentPrediction` 是在模型训练后使用的预测类。</span><span class="sxs-lookup"><span data-stu-id="bebb2-163">`SentimentPrediction` is the prediction class used after model training.</span></span> <span data-ttu-id="bebb2-164">它继承自 `SentimentData`，因此输入 `SentimentText` 可与输出预测结果一并显示。</span><span class="sxs-lookup"><span data-stu-id="bebb2-164">It inherits from `SentimentData` so that the input `SentimentText` can be displayed along with the output prediction.</span></span> <span data-ttu-id="bebb2-165">`Prediction` 布尔值是随附新的输入 `SentimentText` 提供时模型预测出的值。</span><span class="sxs-lookup"><span data-stu-id="bebb2-165">The `Prediction` boolean is the value that the model predicts when supplied with new input `SentimentText`.</span></span>

<span data-ttu-id="bebb2-166">输出类 `SentimentPrediction` 包含另外两个由模型计算得出的属性：`Score`（模型计算得出的原始分数）和 `Probability`（校准到具有积极情绪的文本几率的分数）。</span><span class="sxs-lookup"><span data-stu-id="bebb2-166">The output class `SentimentPrediction` contains two other properties calculated by the model: `Score` - the raw score calculated by the model, and `Probability` - the score calibrated to the likelihood of the text having positive sentiment.</span></span>

<span data-ttu-id="bebb2-167">在本教程中，最重要的属性是 `Prediction`。</span><span class="sxs-lookup"><span data-stu-id="bebb2-167">For this tutorial, the most important property is `Prediction`.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="bebb2-168">加载数据</span><span class="sxs-lookup"><span data-stu-id="bebb2-168">Load the data</span></span>

<span data-ttu-id="bebb2-169">ML.NET 中的数据表示为 [IDataView 类](xref:Microsoft.ML.IDataView)。</span><span class="sxs-lookup"><span data-stu-id="bebb2-169">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="bebb2-170">`IDataView` 是用于描述表格数据（数字和文本）的一种灵活且有效的方法。</span><span class="sxs-lookup"><span data-stu-id="bebb2-170">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="bebb2-171">可从文本文件或实时（例如，SQL 数据库或日志文件）将数据加载到 `IDataView` 对象。</span><span class="sxs-lookup"><span data-stu-id="bebb2-171">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span>

<span data-ttu-id="bebb2-172">[MLContext 类](xref:Microsoft.ML.MLContext)是所有 ML.NET 操作的起点。</span><span class="sxs-lookup"><span data-stu-id="bebb2-172">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations.</span></span> <span data-ttu-id="bebb2-173">初始化 `mlContext` 会创建一个新的 ML.NET 环境，可在模型创建工作流对象之间共享该环境。</span><span class="sxs-lookup"><span data-stu-id="bebb2-173">Initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="bebb2-174">从概念上讲，它与实体框架中的 `DBContext` 类似。</span><span class="sxs-lookup"><span data-stu-id="bebb2-174">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

<span data-ttu-id="bebb2-175">准备应用，然后加载数据：</span><span class="sxs-lookup"><span data-stu-id="bebb2-175">You prepare the app, and then load data:</span></span>

1. <span data-ttu-id="bebb2-176">使用以下代码替换 `Main` 方法中的 `Console.WriteLine("Hello World!")` 行，以声明和初始化 mlContext 变量：</span><span class="sxs-lookup"><span data-stu-id="bebb2-176">Replace the `Console.WriteLine("Hello World!")` line in the `Main` method with the following code to declare and initialize the mlContext variable:</span></span>

    [!code-csharp[CreateMLContext](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CreateMLContext "Create the ML Context")]

2. <span data-ttu-id="bebb2-177">将以下代码作为下一行代码添加到 `Main()` 方法中：</span><span class="sxs-lookup"><span data-stu-id="bebb2-177">Add the following as the next line of code in the `Main()` method:</span></span>

    [!code-csharp[CallLoadData](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CallLoadData)]

3. <span data-ttu-id="bebb2-178">使用下面的代码紧随 `Main()` 方法后创建 `LoadData()` 方法：</span><span class="sxs-lookup"><span data-stu-id="bebb2-178">Create the `LoadData()` method, just after the `Main()` method, using the following code:</span></span>

    ```csharp
    public static TrainTestData LoadData(MLContext mlContext)
    {

    }
    ```

    <span data-ttu-id="bebb2-179">`LoadData()` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="bebb2-179">The `LoadData()` method executes the following tasks:</span></span>

    - <span data-ttu-id="bebb2-180">加载数据。</span><span class="sxs-lookup"><span data-stu-id="bebb2-180">Loads the data.</span></span>
    - <span data-ttu-id="bebb2-181">将加载的数据集拆分为训练数据集和测试数据集。</span><span class="sxs-lookup"><span data-stu-id="bebb2-181">Splits the loaded dataset into train and test datasets.</span></span>
    - <span data-ttu-id="bebb2-182">返回拆分的训练数据集和测试数据集。</span><span class="sxs-lookup"><span data-stu-id="bebb2-182">Returns the split train and test datasets.</span></span>

4. <span data-ttu-id="bebb2-183">将以下代码添加为 `LoadData()` 方法的首行：</span><span class="sxs-lookup"><span data-stu-id="bebb2-183">Add the following code as the first line of the `LoadData()` method:</span></span>

    [!code-csharp[LoadData](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#LoadData "loading dataset")]

    <span data-ttu-id="bebb2-184">[LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) 方法用于定义数据架构并读取文件。</span><span class="sxs-lookup"><span data-stu-id="bebb2-184">The [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) method defines the data schema and reads in the file.</span></span> <span data-ttu-id="bebb2-185">它使用数据路径变量并返回 `IDataView`。</span><span class="sxs-lookup"><span data-stu-id="bebb2-185">It takes in the data path variables and returns an `IDataView`.</span></span>

### <a name="split-the-dataset-for-model-training-and-testing"></a><span data-ttu-id="bebb2-186">拆分数据集以进行模型训练和测试</span><span class="sxs-lookup"><span data-stu-id="bebb2-186">Split the dataset for model training and testing</span></span>

<span data-ttu-id="bebb2-187">准备模型时，使用部分数据集来训练它，并使用部分数据集来测试模型的准确性。</span><span class="sxs-lookup"><span data-stu-id="bebb2-187">When preparing a model, you use part of the dataset to train it and part of the dataset to test the model's accuracy.</span></span>

1. <span data-ttu-id="bebb2-188">要将加载的数据拆分为所需的数据集，请添加以下代码作为 `LoadData()` 方法中的下一行：</span><span class="sxs-lookup"><span data-stu-id="bebb2-188">To split the loaded data into the needed datasets, add the following code as the next line in the `LoadData()` method:</span></span>

    [!code-csharp[SplitData](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#SplitData "Split the Data")]

    <span data-ttu-id="bebb2-189">上述代码使用 [TrainTestSplit()](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit%2A) 方法将加载的数据集拆分为训练数据集和测试数据集，并在 <xref:Microsoft.ML.DataOperationsCatalog.TrainTestData> 类中返回它们。</span><span class="sxs-lookup"><span data-stu-id="bebb2-189">The previous code uses the [TrainTestSplit()](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit%2A) method to split the loaded dataset into train and test datasets and return them in the <xref:Microsoft.ML.DataOperationsCatalog.TrainTestData> class.</span></span> <span data-ttu-id="bebb2-190">使用 `testFraction` 参数指定数据的测试集百分比。</span><span class="sxs-lookup"><span data-stu-id="bebb2-190">Specify the test set percentage of data with the `testFraction`parameter.</span></span> <span data-ttu-id="bebb2-191">默认值为 10%，在本例中使用 20%，以评估更多数据。</span><span class="sxs-lookup"><span data-stu-id="bebb2-191">The default is 10%, in this case you use 20% to evaluate more data.</span></span>

2. <span data-ttu-id="bebb2-192">在 `LoadData()` 方法末尾返回 `splitDataView`：</span><span class="sxs-lookup"><span data-stu-id="bebb2-192">Return the `splitDataView` at the end of the `LoadData()` method:</span></span>

    [!code-csharp[ReturnSplitData](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#ReturnSplitData)]

## <a name="build-and-train-the-model"></a><span data-ttu-id="bebb2-193">生成和定型模型</span><span class="sxs-lookup"><span data-stu-id="bebb2-193">Build and train the model</span></span>

1. <span data-ttu-id="bebb2-194">将以下调用添加到 `BuildAndTrainModel` 方法作为 `Main()` 方法的下一行代码：</span><span class="sxs-lookup"><span data-stu-id="bebb2-194">Add the following call to the `BuildAndTrainModel`method as the next line of code in the `Main()` method:</span></span>

    [!code-csharp[CallBuildAndTrainModel](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CallBuildAndTrainModel)]

    <span data-ttu-id="bebb2-195">`BuildAndTrainModel()` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="bebb2-195">The `BuildAndTrainModel()` method executes the following tasks:</span></span>

    - <span data-ttu-id="bebb2-196">提取并转换数据。</span><span class="sxs-lookup"><span data-stu-id="bebb2-196">Extracts and transforms the data.</span></span>
    - <span data-ttu-id="bebb2-197">定型模型。</span><span class="sxs-lookup"><span data-stu-id="bebb2-197">Trains the model.</span></span>
    - <span data-ttu-id="bebb2-198">根据测试数据预测情绪。</span><span class="sxs-lookup"><span data-stu-id="bebb2-198">Predicts sentiment based on test data.</span></span>
    - <span data-ttu-id="bebb2-199">返回模型。</span><span class="sxs-lookup"><span data-stu-id="bebb2-199">Returns the model.</span></span>

2. <span data-ttu-id="bebb2-200">使用下面的代码紧随 `Main()` 方法后创建 `BuildAndTrainModel()` 方法：</span><span class="sxs-lookup"><span data-stu-id="bebb2-200">Create the `BuildAndTrainModel()` method, just after the `Main()` method, using the following code:</span></span>

    ```csharp
    public static ITransformer BuildAndTrainModel(MLContext mlContext, IDataView splitTrainSet)
    {

    }
    ```

### <a name="extract-and-transform-the-data"></a><span data-ttu-id="bebb2-201">提取和转换数据</span><span class="sxs-lookup"><span data-stu-id="bebb2-201">Extract and transform the data</span></span>

1. <span data-ttu-id="bebb2-202">将 `FeaturizeText` 作为下一行代码调用：</span><span class="sxs-lookup"><span data-stu-id="bebb2-202">Call `FeaturizeText` as the next line of code:</span></span>

    [!code-csharp[FeaturizeText](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#FeaturizeText "Featurize the text")]

    <span data-ttu-id="bebb2-203">上述代码中的 `FeaturizeText()` 方法将文本列 (`SentimentText`) 转换为机器学习算法使用的数字键类型的 `Features` 列，并将其作为新的数据集列添加：</span><span class="sxs-lookup"><span data-stu-id="bebb2-203">The `FeaturizeText()` method in the previous code converts the text column (`SentimentText`) into a numeric key type `Features` column used by the machine learning algorithm and adds it as a new dataset column:</span></span>

    |<span data-ttu-id="bebb2-204">情绪文本</span><span class="sxs-lookup"><span data-stu-id="bebb2-204">SentimentText</span></span>                         |<span data-ttu-id="bebb2-205">情绪</span><span class="sxs-lookup"><span data-stu-id="bebb2-205">Sentiment</span></span> |<span data-ttu-id="bebb2-206">特征</span><span class="sxs-lookup"><span data-stu-id="bebb2-206">Features</span></span>              |
    |--------------------------------------|----------|----------------------|
    |<span data-ttu-id="bebb2-207">女服务员的服务速度有点慢。</span><span class="sxs-lookup"><span data-stu-id="bebb2-207">Waitress was a little slow in service.</span></span>|    <span data-ttu-id="bebb2-208">0</span><span class="sxs-lookup"><span data-stu-id="bebb2-208">0</span></span>     |<span data-ttu-id="bebb2-209">[0.76, 0.65, 0.44, …]</span><span class="sxs-lookup"><span data-stu-id="bebb2-209">[0.76, 0.65, 0.44, …]</span></span> |
    |<span data-ttu-id="bebb2-210">酥皮不行。</span><span class="sxs-lookup"><span data-stu-id="bebb2-210">Crust is not good.</span></span>                    |    <span data-ttu-id="bebb2-211">0</span><span class="sxs-lookup"><span data-stu-id="bebb2-211">0</span></span>     |<span data-ttu-id="bebb2-212">[0.98, 0.43, 0.54, …]</span><span class="sxs-lookup"><span data-stu-id="bebb2-212">[0.98, 0.43, 0.54, …]</span></span> |
    |<span data-ttu-id="bebb2-213">哇...喜欢这个地方。</span><span class="sxs-lookup"><span data-stu-id="bebb2-213">Wow... Loved this place.</span></span>              |    <span data-ttu-id="bebb2-214">1</span><span class="sxs-lookup"><span data-stu-id="bebb2-214">1</span></span>     |<span data-ttu-id="bebb2-215">[0.35, 0.73, 0.46, …]</span><span class="sxs-lookup"><span data-stu-id="bebb2-215">[0.35, 0.73, 0.46, …]</span></span> |
    |<span data-ttu-id="bebb2-216">服务很及时。</span><span class="sxs-lookup"><span data-stu-id="bebb2-216">Service was very prompt.</span></span>              |    <span data-ttu-id="bebb2-217">1</span><span class="sxs-lookup"><span data-stu-id="bebb2-217">1</span></span>     |<span data-ttu-id="bebb2-218">[0.39, 0, 0.75, …]</span><span class="sxs-lookup"><span data-stu-id="bebb2-218">[0.39, 0, 0.75, …]</span></span>    |

### <a name="add-a-learning-algorithm"></a><span data-ttu-id="bebb2-219">添加学习算法</span><span class="sxs-lookup"><span data-stu-id="bebb2-219">Add a learning algorithm</span></span>

<span data-ttu-id="bebb2-220">此应用使用对数据项或数据行进行分类的分类算法。</span><span class="sxs-lookup"><span data-stu-id="bebb2-220">This app uses a classification algorithm that categorizes items or rows of data.</span></span> <span data-ttu-id="bebb2-221">应用将网站评论分类为正面评论或负面评论，因此，请使用二元分类任务。</span><span class="sxs-lookup"><span data-stu-id="bebb2-221">The app categorizes website comments as either positive or negative, so use the binary classification task.</span></span>

<span data-ttu-id="bebb2-222">将机器学习任务追加到数据转换定义中，方法是在 `BuildAndTrainModel()` 中添加以下代码作为下一行代码：</span><span class="sxs-lookup"><span data-stu-id="bebb2-222">Append the machine learning task to the data transformation definitions by adding the following as the next line of code in `BuildAndTrainModel()`:</span></span>

[!code-csharp[SdcaLogisticRegressionBinaryTrainer](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#AddTrainer "Add a SdcaLogisticRegressionBinaryTrainer")]

<span data-ttu-id="bebb2-223">[SdcaLogisticRegressionBinaryTrainer](xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer) 是你的分类训练算法。</span><span class="sxs-lookup"><span data-stu-id="bebb2-223">The [SdcaLogisticRegressionBinaryTrainer](xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer) is your classification training algorithm.</span></span> <span data-ttu-id="bebb2-224">此算法会追加到 `estimator` 并接受特征化的 `SentimentText` (`Features`) 和 `Label` 输入参数，以便从历史数据中学习。</span><span class="sxs-lookup"><span data-stu-id="bebb2-224">This is appended to the `estimator` and accepts the featurized `SentimentText` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span>

### <a name="train-the-model"></a><span data-ttu-id="bebb2-225">定型模型</span><span class="sxs-lookup"><span data-stu-id="bebb2-225">Train the model</span></span>

<span data-ttu-id="bebb2-226">在 `BuildAndTrainModel()` 方法中添加以下代码作为下一代码行，使模型适应 `splitTrainSet` 数据，并返回经过训练的模型：</span><span class="sxs-lookup"><span data-stu-id="bebb2-226">Fit the model to the `splitTrainSet` data and return the trained model by adding the following as the next line of code in the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[TrainModel](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#TrainModel "Train the model")]

<span data-ttu-id="bebb2-227">[Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) 方法通过转换数据集并应用训练来训练模型。</span><span class="sxs-lookup"><span data-stu-id="bebb2-227">The [Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) method trains your model by transforming the dataset and applying the training.</span></span>

### <a name="return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="bebb2-228">返回定型模型以用于评估</span><span class="sxs-lookup"><span data-stu-id="bebb2-228">Return the model trained to use for evaluation</span></span>

 <span data-ttu-id="bebb2-229">在 `BuildAndTrainModel()` 方法末尾返回模型：</span><span class="sxs-lookup"><span data-stu-id="bebb2-229">Return the model at the end of the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[ReturnModel](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#ReturnModel "Return the model")]

## <a name="evaluate-the-model"></a><span data-ttu-id="bebb2-230">评估模型</span><span class="sxs-lookup"><span data-stu-id="bebb2-230">Evaluate the model</span></span>

<span data-ttu-id="bebb2-231">训练模型后，使用测试数据验证模型的性能。</span><span class="sxs-lookup"><span data-stu-id="bebb2-231">After your model is trained, use your test data validate the model's performance.</span></span>

1. <span data-ttu-id="bebb2-232">使用以下代码紧跟 `BuildAndTrainModel()` 之后创建 `Evaluate()` 方法：</span><span class="sxs-lookup"><span data-stu-id="bebb2-232">Create the `Evaluate()` method, just after `BuildAndTrainModel()`, with the following code:</span></span>

    ```csharp
    public static void Evaluate(MLContext mlContext, ITransformer model, IDataView splitTestSet)
    {

    }
    ```

    <span data-ttu-id="bebb2-233">`Evaluate()` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="bebb2-233">The `Evaluate()` method executes the following tasks:</span></span>

    - <span data-ttu-id="bebb2-234">加载测试数据集。</span><span class="sxs-lookup"><span data-stu-id="bebb2-234">Loads the test dataset.</span></span>
    - <span data-ttu-id="bebb2-235">创建 BinaryClassification 计算器。</span><span class="sxs-lookup"><span data-stu-id="bebb2-235">Creates the BinaryClassification evaluator.</span></span>
    - <span data-ttu-id="bebb2-236">评估模型并创建指标。</span><span class="sxs-lookup"><span data-stu-id="bebb2-236">Evaluates the model and creates metrics.</span></span>
    - <span data-ttu-id="bebb2-237">显示指标。</span><span class="sxs-lookup"><span data-stu-id="bebb2-237">Displays the metrics.</span></span>

2. <span data-ttu-id="bebb2-238">使用下面的代码，在 `BuildAndTrainModel()` 方法调用的正下方，从 `Main()` 方法中添加对新方法的调用：</span><span class="sxs-lookup"><span data-stu-id="bebb2-238">Add a call to the new method from the `Main()` method, right under the `BuildAndTrainModel()` method call, using the following code:</span></span>

    [!code-csharp[CallEvaluate](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CallEvaluate "Call the Evaluate method")]

3. <span data-ttu-id="bebb2-239">将以下代码添加到 `Evaluate()` 以转换 `splitTestSet` 数据：</span><span class="sxs-lookup"><span data-stu-id="bebb2-239">Transform the `splitTestSet` data by adding the following code to `Evaluate()`:</span></span>

    [!code-csharp[PredictWithTransformer](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#TransformData "Predict using the Transformer")]

    <span data-ttu-id="bebb2-240">之前的代码使用 [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) 方法对测试数据集提供的多个输入行进行预测。</span><span class="sxs-lookup"><span data-stu-id="bebb2-240">The previous code uses the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method to make predictions for multiple provided input rows of a test dataset.</span></span>

4. <span data-ttu-id="bebb2-241">通过在 `Evaluate()` 方法中添加以下代码作为下一代码行来评估模型：</span><span class="sxs-lookup"><span data-stu-id="bebb2-241">Evaluate the model by adding the following as the next line of code in the `Evaluate()` method:</span></span>

    [!code-csharp[ComputeMetrics](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#Evaluate "Compute Metrics")]

<span data-ttu-id="bebb2-242">获得预测集 (`predictions`) 后，[Evaluate()](xref:Microsoft.ML.BinaryClassificationCatalog.Evaluate%2A) 方法会对模型进行评估，其会将预测值与测试数据集中的实际 `Labels` 进行比较，并返回有关模型执行情况的 [CalibratedBinaryClassificationMetrics](xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics) 对象。</span><span class="sxs-lookup"><span data-stu-id="bebb2-242">Once you have the prediction set (`predictions`), the [Evaluate()](xref:Microsoft.ML.BinaryClassificationCatalog.Evaluate%2A) method assesses the model, which compares the predicted values with the actual `Labels` in the test dataset and returns a [CalibratedBinaryClassificationMetrics](xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics) object on how the model is performing.</span></span>

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="bebb2-243">显示用于模型验证的指标</span><span class="sxs-lookup"><span data-stu-id="bebb2-243">Displaying the metrics for model validation</span></span>

<span data-ttu-id="bebb2-244">使用以下代码显示指标：</span><span class="sxs-lookup"><span data-stu-id="bebb2-244">Use the following code to display the metrics:</span></span>

[!code-csharp[DisplayMetrics](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#DisplayMetrics "Display selected metrics")]

- <span data-ttu-id="bebb2-245">`Accuracy` 指标可获取模型的准确性，即测试集中正确预测所占的比例。</span><span class="sxs-lookup"><span data-stu-id="bebb2-245">The `Accuracy` metric gets the accuracy of a model, which is the proportion of correct predictions in the test set.</span></span>

- <span data-ttu-id="bebb2-246">`AreaUnderRocCurve` 指标指示模型对正面类和负面类进行正确分类的置信度。</span><span class="sxs-lookup"><span data-stu-id="bebb2-246">The `AreaUnderRocCurve` metric indicates how confident the model is correctly classifying the positive and negative classes.</span></span> <span data-ttu-id="bebb2-247">应该使 `AreaUnderRocCurve` 尽可能接近 1。</span><span class="sxs-lookup"><span data-stu-id="bebb2-247">You want the `AreaUnderRocCurve` to be as close to one as possible.</span></span>

- <span data-ttu-id="bebb2-248">`F1Score` 指标可获取模型的 F1 分数，该分数是[查准率](../resources/glossary.md#precision)和[查全率](../resources/glossary.md#recall)之间的平衡关系的度量值。</span><span class="sxs-lookup"><span data-stu-id="bebb2-248">The `F1Score` metric gets the model's F1 score, which is a measure of balance between [precision](../resources/glossary.md#precision) and [recall](../resources/glossary.md#recall).</span></span>  <span data-ttu-id="bebb2-249">应该使 `F1Score` 尽可能接近 1。</span><span class="sxs-lookup"><span data-stu-id="bebb2-249">You want the `F1Score` to be as close to one as possible.</span></span>

### <a name="predict-the-test-data-outcome"></a><span data-ttu-id="bebb2-250">预测测试数据结果</span><span class="sxs-lookup"><span data-stu-id="bebb2-250">Predict the test data outcome</span></span>

1. <span data-ttu-id="bebb2-251">使用下面的代码紧随 `Evaluate()` 方法后创建 `UseModelWithSingleItem()` 方法：</span><span class="sxs-lookup"><span data-stu-id="bebb2-251">Create the `UseModelWithSingleItem()` method, just after the `Evaluate()` method, using the following code:</span></span>

    ```csharp
    private static void UseModelWithSingleItem(MLContext mlContext, ITransformer model)
    {

    }
    ```

    <span data-ttu-id="bebb2-252">`UseModelWithSingleItem()` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="bebb2-252">The `UseModelWithSingleItem()` method executes the following tasks:</span></span>

    - <span data-ttu-id="bebb2-253">创建测试数据的单个注释。</span><span class="sxs-lookup"><span data-stu-id="bebb2-253">Creates a single comment of test data.</span></span>
    - <span data-ttu-id="bebb2-254">根据测试数据预测情绪。</span><span class="sxs-lookup"><span data-stu-id="bebb2-254">Predicts sentiment based on test data.</span></span>
    - <span data-ttu-id="bebb2-255">结合测试数据和预测进行报告。</span><span class="sxs-lookup"><span data-stu-id="bebb2-255">Combines test data and predictions for reporting.</span></span>
    - <span data-ttu-id="bebb2-256">显示预测结果。</span><span class="sxs-lookup"><span data-stu-id="bebb2-256">Displays the predicted results.</span></span>

2. <span data-ttu-id="bebb2-257">使用下面的代码，在 `Evaluate()` 方法调用的正下方，从 `Main()` 方法中添加对新方法的调用：</span><span class="sxs-lookup"><span data-stu-id="bebb2-257">Add a call to the new method from the `Main()` method, right under the `Evaluate()` method call, using the following code:</span></span>

    [!code-csharp[CallUseModelWithSingleItem](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CallUseModelWithSingleItem "Call the UseModelWithSingleItem method")]

3. <span data-ttu-id="bebb2-258">添加以下代码，以便作为 `UseModelWithSingleItem()` 方法中的第一行进行创建：</span><span class="sxs-lookup"><span data-stu-id="bebb2-258">Add the following code to create as the first line in the `UseModelWithSingleItem()` Method:</span></span>

    [!code-csharp[CreatePredictionEngine](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CreatePredictionEngine1 "Create the PredictionEngine")]

    <span data-ttu-id="bebb2-259">[PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) 是一个简便 API，可使用它对单个数据实例执行预测。</span><span class="sxs-lookup"><span data-stu-id="bebb2-259">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to perform a prediction on a single instance of data.</span></span> <span data-ttu-id="bebb2-260">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) 不是线程安全型。</span><span class="sxs-lookup"><span data-stu-id="bebb2-260">[`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) is not thread-safe.</span></span> <span data-ttu-id="bebb2-261">可以在单线程环境或原型环境中使用。</span><span class="sxs-lookup"><span data-stu-id="bebb2-261">It's acceptable to use in single-threaded or prototype environments.</span></span> <span data-ttu-id="bebb2-262">为了在生产环境中提高性能和线程安全，请使用 `PredictionEnginePool` 服务，这将创建一个在整个应用程序中使用的 [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) 对象的 [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601)。</span><span class="sxs-lookup"><span data-stu-id="bebb2-262">For improved performance and thread safety in production environments, use the `PredictionEnginePool` service, which creates an [`ObjectPool`](xref:Microsoft.Extensions.ObjectPool.ObjectPool%601) of [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) objects for use throughout your application.</span></span> <span data-ttu-id="bebb2-263">请参阅本指南，了解如何[在 ASP.NET Core Web API 中使用 `PredictionEnginePool`](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application)。</span><span class="sxs-lookup"><span data-stu-id="bebb2-263">See this guide on how to [use `PredictionEnginePool` in an ASP.NET Core Web API](../how-to-guides/serve-model-web-api-ml-net.md#register-predictionenginepool-for-use-in-the-application).</span></span>

    > [!NOTE]
    > <span data-ttu-id="bebb2-264">`PredictionEnginePool` 服务扩展目前处于预览状态。</span><span class="sxs-lookup"><span data-stu-id="bebb2-264">`PredictionEnginePool` service extension is currently in preview.</span></span>

4. <span data-ttu-id="bebb2-265">通过创建一个 `SentimentData` 实例，在 `UseModelWithSingleItem()` 方法中添加一个注释来测试定型模型的预测：</span><span class="sxs-lookup"><span data-stu-id="bebb2-265">Add a comment to test the trained model's prediction in the `UseModelWithSingleItem()` method by creating an instance of `SentimentData`:</span></span>

    [!code-csharp[PredictionData](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CreateTestIssue1 "Create test data for single prediction")]

5. <span data-ttu-id="bebb2-266">通过在 `UseModelWithSingleItem()` 方法中将以下代码作为下一行代码添加，将测试评论数据传递到 [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602)：</span><span class="sxs-lookup"><span data-stu-id="bebb2-266">Pass the test comment data to the [`PredictionEngine`](xref:Microsoft.ML.PredictionEngine%602) by adding the following as the next lines of code in the `UseModelWithSingleItem()` method:</span></span>

    [!code-csharp[Predict](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#Predict "Create a prediction of sentiment")]

    <span data-ttu-id="bebb2-267">[Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) 函数对单行数据进行预测。</span><span class="sxs-lookup"><span data-stu-id="bebb2-267">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single row of data.</span></span>

6. <span data-ttu-id="bebb2-268">使用以下代码显示 `SentimentText` 和相应的情绪预测：</span><span class="sxs-lookup"><span data-stu-id="bebb2-268">Display `SentimentText` and corresponding sentiment prediction using the following code:</span></span>

    [!code-csharp[OutputPrediction](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#OutputPrediction "Display prediction output")]

## <a name="use-the-model-for-prediction"></a><span data-ttu-id="bebb2-269">使用模型进行预测</span><span class="sxs-lookup"><span data-stu-id="bebb2-269">Use the model for prediction</span></span>

### <a name="deploy-and-predict-batch-items"></a><span data-ttu-id="bebb2-270">部署和预测批项目</span><span class="sxs-lookup"><span data-stu-id="bebb2-270">Deploy and predict batch items</span></span>

1. <span data-ttu-id="bebb2-271">使用下面的代码紧随 `UseModelWithSingleItem()` 方法后创建 `UseModelWithBatchItems()` 方法：</span><span class="sxs-lookup"><span data-stu-id="bebb2-271">Create the `UseModelWithBatchItems()` method, just after the `UseModelWithSingleItem()` method, using the following code:</span></span>

    ```csharp
    public static void UseModelWithBatchItems(MLContext mlContext, ITransformer model)
    {

    }
    ```

    <span data-ttu-id="bebb2-272">`UseModelWithBatchItems()` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="bebb2-272">The `UseModelWithBatchItems()` method executes the following tasks:</span></span>

    - <span data-ttu-id="bebb2-273">创建批处理测试数据。</span><span class="sxs-lookup"><span data-stu-id="bebb2-273">Creates batch test data.</span></span>
    - <span data-ttu-id="bebb2-274">根据测试数据预测情绪。</span><span class="sxs-lookup"><span data-stu-id="bebb2-274">Predicts sentiment based on test data.</span></span>
    - <span data-ttu-id="bebb2-275">结合测试数据和预测进行报告。</span><span class="sxs-lookup"><span data-stu-id="bebb2-275">Combines test data and predictions for reporting.</span></span>
    - <span data-ttu-id="bebb2-276">显示预测结果。</span><span class="sxs-lookup"><span data-stu-id="bebb2-276">Displays the predicted results.</span></span>

2. <span data-ttu-id="bebb2-277">使用下面的代码，在 `UseModelWithSingleItem()` 方法调用的正下方，从 `Main` 方法中添加对新方法的调用：</span><span class="sxs-lookup"><span data-stu-id="bebb2-277">Add a call to the new method from the `Main` method, right under the `UseModelWithSingleItem()` method call, using the following code:</span></span>

    [!code-csharp[CallPredictModelBatchItems](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CallUseModelWithBatchItems "Call the CallUseModelWithBatchItems method")]

3. <span data-ttu-id="bebb2-278">添加一些评论，以测试 `UseModelWithBatchItems()` 方法中的定型模型预测：</span><span class="sxs-lookup"><span data-stu-id="bebb2-278">Add some comments to test the trained model's predictions in the `UseModelWithBatchItems()` method:</span></span>

    [!code-csharp[PredictionData](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#CreateTestIssues "Create test data for predictions")]

### <a name="predict-comment-sentiment"></a><span data-ttu-id="bebb2-279">预测评论情绪</span><span class="sxs-lookup"><span data-stu-id="bebb2-279">Predict comment sentiment</span></span>

<span data-ttu-id="bebb2-280">使用模型通过 [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) 方法预测评论数据情绪：</span><span class="sxs-lookup"><span data-stu-id="bebb2-280">Use the model to predict the comment data sentiment using the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method:</span></span>

[!code-csharp[Predict](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#Prediction "Create predictions of sentiments")]

### <a name="combine-and-display-the-predictions"></a><span data-ttu-id="bebb2-281">合并并显示预测结果</span><span class="sxs-lookup"><span data-stu-id="bebb2-281">Combine and display the predictions</span></span>

<span data-ttu-id="bebb2-282">使用以下代码为预测创建标头：</span><span class="sxs-lookup"><span data-stu-id="bebb2-282">Create a header for the predictions using the following code:</span></span>

[!code-csharp[OutputHeaders](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#AddInfoMessage "Display prediction outputs")]

<span data-ttu-id="bebb2-283">由于 `SentimentPrediction` 继承自 `SentimentData`，`Transform()` 方法使用预测字段填充 `SentimentText`。</span><span class="sxs-lookup"><span data-stu-id="bebb2-283">Because `SentimentPrediction` is inherited from `SentimentData`, the `Transform()` method populated `SentimentText` with the predicted fields.</span></span> <span data-ttu-id="bebb2-284">随着 ML.NET 进程继续执行，每个组件会添加列，这让显示结果变得轻松：</span><span class="sxs-lookup"><span data-stu-id="bebb2-284">As the ML.NET process processes, each component adds columns, and this makes it easy to display the results:</span></span>

[!code-csharp[DisplayPredictions](~/samples/snippets/machine-learning/SentimentAnalysis/csharp/Program.cs#DisplayResults "Display the predictions")]

## <a name="results"></a><span data-ttu-id="bebb2-285">结果</span><span class="sxs-lookup"><span data-stu-id="bebb2-285">Results</span></span>

<span data-ttu-id="bebb2-286">结果应如下所示。</span><span class="sxs-lookup"><span data-stu-id="bebb2-286">Your results should be similar to the following.</span></span> <span data-ttu-id="bebb2-287">处理期间将显示消息。</span><span class="sxs-lookup"><span data-stu-id="bebb2-287">During processing, messages are displayed.</span></span> <span data-ttu-id="bebb2-288">你可能会看到警告或处理消息。</span><span class="sxs-lookup"><span data-stu-id="bebb2-288">You may see warnings, or processing messages.</span></span> <span data-ttu-id="bebb2-289">为清楚起见，已经从下面的结果中删除这些内容。</span><span class="sxs-lookup"><span data-stu-id="bebb2-289">These have been removed from the following results for clarity.</span></span>

```console
Model quality metrics evaluation
--------------------------------
Accuracy: 83.96%
Auc: 90.51%
F1Score: 84.04%

=============== End of model evaluation ===============

=============== Prediction Test of model with a single sample and test dataset ===============

Sentiment: This was a very bad steak | Prediction: Negative | Probability: 0.1027377
=============== End of Predictions ===============

=============== Prediction Test of loaded model with a multiple samples ===============

Sentiment: This was a horrible meal | Prediction: Negative | Probability: 0.1369192
Sentiment: I love this spaghetti. | Prediction: Positive | Probability: 0.9960636
=============== End of predictions ===============

=============== End of process ===============
Press any key to continue . . .

```

<span data-ttu-id="bebb2-290">祝贺你！</span><span class="sxs-lookup"><span data-stu-id="bebb2-290">Congratulations!</span></span> <span data-ttu-id="bebb2-291">现在，你已成功生成用于分类和预测消息情绪的机器学习模型。</span><span class="sxs-lookup"><span data-stu-id="bebb2-291">You've now successfully built a machine learning model for classifying and predicting messages sentiment.</span></span>

<span data-ttu-id="bebb2-292">生成成功的模型是一个迭代过程。</span><span class="sxs-lookup"><span data-stu-id="bebb2-292">Building successful models is an iterative process.</span></span> <span data-ttu-id="bebb2-293">由于本教程使用小型数据集来提供快速模型训练，因此该模型的初始质量较低。</span><span class="sxs-lookup"><span data-stu-id="bebb2-293">This model has initial lower quality as the tutorial uses small datasets to provide quick model training.</span></span> <span data-ttu-id="bebb2-294">如果对模型质量不满意，可以通过尝试提供更大的训练数据集，或通过为每种算法选择具有不同[超参数](../resources/glossary.md#hyperparameter)的不同训练算法来改进它。</span><span class="sxs-lookup"><span data-stu-id="bebb2-294">If you aren't satisfied with the model quality, you can try to improve it by providing larger training datasets or by choosing different training algorithms with different [hyper-parameters](../resources/glossary.md#hyperparameter) for each algorithm.</span></span>

<span data-ttu-id="bebb2-295">可以在 [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) 存储库中找到本教程的源代码。</span><span class="sxs-lookup"><span data-stu-id="bebb2-295">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bebb2-296">后续步骤</span><span class="sxs-lookup"><span data-stu-id="bebb2-296">Next steps</span></span>

<span data-ttu-id="bebb2-297">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="bebb2-297">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="bebb2-298">创建控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="bebb2-298">Create a console application</span></span>
> - <span data-ttu-id="bebb2-299">准备数据</span><span class="sxs-lookup"><span data-stu-id="bebb2-299">Prepare data</span></span>
> - <span data-ttu-id="bebb2-300">加载数据</span><span class="sxs-lookup"><span data-stu-id="bebb2-300">Load the data</span></span>
> - <span data-ttu-id="bebb2-301">生成和定型模型</span><span class="sxs-lookup"><span data-stu-id="bebb2-301">Build and train the model</span></span>
> - <span data-ttu-id="bebb2-302">评估模型</span><span class="sxs-lookup"><span data-stu-id="bebb2-302">Evaluate the model</span></span>
> - <span data-ttu-id="bebb2-303">使用模型进行预测</span><span class="sxs-lookup"><span data-stu-id="bebb2-303">Use the model to make a prediction</span></span>
> - <span data-ttu-id="bebb2-304">查看结果</span><span class="sxs-lookup"><span data-stu-id="bebb2-304">See the results</span></span>

<span data-ttu-id="bebb2-305">进入下一教程了解详细信息</span><span class="sxs-lookup"><span data-stu-id="bebb2-305">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="bebb2-306">问题分类</span><span class="sxs-lookup"><span data-stu-id="bebb2-306">Issue Classification</span></span>](github-issue-classification.md)

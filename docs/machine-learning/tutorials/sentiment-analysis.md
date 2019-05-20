---
title: 教程：分析网站评论 - 二元分类
description: 本教程演示如何创建 .NET Core 控制台应用程序，该应用程序对网站评论情绪进行分类并采取适当的措施。 二元情绪分类器在 Visual Studio 2017 中使用 C#。
ms.date: 04/18/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 1989a11a2f06ce4d713d6c3ecc70de0da606604e
ms.sourcegitcommit: 438824ff21f77c4301c6ba8a89a106114aa27bc8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/09/2019
ms.locfileid: "65462233"
---
# <a name="tutorial-analyze-sentiment-of-website-comments-with-binary-classification-in-mlnet"></a><span data-ttu-id="4947f-104">教程：在 ML.NET 中使用二元分类分析网站评论的情绪</span><span class="sxs-lookup"><span data-stu-id="4947f-104">Tutorial: Analyze sentiment of website comments with binary classification in ML.NET</span></span>

<span data-ttu-id="4947f-105">本教程演示如何创建 .NET Core 控制台应用程序，该应用程序对网站评论情绪进行分类并采取适当的措施。</span><span class="sxs-lookup"><span data-stu-id="4947f-105">This tutorial shows you how to create a .NET Core console application that classifies sentiment from website comments and takes the appropriate action.</span></span> <span data-ttu-id="4947f-106">二元情绪分类器在 Visual Studio 2017 中使用 C#。</span><span class="sxs-lookup"><span data-stu-id="4947f-106">The binary sentiment classifier uses C# in Visual Studio 2017.</span></span>

<span data-ttu-id="4947f-107">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="4947f-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="4947f-108">创建控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="4947f-108">Create a console application</span></span>
> * <span data-ttu-id="4947f-109">准备数据</span><span class="sxs-lookup"><span data-stu-id="4947f-109">Prepare data</span></span>
> * <span data-ttu-id="4947f-110">加载数据</span><span class="sxs-lookup"><span data-stu-id="4947f-110">Load the data</span></span>
> * <span data-ttu-id="4947f-111">生成和定型模型</span><span class="sxs-lookup"><span data-stu-id="4947f-111">Build and train the model</span></span>
> * <span data-ttu-id="4947f-112">评估模型</span><span class="sxs-lookup"><span data-stu-id="4947f-112">Evaluate the model</span></span>
> * <span data-ttu-id="4947f-113">使用模型进行预测</span><span class="sxs-lookup"><span data-stu-id="4947f-113">Use the model to make a prediction</span></span>
> * <span data-ttu-id="4947f-114">查看结果</span><span class="sxs-lookup"><span data-stu-id="4947f-114">See the results</span></span>

<span data-ttu-id="4947f-115">可以在 [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) 存储库中找到本教程的源代码。</span><span class="sxs-lookup"><span data-stu-id="4947f-115">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4947f-116">系统必备</span><span class="sxs-lookup"><span data-stu-id="4947f-116">Prerequisites</span></span>

* <span data-ttu-id="4947f-117">安装了“.NET Core 跨平台开发”工作负荷的 [Visual Studio 2017 15.6 或更高版本](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017)</span><span class="sxs-lookup"><span data-stu-id="4947f-117">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed</span></span>

* <span data-ttu-id="4947f-118">[UCI Sentiment Labeled Sentences 数据集](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip)（zip 文件）</span><span class="sxs-lookup"><span data-stu-id="4947f-118">[UCI Sentiment Labeled Sentences dataset](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) (ZIP file)</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="4947f-119">创建控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="4947f-119">Create a console application</span></span>

1. <span data-ttu-id="4947f-120">创建名为“SentimentAnalysis”的 **.NET Core 控制台应用程序**。</span><span class="sxs-lookup"><span data-stu-id="4947f-120">Create a **.NET Core Console Application** called "SentimentAnalysis".</span></span>

2. <span data-ttu-id="4947f-121">在项目中创建名为“Data”的目录，用于保存数据集文件。</span><span class="sxs-lookup"><span data-stu-id="4947f-121">Create a directory named *Data* in your project to save your data set files.</span></span>

3. <span data-ttu-id="4947f-122">安装“Microsoft.ML NuGet 包”：</span><span class="sxs-lookup"><span data-stu-id="4947f-122">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="4947f-123">在“解决方案资源管理器”中，右键单击项目，然后选择“管理 NuGet 包”。</span><span class="sxs-lookup"><span data-stu-id="4947f-123">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="4947f-124">选择“nuget.org”作为包源，然后选择“浏览”选项卡。搜索“Microsoft.ML”，选择所需的包，然后选择“安装”按钮。</span><span class="sxs-lookup"><span data-stu-id="4947f-124">Choose "nuget.org" as the package source, and then select the **Browse** tab. Search for **Microsoft.ML**, select the package you want, and then select the **Install** button.</span></span> <span data-ttu-id="4947f-125">同意所选包的许可条款，继续执行安装。</span><span class="sxs-lookup"><span data-stu-id="4947f-125">Proceed with the installation by agreeing to the the license terms for the package you choose.</span></span> <span data-ttu-id="4947f-126">对 **Microsoft.ML.FastTree** NuGet 包执行相同操作。</span><span class="sxs-lookup"><span data-stu-id="4947f-126">Do the same for the **Microsoft.ML.FastTree** NuGet package.</span></span>

## <a name="prepare-your-data"></a><span data-ttu-id="4947f-127">准备数据</span><span class="sxs-lookup"><span data-stu-id="4947f-127">Prepare your data</span></span>

> [!NOTE]
> <span data-ttu-id="4947f-128">本教程的数据集摘自 KDD 2015 中由 Kotzias 等</span><span class="sxs-lookup"><span data-stu-id="4947f-128">The datasets for this tutorial are from the 'From Group to Individual Labels using Deep Features', Kotzias et.</span></span> <span data-ttu-id="4947f-129">提出的“From Group to Individual Labels using Deep Features”，</span><span class="sxs-lookup"><span data-stu-id="4947f-129">al,.</span></span> <span data-ttu-id="4947f-130">并托管在 UCI 机器学习存储库中（Dua, D. 和 Karra Taniskidou, E.(2017)）。</span><span class="sxs-lookup"><span data-stu-id="4947f-130">KDD 2015, and hosted at the UCI Machine Learning Repository - Dua, D. and Karra Taniskidou, E. (2017).</span></span> <span data-ttu-id="4947f-131">UCI 机器学习存储库 [http://archive.ics.uci.edu/ml]。</span><span class="sxs-lookup"><span data-stu-id="4947f-131">UCI Machine Learning Repository [http://archive.ics.uci.edu/ml].</span></span> <span data-ttu-id="4947f-132">加利福尼亚州，加利福尼亚大学：欧文分校，信息与计算机科学学院。</span><span class="sxs-lookup"><span data-stu-id="4947f-132">Irvine, CA: University of California, School of Information and Computer Science.</span></span>

1. <span data-ttu-id="4947f-133">下载 [UCI Sentiment Labeled Sentences 数据集 zip 文件](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip)并解压缩。</span><span class="sxs-lookup"><span data-stu-id="4947f-133">Download [UCI Sentiment Labeled Sentences dataset ZIP file](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip), and unzip.</span></span>

2. <span data-ttu-id="4947f-134">将 `yelp_labelled.txt` 文件复制到已创建的“数据”目录中。</span><span class="sxs-lookup"><span data-stu-id="4947f-134">Copy the `yelp_labelled.txt` file into the *Data* directory you created.</span></span>

3. <span data-ttu-id="4947f-135">在“解决方案资源管理器”中，右键单击 `yelp_labeled.txt` 文件并选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="4947f-135">In Solution Explorer, right-click the `yelp_labeled.txt` file and select **Properties**.</span></span> <span data-ttu-id="4947f-136">在“高级”下，将“复制到输出目录”的值更改为“如果较新则复制”。</span><span class="sxs-lookup"><span data-stu-id="4947f-136">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="4947f-137">创建类和定义路径</span><span class="sxs-lookup"><span data-stu-id="4947f-137">Create classes and define paths</span></span>

1. <span data-ttu-id="4947f-138">将以下附加的 `using` 语句添加到“Program.cs”文件顶部：</span><span class="sxs-lookup"><span data-stu-id="4947f-138">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

    [!code-csharp[AddUsings](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddUsings "Add necessary usings")]

2. <span data-ttu-id="4947f-139">创建两个全局字段来存储最近下载的数据集文件路径和已保存的模型文件路径：</span><span class="sxs-lookup"><span data-stu-id="4947f-139">Create two global fields to hold the recently downloaded dataset file path and the saved model file path:</span></span>

    * <span data-ttu-id="4947f-140">`_dataPath` 具有用于定型模型的数据集路径。</span><span class="sxs-lookup"><span data-stu-id="4947f-140">`_dataPath` has the path to the dataset used to train the model.</span></span>
    * <span data-ttu-id="4947f-141">`_modelPath` 具有在其中保存定型模型的路径。</span><span class="sxs-lookup"><span data-stu-id="4947f-141">`_modelPath` has the path where the trained model is saved.</span></span>

3. <span data-ttu-id="4947f-142">将以下代码添加到 `Main` 方法正上方的行中，以指定路径：</span><span class="sxs-lookup"><span data-stu-id="4947f-142">Add the following code to the line right above the `Main` method to specify the paths:</span></span>

    [!code-csharp[Declare global variables](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DeclareGlobalVariables "Declare global variables")]

4. <span data-ttu-id="4947f-143">接下来，为输入数据和预测结果创建类。</span><span class="sxs-lookup"><span data-stu-id="4947f-143">Next, create classes for your input data and predictions.</span></span> <span data-ttu-id="4947f-144">向项目添加一个新类：</span><span class="sxs-lookup"><span data-stu-id="4947f-144">Add a new class to your project:</span></span>

    - <span data-ttu-id="4947f-145">在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新项”。</span><span class="sxs-lookup"><span data-stu-id="4947f-145">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

    - <span data-ttu-id="4947f-146">在“添加新项”对话框中，选择“类”并将“名称”字段更改为“SentimentData.cs”。</span><span class="sxs-lookup"><span data-stu-id="4947f-146">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="4947f-147">然后，选择“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="4947f-147">Then, select the **Add** button.</span></span>

5. <span data-ttu-id="4947f-148">“SentimentData.cs”文件随即在代码编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="4947f-148">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="4947f-149">将下面的 `using` 语句添加到 SentimentData.cs 的顶部：</span><span class="sxs-lookup"><span data-stu-id="4947f-149">Add the following `using` statement to the top of *SentimentData.cs*:</span></span>

    [!code-csharp[AddUsings](~/samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#AddUsings "Add necessary usings")]

6. <span data-ttu-id="4947f-150">删除现有类定义并向“SentimentData.cs”文件添加以下代码，其中有两个类 `SentimentData` 和 `SentimentPrediction`：</span><span class="sxs-lookup"><span data-stu-id="4947f-150">Remove the existing class definition and add the following code, which has two classes `SentimentData` and `SentimentPrediction`, to the *SentimentData.cs* file:</span></span>

    [!code-csharp[DeclareTypes](~/samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#DeclareTypes "Declare data record types")]

### <a name="how-the-data-was-prepared"></a><span data-ttu-id="4947f-151">如何准备数据</span><span class="sxs-lookup"><span data-stu-id="4947f-151">How the data was prepared</span></span>
<span data-ttu-id="4947f-152">输入数据集类 `SentimentData` 拥有一个用于用户评论 (`SentimentText`) 的 `string`，以及一个用于情绪的 `bool` (`Sentiment`)，值为 1（正面）或 0（负面）。</span><span class="sxs-lookup"><span data-stu-id="4947f-152">The input dataset class, `SentimentData`, has a `string` for user comments (`SentimentText`) and a `bool` (`Sentiment`) value of either 1 (positive) or 0 (negative) for sentiment.</span></span> <span data-ttu-id="4947f-153">这两个字段都附加了 [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) 特性，其描述了每个字段的数据文件顺序。</span><span class="sxs-lookup"><span data-stu-id="4947f-153">Both fields have [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) attributes attached to them, which describes the data file order of each field.</span></span>  <span data-ttu-id="4947f-154">此外，`Sentiment` 属性具有 [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A) 特性，以将其指定为 `Label` 字段。</span><span class="sxs-lookup"><span data-stu-id="4947f-154">In addition, the `Sentiment` property has a [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A) attribute to designate it as the `Label` field.</span></span> <span data-ttu-id="4947f-155">下面的示例文件没有标题行，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4947f-155">The following example file doesn't have a header row, and looks like this:</span></span>

|<span data-ttu-id="4947f-156">情绪文本</span><span class="sxs-lookup"><span data-stu-id="4947f-156">SentimentText</span></span>                         |<span data-ttu-id="4947f-157">情绪（标签）</span><span class="sxs-lookup"><span data-stu-id="4947f-157">Sentiment (Label)</span></span> |
|--------------------------------------|----------|
|<span data-ttu-id="4947f-158">女服务员的服务速度有点慢。</span><span class="sxs-lookup"><span data-stu-id="4947f-158">Waitress was a little slow in service.</span></span>|    <span data-ttu-id="4947f-159">0</span><span class="sxs-lookup"><span data-stu-id="4947f-159">0</span></span>     |
|<span data-ttu-id="4947f-160">酥皮不行。</span><span class="sxs-lookup"><span data-stu-id="4947f-160">Crust is not good.</span></span>                    |    <span data-ttu-id="4947f-161">0</span><span class="sxs-lookup"><span data-stu-id="4947f-161">0</span></span>     |
|<span data-ttu-id="4947f-162">哇...喜欢这个地方。</span><span class="sxs-lookup"><span data-stu-id="4947f-162">Wow... Loved this place.</span></span>              |    <span data-ttu-id="4947f-163">1</span><span class="sxs-lookup"><span data-stu-id="4947f-163">1</span></span>     |
|<span data-ttu-id="4947f-164">服务很及时。</span><span class="sxs-lookup"><span data-stu-id="4947f-164">Service was very prompt.</span></span>              |    <span data-ttu-id="4947f-165">1</span><span class="sxs-lookup"><span data-stu-id="4947f-165">1</span></span>     |

<span data-ttu-id="4947f-166">`SentimentPrediction` 是在训练模型后使用的预测类。</span><span class="sxs-lookup"><span data-stu-id="4947f-166">`SentimentPrediction` is the prediction class used after the model training.</span></span> <span data-ttu-id="4947f-167">它继承自 `SentimentData`，用于显示带预测的 `SentimentText`。</span><span class="sxs-lookup"><span data-stu-id="4947f-167">It inherits from `SentimentData` for displaying the `SentimentText` with the predictions.</span></span> <span data-ttu-id="4947f-168">`SentimentPrediction` 拥有一个布尔值 (`Sentiment`) 和一个 `PredictedLabel` `ColumnName` 特性。</span><span class="sxs-lookup"><span data-stu-id="4947f-168">`SentimentPrediction` has a single boolean (`Sentiment`) and a `PredictedLabel` `ColumnName` attribute.</span></span> <span data-ttu-id="4947f-169">`Label` 用于创建和训练模型，并且与拆分测试数据集结合使用来评估模型。</span><span class="sxs-lookup"><span data-stu-id="4947f-169">The `Label` is used to create and train the model, and it's also used with the split out test dataset to evaluate the model.</span></span> <span data-ttu-id="4947f-170">`PredictedLabel` 在预测和评估过程中使用。</span><span class="sxs-lookup"><span data-stu-id="4947f-170">The `PredictedLabel` is used during prediction and evaluation.</span></span> <span data-ttu-id="4947f-171">对于评估，将使用训练数据、预测值和模型。</span><span class="sxs-lookup"><span data-stu-id="4947f-171">For evaluation, training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="4947f-172">[MLContext 类](xref:Microsoft.ML.MLContext)是所有 ML.NET 操作的起点。</span><span class="sxs-lookup"><span data-stu-id="4947f-172">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations.</span></span> <span data-ttu-id="4947f-173">初始化 `mlContext` 会创建一个新的 ML.NET 环境，可在模型创建工作流对象之间共享该环境。</span><span class="sxs-lookup"><span data-stu-id="4947f-173">Initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="4947f-174">从概念上讲，它与实体框架中的 `DBContext` 类似。</span><span class="sxs-lookup"><span data-stu-id="4947f-174">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="4947f-175">加载数据</span><span class="sxs-lookup"><span data-stu-id="4947f-175">Load the data</span></span>
<span data-ttu-id="4947f-176">ML.NET 中的数据表示为 [IDataView 类](xref:Microsoft.ML.IDataView)。</span><span class="sxs-lookup"><span data-stu-id="4947f-176">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="4947f-177">`IDataView` 是用于描述表格数据（数字和文本）的一种灵活且有效的方法。</span><span class="sxs-lookup"><span data-stu-id="4947f-177">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="4947f-178">可从文本文件或实时（例如，SQL 数据库或日志文件）将数据加载到 `IDataView` 对象。</span><span class="sxs-lookup"><span data-stu-id="4947f-178">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span>

<span data-ttu-id="4947f-179">准备应用，然后加载数据：</span><span class="sxs-lookup"><span data-stu-id="4947f-179">You prepare the app, and then load data:</span></span>

1. <span data-ttu-id="4947f-180">使用以下代码替换 `Main` 方法中的 `Console.WriteLine("Hello World!")` 行，以声明和初始化 mlContext 变量：</span><span class="sxs-lookup"><span data-stu-id="4947f-180">Replace the `Console.WriteLine("Hello World!")` line in the `Main` method with the following code to declare and initialize the mlContext variable:</span></span>

    [!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateMLContext "Create the ML Context")]

2. <span data-ttu-id="4947f-181">将以下代码作为下一行代码添加到 `Main()` 方法中：</span><span class="sxs-lookup"><span data-stu-id="4947f-181">Add the following as the next line of code in the `Main()` method:</span></span>

    [!code-csharp[CallLoadData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallLoadData)]

3. <span data-ttu-id="4947f-182">使用下面的代码紧随 `Main()` 方法后创建 `LoadData()` 方法：</span><span class="sxs-lookup"><span data-stu-id="4947f-182">Create the `LoadData()` method, just after the `Main()` method, using the following code:</span></span>

    ```csharp
    public static TrainTestData LoadData(MLContext mlContext)
    {

    }
    ```

    <span data-ttu-id="4947f-183">`LoadData()` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="4947f-183">The `LoadData()` method executes the following tasks:</span></span>

    * <span data-ttu-id="4947f-184">加载数据。</span><span class="sxs-lookup"><span data-stu-id="4947f-184">Loads the data.</span></span>
    * <span data-ttu-id="4947f-185">将加载的数据集拆分为训练数据集和测试数据集。</span><span class="sxs-lookup"><span data-stu-id="4947f-185">Splits the loaded dataset into train and test datasets.</span></span>
    * <span data-ttu-id="4947f-186">返回拆分的训练数据集和测试数据集。</span><span class="sxs-lookup"><span data-stu-id="4947f-186">Returns the split train and test datasets.</span></span>

4. <span data-ttu-id="4947f-187">将以下代码添加为 `LoadData()` 方法的首行：</span><span class="sxs-lookup"><span data-stu-id="4947f-187">Add the following code as the first line of the `LoadData()` method:</span></span>

    [!code-csharp[LoadData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#LoadData "loading dataset")]

    <span data-ttu-id="4947f-188">[LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) 用于定义数据架构并读取文件。</span><span class="sxs-lookup"><span data-stu-id="4947f-188">The [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) defines the data schema and reads in the file.</span></span> <span data-ttu-id="4947f-189">它使用数据路径变量并返回 `IDataView`。</span><span class="sxs-lookup"><span data-stu-id="4947f-189">It takes in the data path variables and returns an `IDataView`.</span></span>

### <a name="split-the-dataset-for-model-training-and-testing"></a><span data-ttu-id="4947f-190">拆分数据集以进行模型训练和测试</span><span class="sxs-lookup"><span data-stu-id="4947f-190">Split the dataset for model training and testing</span></span>

<span data-ttu-id="4947f-191">准备模型时，使用部分数据集来训练它，并使用部分数据集来测试模型的准确性。</span><span class="sxs-lookup"><span data-stu-id="4947f-191">When preparing a model, you use part of the dataset to train it and part of the dataset to test the model's accuracy.</span></span>

1. <span data-ttu-id="4947f-192">要将加载的数据拆分为所需的数据集，请添加以下代码作为 `LoadData()` 方法中的下一行：</span><span class="sxs-lookup"><span data-stu-id="4947f-192">To split the loaded data into the needed datasets, add the following code as the next line in the `LoadData()` method:</span></span>

    [!code-csharp[SplitData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#SplitData "Split the Data")]

    <span data-ttu-id="4947f-193">上述代码使用 [TrainTestSplit()](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit%2A) 方法将加载的数据集拆分为训练数据集和测试数据集，并在 [TrainTestData](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData) 类中返回它们。</span><span class="sxs-lookup"><span data-stu-id="4947f-193">The previous code uses the [TrainTestSplit()](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit%2A) method to split the loaded dataset into train and test datasets and return them in the [TrainTestData](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData) class.</span></span> <span data-ttu-id="4947f-194">使用 `testFraction` 参数指定数据的测试集百分比。</span><span class="sxs-lookup"><span data-stu-id="4947f-194">Specify the test set percentage of data with the `testFraction`parameter.</span></span> <span data-ttu-id="4947f-195">默认值为 10%，在本例中使用 20%，以评估更多数据。</span><span class="sxs-lookup"><span data-stu-id="4947f-195">The default is 10%, in this case you use 20% to evaluate more data.</span></span>

2. <span data-ttu-id="4947f-196">在 `LoadData()` 方法末尾返回 `splitDataView`：</span><span class="sxs-lookup"><span data-stu-id="4947f-196">Return the `splitDataView` at the end of the `LoadData()` method:</span></span>

    [!code-csharp[ReturnSplitData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#ReturnSplitData)]

## <a name="build-and-train-the-model"></a><span data-ttu-id="4947f-197">生成和定型模型</span><span class="sxs-lookup"><span data-stu-id="4947f-197">Build and train the model</span></span>

1. <span data-ttu-id="4947f-198">将以下调用添加到 `BuildAndTrainModel` 方法作为 `Main()` 方法的下一行代码：</span><span class="sxs-lookup"><span data-stu-id="4947f-198">Add the following call to the `BuildAndTrainModel`method as the next line of code in the `Main()` method:</span></span>

    [!code-csharp[CallBuildAndTrainModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallBuildAndTrainModel)]

    <span data-ttu-id="4947f-199">`BuildAndTrainModel()` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="4947f-199">The `BuildAndTrainModel()` method executes the following tasks:</span></span>

    * <span data-ttu-id="4947f-200">提取并转换数据。</span><span class="sxs-lookup"><span data-stu-id="4947f-200">Extracts and transforms the data.</span></span>
    * <span data-ttu-id="4947f-201">定型模型。</span><span class="sxs-lookup"><span data-stu-id="4947f-201">Trains the model.</span></span>
    * <span data-ttu-id="4947f-202">根据测试数据预测情绪。</span><span class="sxs-lookup"><span data-stu-id="4947f-202">Predicts sentiment based on test data.</span></span>
    * <span data-ttu-id="4947f-203">返回模型。</span><span class="sxs-lookup"><span data-stu-id="4947f-203">Returns the model.</span></span>

2. <span data-ttu-id="4947f-204">使用下面的代码紧随 `Main()` 方法后创建 `BuildAndTrainModel()` 方法：</span><span class="sxs-lookup"><span data-stu-id="4947f-204">Create the `BuildAndTrainModel()` method, just after the `Main()` method, using the following code:</span></span>

    ```csharp
    public static ITransformer BuildAndTrainModel(MLContext mlContext, IDataView splitTrainSet)
    {

    }
    ```

### <a name="extract-and-transform-the-data"></a><span data-ttu-id="4947f-205">提取和转换数据</span><span class="sxs-lookup"><span data-stu-id="4947f-205">Extract and transform the data</span></span>

1. <span data-ttu-id="4947f-206">将 `FeaturizeText` 作为下一行代码调用：</span><span class="sxs-lookup"><span data-stu-id="4947f-206">Call `FeaturizeText` as the next line of code:</span></span>

    [!code-csharp[FeaturizeText](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#FeaturizeText "Featurize the text")]

    <span data-ttu-id="4947f-207">上述代码中的 `FeaturizeText()` 方法将文本列 (`SentimentText`) 转换为机器学习算法使用的数字键类型的 `Features` 列，并将其作为新的数据集列添加：</span><span class="sxs-lookup"><span data-stu-id="4947f-207">The `FeaturizeText()` method in the previous code converts the text column (`SentimentText`) into a numeric key type `Features` column used by the machine learning algorithm and adds it as a new dataset column:</span></span>

    |<span data-ttu-id="4947f-208">情绪文本</span><span class="sxs-lookup"><span data-stu-id="4947f-208">SentimentText</span></span>                         |<span data-ttu-id="4947f-209">情绪</span><span class="sxs-lookup"><span data-stu-id="4947f-209">Sentiment</span></span> |<span data-ttu-id="4947f-210">功能</span><span class="sxs-lookup"><span data-stu-id="4947f-210">Features</span></span>              |
    |--------------------------------------|----------|----------------------|
    |<span data-ttu-id="4947f-211">女服务员的服务速度有点慢。</span><span class="sxs-lookup"><span data-stu-id="4947f-211">Waitress was a little slow in service.</span></span>|    <span data-ttu-id="4947f-212">0</span><span class="sxs-lookup"><span data-stu-id="4947f-212">0</span></span>     |<span data-ttu-id="4947f-213">[0.76, 0.65, 0.44, …]</span><span class="sxs-lookup"><span data-stu-id="4947f-213">[0.76, 0.65, 0.44, …]</span></span> |
    |<span data-ttu-id="4947f-214">酥皮不行。</span><span class="sxs-lookup"><span data-stu-id="4947f-214">Crust is not good.</span></span>                    |    <span data-ttu-id="4947f-215">0</span><span class="sxs-lookup"><span data-stu-id="4947f-215">0</span></span>     |<span data-ttu-id="4947f-216">[0.98, 0.43, 0.54, …]</span><span class="sxs-lookup"><span data-stu-id="4947f-216">[0.98, 0.43, 0.54, …]</span></span> |
    |<span data-ttu-id="4947f-217">哇...喜欢这个地方。</span><span class="sxs-lookup"><span data-stu-id="4947f-217">Wow... Loved this place.</span></span>              |    <span data-ttu-id="4947f-218">1</span><span class="sxs-lookup"><span data-stu-id="4947f-218">1</span></span>     |<span data-ttu-id="4947f-219">[0.35, 0.73, 0.46, …]</span><span class="sxs-lookup"><span data-stu-id="4947f-219">[0.35, 0.73, 0.46, …]</span></span> |
    |<span data-ttu-id="4947f-220">服务很及时。</span><span class="sxs-lookup"><span data-stu-id="4947f-220">Service was very prompt.</span></span>              |    <span data-ttu-id="4947f-221">1</span><span class="sxs-lookup"><span data-stu-id="4947f-221">1</span></span>     |<span data-ttu-id="4947f-222">[0.39, 0, 0.75, …]</span><span class="sxs-lookup"><span data-stu-id="4947f-222">[0.39, 0, 0.75, …]</span></span>    |

### <a name="add-a-learning-algorithm"></a><span data-ttu-id="4947f-223">添加学习算法</span><span class="sxs-lookup"><span data-stu-id="4947f-223">Add a learning algorithm</span></span>

<span data-ttu-id="4947f-224">此应用使用对数据项或数据行进行分类的分类算法。</span><span class="sxs-lookup"><span data-stu-id="4947f-224">This app uses a classification algorithm that categorizes items or rows of data.</span></span> <span data-ttu-id="4947f-225">应用将网站评论分类为正面评论或负面评论，因此，请使用二元分类任务。</span><span class="sxs-lookup"><span data-stu-id="4947f-225">The app categorizes website comments as either positive or negative, so use the binary classification task.</span></span>

<span data-ttu-id="4947f-226">将机器学习任务追加到数据转换定义中，方法是在 `BuildAndTrainModel()` 中添加以下代码作为下一行代码：</span><span class="sxs-lookup"><span data-stu-id="4947f-226">Append the machine learning task to the data transformation definitions by adding the following as the next line of code in `BuildAndTrainModel()`:</span></span>

[!code-csharp[SdcaLogisticRegressionBinaryTrainer](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddTrainer "Add a SdcaLogisticRegressionBinaryTrainer")]

<span data-ttu-id="4947f-227">[SdcaLogisticRegressionBinaryTrainer](xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer) 是你的分类训练算法。</span><span class="sxs-lookup"><span data-stu-id="4947f-227">The [SdcaLogisticRegressionBinaryTrainer](xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer) is your classification training algorithm.</span></span> <span data-ttu-id="4947f-228">此算法会追加到 `estimator` 并接受特征化的 `SentimentText` (`Features`) 和 `Label` 输入参数，以便从历史数据中学习。</span><span class="sxs-lookup"><span data-stu-id="4947f-228">This is appended to the `estimator` and accepts the featurized `SentimentText` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span>

### <a name="train-the-model"></a><span data-ttu-id="4947f-229">定型模型</span><span class="sxs-lookup"><span data-stu-id="4947f-229">Train the model</span></span>

<span data-ttu-id="4947f-230">在 `BuildAndTrainModel()` 方法中添加以下代码作为下一代码行，使模型适应 `splitTrainSet` 数据，并返回经过训练的模型：</span><span class="sxs-lookup"><span data-stu-id="4947f-230">Fit the model to the `splitTrainSet` data and return the trained model by adding the following as the next line of code in the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[TrainModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#TrainModel "Train the model")]

<span data-ttu-id="4947f-231">[Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) 方法通过转换数据集并应用训练来训练模型。</span><span class="sxs-lookup"><span data-stu-id="4947f-231">The [Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) method trains your model by transforming the dataset and applying the training.</span></span>

### <a name="return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="4947f-232">返回定型模型以用于评估</span><span class="sxs-lookup"><span data-stu-id="4947f-232">Return the model trained to use for evaluation</span></span>

 <span data-ttu-id="4947f-233">在 `BuildAndTrainModel()` 方法末尾返回模型：</span><span class="sxs-lookup"><span data-stu-id="4947f-233">Return the model at the end of the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[ReturnModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#ReturnModel "Return the model")]

## <a name="evaluate-the-model"></a><span data-ttu-id="4947f-234">评估模型</span><span class="sxs-lookup"><span data-stu-id="4947f-234">Evaluate the model</span></span>

<span data-ttu-id="4947f-235">训练模型后，使用测试数据验证模型的性能。</span><span class="sxs-lookup"><span data-stu-id="4947f-235">After your model is trained, use your test data validate the model's performance.</span></span>

1. <span data-ttu-id="4947f-236">使用以下代码紧跟 `BuildAndTrainModel()` 之后创建 `Evaluate()` 方法：</span><span class="sxs-lookup"><span data-stu-id="4947f-236">Create the `Evaluate()` method, just after `BuildAndTrainModel()`, with the following code:</span></span>

    ```csharp
    public static void Evaluate(MLContext mlContext, ITransformer model, IDataView splitTestSet)
    {

    }
    ```

    <span data-ttu-id="4947f-237">`Evaluate()` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="4947f-237">The `Evaluate()` method executes the following tasks:</span></span>

    * <span data-ttu-id="4947f-238">加载测试数据集。</span><span class="sxs-lookup"><span data-stu-id="4947f-238">Loads the test dataset.</span></span>
    * <span data-ttu-id="4947f-239">创建 BinaryClassification 计算器。</span><span class="sxs-lookup"><span data-stu-id="4947f-239">Creates the BinaryClassification evaluator.</span></span>
    * <span data-ttu-id="4947f-240">评估模型并创建指标。</span><span class="sxs-lookup"><span data-stu-id="4947f-240">Evaluates the model and creates metrics.</span></span>
    * <span data-ttu-id="4947f-241">显示指标。</span><span class="sxs-lookup"><span data-stu-id="4947f-241">Displays the metrics.</span></span>

2. <span data-ttu-id="4947f-242">使用下面的代码，在 `BuildAndTrainModel()` 方法调用的正下方，从 `Main()` 方法中添加对新方法的调用：</span><span class="sxs-lookup"><span data-stu-id="4947f-242">Add a call to the new method from the `Main()` method, right under the `BuildAndTrainModel()` method call, using the following code:</span></span>

    [!code-csharp[CallEvaluate](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallEvaluate "Call the Evaluate method")]

3. <span data-ttu-id="4947f-243">将以下代码添加到 `Evaluate()` 以转换 `splitTestSet` 数据：</span><span class="sxs-lookup"><span data-stu-id="4947f-243">Transform the `splitTestSet` data by adding the following code to `Evaluate()`:</span></span>

    [!code-csharp[PredictWithTransformer](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#TransformData "Predict using the Transformer")]

    <span data-ttu-id="4947f-244">之前的代码使用 [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) 方法对测试数据集提供的多个输入行进行预测。</span><span class="sxs-lookup"><span data-stu-id="4947f-244">The previous code uses the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method to make predictions for multiple provided input rows of a test dataset.</span></span>

4. <span data-ttu-id="4947f-245">通过在 `Evaluate()` 方法中添加以下代码作为下一代码行来评估模型：</span><span class="sxs-lookup"><span data-stu-id="4947f-245">Evaluate the model by adding the following as the next line of code in the `Evaluate()` method:</span></span>

    [!code-csharp[ComputeMetrics](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Evaluate "Compute Metrics")]

<span data-ttu-id="4947f-246">获得预测集 (`predictions`) 后，[Evaluate()](xref:Microsoft.ML.BinaryClassificationCatalog.Evaluate%2A) 方法会对模型进行评估，其会将预测值与测试数据集中的实际 `Labels` 进行比较，并返回有关模型执行情况的 [CalibratedBinaryClassificationMetrics](xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics) 对象。</span><span class="sxs-lookup"><span data-stu-id="4947f-246">Once you have the prediction set (`predictions`), the [Evaluate()](xref:Microsoft.ML.BinaryClassificationCatalog.Evaluate%2A) method assesses the model, which compares the predicted values with the actual `Labels` in the test dataset and returns a [CalibratedBinaryClassificationMetrics](xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics) object on how the model is performing.</span></span>

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="4947f-247">显示用于模型验证的指标</span><span class="sxs-lookup"><span data-stu-id="4947f-247">Displaying the metrics for model validation</span></span>

<span data-ttu-id="4947f-248">使用以下代码显示指标：</span><span class="sxs-lookup"><span data-stu-id="4947f-248">Use the following code to display the metrics:</span></span>

[!code-csharp[DisplayMetrics](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DisplayMetrics "Display selected metrics")]

* <span data-ttu-id="4947f-249">`Accuracy` 指标可获取模型的准确性，即测试集中正确预测所占的比例。</span><span class="sxs-lookup"><span data-stu-id="4947f-249">The `Accuracy` metric gets the accuracy of a model, which is the proportion of correct predictions in the test set.</span></span>

* <span data-ttu-id="4947f-250">`AreaUnderRocCurve` 指标指示模型对正面类和负面类进行正确分类的置信度。</span><span class="sxs-lookup"><span data-stu-id="4947f-250">The `AreaUnderRocCurve` metric indicates how confident the model is correctly classifying the positive and negative classes.</span></span> <span data-ttu-id="4947f-251">应该使 `AreaUnderRocCurve` 尽可能接近 1。</span><span class="sxs-lookup"><span data-stu-id="4947f-251">You want the `AreaUnderRocCurve` to be as close to one as possible.</span></span>

* <span data-ttu-id="4947f-252">`F1Score` 指标可获取模型的 F1 分数，该分数是[查准率](../resources/glossary.md#precision)和[查全率](../resources/glossary.md#recall)之间的平衡关系的度量值。</span><span class="sxs-lookup"><span data-stu-id="4947f-252">The `F1Score` metric gets the model's F1 score, which is a measure of balance between [precision](../resources/glossary.md#precision) and [recall](../resources/glossary.md#recall).</span></span>  <span data-ttu-id="4947f-253">应该使 `F1Score` 尽可能接近 1。</span><span class="sxs-lookup"><span data-stu-id="4947f-253">You want the `F1Score` to be as close to one as possible.</span></span>

### <a name="predict-the-test-data-outcome"></a><span data-ttu-id="4947f-254">预测测试数据结果</span><span class="sxs-lookup"><span data-stu-id="4947f-254">Predict the test data outcome</span></span>

1. <span data-ttu-id="4947f-255">使用下面的代码紧随 `Evaluate()` 方法后创建 `UseModelWithSingleItem()` 方法：</span><span class="sxs-lookup"><span data-stu-id="4947f-255">Create the `UseModelWithSingleItem()` method, just after the `Evaluate()` method, using the following code:</span></span>

    ```csharp
    private static void UseModelWithSingleItem(MLContext mlContext, ITransformer model)
    {

    }
    ```

    <span data-ttu-id="4947f-256">`UseModelWithSingleItem()` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="4947f-256">The `UseModelWithSingleItem()` method executes the following tasks:</span></span>

    * <span data-ttu-id="4947f-257">创建测试数据的单个注释。</span><span class="sxs-lookup"><span data-stu-id="4947f-257">Creates a single comment of test data.</span></span>
    * <span data-ttu-id="4947f-258">根据测试数据预测情绪。</span><span class="sxs-lookup"><span data-stu-id="4947f-258">Predicts sentiment based on test data.</span></span>
    * <span data-ttu-id="4947f-259">结合测试数据和预测进行报告。</span><span class="sxs-lookup"><span data-stu-id="4947f-259">Combines test data and predictions for reporting.</span></span>
    * <span data-ttu-id="4947f-260">显示预测结果。</span><span class="sxs-lookup"><span data-stu-id="4947f-260">Displays the predicted results.</span></span>

2. <span data-ttu-id="4947f-261">使用下面的代码，在 `Evaluate()` 方法调用的正下方，从 `Main()` 方法中添加对新方法的调用：</span><span class="sxs-lookup"><span data-stu-id="4947f-261">Add a call to the new method from the `Main()` method, right under the `Evaluate()` method call, using the following code:</span></span>

    [!code-csharp[CallUseModelWithSingleItem](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallUseModelWithSingleItem "Call the UseModelWithSingleItem method")]

3. <span data-ttu-id="4947f-262">添加以下代码，以便作为 `Predict()` 方法中的第一行进行创建：</span><span class="sxs-lookup"><span data-stu-id="4947f-262">Add the following code to create as the first line in the `Predict()` Method:</span></span>

    [!code-csharp[CreatePredictionEngine](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreatePredictionEngine1 "Create the PredictionEngine")]

    <span data-ttu-id="4947f-263">[PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) 是一个简便 API，可用于传入单个数据实例，然后对其执行预测。</span><span class="sxs-lookup"><span data-stu-id="4947f-263">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to pass in and then perform a prediction on a single instance of data.</span></span>

4. <span data-ttu-id="4947f-264">通过创建一个 `SentimentData` 实例，在 `Predict()` 方法中添加一个注释来测试定型模型的预测：</span><span class="sxs-lookup"><span data-stu-id="4947f-264">Add a comment to test the trained model's prediction in the `Predict()` method by creating an instance of `SentimentData`:</span></span>

    [!code-csharp[PredictionData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateTestIssue1 "Create test data for single prediction")]

5. <span data-ttu-id="4947f-265">通过在 `UseModelWithSingleItem()` 方法中将以下代码作为下一行代码添加，将测试评论数据传递到 `Prediction Engine`：</span><span class="sxs-lookup"><span data-stu-id="4947f-265">Pass the test comment data to the `Prediction Engine` by adding the following as the next lines of code in the `UseModelWithSingleItem()` method:</span></span>

    [!code-csharp[Predict](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Predict "Create a prediction of sentiment")]

    <span data-ttu-id="4947f-266">[Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) 函数对单行数据进行预测。</span><span class="sxs-lookup"><span data-stu-id="4947f-266">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single row of data.</span></span>

6. <span data-ttu-id="4947f-267">使用以下代码显示 `SentimentText` 和相应的情绪预测：</span><span class="sxs-lookup"><span data-stu-id="4947f-267">Display `SentimentText` and corresponding sentiment prediction using the following code:</span></span>

    [!code-csharp[OutputPrediction](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#OutputPrediction "Display prediction output")]

## <a name="use-the-model-for-prediction"></a><span data-ttu-id="4947f-268">使用模型进行预测</span><span class="sxs-lookup"><span data-stu-id="4947f-268">Use the model for prediction</span></span>

### <a name="deploy-and-predict-batch-items"></a><span data-ttu-id="4947f-269">部署和预测批项目</span><span class="sxs-lookup"><span data-stu-id="4947f-269">Deploy and predict batch items</span></span>

1. <span data-ttu-id="4947f-270">使用下面的代码紧随 `UseModelWithSingleItem()` 方法后创建 `UseModelWithBatchItems()` 方法：</span><span class="sxs-lookup"><span data-stu-id="4947f-270">Create the `UseModelWithBatchItems()` method, just after the `UseModelWithSingleItem()` method, using the following code:</span></span>

    ```csharp
    public static void UseModelWithBatchItems(MLContext mlContext)
    {

    }
    ```

    <span data-ttu-id="4947f-271">`UseModelWithBatchItems()` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="4947f-271">The `UseModelWithBatchItems()` method executes the following tasks:</span></span>

    * <span data-ttu-id="4947f-272">创建批处理测试数据。</span><span class="sxs-lookup"><span data-stu-id="4947f-272">Creates batch test data.</span></span>
    * <span data-ttu-id="4947f-273">根据测试数据预测情绪。</span><span class="sxs-lookup"><span data-stu-id="4947f-273">Predicts sentiment based on test data.</span></span>
    * <span data-ttu-id="4947f-274">结合测试数据和预测进行报告。</span><span class="sxs-lookup"><span data-stu-id="4947f-274">Combines test data and predictions for reporting.</span></span>
    * <span data-ttu-id="4947f-275">显示预测结果。</span><span class="sxs-lookup"><span data-stu-id="4947f-275">Displays the predicted results.</span></span>

2. <span data-ttu-id="4947f-276">使用下面的代码，在 `UseModelWithSingleItem()` 方法调用的正下方，从 `Main` 方法中添加对新方法的调用：</span><span class="sxs-lookup"><span data-stu-id="4947f-276">Add a call to the new method from the `Main` method, right under the `UseModelWithSingleItem()` method call, using the following code:</span></span>

    [!code-csharp[CallPredictModelBatchItems](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallUseModelWithBatchItems "Call the CallUseModelWithBatchItems method")]

3. <span data-ttu-id="4947f-277">添加一些评论，以测试 `UseModelWithBatchItems()` 方法中的定型模型预测：</span><span class="sxs-lookup"><span data-stu-id="4947f-277">Add some comments to test the trained model's predictions in the `UseModelWithBatchItems()` method:</span></span>

    [!code-csharp[PredictionData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateTestIssues "Create test data for predictions")]

### <a name="predict-comment-sentiment"></a><span data-ttu-id="4947f-278">预测评论情绪</span><span class="sxs-lookup"><span data-stu-id="4947f-278">Predict comment sentiment</span></span>

<span data-ttu-id="4947f-279">使用模型通过 [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) 方法预测评论数据情绪：</span><span class="sxs-lookup"><span data-stu-id="4947f-279">Use the model to predict the comment data sentiment using the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method:</span></span>

[!code-csharp[Predict](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Prediction "Create predictions of sentiments")]

### <a name="combine-and-display-the-predictions"></a><span data-ttu-id="4947f-280">合并并显示预测结果</span><span class="sxs-lookup"><span data-stu-id="4947f-280">Combine and display the predictions</span></span>

<span data-ttu-id="4947f-281">使用以下代码为预测创建标头：</span><span class="sxs-lookup"><span data-stu-id="4947f-281">Create a header for the predictions using the following code:</span></span>

[!code-csharp[OutputHeaders](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddInfoMessage "Display prediction outputs")]

<span data-ttu-id="4947f-282">由于 `SentimentPrediction` 继承自 `SentimentData`，`Transform()` 方法使用预测字段填充 `SentimentText`。</span><span class="sxs-lookup"><span data-stu-id="4947f-282">Because `SentimentPrediction` is inherited from `SentimentData`, the `Transform()` method populated `SentimentText` with the predicted fields.</span></span> <span data-ttu-id="4947f-283">随着 ML.NET 进程继续执行，每个组件会添加列，这让显示结果变得轻松：</span><span class="sxs-lookup"><span data-stu-id="4947f-283">As the ML.NET process processes, each component adds columns, and this makes it easy to display the results:</span></span>

[!code-csharp[DisplayPredictions](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DisplayResults "Display the predictions")]

## <a name="results"></a><span data-ttu-id="4947f-284">结果</span><span class="sxs-lookup"><span data-stu-id="4947f-284">Results</span></span>

<span data-ttu-id="4947f-285">结果应如下所示。</span><span class="sxs-lookup"><span data-stu-id="4947f-285">Your results should be similar to the following.</span></span> <span data-ttu-id="4947f-286">处理期间将显示消息。</span><span class="sxs-lookup"><span data-stu-id="4947f-286">During processing, messages are displayed.</span></span> <span data-ttu-id="4947f-287">你可能会看到警告或处理消息。</span><span class="sxs-lookup"><span data-stu-id="4947f-287">You may see warnings, or processing messages.</span></span> <span data-ttu-id="4947f-288">为清楚起见，已经从下面的结果中删除这些内容。</span><span class="sxs-lookup"><span data-stu-id="4947f-288">These have been removed from the following results for clarity.</span></span>

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

<span data-ttu-id="4947f-289">祝贺你！</span><span class="sxs-lookup"><span data-stu-id="4947f-289">Congratulations!</span></span> <span data-ttu-id="4947f-290">现在，你已成功生成用于分类和预测消息情绪的机器学习模型。</span><span class="sxs-lookup"><span data-stu-id="4947f-290">You've now successfully built a machine learning model for classifying and predicting messages sentiment.</span></span>

<span data-ttu-id="4947f-291">生成成功的模型是一个迭代过程。</span><span class="sxs-lookup"><span data-stu-id="4947f-291">Building successful models is an iterative process.</span></span> <span data-ttu-id="4947f-292">由于本教程使用小型数据集来提供快速模型训练，因此该模型的初始质量较低。</span><span class="sxs-lookup"><span data-stu-id="4947f-292">This model has initial lower quality as the tutorial uses small datasets to provide quick model training.</span></span> <span data-ttu-id="4947f-293">如果对模型质量不满意，可以通过尝试提供更大的训练数据集，或通过为每种算法选择具有不同[超参数](../resources/glossary.md##hyperparameter)的不同训练算法来改进它。</span><span class="sxs-lookup"><span data-stu-id="4947f-293">If you aren't satisfied with the model quality, you can try to improve it by providing larger training datasets or by choosing different training algorithms with different [hyper-parameters](../resources/glossary.md##hyperparameter) for each algorithm.</span></span>

<span data-ttu-id="4947f-294">可以在 [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) 存储库中找到本教程的源代码。</span><span class="sxs-lookup"><span data-stu-id="4947f-294">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4947f-295">后续步骤</span><span class="sxs-lookup"><span data-stu-id="4947f-295">Next steps</span></span>

<span data-ttu-id="4947f-296">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="4947f-296">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="4947f-297">创建控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="4947f-297">Create a console application</span></span>
> * <span data-ttu-id="4947f-298">准备数据</span><span class="sxs-lookup"><span data-stu-id="4947f-298">Prepare data</span></span>
> * <span data-ttu-id="4947f-299">加载数据</span><span class="sxs-lookup"><span data-stu-id="4947f-299">Load the data</span></span>
> * <span data-ttu-id="4947f-300">生成和定型模型</span><span class="sxs-lookup"><span data-stu-id="4947f-300">Build and train the model</span></span>
> * <span data-ttu-id="4947f-301">评估模型</span><span class="sxs-lookup"><span data-stu-id="4947f-301">Evaluate the model</span></span>
> * <span data-ttu-id="4947f-302">使用模型进行预测</span><span class="sxs-lookup"><span data-stu-id="4947f-302">Use the model to make a prediction</span></span>
> * <span data-ttu-id="4947f-303">查看结果</span><span class="sxs-lookup"><span data-stu-id="4947f-303">See the results</span></span>

<span data-ttu-id="4947f-304">进入下一教程了解详细信息</span><span class="sxs-lookup"><span data-stu-id="4947f-304">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="4947f-305">问题分类</span><span class="sxs-lookup"><span data-stu-id="4947f-305">Issue Classification</span></span>](github-issue-classification.md)

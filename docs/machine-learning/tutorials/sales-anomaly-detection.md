---
title: 在销售异常情况检测方案中使用 ML.NET
description: 了解如何在产品销售异常情况检测方案中使用 ML.NET，以了解如何针对异常峰值和更改点分析数据，从而采取适当的措施。
ms.date: 05/29/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: e092aea66ca9f439cf97c1ebee83097def0f520b
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758795"
---
# <a name="tutorial-use-mlnet-for-product-sales-anomaly-detection"></a><span data-ttu-id="1eaa8-103">教程：将 ML.NET 用于产品销售异常情况检测</span><span class="sxs-lookup"><span data-stu-id="1eaa8-103">Tutorial: Use ML.NET for product sales anomaly detection</span></span> 

<span data-ttu-id="1eaa8-104">本示例教程演示如何使用 ML.NET 检测产品销售数据中的异常情况，以便在 Visual Studio 2019 中使用 C# 通过 .NET Core 控制台应用程序采取适当的措施。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-104">This sample tutorial illustrates using ML.NET to detect anomalies in product sales data to take the appropriate action via a .NET Core console application using C# in Visual Studio 2019.</span></span> 

<span data-ttu-id="1eaa8-105">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="1eaa8-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="1eaa8-106">加载数据</span><span class="sxs-lookup"><span data-stu-id="1eaa8-106">Load the data</span></span>
> * <span data-ttu-id="1eaa8-107">训练模型用于峰值异常情况检测</span><span class="sxs-lookup"><span data-stu-id="1eaa8-107">Train the model for spike anomaly detection</span></span>
> * <span data-ttu-id="1eaa8-108">使用经过训练的模型检测峰值异常情况</span><span class="sxs-lookup"><span data-stu-id="1eaa8-108">Detect spike anomalies with the trained model</span></span>
> * <span data-ttu-id="1eaa8-109">训练模型用于更改点异常情况检测</span><span class="sxs-lookup"><span data-stu-id="1eaa8-109">Train the model for change point anomaly detection</span></span>
> * <span data-ttu-id="1eaa8-110">使用经过训练的模型检测更改点异常情况</span><span class="sxs-lookup"><span data-stu-id="1eaa8-110">Detect change point anomalies with the trained model</span></span>

<span data-ttu-id="1eaa8-111">可以在 [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection) 存储库中找到本教程的源代码。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-111">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1eaa8-112">系统必备</span><span class="sxs-lookup"><span data-stu-id="1eaa8-112">Prerequisites</span></span>

* <span data-ttu-id="1eaa8-113">安装了“.NET Core 跨平台开发”工作负载的 [Visual Studio 2017 15.6 或更高版本](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-113">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the ".NET Core cross-platform development" workload installed.</span></span>

* [<span data-ttu-id="1eaa8-114">product-sales.csv 数据集</span><span class="sxs-lookup"><span data-stu-id="1eaa8-114">The product-sales.csv dataset</span></span>](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv)

>[!NOTE]
> <span data-ttu-id="1eaa8-115">`product-sales.csv` 中的数据格式基于“Shampoo Sales Over a Three Year Period”数据集，该数据集最初来自 DataMarket，由 Rob Hyndman 创建的 Time Series Data Library (TSDL) 提供。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-115">The data format in `product-sales.csv` is based on the dataset “Shampoo Sales Over a Three Year Period” originally sourced from DataMarket and provided by Time Series Data Library (TSDL), created by Rob Hyndman.</span></span> <span data-ttu-id="1eaa8-116">“Shampoo Sales Over a Three Year Period”数据集根据 DataMarket 默认开放许可进行许可。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-116">“Shampoo Sales Over a Three Year Period” Dataset Licensed Under the DataMarket Default Open License.</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="1eaa8-117">创建控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="1eaa8-117">Create a console application</span></span>

1. <span data-ttu-id="1eaa8-118">创建名为“ProductSalesAnomalyDetection”的 **.NET Core 控制台应用程序**。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-118">Create a **.NET Core Console Application** called "ProductSalesAnomalyDetection".</span></span>

2. <span data-ttu-id="1eaa8-119">在项目中创建名为“Data”的目录，用于保存数据集文件  。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-119">Create a directory named *Data* in your project to save your data set files.</span></span>

3. <span data-ttu-id="1eaa8-120">安装“Microsoft.ML NuGet 包”  ：</span><span class="sxs-lookup"><span data-stu-id="1eaa8-120">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="1eaa8-121">在“解决方案资源管理器”中，右键单击项目，然后选择“管理 NuGet 包”  。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-121">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="1eaa8-122">选择“nuget.org”作为包源，然后选择“浏览”选项卡并搜索“Microsoft.ML”，选择列表中的“v1.0.0”包，再选择“安装”按钮    。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-122">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**, select the **v1.0.0** package in the list, and select the **Install** button.</span></span> <span data-ttu-id="1eaa8-123">选择“预览更改”  对话框上的“确定”  按钮，如果你同意所列包的许可条款，则选择“接受许可”  对话框上的“我接受”  按钮。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-123">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span> <span data-ttu-id="1eaa8-124">对 **Microsoft.ML.TimeSeries v0.12.0** 重复这些步骤。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-124">Repeat these steps for **Microsoft.ML.TimeSeries v0.12.0**.</span></span>

4. <span data-ttu-id="1eaa8-125">在 Program.cs 文件的顶部添加以下 `using` 语句  ：</span><span class="sxs-lookup"><span data-stu-id="1eaa8-125">Add the following `using` statements at the top of your *Program.cs* file:</span></span>

    [!code-csharp[AddUsings](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddUsings "Add necessary usings")]

### <a name="download-your-data"></a><span data-ttu-id="1eaa8-126">下载数据</span><span class="sxs-lookup"><span data-stu-id="1eaa8-126">Download your data</span></span>

1. <span data-ttu-id="1eaa8-127">下载数据集并将其保存到之前创建的 *Data* 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="1eaa8-127">Download the dataset and save it to the *Data* folder you previously created:</span></span>

   * <span data-ttu-id="1eaa8-128">右键单击 [*product-sales.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv) 并选择“将链接(或目标)另存为...”</span><span class="sxs-lookup"><span data-stu-id="1eaa8-128">Right click on [*product-sales.csv*](https://raw.githubusercontent.com/dotnet/machinelearning-samples/master/samples/csharp/getting-started/AnomalyDetection_Sales/SpikeDetection/Data/product-sales.csv) and select "Save Link (or Target) As..."</span></span>

     <span data-ttu-id="1eaa8-129">确保将 \*.csv 文件保存到 *Data* 文件夹，或者在将其保存到其他位置后，将 \*.csv 文件移动到 *Data* 文件夹。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-129">Make sure you either save the \*.csv file to the *Data* folder, or after you save it elsewhere, move the \*.csv file to the *Data* folder.</span></span>

2. <span data-ttu-id="1eaa8-130">在解决方案资源管理器中，右键单击 \*.csv 文件并选择“属性”  。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-130">In Solution Explorer, right-click the \*.csv file and select **Properties**.</span></span> <span data-ttu-id="1eaa8-131">在“高级”下，将“复制到输出目录”的值更改为“如果较新则复制”    。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-131">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

<span data-ttu-id="1eaa8-132">下表是来自 \*.csv 文件的数据预览：</span><span class="sxs-lookup"><span data-stu-id="1eaa8-132">The following table is a data preview from your \*.csv file:</span></span>

|<span data-ttu-id="1eaa8-133">月份</span><span class="sxs-lookup"><span data-stu-id="1eaa8-133">Month</span></span>  |<span data-ttu-id="1eaa8-134">ProductSales</span><span class="sxs-lookup"><span data-stu-id="1eaa8-134">ProductSales</span></span> |
|-------|-------------|
|<span data-ttu-id="1eaa8-135">1-Jan</span><span class="sxs-lookup"><span data-stu-id="1eaa8-135">1-Jan</span></span>  |    <span data-ttu-id="1eaa8-136">271</span><span class="sxs-lookup"><span data-stu-id="1eaa8-136">271</span></span>      |
|<span data-ttu-id="1eaa8-137">2-Jan</span><span class="sxs-lookup"><span data-stu-id="1eaa8-137">2-Jan</span></span>  |    <span data-ttu-id="1eaa8-138">150.9</span><span class="sxs-lookup"><span data-stu-id="1eaa8-138">150.9</span></span>    |
|<span data-ttu-id="1eaa8-139">.....</span><span class="sxs-lookup"><span data-stu-id="1eaa8-139">.....</span></span>  |    <span data-ttu-id="1eaa8-140">.....</span><span class="sxs-lookup"><span data-stu-id="1eaa8-140">.....</span></span>    |
|<span data-ttu-id="1eaa8-141">1-Feb</span><span class="sxs-lookup"><span data-stu-id="1eaa8-141">1-Feb</span></span>  |    <span data-ttu-id="1eaa8-142">199.3</span><span class="sxs-lookup"><span data-stu-id="1eaa8-142">199.3</span></span>    |
|<span data-ttu-id="1eaa8-143">.....</span><span class="sxs-lookup"><span data-stu-id="1eaa8-143">.....</span></span>  |    <span data-ttu-id="1eaa8-144">.....</span><span class="sxs-lookup"><span data-stu-id="1eaa8-144">.....</span></span>    |

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="1eaa8-145">创建类和定义路径</span><span class="sxs-lookup"><span data-stu-id="1eaa8-145">Create classes and define paths</span></span>

<span data-ttu-id="1eaa8-146">接下来，定义输入类数据结构。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-146">Next, define your input class data structure.</span></span>

<span data-ttu-id="1eaa8-147">向项目添加一个新类：</span><span class="sxs-lookup"><span data-stu-id="1eaa8-147">Add a new class to your project:</span></span>

1. <span data-ttu-id="1eaa8-148">在“解决方案资源管理器”中，右键单击该项目，然后选择“添加”>“新项”   。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-148">In **Solution Explorer**, right-click the project, and then select **Add > New Item**.</span></span>

2. <span data-ttu-id="1eaa8-149">在“添加新项”对话框中，选择“类”并将“名称”字段更改为“ProductSalesData.cs”     。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-149">In the **Add New Item dialog box**, select **Class** and change the **Name** field to *ProductSalesData.cs*.</span></span> <span data-ttu-id="1eaa8-150">然后，选择“添加”  按钮。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-150">Then, select the **Add** button.</span></span>

<span data-ttu-id="1eaa8-151">此时，*ProductSalesData.cs* 文件在代码编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-151">The *ProductSalesData.cs* file opens in the code editor.</span></span> <span data-ttu-id="1eaa8-152">将以下 `using` 语句添加到 *ProductSalesData.cs* 顶部：</span><span class="sxs-lookup"><span data-stu-id="1eaa8-152">Add the following `using` statement to the top of *ProductSalesData.cs*:</span></span>

```csharp
using Microsoft.ML.Data;
```

<span data-ttu-id="1eaa8-153">删除现有类定义并向 *ProductSalesData.cs* 文件添加以下代码，其中有两个类 `ProductSalesData` 和 `ProductSalesPrediction`：</span><span class="sxs-lookup"><span data-stu-id="1eaa8-153">Remove the existing class definition and add the following code, which has two classes `ProductSalesData` and `ProductSalesPrediction`, to the *ProductSalesData.cs* file:</span></span>

[!code-csharp[DeclareTypes](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/ProductSalesData.cs#DeclareTypes "Declare data record types")]

<span data-ttu-id="1eaa8-154">`ProductSalesData` 指定输入数据类。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-154">`ProductSalesData` specifies an input data class.</span></span> <span data-ttu-id="1eaa8-155">[LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) 属性指定应加载数据集中的哪些列（按列索引）。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-155">The [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) attribute specifies which columns (by column index) in the dataset should be loaded.</span></span> 

<span data-ttu-id="1eaa8-156">将以下附加的 `using` 语句添加到“Program.cs”  文件顶部：</span><span class="sxs-lookup"><span data-stu-id="1eaa8-156">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddUsings "Add necessary usings")]

<span data-ttu-id="1eaa8-157">需要创建两个全局字段来存储最近下载的数据集文件路径和已保存的模型文件路径：</span><span class="sxs-lookup"><span data-stu-id="1eaa8-157">You need to create two global fields to hold the recently downloaded dataset file path and the saved model file path:</span></span>

* <span data-ttu-id="1eaa8-158">`_dataPath` 具有用于定型模型的数据集路径。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-158">`_dataPath` has the path to the dataset used to train the model.</span></span>
* <span data-ttu-id="1eaa8-159">`_docsize` 具有数据集文件中记录的数量。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-159">`_docsize` has the number of records in dataset file.</span></span> <span data-ttu-id="1eaa8-160">可使用此数据计算 `pvalueHistoryLength`。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-160">You'll use this to calculate `pvalueHistoryLength`.</span></span>

<span data-ttu-id="1eaa8-161">将以下代码添加到 `Main` 方法上方的行中，以指定这些路径：</span><span class="sxs-lookup"><span data-stu-id="1eaa8-161">Add the following code to the line right above the `Main` method to specify those paths:</span></span>

[!code-csharp[Declare global variables](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DeclareGlobalVariables "Declare global variables")]

<span data-ttu-id="1eaa8-162">执行所有 ML.NET 操作都是从 [MLContext 类](xref:Microsoft.ML.MLContext)开始，初始化 `mlContext` 可创建一个新的 ML.NET 环境，可在模型创建工作流对象之间共享该环境。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-162">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="1eaa8-163">从概念上讲，它与实体框架中的 `DBContext` 类似。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-163">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="1eaa8-164">在 Main 中初始化变量</span><span class="sxs-lookup"><span data-stu-id="1eaa8-164">Initialize variables in Main</span></span>

<span data-ttu-id="1eaa8-165">使用以下代码替换 `Main` 方法中的 `Console.WriteLine("Hello World!")` 行，以声明和初始化 `mlContext` 变量：</span><span class="sxs-lookup"><span data-stu-id="1eaa8-165">Replace the `Console.WriteLine("Hello World!")` line in the `Main` method with the following code to declare and initialize the `mlContext` variable:</span></span>

[!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CreateMLContext "Create the ML Context")]

### <a name="load-the-data"></a><span data-ttu-id="1eaa8-166">加载数据</span><span class="sxs-lookup"><span data-stu-id="1eaa8-166">Load the data</span></span>

<span data-ttu-id="1eaa8-167">ML.NET 中的数据表示为 [IDataView 类](xref:Microsoft.ML.IDataView)。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-167">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="1eaa8-168">`IDataView` 是用于描述表格数据（数字和文本）的一种灵活且有效的方法。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-168">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="1eaa8-169">可从文本文件或实时（例如，SQL 数据库或日志文件）将数据加载到 `IDataView` 对象。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-169">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span> <span data-ttu-id="1eaa8-170">添加以下代码作为 `Main()` 方法的下一行：</span><span class="sxs-lookup"><span data-stu-id="1eaa8-170">Add the following code as the next line of the `Main()` method:</span></span>

[!code-csharp[LoadData](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#LoadData "loading dataset")]

<span data-ttu-id="1eaa8-171">[LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) 用于定义数据架构并读取文件。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-171">The [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) defines the data schema and reads in the file.</span></span> <span data-ttu-id="1eaa8-172">它使用数据路径变量并返回 `IDataView`。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-172">It takes in the data path variables and returns an `IDataView`.</span></span>

## <a name="ml-task---time-series-anomaly-detection"></a><span data-ttu-id="1eaa8-173">ML 任务 - 时序异常情况检测</span><span class="sxs-lookup"><span data-stu-id="1eaa8-173">ML task - time series anomaly detection</span></span> 

<span data-ttu-id="1eaa8-174">异常情况检测标记意外或异常事件/行为。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-174">Anomaly detection flags unexpected or unusual events or behaviors.</span></span> <span data-ttu-id="1eaa8-175">它提供寻找问题所在位置的线索，并帮助回答“这是否奇怪？”的问题。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-175">It gives clues where to look for problems and helps you answer the question "Is this weird?".</span></span>

![这是否奇怪](./media/sales-anomaly-detection/anomalydetection.png)

<span data-ttu-id="1eaa8-177">异常情况检测是检测时序数据离群值的过程；在给定的输入时序上指向“怪异”或不是预期行为的行为。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-177">Anomaly detection is the process of detecting time-series data outliers; points on a given input time-series where the behavior isn't what was expected, or "weird".</span></span>

<span data-ttu-id="1eaa8-178">这在很多方面都很有用。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-178">This can be useful in lots of ways.</span></span> <span data-ttu-id="1eaa8-179">例如：</span><span class="sxs-lookup"><span data-stu-id="1eaa8-179">For instance:</span></span>

<span data-ttu-id="1eaa8-180">如果你有一辆车，你可能想要知道：此油量计读数是否正常，或者是否存在漏油现象？</span><span class="sxs-lookup"><span data-stu-id="1eaa8-180">If you have a car, you might want to know: Is this oil gauge reading normal, or do I have a leak?</span></span>
<span data-ttu-id="1eaa8-181">如果正在监视能耗，你需要知道：是否出现了中断？</span><span class="sxs-lookup"><span data-stu-id="1eaa8-181">If you're monitoring power consumption, you’d want to know: Is there an outage?</span></span>

<span data-ttu-id="1eaa8-182">可以检测到两种类型的时序异常情况：</span><span class="sxs-lookup"><span data-stu-id="1eaa8-182">There are two types of time series anomalies that can be detected:</span></span> 

* <span data-ttu-id="1eaa8-183">**峰值**指示系统中异常行为的临时突发。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-183">**Spikes** indicate temporary bursts of anomalous behavior in the system.</span></span> 

* <span data-ttu-id="1eaa8-184">**更改点**指示系统中一段时间内持续更改的开始。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-184">**Change points** indicate the beginning of persistent changes over time in the system.</span></span> 

<span data-ttu-id="1eaa8-185">在 ML.NET 中，IID 峰值检测或 IID 更改点检测算法适用于[独立且均匀分布的数据集](https://en.wikipedia.org/wiki/Independent_and_identically_distributed_random_variables)。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-185">In ML.NET, The IID Spike Detection or IID Change point Detection algorithms are suited for [independent and identically distributed datasets](https://en.wikipedia.org/wiki/Independent_and_identically_distributed_random_variables).</span></span> 

<span data-ttu-id="1eaa8-186">将分析相同的产品销售数据来检测峰值和更改点。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-186">You'll analyze the same product sales data to detect spikes and change points.</span></span> <span data-ttu-id="1eaa8-187">峰值检测和更改点检测的模型生成和训练过程相同；主要区别在于使用的特定检测算法。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-187">The building and training model process is the same for spike detection and change point detection; the main difference is the specific detection algorithm used.</span></span>

## <a name="spike-detection"></a><span data-ttu-id="1eaa8-188">峰值检测</span><span class="sxs-lookup"><span data-stu-id="1eaa8-188">Spike detection</span></span> 

<span data-ttu-id="1eaa8-189">峰值检测旨在识别与大部分时序数据值明显不同的突然但临时的突发。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-189">The goal of spike detection is to identify sudden yet temporary bursts that significantly differ from the majority of the time series data values.</span></span> <span data-ttu-id="1eaa8-190">及时检测到这些可疑的罕见项目、事件或观测很重要，这样才能尽量减少其出现。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-190">It's important to detect these suspicious rare items, events or observations in a timely manner to be minimized.</span></span> <span data-ttu-id="1eaa8-191">以下方法可用于检测各种异常情况，例如：中断、网络攻击或病毒式 Web 内容。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-191">The following approach can be used to detect a variety of anomalies such as: outages, cyber-attacks, or viral web content.</span></span> <span data-ttu-id="1eaa8-192">下图是时序数据集中峰值的示例：</span><span class="sxs-lookup"><span data-stu-id="1eaa8-192">The following image is an example of spikes in a time series dataset:</span></span>

![SpikeDetection](./media/sales-anomaly-detection/SpikeDetection.png)

### <a name="create-the-detectspike-method"></a><span data-ttu-id="1eaa8-194">创建 DetectSpike() 方法</span><span class="sxs-lookup"><span data-stu-id="1eaa8-194">Create the DetectSpike() method</span></span>

<span data-ttu-id="1eaa8-195">将以下调用添加到 `DetectSpike()` 方法作为 `Main()` 方法的下一行代码：</span><span class="sxs-lookup"><span data-stu-id="1eaa8-195">Add the following call to the `DetectSpike()`method as the next line of code in the `Main()` method:</span></span>

[!code-csharp[CallDetectSpike](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CallDetectSpike)]

<span data-ttu-id="1eaa8-196">`DetectSpike()` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="1eaa8-196">The `DetectSpike()` method executes the following tasks:</span></span>

* <span data-ttu-id="1eaa8-197">定型模型。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-197">Trains the model.</span></span>
* <span data-ttu-id="1eaa8-198">根据历史销售数据检测峰值。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-198">Detects spikes based on on historical sales data.</span></span>
* <span data-ttu-id="1eaa8-199">显示结果。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-199">Displays the results.</span></span>

<span data-ttu-id="1eaa8-200">使用下面的代码紧随 `Main()` 方法后创建 `DetectSpike()` 方法：</span><span class="sxs-lookup"><span data-stu-id="1eaa8-200">Create the `DetectSpike()` method, just after the `Main()` method, using the following code:</span></span>

```csharp
static void DetectSpike(MLContext mlContext, int docSize, IDataView productSales)
{

}
```

<span data-ttu-id="1eaa8-201">使用 [IidSpikeEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidSpikeEstimator) 训练模型用于峰值检测。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-201">Use the [IidSpikeEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidSpikeEstimator) to train the model for spike detection.</span></span> <span data-ttu-id="1eaa8-202">使用以下代码将其添加到 `DetectChangepoint()` 方法中：</span><span class="sxs-lookup"><span data-stu-id="1eaa8-202">Add it to the `DetectChangepoint()` method with the following code:</span></span>

[!code-csharp[AddSpikeTrainer](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddSpikeTrainer)]

<span data-ttu-id="1eaa8-203">通过在 `DetectSpike()` 方法中添加以下代码作为下一代码行来使模型适应 `productSales` 数据：</span><span class="sxs-lookup"><span data-stu-id="1eaa8-203">Fit the model to the `productSales` data by adding the following as the next line of code in the `DetectSpike()` method:</span></span>

[!code-csharp[TrainModel1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TrainModel1)]

<span data-ttu-id="1eaa8-204">[Fit()](xref:Microsoft.ML.Data.TrivialEstimator%601.Fit%2A) 方法通过转换数据集并应用训练来训练模型。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-204">The [Fit()](xref:Microsoft.ML.Data.TrivialEstimator%601.Fit%2A) method trains your model by transforming the dataset and applying the training.</span></span>

<span data-ttu-id="1eaa8-205">添加以下代码行将 `productSales` 数据转换为 `DetectSpike()` 方法中的下一行：</span><span class="sxs-lookup"><span data-stu-id="1eaa8-205">Add the following line of code to transform the `productSales` data as the next line in the `DetectSpike()` method:</span></span>

[!code-csharp[TransformData1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TransformData1)]

<span data-ttu-id="1eaa8-206">之前的代码使用 [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) 方法对测试数据集提供的多个输入行进行预测。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-206">The previous code uses the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method to make predictions for multiple provided input rows of a test dataset.</span></span>

<span data-ttu-id="1eaa8-207">使用 [CreateEnumerable()](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A) 方法和以下代码将 `transformedData` 转换为强类型 `IEnumerable`，以方便显示：</span><span class="sxs-lookup"><span data-stu-id="1eaa8-207">Convert your `transformedData` into a strongly-typed `IEnumerable` for easier display using the [CreateEnumerable()](xref:Microsoft.ML.DataOperationsCatalog.CreateEnumerable%2A) method with the following code:</span></span>

[!code-csharp[CreateEnumerable1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CreateEnumerable1)]

<span data-ttu-id="1eaa8-208">使用以下 <xref:System.Console.WriteLine?displayProperty=nameWithType> 代码创建显示标头行：</span><span class="sxs-lookup"><span data-stu-id="1eaa8-208">Create a display header line using the following <xref:System.Console.WriteLine?displayProperty=nameWithType> code:</span></span>

[!code-csharp[DisplayHeader1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayHeader1)]

<span data-ttu-id="1eaa8-209">将在峰值检测结果中显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="1eaa8-209">You'll display the following information in your spike detection results:</span></span>

* <span data-ttu-id="1eaa8-210">`Alert` 指示给定数据点的峰值警报。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-210">`Alert` indicates a spike alert for a given data point.</span></span>

* <span data-ttu-id="1eaa8-211">`Score` 是数据集中给定数据点的 `ProductSales` 值。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-211">`Score` is the `ProductSales` value for a given data point in the dataset.</span></span>

* <span data-ttu-id="1eaa8-212">`P-Value`“P”代表概率，</span><span class="sxs-lookup"><span data-stu-id="1eaa8-212">`P-Value` The "P" stands for probability.</span></span> <span data-ttu-id="1eaa8-213">其指示此数据点为异常数据点的可能性。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-213">This indicates how likely this data point is an anomaly.</span></span> 

<span data-ttu-id="1eaa8-214">使用以下代码循环访问 `predictions` `IEnumerable` 并显示结果：</span><span class="sxs-lookup"><span data-stu-id="1eaa8-214">Use the following code to iterate through the `predictions` `IEnumerable` and display the results:</span></span>

[!code-csharp[DisplayResults1](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayResults1)]

## <a name="spike-detection-results"></a><span data-ttu-id="1eaa8-215">峰值检测结果</span><span class="sxs-lookup"><span data-stu-id="1eaa8-215">Spike detection results</span></span>

<span data-ttu-id="1eaa8-216">结果应如下所示。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-216">Your results should be similar to the following.</span></span> <span data-ttu-id="1eaa8-217">处理期间将显示消息。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-217">During processing, messages are displayed.</span></span> <span data-ttu-id="1eaa8-218">你可能会看到警告或处理消息。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-218">You may see warnings, or processing messages.</span></span> <span data-ttu-id="1eaa8-219">为清楚起见，已经从下面的结果中删除这些内容。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-219">These have been removed from the following results for clarity.</span></span>

```console
Detect temporary changes in pattern
=============== Training the model ===============
=============== End of training process ===============
Alert   Score   P-Value
0       271.00  0.50
0       150.90  0.00
0       188.10  0.41
0       124.30  0.13
0       185.30  0.47
0       173.50  0.47
0       236.80  0.19
0       229.50  0.27
0       197.80  0.48
0       127.90  0.13
1       341.50  0.00 <-- Spike detected
0       190.90  0.48
0       199.30  0.48
0       154.50  0.24
0       215.10  0.42
0       278.30  0.19
0       196.40  0.43
0       292.00  0.17
0       231.00  0.45
0       308.60  0.18
0       294.90  0.19
1       426.60  0.00 <-- Spike detected
0       269.50  0.47
0       347.30  0.21
0       344.70  0.27
0       445.40  0.06
0       320.90  0.49
0       444.30  0.12
0       406.30  0.29
0       442.40  0.21
1       580.50  0.00 <-- Spike detected
0       412.60  0.45
1       687.00  0.01 <-- Spike detected
0       480.30  0.40
0       586.30  0.20
0       651.90  0.14
```

## <a name="change-point-detection"></a><span data-ttu-id="1eaa8-220">更改点检测</span><span class="sxs-lookup"><span data-stu-id="1eaa8-220">Change point detection</span></span>

<span data-ttu-id="1eaa8-221">`Change points` 是时序事件流值分布的持续更改，例如级别更改和趋势。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-221">`Change points` are persistent changes in a time series event stream distribution of values, like level changes and trends.</span></span> <span data-ttu-id="1eaa8-222">这些持续更改的持续时间比 `spikes` 的持续时间长得多，可能指示灾难性事件。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-222">These persistent changes last much longer than `spikes` and could indicate catastrophic event(s).</span></span> <span data-ttu-id="1eaa8-223">`Change points` 通常对肉眼不可见，但可以使用诸如以下方法的方法在数据中检测到。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-223">`Change points` are not usually visible to the naked eye, but can be detected in your data using approaches such as in the following method.</span></span>  <span data-ttu-id="1eaa8-224">下图是更改点检测的示例：</span><span class="sxs-lookup"><span data-stu-id="1eaa8-224">The following image is an example of a change point detection:</span></span>

![ChangePointDetection](./media/sales-anomaly-detection/ChangePointDetection.png)

### <a name="create-the-detectchangepoint-method"></a><span data-ttu-id="1eaa8-226">创建 DetectChangepoint() 方法</span><span class="sxs-lookup"><span data-stu-id="1eaa8-226">Create the DetectChangepoint() method</span></span>

<span data-ttu-id="1eaa8-227">将以下调用添加到 `DetectChangepoint()` 方法作为 `Main()` 方法的下一行代码：</span><span class="sxs-lookup"><span data-stu-id="1eaa8-227">Add the following call to the `DetectChangepoint()`method as the next line of code in the `Main()` method:</span></span>

[!code-csharp[CallDetectChangepoint](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CallDetectChangepoint)]

<span data-ttu-id="1eaa8-228">`DetectChangepoint()` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="1eaa8-228">The `DetectChangepoint()` method executes the following tasks:</span></span>

* <span data-ttu-id="1eaa8-229">定型模型。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-229">Trains the model.</span></span>
* <span data-ttu-id="1eaa8-230">根据历史销售数据检测更改点。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-230">Detects change points based on historical sales data.</span></span>
* <span data-ttu-id="1eaa8-231">显示结果。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-231">Displays the results.</span></span>

<span data-ttu-id="1eaa8-232">使用下面的代码紧随 `Main()` 方法后创建 `DetectChangepoint()` 方法：</span><span class="sxs-lookup"><span data-stu-id="1eaa8-232">Create the `DetectChangepoint()` method, just after the `Main()` method, using the following code:</span></span>

```csharp
static void DetectChangepoint(MLContext mlContext, int docSize, IDataView productSales)
{

}
```

<span data-ttu-id="1eaa8-233">[iidChangePointEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidChangePointEstimator) 用于训练模型来进行更改点检测。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-233">The [iidChangePointEstimator](xref:Microsoft.ML.Transforms.TimeSeries.IidChangePointEstimator) is used to train the model for change point detection.</span></span> <span data-ttu-id="1eaa8-234">使用以下代码将其添加到 `DetectChangepoint()` 方法中：</span><span class="sxs-lookup"><span data-stu-id="1eaa8-234">Add it to the `DetectChangepoint()` method with the following code:</span></span>

[!code-csharp[AddChangepointTrainer](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#AddChangepointTrainer)]

<span data-ttu-id="1eaa8-235">如之前一样，通过在 `DetectChangePoint()` 方法中添加以下代码作为下一代码行来使模型适应 `productSales` 数据：</span><span class="sxs-lookup"><span data-stu-id="1eaa8-235">As you did previously, fit the model to the `productSales` data by adding the following as the next line of code in the `DetectChangePoint()` method:</span></span>

[!code-csharp[TrainModel2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TrainModel2)]

<span data-ttu-id="1eaa8-236">使用 `Transform()` 方法通过将以下代码添加到 `DetectChangePoint()` 来转换 `Training` 数据：</span><span class="sxs-lookup"><span data-stu-id="1eaa8-236">Use the `Transform()` method to transform the `Training` data by adding the following code to `DetectChangePoint()`:</span></span>

[!code-csharp[TransformData2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#TransformData2)]

<span data-ttu-id="1eaa8-237">如之前一样，使用 `CreateEnumerable()` 方法和以下代码将 `transformedData` 转换为强类型 `IEnumerable`，以方便显示：</span><span class="sxs-lookup"><span data-stu-id="1eaa8-237">As you did previously, convert your `transformedData` into a strongly-typed `IEnumerable` for easier display using the `CreateEnumerable()`method with the following code:</span></span>

[!code-csharp[CreateEnumerable2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#CreateEnumerable2)]

<span data-ttu-id="1eaa8-238">使用以下代码创建显示标头，用作 `DetectChangePoint()` 方法中的下一行：</span><span class="sxs-lookup"><span data-stu-id="1eaa8-238">Create a display header with the following code as the next line in the `DetectChangePoint()` method:</span></span>

[!code-csharp[DisplayHeader2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayHeader2)]

<span data-ttu-id="1eaa8-239">将在更改点检测结果中显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="1eaa8-239">You'll display the following information in your change point detection results:</span></span>

* <span data-ttu-id="1eaa8-240">`Alert` 指示给定数据点的更改点警报。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-240">`Alert` indicates a change point alert for a given data point.</span></span>
* <span data-ttu-id="1eaa8-241">`Score` 是数据集中给定数据点的 `ProductSales` 值。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-241">`Score` is the `ProductSales` value for a given data point in the dataset.</span></span>
* <span data-ttu-id="1eaa8-242">`P-Value`“P”代表概率，</span><span class="sxs-lookup"><span data-stu-id="1eaa8-242">`P-Value` The "P" stands for probability.</span></span> <span data-ttu-id="1eaa8-243">其指示此数据点为异常数据点的可能性。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-243">This indicates how likely this data point is an anomaly.</span></span> 
* <span data-ttu-id="1eaa8-244">`Martingale value` 用于根据 P 值序列识别数据点的“奇怪”程度。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-244">`Martingale value` is used to identify how "weird" a data point is, based on the sequence of P-values.</span></span>  

<span data-ttu-id="1eaa8-245">使用以下代码循环访问 `predictions` `IEnumerable` 并显示结果：</span><span class="sxs-lookup"><span data-stu-id="1eaa8-245">Iterate through the `predictions` `IEnumerable` and display the results with the following code:</span></span>

[!code-csharp[DisplayResults2](~/samples/machine-learning/tutorials/ProductSalesAnomalyDetection/Program.cs#DisplayResults2)]

## <a name="change-point-detection-results"></a><span data-ttu-id="1eaa8-246">更改点检测结果</span><span class="sxs-lookup"><span data-stu-id="1eaa8-246">Change point detection results</span></span>

<span data-ttu-id="1eaa8-247">结果应如下所示。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-247">Your results should be similar to the following.</span></span> <span data-ttu-id="1eaa8-248">处理期间将显示消息。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-248">During processing, messages are displayed.</span></span> <span data-ttu-id="1eaa8-249">你可能会看到警告或处理消息。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-249">You may see warnings, or processing messages.</span></span> <span data-ttu-id="1eaa8-250">为清楚起见，已经从下面的结果中删除这些内容。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-250">These have been removed from the following results for clarity.</span></span>

```console
Detect Persistent changes in pattern
=============== Training the model Using Change Point Detection Algorithm===============
=============== End of training process ===============
Alert   Score   P-Value Martingale value
0       271.00  0.50    0.00
0       150.90  0.00    2.33
0       188.10  0.41    2.80
0       124.30  0.13    9.16
0       185.30  0.47    9.77
0       173.50  0.47    10.41
0       236.80  0.19    24.46
0       229.50  0.27    42.38
1       197.80  0.48    44.23 <-- alert is on, predicted changepoint
0       127.90  0.13    145.25
0       341.50  0.00    0.01
0       190.90  0.48    0.01
0       199.30  0.48    0.00
0       154.50  0.24    0.00
0       215.10  0.42    0.00
0       278.30  0.19    0.00
0       196.40  0.43    0.00
0       292.00  0.17    0.01
0       231.00  0.45    0.00
0       308.60  0.18    0.00
0       294.90  0.19    0.00
0       426.60  0.00    0.00
0       269.50  0.47    0.00
0       347.30  0.21    0.00
0       344.70  0.27    0.00
0       445.40  0.06    0.02
0       320.90  0.49    0.01
0       444.30  0.12    0.02
0       406.30  0.29    0.01
0       442.40  0.21    0.01
0       580.50  0.00    0.01
0       412.60  0.45    0.01
0       687.00  0.01    0.12
0       480.30  0.40    0.08
0       586.30  0.20    0.03
0       651.90  0.14    0.09
```

<span data-ttu-id="1eaa8-251">祝贺你！</span><span class="sxs-lookup"><span data-stu-id="1eaa8-251">Congratulations!</span></span> <span data-ttu-id="1eaa8-252">现在已成功生成用于检测销售数据中的峰值和更改点异常情况的机器学习模型。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-252">You've now successfully built machine learning models for detecting spikes and change point anomalies in sales data.</span></span>

<span data-ttu-id="1eaa8-253">可以在 [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection) 存储库中找到本教程的源代码。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-253">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/ProductSalesAnomalyDetection) repository.</span></span>

<span data-ttu-id="1eaa8-254">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="1eaa8-254">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="1eaa8-255">加载数据</span><span class="sxs-lookup"><span data-stu-id="1eaa8-255">Load the data</span></span>
> * <span data-ttu-id="1eaa8-256">训练模型用于峰值异常情况检测</span><span class="sxs-lookup"><span data-stu-id="1eaa8-256">Train the model for spike anomaly detection</span></span>
> * <span data-ttu-id="1eaa8-257">使用经过训练的模型检测峰值异常情况</span><span class="sxs-lookup"><span data-stu-id="1eaa8-257">Detect spike anomalies with the trained model</span></span>
> * <span data-ttu-id="1eaa8-258">训练模型用于更改点异常情况检测</span><span class="sxs-lookup"><span data-stu-id="1eaa8-258">Train the model for change point anomaly detection</span></span>
> * <span data-ttu-id="1eaa8-259">使用经过训练的模型检测更改点异常情况</span><span class="sxs-lookup"><span data-stu-id="1eaa8-259">Detect change point anomalies with the trained mode</span></span>

## <a name="next-steps"></a><span data-ttu-id="1eaa8-260">后续步骤</span><span class="sxs-lookup"><span data-stu-id="1eaa8-260">Next steps</span></span>

<span data-ttu-id="1eaa8-261">请查看机器学习示例 GitHub 存储库，以探索能耗异常情况检测示例。</span><span class="sxs-lookup"><span data-stu-id="1eaa8-261">Check out the Machine Learning samples GitHub repository to explore a Power Consumption Anomaly Detection sample.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="1eaa8-262">dotnet/machinelearning-samples GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="1eaa8-262">dotnet/machinelearning-samples GitHub repository</span></span>](https://github.com/dotnet/machinelearning-samples/tree/master/samples/csharp/getting-started/AnomalyDetection_PowerMeterReadings)

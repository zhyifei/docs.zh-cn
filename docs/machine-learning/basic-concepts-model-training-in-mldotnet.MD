---
title: ML.NET 中模型定型的基本概念
description: 本文介绍与 ML.NET 中模型定型方案相关的基本概念。 并非所有观念均与更简单的方案“使用现有模型预测”相关。
ms.date: 02/13/2019
ms.topic: overview
ms.custom: mvc
ms.openlocfilehash: c47d5832527dca1416abfc55756dca48f1daf493
ms.sourcegitcommit: bef803e2025642df39f2f1e046767d89031e0304
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2019
ms.locfileid: "56303655"
---
# <a name="basic-concepts-for-model-training-in-mlnet"></a><span data-ttu-id="ee562-104">ML.NET 中模型定型的基本概念</span><span class="sxs-lookup"><span data-stu-id="ee562-104">Basic concepts for model training in ML.NET</span></span>

<span data-ttu-id="ee562-105">本文介绍与 ML.NET 中模型定型方案相关的基本概念。</span><span class="sxs-lookup"><span data-stu-id="ee562-105">This article explains the basic concepts covering *model training* scenarios in ML.NET.</span></span> <span data-ttu-id="ee562-106">并非所有观念均与更简单的方案“使用现有模型预测”相关。</span><span class="sxs-lookup"><span data-stu-id="ee562-106">Not all concepts are relevant to the more simple scenario of *prediction with an existing model*.</span></span>

## <a name="model-training-concepts"></a><span data-ttu-id="ee562-107">模型定型概念</span><span class="sxs-lookup"><span data-stu-id="ee562-107">Model training concepts</span></span>

<span data-ttu-id="ee562-108">本文档介绍与 ML.NET 中模型定型相关的以下概念：</span><span class="sxs-lookup"><span data-stu-id="ee562-108">This document covers the following concepts related to model training in ML.NET:</span></span>

- <span data-ttu-id="ee562-109">[数据](#data)表示为 `IDataView` 接口。</span><span class="sxs-lookup"><span data-stu-id="ee562-109">[*Data*](#data) represented as an `IDataView` interface.</span></span>
  - <span data-ttu-id="ee562-110">在 ML.NET 中，数据类似于 SQL 视图：它是延迟评估的、不可变的、可应用游标的、异源的架构化数据集。</span><span class="sxs-lookup"><span data-stu-id="ee562-110">In ML.NET, data is similar to a SQL view: It's a lazily evaluated, immutable, cursorable, heterogenous, schematized dataset.</span></span> 
  - <span data-ttu-id="ee562-111">可参阅有关数据接口的精彩文档 [IDataView 设计原则](https://github.com/dotnet/machinelearning/blob/master/docs/code/IDataViewDesignPrinciples.md)。</span><span class="sxs-lookup"><span data-stu-id="ee562-111">An excellent document about the data interface is [IDataView Design Principles](https://github.com/dotnet/machinelearning/blob/master/docs/code/IDataViewDesignPrinciples.md).</span></span>
- <span data-ttu-id="ee562-112">[转换器](#transformer)表示为 `ITransformer` 接口。</span><span class="sxs-lookup"><span data-stu-id="ee562-112">[*Transformer*](#transformer) represented as `ITransformer` interface.</span></span>
  - <span data-ttu-id="ee562-113">转换器是一种组件，它提取数据，对其执行某些操作，然后返回转换后的新数据。</span><span class="sxs-lookup"><span data-stu-id="ee562-113">A transformer is a component that takes data, does some work on it, and returns new transformed data.</span></span>
  - <span data-ttu-id="ee562-114">例如，可以将机器学习模型视为转换器，用于提取特征并返回预测数据。</span><span class="sxs-lookup"><span data-stu-id="ee562-114">For example, you can think of a machine learning model as a transformer that takes features and returns predictions.</span></span>
  - <span data-ttu-id="ee562-115">再举一个例子，文本 tokenizer 提取单个文本列，并输出矢量列，包含从文本中提取出来的单个字词。</span><span class="sxs-lookup"><span data-stu-id="ee562-115">Another example, text tokenizer takes a single text column and outputs a vector column with individual words extracted out of the texts.</span></span>
- <span data-ttu-id="ee562-116">[数据读取器](#data-reader)表示为 `IDataReader<T>` 接口。</span><span class="sxs-lookup"><span data-stu-id="ee562-116">[*Data reader*](#data-reader) represented as an `IDataReader<T>` interface.</span></span>
  - <span data-ttu-id="ee562-117">数据读取器是用于创建数据的 ML.NET 组件。</span><span class="sxs-lookup"><span data-stu-id="ee562-117">The data reader is ML.NET component to create data.</span></span> <span data-ttu-id="ee562-118">它采用 `T` 的实例，并返回其中的数据。</span><span class="sxs-lookup"><span data-stu-id="ee562-118">It takes an instance of `T` and returns data out of it.</span></span> 
  - <span data-ttu-id="ee562-119">例如，TextLoader 是一个 `IDataReader<IMultiStreamSource>`。</span><span class="sxs-lookup"><span data-stu-id="ee562-119">For example, a *TextLoader* is an `IDataReader<IMultiStreamSource>`.</span></span> <span data-ttu-id="ee562-120">它提取源，然后产生数据。</span><span class="sxs-lookup"><span data-stu-id="ee562-120">It takes the source and produces data.</span></span> 
- <span data-ttu-id="ee562-121">[估算器](#estimator)表示为 `IEstimator<T>` 接口。</span><span class="sxs-lookup"><span data-stu-id="ee562-121">[*Estimator*](#estimator) represented as an `IEstimator<T>` interface.</span></span>
  - <span data-ttu-id="ee562-122">这是学习数据的对象。</span><span class="sxs-lookup"><span data-stu-id="ee562-122">This is an object that learns from data.</span></span> <span data-ttu-id="ee562-123">学习的结果是转换器。</span><span class="sxs-lookup"><span data-stu-id="ee562-123">The result of the learning is a *transformer*.</span></span>
  - <span data-ttu-id="ee562-124">可将机器学习算法视为估算器，依赖数据进行学习并生成机器学习模型。</span><span class="sxs-lookup"><span data-stu-id="ee562-124">You can think of a machine learning *algorithm* as an estimator that learns on data and produces a machine learning *model*.</span></span>
- <span data-ttu-id="ee562-125">[预测函数](#prediction-function)表示为 `PredictionEngine<TSrc, TDst>` 类。</span><span class="sxs-lookup"><span data-stu-id="ee562-125">[*Prediction function*](#prediction-function) represented as a `PredictionEngine<TSrc, TDst>` class.</span></span>
  - <span data-ttu-id="ee562-126">可将预测函数视为一个向某个行应用转换器的计算机（例如在预测时）。</span><span class="sxs-lookup"><span data-stu-id="ee562-126">The prediction function can be seen as a machine that applies a transformer to one row, such as at prediction time.</span></span>

## <a name="data"></a><span data-ttu-id="ee562-127">数据</span><span class="sxs-lookup"><span data-stu-id="ee562-127">Data</span></span>

<span data-ttu-id="ee562-128">在 ML.NET 中，数据类似于 SQL 视图：它是延迟评估的、可应用游标的、异源的架构化数据集。</span><span class="sxs-lookup"><span data-stu-id="ee562-128">In ML.NET, data is similar to a SQL view: It's a lazily evaluated, cursorable, heterogenous, schematized dataset.</span></span>

- <span data-ttu-id="ee562-129">它具有架构（`ISchema` 接口的实例），其中包含数据视图列的相关信息。</span><span class="sxs-lookup"><span data-stu-id="ee562-129">It has *Schema* (an instance of an `ISchema` interface) that contains the information about the data view's columns.</span></span>
  - <span data-ttu-id="ee562-130">每列均包含“名称”、“类型”和与之相关联的任意元数据集。</span><span class="sxs-lookup"><span data-stu-id="ee562-130">Each column has a *Name*, a *Type*, and an arbitrary set of *metadata* associated with it.</span></span>
  - <span data-ttu-id="ee562-131">列的元数据包含矢量列槽名称等信息。</span><span class="sxs-lookup"><span data-stu-id="ee562-131">The column's *metadata* contains information like slot names of a vector column and the like.</span></span> <span data-ttu-id="ee562-132">元数据本身表示为另一个单行数据，该数据对每一个列是唯一的。</span><span class="sxs-lookup"><span data-stu-id="ee562-132">The metadata itself is represented as another one-row *data* that is unique to each column.</span></span>
  - <span data-ttu-id="ee562-133">数据视图是游标的源。</span><span class="sxs-lookup"><span data-stu-id="ee562-133">The data view is a source of *cursors*.</span></span> <span data-ttu-id="ee562-134">回想一下 SQL 游标：游标是一个对象，它循环访问数据，一次一行，且表示可用数据。</span><span class="sxs-lookup"><span data-stu-id="ee562-134">Think SQL cursors: A cursor is an object that iterates through the data, one row at a time, and presents the available data.</span></span>
  - <span data-ttu-id="ee562-135">正常情况下，数据可根据需要，具有尽可能多的活动游标。</span><span class="sxs-lookup"><span data-stu-id="ee562-135">Naturally, data can have as many active cursors over it as needed.</span></span> <span data-ttu-id="ee562-136">由于数据本身是不可变的，因此游标是独立的。</span><span class="sxs-lookup"><span data-stu-id="ee562-136">Since data itself is immutable, cursors are truly independent.</span></span>
  - <span data-ttu-id="ee562-137">游标通常只访问列的子集：为提高效率，ML.NET 只计算游标需要的列的值。</span><span class="sxs-lookup"><span data-stu-id="ee562-137">Cursors typically access only a subset of columns: For efficiency, ML.NET computes only the values of columns that are needed by the cursor.</span></span>

## <a name="transformer"></a><span data-ttu-id="ee562-138">转换器</span><span class="sxs-lookup"><span data-stu-id="ee562-138">Transformer</span></span>

<span data-ttu-id="ee562-139">转换器是一种组件，它提取数据，对其执行某些操作，然后返回转换后的新数据。</span><span class="sxs-lookup"><span data-stu-id="ee562-139">A transformer is a component that takes data, does some work on it, and returns new transformed data.</span></span>

<span data-ttu-id="ee562-140">ML.NET 中的大多数转换器往往一次操作一个输入列，然后生成输出列。</span><span class="sxs-lookup"><span data-stu-id="ee562-140">Most transformers in ML.NET tend to operate on one *input column* at a time, and produce the *output column*.</span></span> <span data-ttu-id="ee562-141">例如，`new HashTransformer("bar", "foo")` 采用列“foo”中的值，对其进行哈希操作，然后将其放到“bar”列。</span><span class="sxs-lookup"><span data-stu-id="ee562-141">For example, a `new HashTransformer("bar", "foo")` takes the values from column "foo", hashes them, and puts them into column "bar".</span></span> 

<span data-ttu-id="ee562-142">输入列和输出列名称相同是很常见的。</span><span class="sxs-lookup"><span data-stu-id="ee562-142">It's also common that the input and output column names are the same.</span></span> <span data-ttu-id="ee562-143">在这种情况下，旧的列被替换为新的列。</span><span class="sxs-lookup"><span data-stu-id="ee562-143">In this case, the old column is replaced with the new one.</span></span> <span data-ttu-id="ee562-144">例如，`new HashTransformer("foo")` 采用列“foo”中的值，对其进行哈希操作，然后将其放到“foo”。</span><span class="sxs-lookup"><span data-stu-id="ee562-144">For example, a `new HashTransformer("foo")` takes the values from column "foo", hashes them, and puts them back into "foo".</span></span> 

<span data-ttu-id="ee562-145">如果调用 `Transform`，任何转换器都会生成新的数据视图。</span><span class="sxs-lookup"><span data-stu-id="ee562-145">Any transformer, produces a new data view when `Transform` is called.</span></span> <span data-ttu-id="ee562-146">请记住，数据视图是不可变的。</span><span class="sxs-lookup"><span data-stu-id="ee562-146">Remember, data views are immutable.</span></span>

<span data-ttu-id="ee562-147">另一个重要的考虑因素是，由于数据评估延迟，转换器也会延迟。</span><span class="sxs-lookup"><span data-stu-id="ee562-147">Another important consideration is that, because data is lazily evaluated, *transformers are lazy too*.</span></span> <span data-ttu-id="ee562-148">本质上讲，调用之后</span><span class="sxs-lookup"><span data-stu-id="ee562-148">Essentially, after you call</span></span>

```csharp
var newData = transformer.Transform(oldData)
```

<span data-ttu-id="ee562-149">未发生任何实际计算。</span><span class="sxs-lookup"><span data-stu-id="ee562-149">no actual computation happens.</span></span> <span data-ttu-id="ee562-150">仅当通过 `newData` 获得游标并开始使用值时，`newData` 才会调用 `transformer` 转换逻辑（甚至是仅在需要 `transformer` 才能生成请求的列的情况下）。</span><span class="sxs-lookup"><span data-stu-id="ee562-150">Only after you get a cursor from `newData` and start consuming the value does `newData` invoke the `transformer` transformation logic (and even then, it only happens if the `transformer` in question is needed to produce the requested columns).</span></span>

### <a name="transformer-chains"></a><span data-ttu-id="ee562-151">转换器链</span><span class="sxs-lookup"><span data-stu-id="ee562-151">Transformer chains</span></span>

<span data-ttu-id="ee562-152">转换器有一个有用的属性，是用户可以将一系列转换器的整个应用序列构建为另一个转换器：</span><span class="sxs-lookup"><span data-stu-id="ee562-152">A useful property of a transformer is that *you can build a sequential application of transformers as yet another transformer*:</span></span>

```csharp
var fullTransformer = transformer1.Append(transformer2).Append(transformer3);
```

<span data-ttu-id="ee562-153">此属性通常在 ML.NET 中使用：通常情况下，定型的 ML.NET 模型就是一个转换器链，对于所有要实现的用途和目的，它就是一个转换器。</span><span class="sxs-lookup"><span data-stu-id="ee562-153">This property is commonly used in ML.NET: typically, the trained ML.NET model is a chain of transformers, which is, for all intents and purposes, a *transformer*.</span></span>

## <a name="data-reader"></a><span data-ttu-id="ee562-154">数据读取器</span><span class="sxs-lookup"><span data-stu-id="ee562-154">Data reader</span></span>

<span data-ttu-id="ee562-155">数据读取器是用于“创建”数据的 ML.NET 组件：它采用 `T` 的实例并返回相关数据。</span><span class="sxs-lookup"><span data-stu-id="ee562-155">The data reader is an ML.NET component to 'create' data: it takes an instance of `T` and returns data out of it.</span></span>

<span data-ttu-id="ee562-156">需要注意的一个有趣属性是，可以通过将转换器附加到现有数据读取器，来创建一个数据读取器。</span><span class="sxs-lookup"><span data-stu-id="ee562-156">An interesting property to note is that you can create a data reader by attaching a transformer to an existing data reader.</span></span> <span data-ttu-id="ee562-157">这样便可获得包含转换行为的读取器：</span><span class="sxs-lookup"><span data-stu-id="ee562-157">This way you can have a reader with transformation behavior baked in:</span></span>

```csharp
var newReader = reader.Append(transformer1).Append(transformer2)
```

<span data-ttu-id="ee562-158">与转换器的另一个相似之处是，由于数据评估延迟，读取器也延迟：调用 `reader.Read()` 后未发生任何（或最小程度的）实际“读取”：仅当生成的数据请求游标时，读取器才开始工作。</span><span class="sxs-lookup"><span data-stu-id="ee562-158">Another similarity to transformers is that, since data is lazily evaluated, *readers are lazy*: no (or minimal) actual 'reading' happens when you call `reader.Read()`: only when a cursor is requested on the resulting data does the reader begin to work.</span></span>

## <a name="estimator"></a><span data-ttu-id="ee562-159">估算器</span><span class="sxs-lookup"><span data-stu-id="ee562-159">Estimator</span></span>

<span data-ttu-id="ee562-160">估算器是学习数据的对象。</span><span class="sxs-lookup"><span data-stu-id="ee562-160">The *estimator* is an object that learns from data.</span></span> <span data-ttu-id="ee562-161">学习的结果是转换器。</span><span class="sxs-lookup"><span data-stu-id="ee562-161">The result of the learning is a *transformer*.</span></span>

<span data-ttu-id="ee562-162">在 ML.NET 中，使用此属性创建将不同估算器链接在一起的学习管道：</span><span class="sxs-lookup"><span data-stu-id="ee562-162">In ML.NET, use this property to create learning pipelines that chain together different estimators:</span></span>

```csharp
MLContext mlContext = new MLContext(seed: 0);

var pipeline = mlContext.Transforms.CopyColumns("Label","FareAmount")
    .Append(mlContext.Transforms.Categorical.OneHotEncoding("VendorId"))
    .Append(mlContext.Transforms.Categorical.OneHotEncoding("RateCode"))
    .Append(mlContext.Transforms.Categorical.OneHotEncoding("PaymentType"))
    .Append(mlContext.Transforms.Concatenate("Features","VendorId","RateCode","PassengerCount","TripTime","TripDistance","PaymentType"))
    .Append(mlContext.Regression.Trainers.FastTree("Label","Features"));

var model = pipeline.Fit(dataView);
```

<span data-ttu-id="ee562-163">估算器的一个重要属性是“估算器积极，无惰性”：每个 `Fit` 调用都会导致学习行为，操作可能会很耗时。</span><span class="sxs-lookup"><span data-stu-id="ee562-163">One important property of estimators is that *estimators are eager, not lazy*: every call to `Fit` is causing learning to happen, which is potentially a time-consuming operation.</span></span>

## <a name="prediction-function"></a><span data-ttu-id="ee562-164">预测函数</span><span class="sxs-lookup"><span data-stu-id="ee562-164">Prediction function</span></span>

<span data-ttu-id="ee562-165">可将预测函数视为向某行应用转换器的组件。</span><span class="sxs-lookup"><span data-stu-id="ee562-165">The prediction function can be seen as a component that applies a transformer to one row.</span></span>

<span data-ttu-id="ee562-166">获取模型（通过 `Fit()` 定型或从其他位置加载的转换器）后，可通过 `model.Transform(data)` 的常规调用，使用模型进行预测。</span><span class="sxs-lookup"><span data-stu-id="ee562-166">Once you get the model (a *transformer* either trained via `Fit()`, or loaded from somewhere), you can use it to make predictions using the normal calls to `model.Transform(data)`.</span></span> <span data-ttu-id="ee562-167">然而，在实际情景中使用此模型时，通常没有多少可用来进行预测的示例。</span><span class="sxs-lookup"><span data-stu-id="ee562-167">However, when you use this model in a real-life scenario, you often don't have many examples to predict on.</span></span> <span data-ttu-id="ee562-168">往往一次只有一个示例，且需要立即通过示例进行及时预测。</span><span class="sxs-lookup"><span data-stu-id="ee562-168">Instead, you have one example at a time, and you need to make timely predictions on them immediately.</span></span>

<span data-ttu-id="ee562-169">当然，可将此缩减为批预测：</span><span class="sxs-lookup"><span data-stu-id="ee562-169">Of course, you can reduce this to the batch prediction:</span></span>

- <span data-ttu-id="ee562-170">创建只有一行的数据视图。</span><span class="sxs-lookup"><span data-stu-id="ee562-170">Create a data view with exactly one row.</span></span>
- <span data-ttu-id="ee562-171">调用 `model.Transform(data)` 以获取预测的数据视图。</span><span class="sxs-lookup"><span data-stu-id="ee562-171">Call `model.Transform(data)` to get the predicted data view.</span></span>
- <span data-ttu-id="ee562-172">获取生成数据上的游标。</span><span class="sxs-lookup"><span data-stu-id="ee562-172">Get a cursor over the resulting data.</span></span>
- <span data-ttu-id="ee562-173">将游标移动一步，到达第一（且唯一）行。</span><span class="sxs-lookup"><span data-stu-id="ee562-173">Advance the cursor one step to get to the first (and only) row.</span></span>
- <span data-ttu-id="ee562-174">从其中提取预测值。</span><span class="sxs-lookup"><span data-stu-id="ee562-174">Extract the predicted values out of it.</span></span>

<span data-ttu-id="ee562-175">可使用[架构理解](https://github.com/dotnet/machinelearning/blob/master/docs/code/SchemaComprehension.md)，通过两个用户定义的对象（`InputExample` 和 `OutputPrediction`）实现上述算法，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ee562-175">The preceding algorithm can be implemented using the [schema comprehension](https://github.com/dotnet/machinelearning/blob/master/docs/code/SchemaComprehension.md), with two user-defined objects `InputExample` and `OutputPrediction` as follows:</span></span>

```csharp
var inputData = mlContext.Data.ReadFromEnumerable(new InputExample[] { example });
var outputData = model.Transform(inputData);
var output = mlContext.CreateEnumerable<OutputPrediction>(outputData,reuseRowObject:false).First();
```

<span data-ttu-id="ee562-176">但这很麻烦，并会产生性能成本。</span><span class="sxs-lookup"><span data-stu-id="ee562-176">But this is cumbersome and incurs performance costs.</span></span> <span data-ttu-id="ee562-177">而预测函数对象可通过扩展方法 `CreatePredictionEngine` 执行相同的操作，但速度更快、更方便：</span><span class="sxs-lookup"><span data-stu-id="ee562-177">Instead, a prediction function object performs the same work, but faster and more convenient, via an extension method `CreatePredictionEngine`:</span></span>

```csharp
var predictionEngine = model.CreatePredictionEngine<InputExample,OutputPrediction>(mlContext);
var prediction = predictionEngine.Predict(example);
```

<span data-ttu-id="ee562-178">预测函数是不可重入的/线程安全的。</span><span class="sxs-lookup"><span data-stu-id="ee562-178">The prediction function is *not re-entrant / thread-safe*.</span></span> <span data-ttu-id="ee562-179">如果想要使用多个线程同时进行预测，每个线程都需要有一个预测函数。</span><span class="sxs-lookup"><span data-stu-id="ee562-179">If you want to conduct predictions simultaneously with multiple threads, you need to have a prediction function per thread.</span></span>

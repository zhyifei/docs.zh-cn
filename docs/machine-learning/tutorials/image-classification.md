---
title: 教程：使用 TensorFlow 生成 ML.NET 自定义图像分类器
description: 了解如何通过重用预定型 TensorFlow 模型，在 TensorFlow 迁移学习方案中生成 ML.NET 自定义图像分类器来分类图像。
ms.date: 05/06/2019
ms.topic: tutorial
ms.custom: mvc
ms.openlocfilehash: f7fddc2d6c60a719090af36b7fe91919bfbd115c
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063620"
---
# <a name="tutorial-build-an-mlnet-custom-image-classifier-with-tensorflow"></a><span data-ttu-id="63b00-103">教程：使用 TensorFlow 生成 ML.NET 自定义图像分类器</span><span class="sxs-lookup"><span data-stu-id="63b00-103">Tutorial: Build an ML.NET custom image classifier with TensorFlow</span></span>

<span data-ttu-id="63b00-104">本示例教程展示了如何使用已定型的图像分类器 `TensorFlow` 模型来生成新的自定义模型，以将图像分类为若干类别。</span><span class="sxs-lookup"><span data-stu-id="63b00-104">This sample tutorial illustrates how you can use an already trained Image Classifier `TensorFlow` model to build a new custom model to classify images into a few categories.</span></span>

<span data-ttu-id="63b00-105">如果可以重用已预定型的模型来解决类似问题，并重新定型此模型的所有层或部分层来解决问题，那该有多好！</span><span class="sxs-lookup"><span data-stu-id="63b00-105">What if you could reuse a model that's already been pre trained to solve a similar problem and retrain either all or some of the layers of that model to make it solve your problem?</span></span> <span data-ttu-id="63b00-106">重用部分已定型的模型来生成新模型的技术称为[迁移学习](https://en.wikipedia.org/wiki/Transfer_learning)。</span><span class="sxs-lookup"><span data-stu-id="63b00-106">This technique of reusing part of an already trained model to build a new model is known as [transfer learning](https://en.wikipedia.org/wiki/Transfer_learning).</span></span>

<span data-ttu-id="63b00-107">从头开始定型[图像分类](https://en.wikipedia.org/wiki/Outline_of_object_recognition)模型需要设置数百万个参数、大量已标记的定型数据和海量计算资源（数百个 GPU 小时）。</span><span class="sxs-lookup"><span data-stu-id="63b00-107">Training an [Image Classification](https://en.wikipedia.org/wiki/Outline_of_object_recognition) model from scratch requires setting millions of parameters, a ton of labeled training data and a vast amount of compute resources (hundreds of GPU hours).</span></span> <span data-ttu-id="63b00-108">虽然不如从头开始定型自定义模型有效，但借助迁移学习，可以通过处理数千张图像（与数百万张已标记的图像相比）来简化此过程，并非常快速地生成自定义模型（在没有 GPU 的计算机上一小时内完成）。</span><span class="sxs-lookup"><span data-stu-id="63b00-108">While not as effective as training a custom model from scratch, transfer learning allows you to shortcut this process by working with thousands of images vs. millions of labeled images and build a customized model fairly quickly (within an hour on a machine without a GPU).</span></span>

<span data-ttu-id="63b00-109">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="63b00-109">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="63b00-110">了解问题</span><span class="sxs-lookup"><span data-stu-id="63b00-110">Understand the problem</span></span>
> * <span data-ttu-id="63b00-111">重用和优化预定型模型</span><span class="sxs-lookup"><span data-stu-id="63b00-111">Reuse and tune the pre-trained model</span></span>
> * <span data-ttu-id="63b00-112">分类图像</span><span class="sxs-lookup"><span data-stu-id="63b00-112">Classify Images</span></span>

## <a name="image-classification-sample-overview"></a><span data-ttu-id="63b00-113">图像分类示例概述</span><span class="sxs-lookup"><span data-stu-id="63b00-113">Image classification sample overview</span></span>

<span data-ttu-id="63b00-114">此示例是一个控制台应用，使用 ML.NET 并通过重用预定型模型来生成图像分类器，以对定型数据很少的图像进行分类。</span><span class="sxs-lookup"><span data-stu-id="63b00-114">The sample is a console application that uses ML.NET to build an image classifier by reusing a pre-trained model to classify images with a small amount of training data.</span></span>

<span data-ttu-id="63b00-115">可以在 [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) 存储库中找到本教程的源代码。</span><span class="sxs-lookup"><span data-stu-id="63b00-115">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="63b00-116">系统必备</span><span class="sxs-lookup"><span data-stu-id="63b00-116">Prerequisites</span></span>

* <span data-ttu-id="63b00-117">安装了“.NET Core 跨平台开发”工作负载的 [Visual Studio 2017 15.6 或更高版本](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017)。</span><span class="sxs-lookup"><span data-stu-id="63b00-117">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed.</span></span>

* <span data-ttu-id="63b00-118">Microsoft.ML 1.0.0 Nuget 包</span><span class="sxs-lookup"><span data-stu-id="63b00-118">Microsoft.ML 1.0.0 Nuget package</span></span>
* <span data-ttu-id="63b00-119">Microsoft.ML.ImageAnalytics 1.0.0 Nuget 包</span><span class="sxs-lookup"><span data-stu-id="63b00-119">Microsoft.ML.ImageAnalytics 1.0.0 Nuget package</span></span>
* <span data-ttu-id="63b00-120">Microsoft.ML.TensorFlow 0.12.0 Nuget 包</span><span class="sxs-lookup"><span data-stu-id="63b00-120">Microsoft.ML.TensorFlow 0.12.0 Nuget package</span></span>

* [<span data-ttu-id="63b00-121">教程资产目录 .ZIP 文件</span><span class="sxs-lookup"><span data-stu-id="63b00-121">The tutorial assets directory .ZIP file</span></span>](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip)

* [<span data-ttu-id="63b00-122">InceptionV3 机器学习模型</span><span class="sxs-lookup"><span data-stu-id="63b00-122">The InceptionV3 machine learning model</span></span>](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip)

## <a name="select-the-appropriate-machine-learning-task"></a><span data-ttu-id="63b00-123">选择适当的机器学习任务</span><span class="sxs-lookup"><span data-stu-id="63b00-123">Select the appropriate machine learning task</span></span>

<span data-ttu-id="63b00-124">[深度学习](https://en.wikipedia.org/wiki/Deep_learning)是机器学习的一部分，颠覆了计算机视觉和语音识别等领域。</span><span class="sxs-lookup"><span data-stu-id="63b00-124">[Deep learning](https://en.wikipedia.org/wiki/Deep_learning) is a subset of Machine Learning, which is revolutionizing areas like Computer Vision and Speech Recognition.</span></span>

<span data-ttu-id="63b00-125">深度学习模型是使用包含多个学习层的大量[已标记的数据](https://en.wikipedia.org/wiki/Labeled_data)和[神经网络](https://en.wikipedia.org/wiki/Artificial_neural_network)来定型。</span><span class="sxs-lookup"><span data-stu-id="63b00-125">Deep learning models are trained by using large sets of [labeled data](https://en.wikipedia.org/wiki/Labeled_data) and [neural networks](https://en.wikipedia.org/wiki/Artificial_neural_network) that contain multiple learning layers.</span></span> <span data-ttu-id="63b00-126">深度学习：</span><span class="sxs-lookup"><span data-stu-id="63b00-126">Deep learning:</span></span>

* <span data-ttu-id="63b00-127">执行计算机视觉等一些任务的效果更好。</span><span class="sxs-lookup"><span data-stu-id="63b00-127">Performs better on some tasks like Computer Vision.</span></span>

* <span data-ttu-id="63b00-128">处理大量数据的效果好。</span><span class="sxs-lookup"><span data-stu-id="63b00-128">Performs well on huge data amounts.</span></span>

<span data-ttu-id="63b00-129">图像分类是常见的机器学习任务，可便于自动将图像分类为多个类别，比如：</span><span class="sxs-lookup"><span data-stu-id="63b00-129">Image Classification is a common Machine Learning task that allows us to automatically classify images into multiple categories such as:</span></span>

* <span data-ttu-id="63b00-130">检测图像中是否有人脸。</span><span class="sxs-lookup"><span data-stu-id="63b00-130">Detecting a human face in an image or not.</span></span>
* <span data-ttu-id="63b00-131">检测是猫还是狗。</span><span class="sxs-lookup"><span data-stu-id="63b00-131">Detecting Cats vs. dogs.</span></span>

 <span data-ttu-id="63b00-132">或者在以下图像中，确定图像是食物、玩具还是家用电器：</span><span class="sxs-lookup"><span data-stu-id="63b00-132">Or as in the following images determining if an image is a(n)  food, toy, or appliance:</span></span>

<span data-ttu-id="63b00-133">![披萨图像](./media/image-classification/220px-Pepperoni_pizza.jpg)
![泰迪熊图像](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![烤面包机图像](./media/image-classification/193px-Broodrooster.jpg)</span><span class="sxs-lookup"><span data-stu-id="63b00-133">![pizza image](./media/image-classification/220px-Pepperoni_pizza.jpg)
![teddy bear image](./media/image-classification/119px-Nalle_-_a_small_brown_teddy_bear.jpg)
![toaster image](./media/image-classification/193px-Broodrooster.jpg)</span></span>

>[!Note]
> <span data-ttu-id="63b00-134">上面的图像属于维基共享资源，并按如下方式进行属性化：</span><span class="sxs-lookup"><span data-stu-id="63b00-134">The preceding images belong to Wikimedia Commons and are attributed as follows:</span></span>
>
> * <span data-ttu-id="63b00-135">“220px-Pepperoni_pizza.jpg”公有领域， https://commons.wikimedia.org/w/index.php?curid=79505</span><span class="sxs-lookup"><span data-stu-id="63b00-135">"220px-Pepperoni_pizza.jpg" Public Domain, https://commons.wikimedia.org/w/index.php?curid=79505,</span></span>
> * <span data-ttu-id="63b00-136">“119px-Nalle_-_a_small_brown_teddy_bear.jpg”作者为 [Jonik](https://commons.wikimedia.org/wiki/User:Jonik) - 独自拍摄，CC BY-SA 2.0， https://commons.wikimedia.org/w/index.php?curid=48166。</span><span class="sxs-lookup"><span data-stu-id="63b00-136">"119px-Nalle_-_a_small_brown_teddy_bear.jpg" By [Jonik](https://commons.wikimedia.org/wiki/User:Jonik) - Self-photographed, CC BY-SA 2.0, https://commons.wikimedia.org/w/index.php?curid=48166.</span></span>
> * <span data-ttu-id="63b00-137">“193px-Broodrooster.jpg”作者为 [M.Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972) - 自有作品，CC BY-SA 3.0， https://commons.wikimedia.org/w/index.php?curid=27403</span><span class="sxs-lookup"><span data-stu-id="63b00-137">"193px-Broodrooster.jpg" By [M.Minderhoud](https://nl.wikipedia.org/wiki/Gebruiker:Michiel1972) - Own work, CC BY-SA 3.0, https://commons.wikimedia.org/w/index.php?curid=27403</span></span>

<span data-ttu-id="63b00-138">迁移学习包括多种策略，如重新定型所有层策略和倒数第二层策略。</span><span class="sxs-lookup"><span data-stu-id="63b00-138">Transfer learning includes a few strategies, such as *retrain all layers* and *penultimate layer*.</span></span> <span data-ttu-id="63b00-139">本教程将介绍并展示如何使用倒数第二层策略。</span><span class="sxs-lookup"><span data-stu-id="63b00-139">This tutorial will explain and show how to use the *penultimate layer strategy*.</span></span> <span data-ttu-id="63b00-140">倒数第二层策略重用已预定型的模型来解决具体问题。</span><span class="sxs-lookup"><span data-stu-id="63b00-140">The *penultimate layer strategy* reuses a model that's already been pre-trained to solve a specific problem.</span></span> <span data-ttu-id="63b00-141">然后，此策略重新定型这个模型的最后一层来解决新问题。</span><span class="sxs-lookup"><span data-stu-id="63b00-141">The strategy then retrains the final layer of that model to make it solve a new problem.</span></span> <span data-ttu-id="63b00-142">重用预定型模型作为新模型的一部分将节省大量时间和资源。</span><span class="sxs-lookup"><span data-stu-id="63b00-142">Reusing the pre-trained model as part of your new model will save significant time and resources.</span></span>

<span data-ttu-id="63b00-143">图像分类模型重用 [Inception 模型](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip)，这是对 `ImageNet` 数据集定型的热门图像识别模型，其中 TensorFlow 模型尝试将所有图像分类为 1000 个类别，如“雨伞”、“针织衫”和“洗碗机”。</span><span class="sxs-lookup"><span data-stu-id="63b00-143">Your image classification model reuses the [Inception model](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip), a popular image recognition model trained on the `ImageNet` dataset where the TensorFlow model tries to classify entire images into a thousand classes, like “Umbrella”, “Jersey”, and “Dishwasher”.</span></span>

<span data-ttu-id="63b00-144">`Inception v3 model` 可以分类为[深度卷积神经网络](https://en.wikipedia.org/wiki/Convolutional_neural_network)，执行艰难视觉识别任务的效果合理，在一些领域中匹敌或超过人为绩效。</span><span class="sxs-lookup"><span data-stu-id="63b00-144">The `Inception v3 model` can be classified as a [deep convolutional neural network](https://en.wikipedia.org/wiki/Convolutional_neural_network) and can achieve reasonable performance on hard visual recognition tasks, matching or exceeding human performance in some domains.</span></span> <span data-ttu-id="63b00-145">此模型/算法是由多个研究人员根据以下原始文章开发的：[“重新思考计算机视觉的 Inception 体系结构”，作者为 Szegedy 以及其他人](https://arxiv.org/abs/1512.00567)</span><span class="sxs-lookup"><span data-stu-id="63b00-145">The model/algorithm was developed by multiple researchers and based on the original paper: ["Rethinking the Inception Architecture for Computer Vision” by Szegedy, et. al.](https://arxiv.org/abs/1512.00567)</span></span>

<span data-ttu-id="63b00-146">由于 `Inception model` 已对数千个不同图像进行过预定型，因此其中包含图像识别所需的[图像特征](https://en.wikipedia.org/wiki/Feature_(computer_vision))。</span><span class="sxs-lookup"><span data-stu-id="63b00-146">Because the `Inception model` has already been pre trained on thousands of different images, it contains the [image features](https://en.wikipedia.org/wiki/Feature_(computer_vision)) needed for image identification.</span></span> <span data-ttu-id="63b00-147">较低图像特征层识别简单特征（如边缘），较高层识别更复杂的特征（如形状）。</span><span class="sxs-lookup"><span data-stu-id="63b00-147">The lower image feature layers recognize simple features (such as edges) and the higher layers recognize more complex features (such as shapes).</span></span> <span data-ttu-id="63b00-148">最后一层对更小的数据集进行定型，因为你是从已了解如何分类图像的预定型模型入手。</span><span class="sxs-lookup"><span data-stu-id="63b00-148">The final layer is trained against a much smaller set of data because you're starting with a pre trained model that already understands how to classify images.</span></span> <span data-ttu-id="63b00-149">由于模型允许分类为超过两个类别，因此这是[多类别分类器](../resources/tasks.md#multiclass-classification)示例。</span><span class="sxs-lookup"><span data-stu-id="63b00-149">As your model allows you to classify more than two categories, this is an example of a [multi-class classifier](../resources/tasks.md#multiclass-classification).</span></span> 

<span data-ttu-id="63b00-150">`TensorFlow` 是热门深度学习和机器学习工具包，可用于定型深度神经网络（和常规数值计算），并在 ML.NET 中实现为 `transformer`。</span><span class="sxs-lookup"><span data-stu-id="63b00-150">`TensorFlow` is a popular deep learning and machine learning toolkit that enables training deep neural networks (and general numeric computations), and is implemented as a `transformer` in ML.NET.</span></span> <span data-ttu-id="63b00-151">在本教程中，它用于重用 `Inception model`。</span><span class="sxs-lookup"><span data-stu-id="63b00-151">For this tutorial, it's used to reuse the `Inception model`.</span></span>

<span data-ttu-id="63b00-152">如下图中所示，在 .NET Core 或 .NET Framework 应用中添加对 ML.NET NuGet 包的引用。</span><span class="sxs-lookup"><span data-stu-id="63b00-152">As shown in the following diagram, you add a reference to the ML.NET NuGet packages in your .NET Core or .NET Framework applications.</span></span> <span data-ttu-id="63b00-153">实际上，ML.NET 包含并引用本机 `TensorFlow` 库，可用于编写代码来加载已定型的现有 `TensorFlow` 模型文件以进行评分。</span><span class="sxs-lookup"><span data-stu-id="63b00-153">Under the covers, ML.NET includes and references the native `TensorFlow` library that allows you to write code that loads an existing trained `TensorFlow` model file for scoring.</span></span>  

![TensorFlow 转换 ML.NET 体系结构图](./media/image-classification/tensorflow-mlnet.png)

<span data-ttu-id="63b00-155">`Inception model` 定型为将图像分类为 1000 个类别，但你只需要在更小的类别集中分类图像。</span><span class="sxs-lookup"><span data-stu-id="63b00-155">The `Inception model` is trained to classify images into a thousand categories, but you need to classify images in a smaller category set, and only those categories.</span></span> <span data-ttu-id="63b00-156">输入 `transfer learning` 的 `transfer` 部分。</span><span class="sxs-lookup"><span data-stu-id="63b00-156">Enter the `transfer` part of `transfer learning`.</span></span> <span data-ttu-id="63b00-157">可以将 `Inception model` 的识别和分类图像功能迁移到自定义图像分类器的新受限类别。</span><span class="sxs-lookup"><span data-stu-id="63b00-157">You can transfer the `Inception model`'s ability to recognize and classify images to the new limited categories of your custom image classifier.</span></span>  

 <span data-ttu-id="63b00-158">你将使用以下三个类别来重新定型此模型中的最后一层：</span><span class="sxs-lookup"><span data-stu-id="63b00-158">You're going to retrain the final layer of that model using a set of three categories:</span></span>

* <span data-ttu-id="63b00-159">食物</span><span class="sxs-lookup"><span data-stu-id="63b00-159">Food</span></span>
* <span data-ttu-id="63b00-160">玩具</span><span class="sxs-lookup"><span data-stu-id="63b00-160">Toy</span></span>
* <span data-ttu-id="63b00-161">家用电器</span><span class="sxs-lookup"><span data-stu-id="63b00-161">Appliance</span></span>

<span data-ttu-id="63b00-162">你的层使用[多项逻辑回归算法](https://en.wikipedia.org/wiki/Multinomial_logistic_regression)尽可能快地找到正确的类别。</span><span class="sxs-lookup"><span data-stu-id="63b00-162">Your layer uses a [multinomial logistic regression algorithm](https://en.wikipedia.org/wiki/Multinomial_logistic_regression) to find the correct category as quickly as possible.</span></span> <span data-ttu-id="63b00-163">此算法使用概率来确定答案，向正确类别提供值 1，向其他类别提供值 0，从而进行分类。</span><span class="sxs-lookup"><span data-stu-id="63b00-163">This algorithm classifies using probabilities to determine the answer, giving a one value to the correct category and a zero value to the others.</span></span>  

### <a name="dataset"></a><span data-ttu-id="63b00-164">数据集</span><span class="sxs-lookup"><span data-stu-id="63b00-164">DataSet</span></span>

<span data-ttu-id="63b00-165">数据源有两个：`.tsv` 文件和图像文件。</span><span class="sxs-lookup"><span data-stu-id="63b00-165">There are two data sources: the `.tsv` file, and the image files.</span></span>  <span data-ttu-id="63b00-166">`tags.tsv` 文件包含两个列：第一列定义为 `ImagePath`，第二列是与图像对应的 `Label`。</span><span class="sxs-lookup"><span data-stu-id="63b00-166">The `tags.tsv` file contains two columns: the first one is defined as `ImagePath` and the second one is the `Label` corresponding to the image.</span></span> <span data-ttu-id="63b00-167">下面的示例文件没有标题行，如下所示：</span><span class="sxs-lookup"><span data-stu-id="63b00-167">The following example file doesn't have a header row, and looks like this:</span></span>

<!-- markdownlint-disable MD010 -->
```tsv
broccoli.jpg    food
pizza.jpg   food
pizza2.jpg  food
teddy2.jpg  toy
teddy3.jpg  toy
teddy4.jpg  toy
toaster.jpg appliance
toaster2.png    appliance
```
<!-- markdownlint-enable MD010 -->

<span data-ttu-id="63b00-168">定型图像和测试图像位于下载 zip 文件的资产文件夹中。</span><span class="sxs-lookup"><span data-stu-id="63b00-168">The training and testing images are located in the assets folders that you'll download in a zip file.</span></span> <span data-ttu-id="63b00-169">这些图像属于维基共享资源。</span><span class="sxs-lookup"><span data-stu-id="63b00-169">These images belong to Wikimedia Commons.</span></span>
> <span data-ttu-id="63b00-170">[维基共享资源](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208)，免费媒体存储库。</span><span class="sxs-lookup"><span data-stu-id="63b00-170">*[Wikimedia Commons](https://commons.wikimedia.org/w/index.php?title=Main_Page&oldid=313158208), the free media repository.*</span></span> <span data-ttu-id="63b00-171">检索时间：2018 年 10 月 17 日 10:48 检索位置：</span><span class="sxs-lookup"><span data-stu-id="63b00-171">Retrieved 10:48, October 17, 2018 from:</span></span>  
> https://commons.wikimedia.org/wiki/Pizza  
> https://commons.wikimedia.org/wiki/Toaster  
> https://commons.wikimedia.org/wiki/Teddy_bear  

## <a name="create-a-console-application"></a><span data-ttu-id="63b00-172">创建控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="63b00-172">Create a console application</span></span>

### <a name="create-a-project"></a><span data-ttu-id="63b00-173">创建项目</span><span class="sxs-lookup"><span data-stu-id="63b00-173">Create a project</span></span>

1. <span data-ttu-id="63b00-174">创建名为“TransferLearningTF”的 **.NET Core 控制台应用程序**。</span><span class="sxs-lookup"><span data-stu-id="63b00-174">Create a **.NET Core Console Application** called "TransferLearningTF".</span></span>

2. <span data-ttu-id="63b00-175">安装“Microsoft.ML NuGet 包”：</span><span class="sxs-lookup"><span data-stu-id="63b00-175">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="63b00-176">在“解决方案资源管理器”中，右键单击项目，然后选择“管理 NuGet 包”。</span><span class="sxs-lookup"><span data-stu-id="63b00-176">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="63b00-177">选择“nuget.org”作为“包源”，选择“浏览”选项卡，再搜索“Microsoft.ML”。</span><span class="sxs-lookup"><span data-stu-id="63b00-177">Choose "nuget.org" as the Package source, select the Browse tab, search for **Microsoft.ML**.</span></span> <span data-ttu-id="63b00-178">单击“版本”下拉列表，选择列表中的“1.0.0”包，然后选择“安装”按钮。</span><span class="sxs-lookup"><span data-stu-id="63b00-178">Click on the **Version** drop-down, select the **1.0.0** package in the list, and select the **Install** button.</span></span> <span data-ttu-id="63b00-179">选择“预览更改”对话框上的“确定”按钮，如果你同意所列包的许可条款，则选择“接受许可”对话框上的“我接受”按钮。</span><span class="sxs-lookup"><span data-stu-id="63b00-179">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span> <span data-ttu-id="63b00-180">对 **Microsoft.ML.ImageAnalytics v1.0.0** 和 **Microsoft.ML.TensorFlow v0.12.0** 重复这些步骤。</span><span class="sxs-lookup"><span data-stu-id="63b00-180">Repeat these steps for **Microsoft.ML.ImageAnalytics v1.0.0** and **Microsoft.ML.TensorFlow v0.12.0**.</span></span>

### <a name="prepare-your-data"></a><span data-ttu-id="63b00-181">准备数据</span><span class="sxs-lookup"><span data-stu-id="63b00-181">Prepare your data</span></span>

1. <span data-ttu-id="63b00-182">下载并解压缩[项目资产目录 zip 文件](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip)。</span><span class="sxs-lookup"><span data-stu-id="63b00-182">Download [The project assets directory zip file](https://download.microsoft.com/download/0/E/5/0E5E0136-21CE-4C66-AC18-9917DED8A4AD/image-classifier-assets.zip), and unzip.</span></span>

2. <span data-ttu-id="63b00-183">将“`assets`”目录复制到“TransferLearningTF”项目目录中。</span><span class="sxs-lookup"><span data-stu-id="63b00-183">Copy the `assets` directory into your *TransferLearningTF* project directory.</span></span> <span data-ttu-id="63b00-184">此目录及其子目录包含本教程所需的数据和支持文件（Inception 模型除外，将在下一步中下载并添加此模型）。</span><span class="sxs-lookup"><span data-stu-id="63b00-184">This directory and its subdirectories contain the data and support files (except for the Inception model, which you'll download and add in the next step) needed for this tutorial.</span></span>

3. <span data-ttu-id="63b00-185">下载并解压缩 [Inception 模型](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip)。</span><span class="sxs-lookup"><span data-stu-id="63b00-185">Download the [Inception model](https://storage.googleapis.com/download.tensorflow.org/models/inception5h.zip), and unzip.</span></span>

4. <span data-ttu-id="63b00-186">将刚刚解压缩的“`inception5h`”目录的内容复制到 TransferLearningTF 项目的“`assets\inputs-train\inception`”目录中。</span><span class="sxs-lookup"><span data-stu-id="63b00-186">Copy the contents of the `inception5h` directory just unzipped into your *TransferLearningTF* project `assets\inputs-train\inception` directory.</span></span> <span data-ttu-id="63b00-187">此目录包含本教程所需的模型和其他支持文件，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="63b00-187">This directory contains the model and additional support files needed for this tutorial, as shown in the following image:</span></span>

   ![Inception 目录内容](./media/image-classification/inception-files.png)

5. <span data-ttu-id="63b00-189">在“解决方案资源管理器”中，右键单击资产目录和子目录中的每个文件，再选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="63b00-189">In Solution Explorer, right-click each of the files in the asset directory and subdirectories and select **Properties**.</span></span> <span data-ttu-id="63b00-190">在“高级”下，将“复制到输出目录”的值更改为“如果较新则复制”。</span><span class="sxs-lookup"><span data-stu-id="63b00-190">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="63b00-191">创建类和定义路径</span><span class="sxs-lookup"><span data-stu-id="63b00-191">Create classes and define paths</span></span>

<span data-ttu-id="63b00-192">将以下附加的 `using` 语句添加到“Program.cs”文件顶部：</span><span class="sxs-lookup"><span data-stu-id="63b00-192">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddUsings)]

<span data-ttu-id="63b00-193">创建全局字段，用于保留各种资产的路径，以及 `LabelTokey`、`ImageReal` 和 `PredictedLabelValue` 的全局变量：</span><span class="sxs-lookup"><span data-stu-id="63b00-193">Create global fields to hold the paths to the various assets, and global variables for the `LabelTokey`,`ImageReal`, and  `PredictedLabelValue`:</span></span>

* <span data-ttu-id="63b00-194">`_assetsPath` 包含资产的路径。</span><span class="sxs-lookup"><span data-stu-id="63b00-194">`_assetsPath` has the path to the assets.</span></span>
* <span data-ttu-id="63b00-195">`_trainTagsTsv` 包含定型图像数据标记 tsv 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="63b00-195">`_trainTagsTsv` has the path to the training image data tags tsv file.</span></span>
* <span data-ttu-id="63b00-196">`_predictTagsTsv` 包含预测图像数据标记 tsv 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="63b00-196">`_predictTagsTsv` has the path to the prediction image data tags tsv file.</span></span>
* <span data-ttu-id="63b00-197">`_trainImagesFolder` 包含用于定型模型的图像的路径。</span><span class="sxs-lookup"><span data-stu-id="63b00-197">`_trainImagesFolder` has the path to the images used to train the model.</span></span>
* <span data-ttu-id="63b00-198">`_predictImagesFolder` 包含已定型的模型要分类的图像的路径。</span><span class="sxs-lookup"><span data-stu-id="63b00-198">`_predictImagesFolder` has the path to the images to be classified by the trained model.</span></span>
* <span data-ttu-id="63b00-199">`_inceptionPb` 包含要重用于重新定型模型的预定型 Inception 模型的路径。</span><span class="sxs-lookup"><span data-stu-id="63b00-199">`_inceptionPb` has the path to the pre-trained Inception model to be reused to retrain your model.</span></span>
* <span data-ttu-id="63b00-200">`_inputImageClassifierZip` 包含从中加载已定型的模型的路径。</span><span class="sxs-lookup"><span data-stu-id="63b00-200">`_inputImageClassifierZip` has the path where the trained model is loaded from.</span></span>
* <span data-ttu-id="63b00-201">`_outputImageClassifierZip` 具有在其中保存定型模型的路径。</span><span class="sxs-lookup"><span data-stu-id="63b00-201">`_outputImageClassifierZip` has the path where the trained model is saved.</span></span>
* <span data-ttu-id="63b00-202">`LabelTokey` 是映射到键的 `Label` 值。</span><span class="sxs-lookup"><span data-stu-id="63b00-202">`LabelTokey` is the `Label` value mapped to a key.</span></span>
* <span data-ttu-id="63b00-203">`ImageReal` 是包含预测出的图像值的列。</span><span class="sxs-lookup"><span data-stu-id="63b00-203">`ImageReal`  is the column containing the predicted image value.</span></span>
* <span data-ttu-id="63b00-204">`PredictedLabelValue` 是包含预测出的标签值的列。</span><span class="sxs-lookup"><span data-stu-id="63b00-204">`PredictedLabelValue` is the column containing the predicted label value.</span></span>

<span data-ttu-id="63b00-205">将以下代码添加到 `Main` 方法正上方的行中以指定这些路径和其他变量：</span><span class="sxs-lookup"><span data-stu-id="63b00-205">Add the following code to the line right above the `Main` method to specify those paths and the other variables:</span></span>

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DeclareGlobalVariables)]

<span data-ttu-id="63b00-206">为输入数据和预测结果创建一些类。</span><span class="sxs-lookup"><span data-stu-id="63b00-206">Create some classes for your input data, and predictions.</span></span> <span data-ttu-id="63b00-207">向项目添加一个新类：</span><span class="sxs-lookup"><span data-stu-id="63b00-207">Add a new class to your project:</span></span>

1. <span data-ttu-id="63b00-208">在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新项”。</span><span class="sxs-lookup"><span data-stu-id="63b00-208">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="63b00-209">在“添加新项”对话框中，选择“类”，并将“名称”字段更改为“ImageData.cs”。</span><span class="sxs-lookup"><span data-stu-id="63b00-209">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *ImageData.cs*.</span></span> <span data-ttu-id="63b00-210">然后，选择“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="63b00-210">Then, select the **Add** button.</span></span>

    <span data-ttu-id="63b00-211">此时，ImageData.cs 文件在代码编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="63b00-211">The *ImageData.cs* file opens in the code editor.</span></span> <span data-ttu-id="63b00-212">将下面的 `using` 语句添加到 ImageData.cs 顶部：</span><span class="sxs-lookup"><span data-stu-id="63b00-212">Add the following `using` statement to the top of *ImageData.cs*:</span></span>

[!code-csharp[AddUsings](../../../samples/machine-learning/tutorials/TransferLearningTF/ImageData.cs#AddUsings)]

<span data-ttu-id="63b00-213">删除现有类定义，并将 `ImageData` 类的以下代码添加到 ImageData.cs 文件中：</span><span class="sxs-lookup"><span data-stu-id="63b00-213">Remove the existing class definition and add the following code for the `ImageData` class to the *ImageData.cs* file:</span></span>

[!code-csharp[DeclareTypes](../../../samples/machine-learning/tutorials/TransferLearningTF/ImageData.cs#DeclareTypes)]

<span data-ttu-id="63b00-214">`ImageData` 是输入图像数据类，包含以下 <xref:System.String> 字段：</span><span class="sxs-lookup"><span data-stu-id="63b00-214">`ImageData` is the input image data class and has the following <xref:System.String> fields:</span></span>

* <span data-ttu-id="63b00-215">`ImagePath` 包含图像文件名。</span><span class="sxs-lookup"><span data-stu-id="63b00-215">`ImagePath` contains the image file name.</span></span>
* <span data-ttu-id="63b00-216">`Label` 包含图像标签值。</span><span class="sxs-lookup"><span data-stu-id="63b00-216">`Label` contains a value for the image label.</span></span>

<span data-ttu-id="63b00-217">向项目添加 `ImagePrediction` 的新类：</span><span class="sxs-lookup"><span data-stu-id="63b00-217">Add a new class to your project for `ImagePrediction`:</span></span>

1. <span data-ttu-id="63b00-218">在“解决方案资源管理器”中，右键单击项目，然后选择“添加” > “新项”。</span><span class="sxs-lookup"><span data-stu-id="63b00-218">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

1. <span data-ttu-id="63b00-219">在“添加新项”对话框中，选择“类”，并将“名称”字段更改为“ImagePrediction.cs”。</span><span class="sxs-lookup"><span data-stu-id="63b00-219">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *ImagePrediction.cs*.</span></span> <span data-ttu-id="63b00-220">然后，选择“添加”按钮。</span><span class="sxs-lookup"><span data-stu-id="63b00-220">Then, select the **Add** button.</span></span>

    <span data-ttu-id="63b00-221">此时，ImagePrediction.cs 文件在代码编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="63b00-221">The *ImagePrediction.cs* file opens in the code editor.</span></span> <span data-ttu-id="63b00-222">删除 ImagePrediction.cs 顶部的 `System.Collections.Generic` 和 `System.Text` `using` 语句：</span><span class="sxs-lookup"><span data-stu-id="63b00-222">Remove both the `System.Collections.Generic` and the `System.Text` `using` statements at the top of *ImagePrediction.cs*:</span></span>

<span data-ttu-id="63b00-223">删除现有类定义，并将包含 `ImagePrediction` 类的以下代码添加到 ImagePrediction.cs 文件中：</span><span class="sxs-lookup"><span data-stu-id="63b00-223">Remove the existing class definition and add the following code, which has the `ImagePrediction` class, to the *ImagePrediction.cs* file:</span></span>

[!code-csharp[DeclareGlobalVariables](../../../samples/machine-learning/tutorials/TransferLearningTF/ImagePrediction.cs#DeclareTypes)]

<span data-ttu-id="63b00-224">`ImagePrediction` 是图像预测类，包含以下字段：</span><span class="sxs-lookup"><span data-stu-id="63b00-224">`ImagePrediction` is the image prediction class and has the following fields:</span></span>

* <span data-ttu-id="63b00-225">`Score` 包含给定图像分类的置信度百分比。</span><span class="sxs-lookup"><span data-stu-id="63b00-225">`Score` contains the confidence percentage for a given image classification.</span></span>
* <span data-ttu-id="63b00-226">`PredictedLabelValue` 包含预测出的图像分类标签的值。</span><span class="sxs-lookup"><span data-stu-id="63b00-226">`PredictedLabelValue` contains a value for the predicted image classification label.</span></span>

<span data-ttu-id="63b00-227">`ImagePrediction` 是在定型模型后用于预测的类。</span><span class="sxs-lookup"><span data-stu-id="63b00-227">`ImagePrediction` is the class used for prediction after the model has been trained.</span></span> <span data-ttu-id="63b00-228">它包含图像路径的 `string` (`ImagePath`)。</span><span class="sxs-lookup"><span data-stu-id="63b00-228">It has a `string` (`ImagePath`) for the image path.</span></span> <span data-ttu-id="63b00-229">`Label` 用于重用和重新定型模型。</span><span class="sxs-lookup"><span data-stu-id="63b00-229">The `Label` is used to reuse and retrain the model.</span></span> <span data-ttu-id="63b00-230">`PredictedLabelValue` 在预测和评估过程中使用。</span><span class="sxs-lookup"><span data-stu-id="63b00-230">The `PredictedLabelValue` is used during prediction and evaluation.</span></span> <span data-ttu-id="63b00-231">对于计算，将使用带定型数据的输入、预测值和模型。</span><span class="sxs-lookup"><span data-stu-id="63b00-231">For evaluation, an input with training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="63b00-232">执行所有 ML.NET 操作都是从 [MLContext 类](xref:Microsoft.ML.MLContext)开始，初始化 `mlContext` 可创建一个新的 ML.NET 环境，可在模型创建工作流对象之间共享该环境。</span><span class="sxs-lookup"><span data-stu-id="63b00-232">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations, and initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="63b00-233">从概念上讲，它与实体框架中的 `DBContext` 类似。</span><span class="sxs-lookup"><span data-stu-id="63b00-233">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

### <a name="initialize-variables-in-main"></a><span data-ttu-id="63b00-234">在 Main 中初始化变量</span><span class="sxs-lookup"><span data-stu-id="63b00-234">Initialize variables in Main</span></span>

<span data-ttu-id="63b00-235">使用 `MLContext` 的新实例初始化 `mlContext` 变量。</span><span class="sxs-lookup"><span data-stu-id="63b00-235">Initialize the `mlContext` variable with a new instance of `MLContext`.</span></span>  <span data-ttu-id="63b00-236">用下面 `Main` 方法中的代码替换 `Console.WriteLine("Hello World!")` 行：</span><span class="sxs-lookup"><span data-stu-id="63b00-236">Replace the `Console.WriteLine("Hello World!")` line with the following code in the `Main` method:</span></span>

[!code-csharp[CreateMLContext](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CreateMLContext)]

### <a name="create-a-struct-for-default-parameters"></a><span data-ttu-id="63b00-237">创建默认参数的结构</span><span class="sxs-lookup"><span data-stu-id="63b00-237">Create a struct for default parameters</span></span>

<span data-ttu-id="63b00-238">需要传入 Inception 模型的多个默认参数。</span><span class="sxs-lookup"><span data-stu-id="63b00-238">The Inception model has several default parameters you need to pass in.</span></span> <span data-ttu-id="63b00-239">紧跟在 `Main()` 方法后面，使用以下代码创建结构，以将默认参数值映射到易记名称：</span><span class="sxs-lookup"><span data-stu-id="63b00-239">Create a struct to map the default parameter values to friendly names with the following code, just after the `Main()` method:</span></span>

[!code-csharp[InceptionSettings](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#InceptionSettings)]

### <a name="create-a-display-utility-method"></a><span data-ttu-id="63b00-240">创建显示实用工具方法</span><span class="sxs-lookup"><span data-stu-id="63b00-240">Create a display utility method</span></span>

<span data-ttu-id="63b00-241">由于将多次显示图像数据和相关预测，请创建显示实用工具方法，用于处理图像和预测结果的显示。</span><span class="sxs-lookup"><span data-stu-id="63b00-241">Since you'll display the image data and the related predictions more than once, create a display utility method to handle displaying the image and prediction results.</span></span>

<span data-ttu-id="63b00-242">`DisplayResults()` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="63b00-242">The `DisplayResults()` method executes the following tasks:</span></span>

* <span data-ttu-id="63b00-243">显示预测结果。</span><span class="sxs-lookup"><span data-stu-id="63b00-243">Displays the predicted results.</span></span>

<span data-ttu-id="63b00-244">紧跟在 `InceptionSettings` 结构后面，使用下面的代码创建 `DisplayResults()` 方法：</span><span class="sxs-lookup"><span data-stu-id="63b00-244">Create the `DisplayResults()` method, just after the `InceptionSettings` struct, using the following code:</span></span>

```csharp
private static void DisplayResults(IEnumerable<ImagePrediction> imagePredictionData)
{

}
```

<span data-ttu-id="63b00-245">`Transform()` 方法在 `ImagePrediction` 中填充 `ImagePath` 以及预测的字段。</span><span class="sxs-lookup"><span data-stu-id="63b00-245">The `Transform()` method populated `ImagePath` in `ImagePrediction` along with the predicted fields.</span></span> <span data-ttu-id="63b00-246">随着 ML.NET 进程继续执行，每个组件会添加列，这让显示结果变得轻松：</span><span class="sxs-lookup"><span data-stu-id="63b00-246">As the ML.NET process progresses, each component adds columns, and this makes it easy to display the results:</span></span>

[!code-csharp[DisplayPredictions](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPredictions)]

<span data-ttu-id="63b00-247">将在两个图像分类方法中调用 `DisplayResults()` 方法。</span><span class="sxs-lookup"><span data-stu-id="63b00-247">You'll call the `DisplayResults()` method in the two image classification methods.</span></span>

### <a name="create-a-tsv-file-utility-method"></a><span data-ttu-id="63b00-248">创建 .tsv 文件实用工具方法</span><span class="sxs-lookup"><span data-stu-id="63b00-248">Create a .tsv file utility method</span></span>

<span data-ttu-id="63b00-249">`ReadFromTsv()` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="63b00-249">The `ReadFromTsv()` method executes the following tasks:</span></span>

* <span data-ttu-id="63b00-250">读取图像数据 `tags.tsv` 文件。</span><span class="sxs-lookup"><span data-stu-id="63b00-250">Reads the image data `tags.tsv` file.</span></span>
* <span data-ttu-id="63b00-251">将文件路径添加到图像文件名中。</span><span class="sxs-lookup"><span data-stu-id="63b00-251">Adds the file path to the image file name.</span></span>
* <span data-ttu-id="63b00-252">将文件数据加载到 IEnumerable`ImageData` 对象中。</span><span class="sxs-lookup"><span data-stu-id="63b00-252">Loads the file data into an IEnumerable`ImageData` object.</span></span>

<span data-ttu-id="63b00-253">使用下面的代码紧随 `PairAndDisplayResults()` 方法后创建 `ReadFromTsv()` 方法：</span><span class="sxs-lookup"><span data-stu-id="63b00-253">Create the `ReadFromTsv()` method, just after the `PairAndDisplayResults()` method, using the following code:</span></span>

```csharp
public static IEnumerable<ImageData> ReadFromTsv(string file, string folder)
{

}
```

<span data-ttu-id="63b00-254">下面的代码分析整个 `tags.tsv` 文件，以将文件路径添加到 `ImagePath` 属性的图像文件名中，并将它和 `Label` 加载到 `ImageData` 对象中。</span><span class="sxs-lookup"><span data-stu-id="63b00-254">The following code parses through the `tags.tsv` file to add the file path to the image file name for the `ImagePath` property and load it and the `Label` into an `ImageData` object.</span></span> <span data-ttu-id="63b00-255">将它添加为 `ReadFromTsv()` 方法的第一行。</span><span class="sxs-lookup"><span data-stu-id="63b00-255">Add it as the first line of the `ReadFromTsv()` method.</span></span>  <span data-ttu-id="63b00-256">必须有完全限定的文件路径，才能显示预测结果。</span><span class="sxs-lookup"><span data-stu-id="63b00-256">You need the fully qualified file path to display the prediction results.</span></span>

[!code-csharp[ReadFromTsv](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReadFromTsv)]
<span data-ttu-id="63b00-257">ML.NET 中包含三个主要概念：[数据](../resources/glossary.md#data)、[转换器](../resources/glossary.md#transformer)和[估算器](../resources/glossary.md#estimator)。</span><span class="sxs-lookup"><span data-stu-id="63b00-257">There are three major concepts in ML.NET: [Data](../resources/glossary.md#data), [Transformers](../resources/glossary.md#transformer), and [Estimators](../resources/glossary.md#estimator).</span></span>

## <a name="reuse-and-tune-pre-trained-model"></a><span data-ttu-id="63b00-258">重用和优化预定型模型</span><span class="sxs-lookup"><span data-stu-id="63b00-258">Reuse and tune pre-trained model</span></span>

<span data-ttu-id="63b00-259">将以下调用添加到 `ReuseAndTuneInceptionModel()` 方法作为 `Main()` 方法的下一行代码：</span><span class="sxs-lookup"><span data-stu-id="63b00-259">Add the following call to the `ReuseAndTuneInceptionModel()`method as the next line of code in the `Main()` method:</span></span>

[!code-csharp[CallReuseAndTuneInceptionModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallReuseAndTuneInceptionModel)]

<span data-ttu-id="63b00-260">`ReuseAndTuneInceptionModel()` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="63b00-260">The `ReuseAndTuneInceptionModel()` method executes the following tasks:</span></span>

* <span data-ttu-id="63b00-261">加载数据</span><span class="sxs-lookup"><span data-stu-id="63b00-261">Loads the data</span></span>
* <span data-ttu-id="63b00-262">提取并转换数据。</span><span class="sxs-lookup"><span data-stu-id="63b00-262">Extracts and transforms the data.</span></span>
* <span data-ttu-id="63b00-263">对 TensorFlow 模型评分。</span><span class="sxs-lookup"><span data-stu-id="63b00-263">Scores the TensorFlow model.</span></span>
* <span data-ttu-id="63b00-264">优化（重新定型）模型。</span><span class="sxs-lookup"><span data-stu-id="63b00-264">Tunes (retrains) the model.</span></span>
* <span data-ttu-id="63b00-265">显示模型结果。</span><span class="sxs-lookup"><span data-stu-id="63b00-265">Displays model results.</span></span>
* <span data-ttu-id="63b00-266">评估模型。</span><span class="sxs-lookup"><span data-stu-id="63b00-266">Evaluates the model.</span></span>
* <span data-ttu-id="63b00-267">返回模型。</span><span class="sxs-lookup"><span data-stu-id="63b00-267">Returns the model.</span></span>

<span data-ttu-id="63b00-268">紧跟在 `InceptionSettings` 结构后面且恰好在 `DisplayResults()` 方法前面，使用以下代码创建 `ReuseAndTuneInceptionModel()` 方法：</span><span class="sxs-lookup"><span data-stu-id="63b00-268">Create the `ReuseAndTuneInceptionModel()` method, just after the `InceptionSettings` struct and just before the `DisplayResults()` method, using the following code:</span></span>

```csharp
public static ITransformer ReuseAndTuneInceptionModel(MLContext mlContext, string dataLocation, string imagesFolder, string inputModelLocation, string outputModelLocation)
{

}
```

### <a name="load-the-data"></a><span data-ttu-id="63b00-269">加载数据</span><span class="sxs-lookup"><span data-stu-id="63b00-269">Load the data</span></span>

<span data-ttu-id="63b00-270">ML.NET 中的数据表示为 [IDataView 类](xref:Microsoft.ML.IDataView)。</span><span class="sxs-lookup"><span data-stu-id="63b00-270">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="63b00-271">`IDataView` 是用于描述表格数据（数字和文本）的一种灵活且有效的方法。</span><span class="sxs-lookup"><span data-stu-id="63b00-271">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="63b00-272">可从文本文件或实时（例如，SQL 数据库或日志文件）将数据加载到 `IDataView` 对象。</span><span class="sxs-lookup"><span data-stu-id="63b00-272">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span>

<span data-ttu-id="63b00-273">使用 `MLContext.Data.LoadFromTextFile` 包装器加载数据。</span><span class="sxs-lookup"><span data-stu-id="63b00-273">Load the data using the `MLContext.Data.LoadFromTextFile` wrapper.</span></span> <span data-ttu-id="63b00-274">将以下代码作为下一行添加到 `ReuseAndTuneInceptionModel()` 方法中：</span><span class="sxs-lookup"><span data-stu-id="63b00-274">Add the following code as the next line in the `ReuseAndTuneInceptionModel()` method:</span></span>

[!code-csharp[LoadData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadData "Load the data")]

### <a name="extract-features-and-transform-the-data"></a><span data-ttu-id="63b00-275">提取功能和转换数据</span><span class="sxs-lookup"><span data-stu-id="63b00-275">Extract Features and transform the data</span></span>

<span data-ttu-id="63b00-276">预处理和清除数据任务至关重要，需要首先执行才能将数据集有效地用于机器学习。</span><span class="sxs-lookup"><span data-stu-id="63b00-276">Pre-processing and cleaning data are important tasks that occur before a dataset is used effectively for machine learning.</span></span>  <span data-ttu-id="63b00-277">在没有这些建模任务的情况下使用数据会产生误导性结果。</span><span class="sxs-lookup"><span data-stu-id="63b00-277">Using data without these modeling tasks can produce misleading results.</span></span>

<span data-ttu-id="63b00-278">机器学习算法理解[特征化](../resources/glossary.md#feature)数据，因此在处理深度神经网络时，必须将图像调整为网络所需的格式。</span><span class="sxs-lookup"><span data-stu-id="63b00-278">Machine learning algorithms understand [featurized](../resources/glossary.md#feature) data, and when dealing with deep neural networks you must adapt the images to the format expected by the network.</span></span> <span data-ttu-id="63b00-279">该格式是[数值向量](../resources/glossary.md#numerical-feature-vector)。</span><span class="sxs-lookup"><span data-stu-id="63b00-279">That format is a [numeric vector](../resources/glossary.md#numerical-feature-vector).</span></span>

<span data-ttu-id="63b00-280">定型和评估后，预测“标签”列值。</span><span class="sxs-lookup"><span data-stu-id="63b00-280">After training and evaluation, predict with the **Label** column values.</span></span> <span data-ttu-id="63b00-281">由于使用的是预定型模型，因此使用 [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) 方法将字段映射到新模型。</span><span class="sxs-lookup"><span data-stu-id="63b00-281">As you're using a pre-trained model, map fields to the new model with the [MapValueToKey()](xref:Microsoft.ML.ConversionsExtensionsCatalog.MapValueToKey%2A) method.</span></span> <span data-ttu-id="63b00-282">此方法会将 `Label` 转换为数值键类型 (`LabelTokey`) 列，并将它添加为新数据集列：将此命名为 `estimator`，因为还会向它添加定型程序。</span><span class="sxs-lookup"><span data-stu-id="63b00-282">This method transforms the `Label` into a numeric key type (`LabelTokey`) column and add it as new dataset column:  Name this `estimator` as you'll also add the trainer to it.</span></span> <span data-ttu-id="63b00-283">添加下一个代码行：</span><span class="sxs-lookup"><span data-stu-id="63b00-283">Add the next line of code:</span></span>

[!code-csharp[MapValueToKey1](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapValueToKey1)]

<span data-ttu-id="63b00-284">图像处理估算器使用预定型[深度神经网络 (DNN)](https://en.wikipedia.org/wiki/Deep_learning#Deep_neural_networks) 特征提取器来提取特征。</span><span class="sxs-lookup"><span data-stu-id="63b00-284">Your image processing estimator uses pre-trained [Deep Neural Network(DNN)](https://en.wikipedia.org/wiki/Deep_learning#Deep_neural_networks) featurizers for feature extraction.</span></span> <span data-ttu-id="63b00-285">处理深度神经网络时，将图像调整为所需的网络格式。</span><span class="sxs-lookup"><span data-stu-id="63b00-285">When dealing with deep neural networks, you  adapt the images to the expected network format.</span></span> <span data-ttu-id="63b00-286">正因为此，你使用多个图像转换将图像数据转换为模型所需的格式：</span><span class="sxs-lookup"><span data-stu-id="63b00-286">This is the reason you use several image transforms to get the image data into the model's expected form:</span></span>

1. <span data-ttu-id="63b00-287">`LoadImages` 转换图像作为位图类型加载到内存中。</span><span class="sxs-lookup"><span data-stu-id="63b00-287">The `LoadImages`transform images are loaded in memory as a Bitmap type.</span></span>
2. <span data-ttu-id="63b00-288">`ResizeImages` 转换可重设图像大小，因为预定型模型有已定义的输入图像宽度和高度。</span><span class="sxs-lookup"><span data-stu-id="63b00-288">The `ResizeImages` transform resizes the images as the pre-trained model has a defined input image width and height.</span></span>
3. <span data-ttu-id="63b00-289">`ExtractPixels` 转换可提取输入图像中的像素，并将它们转换为数值向量。</span><span class="sxs-lookup"><span data-stu-id="63b00-289">The `ExtractPixels` transform extracts the pixels from the input images and converts them into a numeric vector.</span></span>

<span data-ttu-id="63b00-290">将这些图像转换添加为接下来的几行代码：</span><span class="sxs-lookup"><span data-stu-id="63b00-290">Add these image transforms as the next lines of code:</span></span>

[!code-csharp[ImageTransforms](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ImageTransforms)]

<span data-ttu-id="63b00-291">`LoadTensorFlowModel` 是一种便捷方法，允许加载一次 `TensorFlow` 模型，然后使用 `ScoreTensorFlowModel` 创建 `TensorFlowEstimator`。</span><span class="sxs-lookup"><span data-stu-id="63b00-291">The `LoadTensorFlowModel` is a convenience method that allows the `TensorFlow` model to be loaded once and then creates the `TensorFlowEstimator` using `ScoreTensorFlowModel`.</span></span> <span data-ttu-id="63b00-292">`ScoreTensorFlowModel` 提取指定输出（`Inception model` 的图像特征 `softmax2_pre_activation`），并使用预定型 `TensorFlow` 模型对数据集进行评分。</span><span class="sxs-lookup"><span data-stu-id="63b00-292">The `ScoreTensorFlowModel` extracts specified outputs (the `Inception model`'s image features `softmax2_pre_activation`), and scores a dataset using the pre-trained `TensorFlow` model.</span></span>

<span data-ttu-id="63b00-293">`softmax2_pre_activation` 协助模型确定图像属于哪个类别。</span><span class="sxs-lookup"><span data-stu-id="63b00-293">`softmax2_pre_activation` assists the model with determining which class the images belongs to.</span></span> <span data-ttu-id="63b00-294">`softmax2_pre_activation` 返回图像每个类别的概率，所有这些概率的总和必须为 1。</span><span class="sxs-lookup"><span data-stu-id="63b00-294">`softmax2_pre_activation` returns a probability for each of the categories for an image, and all of those probabilities must add up to 1.</span></span> <span data-ttu-id="63b00-295">它假设图像仅属于一个类别，如下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="63b00-295">It assumes that an image will belong to only one category, as shown in the following example:</span></span>

| <span data-ttu-id="63b00-296">类</span><span class="sxs-lookup"><span data-stu-id="63b00-296">Class</span></span>         | <span data-ttu-id="63b00-297">概率</span><span class="sxs-lookup"><span data-stu-id="63b00-297">Probability</span></span>   |
| ------------- | ------------- |
| `Food`        |  <span data-ttu-id="63b00-298">0.001</span><span class="sxs-lookup"><span data-stu-id="63b00-298">0.001</span></span>        |
| `Toy`         |  <span data-ttu-id="63b00-299">0.95</span><span class="sxs-lookup"><span data-stu-id="63b00-299">0.95</span></span>         |
| `Appliance`   |  <span data-ttu-id="63b00-300">0.06</span><span class="sxs-lookup"><span data-stu-id="63b00-300">0.06</span></span>         |

<span data-ttu-id="63b00-301">使用以下代码行将 `TensorFlowTransform` 追加到 `estimator`：</span><span class="sxs-lookup"><span data-stu-id="63b00-301">Append the `TensorFlowTransform` to the `estimator` with the following line of code:</span></span>

[!code-csharp[ScoreTensorFlowModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ScoreTensorFlowModel)]

### <a name="choose-a-training-algorithm"></a><span data-ttu-id="63b00-302">选择定型算法</span><span class="sxs-lookup"><span data-stu-id="63b00-302">Choose a training algorithm</span></span>

<span data-ttu-id="63b00-303">若要添加定型算法，请调用 `mlContext.MulticlassClassification.Trainers.LbfgsMaximumEntropy()` 包装器方法。</span><span class="sxs-lookup"><span data-stu-id="63b00-303">To add the training algorithm, call the `mlContext.MulticlassClassification.Trainers.LbfgsMaximumEntropy()` wrapper method.</span></span>  <span data-ttu-id="63b00-304">[LbfgsMaximumEntropy](xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer) 追加到 `estimator` 中，并接受 Inception 图像特征 (`softmax2_pre_activation`) 和 `Label` 输入参数，以便从历史数据中学习。</span><span class="sxs-lookup"><span data-stu-id="63b00-304">The [LbfgsMaximumEntropy](xref:Microsoft.ML.Trainers.LbfgsMaximumEntropyMulticlassTrainer) is appended to the `estimator` and accepts the Inception image features (`softmax2_pre_activation`) and the `Label` input parameters to learn from the historic data.</span></span>  <span data-ttu-id="63b00-305">使用以下代码添加定型程序：</span><span class="sxs-lookup"><span data-stu-id="63b00-305">Add the trainer with the following code:</span></span>

[!code-csharp[AddTrainer](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#AddTrainer)]

<span data-ttu-id="63b00-306">还需要将 `predictedlabel` 映射到 `predictedlabelvalue`：</span><span class="sxs-lookup"><span data-stu-id="63b00-306">You also need to map the `predictedlabel` to the `predictedlabelvalue`:</span></span>

[!code-csharp[MapValueToKey2](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#MapValueToKey2)]

<span data-ttu-id="63b00-307">`Fit()` 方法通过转换数据集并应用训练来训练模型。</span><span class="sxs-lookup"><span data-stu-id="63b00-307">The `Fit()` method trains your model by transforming the dataset and applying the training.</span></span> <span data-ttu-id="63b00-308">在 `ReuseAndTuneInceptionModel()` 方法中添加以下代码作为下一行代码，使模型拟合训练数据集，并返回经过训练的模型：</span><span class="sxs-lookup"><span data-stu-id="63b00-308">Fit the model to the training dataset and return the trained model by adding the following as the next line of code in the `ReuseAndTuneInceptionModel()` method:</span></span>

[!code-csharp[TrainModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#TrainModel)]

<span data-ttu-id="63b00-309">[Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) 方法对测试数据集的多个提供的输入行进行预测。</span><span class="sxs-lookup"><span data-stu-id="63b00-309">The [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method makes predictions for multiple provided input rows of a test dataset.</span></span>  <span data-ttu-id="63b00-310">将以下代码添加到 `ReuseAndTuneInceptionModel()` 以转换 `Training` 数据：</span><span class="sxs-lookup"><span data-stu-id="63b00-310">Transform the `Training` data by adding the following code to `ReuseAndTuneInceptionModel()`:</span></span>

[!code-csharp[TransformData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#TransformData)]

<span data-ttu-id="63b00-311">为了更方便显示，将图像数据和预测 `DataViews` 转换为强类型 `IEnumerables`，以供配对。</span><span class="sxs-lookup"><span data-stu-id="63b00-311">Convert your image data and prediction `DataViews` into strongly-typed `IEnumerables` to pair for easier display.</span></span> <span data-ttu-id="63b00-312">为此，通过下面的代码使用 `MLContext.CreateEnumerable()` 方法：</span><span class="sxs-lookup"><span data-stu-id="63b00-312">Use the `MLContext.CreateEnumerable()` method to do that, using the following code:</span></span>

[!code-csharp[EnumerateDataViews](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#EnumerateDataViews)]

<span data-ttu-id="63b00-313">作为 `ReuseAndTuneInceptionModel()` 方法的下一行，调用 `DisplayResults()` 方法来显示数据和预测结果：</span><span class="sxs-lookup"><span data-stu-id="63b00-313">Call the `DisplayResults()` method to display your data and predictions as the next line in the `ReuseAndTuneInceptionModel()` method:</span></span>

[!code-csharp[CallDisplayResults1](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallDisplayResults1)]

<span data-ttu-id="63b00-314">在你设置预测后，[Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) 方法便能：</span><span class="sxs-lookup"><span data-stu-id="63b00-314">Once you have the prediction set, the [Evaluate()](xref:Microsoft.ML.RecommendationCatalog.Evaluate%2A) method:</span></span>

* <span data-ttu-id="63b00-315">评估模型（将预测出的值与实际数据集 `Labels` 进行比较）。</span><span class="sxs-lookup"><span data-stu-id="63b00-315">Assesses the model (compares the predicted values with the actual dataset `Labels`).</span></span>

* <span data-ttu-id="63b00-316">返回模型性能指标。</span><span class="sxs-lookup"><span data-stu-id="63b00-316">Returns the model performance metrics.</span></span>

<span data-ttu-id="63b00-317">将以下代码作为下一行添加到 `ReuseAndTuneInceptionModel()` 方法中：</span><span class="sxs-lookup"><span data-stu-id="63b00-317">Add the following code to the `ReuseAndTuneInceptionModel()` method as the next line:</span></span>

[!code-csharp[Evaluate](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#Evaluate)]

<span data-ttu-id="63b00-318">下面是图像分类评估指标：</span><span class="sxs-lookup"><span data-stu-id="63b00-318">The following metrics are evaluated for image classification:</span></span>

* <span data-ttu-id="63b00-319">`Log-loss` - 请参阅[对数损失](../resources/glossary.md#log-loss)。</span><span class="sxs-lookup"><span data-stu-id="63b00-319">`Log-loss` - see [Log Loss](../resources/glossary.md#log-loss).</span></span> <span data-ttu-id="63b00-320">通常会希望对数损失尽可能接近 0。</span><span class="sxs-lookup"><span data-stu-id="63b00-320">You want Log-loss to be as close to zero as possible.</span></span>

* <span data-ttu-id="63b00-321">`Per class Log-loss`。</span><span class="sxs-lookup"><span data-stu-id="63b00-321">`Per class Log-loss`.</span></span> <span data-ttu-id="63b00-322">建议每类别的对数损失尽可能接近 0。</span><span class="sxs-lookup"><span data-stu-id="63b00-322">You want per class Log-loss to be as close to zero as possible.</span></span>

<span data-ttu-id="63b00-323">使用下面的代码显示指标、共享结果，然后处理它们：</span><span class="sxs-lookup"><span data-stu-id="63b00-323">Use the following code to display the metrics, share the results, and then act on them:</span></span>

[!code-csharp[DisplayMetrics](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayMetrics)]

 <span data-ttu-id="63b00-324">添加以下代码，将经过训练的模型作为下一行代码返回：</span><span class="sxs-lookup"><span data-stu-id="63b00-324">Add the following code to return the trained model as the next line:</span></span>

[!code-csharp[SaveModel](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#ReturnModel)]

## <a name="classify-images-with-a-loaded-model"></a><span data-ttu-id="63b00-325">使用已加载的模型来分类图像</span><span class="sxs-lookup"><span data-stu-id="63b00-325">Classify images with a loaded model</span></span>

<span data-ttu-id="63b00-326">将以下 `ClassifyImages()` 方法调用添加为 `Main` 方法的下一行代码：</span><span class="sxs-lookup"><span data-stu-id="63b00-326">Add the following call to the `ClassifyImages()` method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallClassifyImages](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallClassifyImages)]

<span data-ttu-id="63b00-327">`ClassifyImages()` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="63b00-327">The `ClassifyImages()` method executes the following tasks:</span></span>

* <span data-ttu-id="63b00-328">将 .TSV 文件读取到 `IEnumerable` 中。</span><span class="sxs-lookup"><span data-stu-id="63b00-328">Reads .TSV file into `IEnumerable`.</span></span>
* <span data-ttu-id="63b00-329">根据测试数据预测图像分类。</span><span class="sxs-lookup"><span data-stu-id="63b00-329">Predicts image classifications based on test data.</span></span>

<span data-ttu-id="63b00-330">紧跟在 `ReuseAndTuneInceptionModel()` 方法后面且恰好在 `PairAndDisplayResults()` 方法前面，使用以下代码创建 `ClassifyImages()` 方法：</span><span class="sxs-lookup"><span data-stu-id="63b00-330">Create the `ClassifyImages()` method, just after the `ReuseAndTuneInceptionModel()` method and just before the `PairAndDisplayResults()` method, using the following code:</span></span>

```csharp
public static void ClassifyImages(MLContext mlContext, string dataLocation, string imagesFolder, string outputModelLocation, ITransformer model)
{

}
```

<span data-ttu-id="63b00-331">首先，调用 `ReadFromTsv()` 方法来创建 `IEnumerable<ImageData>` 类，其中包含每个 `ImagePath` 的完全限定的路径。</span><span class="sxs-lookup"><span data-stu-id="63b00-331">First, call the `ReadFromTsv()` method to create an `IEnumerable<ImageData>` class that contains the fully qualified path for each `ImagePath`.</span></span> <span data-ttu-id="63b00-332">必须有此文件路径，才能配对数据和预测结果。</span><span class="sxs-lookup"><span data-stu-id="63b00-332">You need that file path to pair your data and prediction results.</span></span> <span data-ttu-id="63b00-333">还需要将 `IEnumerable<ImageData>` 类转换为将用于预测的 `IDataView`。</span><span class="sxs-lookup"><span data-stu-id="63b00-333">You also need to convert the `IEnumerable<ImageData>` class to an `IDataView` that you will use to predict.</span></span> <span data-ttu-id="63b00-334">将以下代码添加为 `ClassifyImages()` 方法的接下来两行代码：</span><span class="sxs-lookup"><span data-stu-id="63b00-334">Add the following code as the next two lines in the `ClassifyImages()` method:</span></span>

[!code-csharp[CallReadFromTSV](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallReadFromTSV)]

<span data-ttu-id="63b00-335">如同之前处理训练图像数据一样，使用传入模型的 [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) 方法预测测试图像数据的类别。</span><span class="sxs-lookup"><span data-stu-id="63b00-335">As you did previously with the training image data, predict the category of the test image data using the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method of the model passed in.</span></span> <span data-ttu-id="63b00-336">将以下代码添加到预测结果的 `ClassifyImages()` 方法，并将 `predictions` `IDataView` 转换为 `IEnumerable` 以供配对和显示：</span><span class="sxs-lookup"><span data-stu-id="63b00-336">Add the following code to the `ClassifyImages()` method for the predictions and to convert the `predictions` `IDataView` into an `IEnumerable` for pairing and display:</span></span>

[!code-csharp[Predict](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#Predict)]

<span data-ttu-id="63b00-337">若要配对和显示测试图像数据和预测结果，请将以下代码添加为 `ClassifyImages()` 方法的下一行，以调用之前创建的 `DisplayResults()` 方法：</span><span class="sxs-lookup"><span data-stu-id="63b00-337">To pair and display your test image data and predictions, add the following code to call the `DisplayResults()` method previously created as the next line in the `ClassifyImages()` method:</span></span>

[!code-csharp[CallDisplayResults2](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallDisplayResults2)]

## <a name="classify-a-single-image-with-a-loaded-model"></a><span data-ttu-id="63b00-338">使用已加载的模型来分类单张图像</span><span class="sxs-lookup"><span data-stu-id="63b00-338">Classify a single image with a loaded model</span></span>

<span data-ttu-id="63b00-339">将以下 `ClassifySingleImage()` 方法调用添加为 `Main` 方法的下一行代码：</span><span class="sxs-lookup"><span data-stu-id="63b00-339">Add the following call to the `ClassifySingleImage()` method as the next line of code in the `Main` method:</span></span>

[!code-csharp[CallClassifySingleImage](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#CallClassifySingleImage)]

<span data-ttu-id="63b00-340">`ClassifySingleImage()` 方法执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="63b00-340">The `ClassifySingleImage()` method executes the following tasks:</span></span>

* <span data-ttu-id="63b00-341">加载 `ImageData` 实例。</span><span class="sxs-lookup"><span data-stu-id="63b00-341">Loads an `ImageData` instance.</span></span>
* <span data-ttu-id="63b00-342">根据测试数据预测图像分类。</span><span class="sxs-lookup"><span data-stu-id="63b00-342">Predicts image classification based on test data.</span></span>

<span data-ttu-id="63b00-343">紧跟在 `ClassifyImages()` 方法后面且恰好在 `PairAndDisplayResults()` 方法前面，使用以下代码创建 `ClassifySingleImage()` 方法：</span><span class="sxs-lookup"><span data-stu-id="63b00-343">Create the `ClassifySingleImage()` method, just after the `ClassifyImages()` method and just before the `PairAndDisplayResults()` method, using the following code:</span></span>

```csharp
public static void ClassifySingleImage(MLContext mlContext, string imagePath, string outputModelLocation, ITransformer model)
{

}
```

<span data-ttu-id="63b00-344">首先，创建 `ImageData` 类，其中包含单个 `ImagePath` 的完全限定的路径和图像文件名。</span><span class="sxs-lookup"><span data-stu-id="63b00-344">First, create an `ImageData` class that contains the fully qualified path and image file name for the single `ImagePath`.</span></span> <span data-ttu-id="63b00-345">将以下代码添加为 `ClassifySingleImage()` 方法的接下来几行：</span><span class="sxs-lookup"><span data-stu-id="63b00-345">Add the following code as the next  lines in the `ClassifySingleImage()` method:</span></span>

[!code-csharp[LoadImageData](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#LoadImageData)]

<span data-ttu-id="63b00-346">[PredictionEngine 类](xref:Microsoft.ML.PredictionEngine%602)是对单个数据实例执行预测的简便 API。</span><span class="sxs-lookup"><span data-stu-id="63b00-346">The [PredictionEngine class](xref:Microsoft.ML.PredictionEngine%602) is a convenience API that performs a prediction on a single instance of data.</span></span> <span data-ttu-id="63b00-347">[Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) 函数对单列数据进行预测。</span><span class="sxs-lookup"><span data-stu-id="63b00-347">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single column of data.</span></span> <span data-ttu-id="63b00-348">通过将以下代码添加到 `ClassifySingleImage()`，将 `imageData` 传递到 `PredictionEngine` 来预测图像类别：</span><span class="sxs-lookup"><span data-stu-id="63b00-348">Pass `imageData` to the `PredictionEngine` to predict the image category by adding the following code to `ClassifySingleImage()`:</span></span>

[!code-csharp[PredictSingle](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#PredictSingle)]

<span data-ttu-id="63b00-349">`ClassifySingleImage()` 方法的下一行代码用于显示预测结果：</span><span class="sxs-lookup"><span data-stu-id="63b00-349">Display the prediction result as the next line of code in the `ClassifySingleImage()` method:</span></span>

[!code-csharp[DisplayPrediction](../../../samples/machine-learning/tutorials/TransferLearningTF/Program.cs#DisplayPrediction)]

## <a name="results"></a><span data-ttu-id="63b00-350">结果</span><span class="sxs-lookup"><span data-stu-id="63b00-350">Results</span></span>

<span data-ttu-id="63b00-351">按照上述步骤操作后，运行控制台应用 (Ctrl + F5)。</span><span class="sxs-lookup"><span data-stu-id="63b00-351">After following the previous steps, run your console app (Ctrl + F5).</span></span> <span data-ttu-id="63b00-352">结果应如以下输出所示。</span><span class="sxs-lookup"><span data-stu-id="63b00-352">Your results should be similar to the following output.</span></span>  <span data-ttu-id="63b00-353">你可能会看到警告或处理消息，为清楚起见，这些消息已从以下结果中删除。</span><span class="sxs-lookup"><span data-stu-id="63b00-353">You may see warnings or processing messages, but these messages have been removed from the following results for clarity.</span></span>

```console
=============== Training classification model ===============
Image: broccoli.jpg predicted as: food with score: 0.976743
Image: pizza.jpg predicted as: food with score: 0.9751652
Image: pizza2.jpg predicted as: food with score: 0.9660203
Image: teddy2.jpg predicted as: toy with score: 0.9748783
Image: teddy3.jpg predicted as: toy with score: 0.9829691
Image: teddy4.jpg predicted as: toy with score: 0.9868168
Image: toaster.jpg predicted as: appliance with score: 0.9769174
Image: toaster2.png predicted as: appliance with score: 0.9800823
=============== Classification metrics ===============
LogLoss is: 0.0228266745633507
PerClassLogLoss is: 0.0277501705149937 , 0.0186303530571291 , 0.0217359128952187
=============== Making classifications ===============
Image: broccoli.png predicted as: food with score: 0.905548
Image: pizza3.jpg predicted as: food with score: 0.9709008
Image: teddy6.jpg predicted as: toy with score: 0.9750155
=============== Making single image classification ===============
Image: toaster3.jpg predicted as: appliance with score: 0.9625379

C:\Program Files\dotnet\dotnet.exe (process 4304) exited with code 0.
Press any key to close this window . . .
```

<span data-ttu-id="63b00-354">祝贺你！</span><span class="sxs-lookup"><span data-stu-id="63b00-354">Congratulations!</span></span> <span data-ttu-id="63b00-355">现已通过重用 ML.NET 中的预定型 `TensorFlow` 模型，成功生成图像分类机器学习模型。</span><span class="sxs-lookup"><span data-stu-id="63b00-355">You've now successfully built a machine learning model for image classification by reusing a pre-trained `TensorFlow` model in ML.NET.</span></span>

<span data-ttu-id="63b00-356">可以在 [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) 存储库中找到本教程的源代码。</span><span class="sxs-lookup"><span data-stu-id="63b00-356">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/TransferLearningTF) repository.</span></span>

<span data-ttu-id="63b00-357">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="63b00-357">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="63b00-358">了解问题</span><span class="sxs-lookup"><span data-stu-id="63b00-358">Understand the problem</span></span>
> * <span data-ttu-id="63b00-359">重用和优化预定型模型</span><span class="sxs-lookup"><span data-stu-id="63b00-359">Reuse and tune the pre-trained model</span></span>
> * <span data-ttu-id="63b00-360">使用已加载的模型来分类图像</span><span class="sxs-lookup"><span data-stu-id="63b00-360">Classify images with a loaded model</span></span>

<span data-ttu-id="63b00-361">请查看机器学习示例 GitHub 存储库，以探索扩展的图像分类示例。</span><span class="sxs-lookup"><span data-stu-id="63b00-361">Check out the Machine Learning samples GitHub repository to explore an expanded image classification sample.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="63b00-362">dotnet/machinelearning-samples GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="63b00-362">dotnet/machinelearning-samples GitHub repository</span></span>](https://github.com/dotnet/machinelearning-samples/)

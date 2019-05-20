---
title: 使用 ML.NET 自动化机器学习
description: 自动模型选择和训练的概述
author: natke
ms.date: 05/01/2019
ms.topic: overview
ms.custom: mvc
ms.author: nakersha
ms.openlocfilehash: e6654718f174c9d8b628b05d85d74952c222eb66
ms.sourcegitcommit: 4c10802ad003374641a2c2373b8a92e3c88babc8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2019
ms.locfileid: "65452722"
---
# <a name="automated-machine-learning-with-mlnet"></a><span data-ttu-id="830ab-103">使用 ML.NET 自动化机器学习</span><span class="sxs-lookup"><span data-stu-id="830ab-103">Automated machine learning with ML.NET</span></span>

<span data-ttu-id="830ab-104">自动化机器学习是 ML.NET 的一项功能，可执行自动模型选择和训练。</span><span class="sxs-lookup"><span data-stu-id="830ab-104">Automated machine learning is a feature of ML.NET that performs automatic model selection and training.</span></span> <span data-ttu-id="830ab-105">指定机器学习任务并提供数据集，自动化 ML 会选择具有最佳指标的模型。</span><span class="sxs-lookup"><span data-stu-id="830ab-105">You specify the machine learning task and supply a dataset, and automated ML chooses the model with the best metrics.</span></span> <span data-ttu-id="830ab-106">它输出：</span><span class="sxs-lookup"><span data-stu-id="830ab-106">It outputs:</span></span>
- <span data-ttu-id="830ab-107">可以加载到预测应用程序中的模型文件</span><span class="sxs-lookup"><span data-stu-id="830ab-107">a model file that can be loaded into your prediction application</span></span>
- <span data-ttu-id="830ab-108">用于进行预测的应用程序代码</span><span class="sxs-lookup"><span data-stu-id="830ab-108">application code to make predictions</span></span>
- <span data-ttu-id="830ab-109">用于特征选择和模型训练的源代码（用于了解模型）</span><span class="sxs-lookup"><span data-stu-id="830ab-109">the source code used for feature selection and model training (to understand the model)</span></span>

> [!NOTE]
> <span data-ttu-id="830ab-110">此功能目前处于预览状态，且材料可能会有所变化。</span><span class="sxs-lookup"><span data-stu-id="830ab-110">This feature is currently in Preview, and material may be subject to change.</span></span> 

<span data-ttu-id="830ab-111">自动化 ML 目前仅限于二元分类、多类分类和回归这三个机器学习[任务](resources/tasks.md)。</span><span class="sxs-lookup"><span data-stu-id="830ab-111">Automated ML is currently limited to the machine learning [tasks](resources/tasks.md) of binary classification, multiclass classification, and regression.</span></span> <span data-ttu-id="830ab-112">未来的版本将支持其他机器学习任务。</span><span class="sxs-lookup"><span data-stu-id="830ab-112">The other machine learning tasks will be supported in future releases.</span></span>

<span data-ttu-id="830ab-113">有三种方法可以使用自动化 ML：</span><span class="sxs-lookup"><span data-stu-id="830ab-113">There are three ways to use automated ML:</span></span>
1. <span data-ttu-id="830ab-114">在命令行中，使用 [ML.NET CLI](automate-training-with-cli.md)</span><span class="sxs-lookup"><span data-stu-id="830ab-114">On the command line, with the [ML.NET CLI](automate-training-with-cli.md)</span></span>
1. <span data-ttu-id="830ab-115">通过应用程序，使用[自动化 ML API](how-to-guides/how-to-use-the-automl-api.md)</span><span class="sxs-lookup"><span data-stu-id="830ab-115">Via an application, with the [automated ML API](how-to-guides/how-to-use-the-automl-api.md)</span></span>
1. <span data-ttu-id="830ab-116">通过图形用户界面，使用 ML.NET 模型生成器</span><span class="sxs-lookup"><span data-stu-id="830ab-116">With a graphical user interface, with the the ML.NET Model Builder</span></span>

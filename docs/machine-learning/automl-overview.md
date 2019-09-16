---
title: 使用 ML.NET 自动化机器学习
description: 自动模型选择和训练的概述
author: natke
ms.date: 05/01/2019
ms.topic: overview
ms.custom: mvc
ms.author: nakersha
ms.openlocfilehash: da2d764e678debc78a25faeb8e48facb44fc4021
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2019
ms.locfileid: "70929424"
---
# <a name="automated-machine-learning-with-mlnet"></a>使用 ML.NET 自动化机器学习

自动化机器学习是 ML.NET 的一项功能，可执行自动模型选择和训练。 指定机器学习任务并提供数据集，自动化 ML 会选择具有最佳指标的模型。 它输出：

- 可以加载到预测应用程序中的模型文件
- 用于进行预测的应用程序代码
- 用于特征选择和模型训练的源代码（用于了解模型）

> [!NOTE]
> 此功能目前处于预览状态，且材料可能会有所变化。 

自动化 ML 目前仅限于二元分类、多类分类和回归这三个机器学习[任务](resources/tasks.md)。 未来的版本将支持其他机器学习任务。

有三种方法可以使用自动化 ML：

1. 通过图形用户界面，使用 [ML.NET 模型生成器](automate-training-with-model-builder.md)
1. 在命令行中，使用 [ML.NET CLI](automate-training-with-cli.md)
1. 通过应用程序，使用[自动化 ML API](how-to-guides/how-to-use-the-automl-api.md)

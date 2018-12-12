---
title: 计算用于评估机器学习模型质量的指标 - ML.NET
description: 了解如何使用 ML.NET 来计算用于评估和验证机器学习模型质量的指标
ms.date: 11/07/2018
ms.custom: mvc,how-to
ms.openlocfilehash: 6fd4dfab6104b4398918e42ed70584b04169a8c1
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53149518"
---
# <a name="calculate-metrics-to-evaluate-machine-learning-model-quality---mlnet"></a>计算用于评估机器学习模型质量的指标 - ML.NET

训练模型后如何评估质量？ 每个机器学习任务都会公开用于质量评估的指标。

可使用任务的相应“上下文”来评估模型，如以下示例所示：

```csharp
// Read the test dataset.
var testData = reader.Read(testDataPath);
// Calculate metrics of the model on the test data.
var metrics = mlContext.Regression.Evaluate(model.Transform(testData), label: "Target");
```
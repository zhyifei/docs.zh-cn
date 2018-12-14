---
title: 在应用中操作定型的机器学习模型 - ML.NET
description: 了解如何借助 ML.NET 在应用程序中使用定型和经过评估的机器学习模型
ms.date: 11/07/2018
ms.custom: mvc,how-to
ms.openlocfilehash: ff3f0a8856382d020129693bcf722f572fd87606
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53131641"
---
# <a name="operationalize-a-trained-machine-learning-model-in-apps---mlnet"></a>在应用中操作定型的机器学习模型 - ML.NET

当模型指标对你而言不错时，就到了“操作”模型的时候了。 可以在不同的环境中使用、保留和重用所生成的 `model` 对象，并在定型期间应用该对象“已学习”的相同步骤。

若要将模型保存到文件中，并重载它（可能在不同的上下文中），请使用以下示例：

```csharp
using (var stream = File.Create(modelPath))
{
    // Saving and loading happens to 'dynamic' models.
    mlContext.Model.Save(model, stream);
}

// Potentially, the lines below can be in a different process altogether.

// When you load the model, it's a transformer.
ITransformer loadedModel;
using (var stream = File.OpenRead(modelPath))
    loadedModel = mlContext.Model.Load(stream);
```

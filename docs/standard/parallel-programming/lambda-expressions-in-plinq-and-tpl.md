---
title: PLINQ 和 TPL 中的 Lambda 表达式
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Func delegate, creating with lambda expression
- Action delegate, creating with lambda expression
- lambda expressions, with Action and Func
ms.assetid: 645b2c17-29d0-4ffa-8684-430743cc2f2d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36a003c96e81996e304fc4347ed05bf7a255c224
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2018
ms.locfileid: "44189430"
---
# <a name="lambda-expressions-in-plinq-and-tpl"></a>PLINQ 和 TPL 中的 Lambda 表达式
任务并行库 (TPL) 包含许多方法，需要使用 <xref:System.Func%601?displayProperty=nameWithType> 或 <xref:System.Action?displayProperty=nameWithType> 系列委托之一作为输入参数。 使用这些委托将自定义程序逻辑传入到并行循环、任务或查询中。 TPL 以及 PLINQ 的代码示例使用 lambda 表达式以内联代码块的形式创建这些委托的实例。 本主题简要介绍 Func 和 Action，并演示如何在任务并行库和 PLINQ 中使用 lambda 表达式。  
  
 **注意**：有关委托的更多常规信息，请参阅[委托](../../csharp/programming-guide/delegates/index.md)和[委托](../../visual-basic/programming-guide/language-features/delegates/index.md)。 有关 C# 和 Visual Basic 中的 lambda 表达式的详细信息，请参阅 [Lambda 表达式](~/docs/csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)和 [Lambda 表达式](~/docs/visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)。  
  
## <a name="func-delegate"></a>Func 委托  
 `Func` 委托封装返回值的一个方法。 在 Func 签名中，最后或最右侧的类型参数始终指定返回类型。 导致编译器错误出现的常见原因之一是，尝试将两个输入参数传入 <xref:System.Func%602?displayProperty=nameWithType>；此类型其实只需要使用一个输入参数。 框架类库定义了 17 个版本的 `Func`：<xref:System.Func%601?displayProperty=nameWithType>、<xref:System.Func%602?displayProperty=nameWithType>、<xref:System.Func%603?displayProperty=nameWithType> 一直到 <xref:System.Func%6017?displayProperty=nameWithType>。  
  
## <a name="action-delegate"></a>Action 委托  
 <xref:System.Action?displayProperty=nameWithType> 委托封装了不返回值或返回 [void](~/docs/csharp/language-reference/keywords/void.md) 的方法（Visual Basic 中的 Sub）。 在 Action 类型签名中，类型参数仅表示输入参数。 与 Func 一样，Framework 类库定义了 Action 的 17 个版本，从没有类型参数的版本到具有 16 个类型参数的版本。  
  
## <a name="example"></a>示例  
 下面的 <xref:System.Threading.Tasks.Parallel.ForEach%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%601%7D%2CSystem.Func%7B%60%600%2CSystem.Threading.Tasks.ParallelLoopState%2C%60%601%2C%60%601%7D%2CSystem.Action%7B%60%601%7D%29?displayProperty=nameWithType> 方法示例展示了如何使用 Lambda 表达式表达 Func 和 Action 委托。  
  
 [!code-csharp[System.Threading.Tasks.Parallel#02](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.threading.tasks.parallel/cs/parallelforeach.cs#02)]
 [!code-vb[System.Threading.Tasks.Parallel#02](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.threading.tasks.parallel/vb/parallelforeach.vb#02)]  
  
## <a name="see-also"></a>请参阅

- [并行编程](../../../docs/standard/parallel-programming/index.md)

---
title: 异常：try...with 表达式 (F#)
description: '了解如何使用 F # try … 与表达式用于异常处理。'
ms.date: 05/16/2016
ms.openlocfilehash: 5e6e16d5fba88841d567512ba7e08a2e8d17bdba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565283"
---
# <a name="exceptions-the-trywith-expression"></a>异常：try...with 表达式

本主题介绍`try...with`表达式，用于对 F # 语言中的异常处理的表达式。


## <a name="syntax"></a>语法

```fsharp
try
    expression1
with
| pattern1 -> expression2
| pattern2 -> expression3
...
```

## <a name="remarks"></a>备注
`try...with`使用表达式来处理 F # 中的异常。 它是类似于`try...catch`C# 中的语句。 在前面的语法中中的代码*expression1*可能会生成异常。 `try...with`表达式返回一个值。 如果不引发任何异常，则整个表达式返回的值*expression1*。 如果将引发异常，每个*模式*有例外，并为第一个匹配的模式，相应反过来比较*表达式*、 称为*异常处理程序*，会执行该分支，并在该异常处理程序中，整个表达式返回表达式的值。 如果没有模式匹配，则直到找到匹配的处理时，异常将传播到调用堆栈中。 从异常处理程序中的每个表达式返回的值的类型必须匹配中的表达式返回的类型`try`块。

通常情况下，还发生了错误的事实意味着没有有效值可从每个异常处理程序中的表达式返回的。 常见模式是设置表达式的类型是选项类型。 下面的代码示例说明了此模式。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5601.fs)]

异常可以是.NET 异常，或它们可以是 F # 异常。 你可以通过定义 F # 例外`exception`关键字。

你可以使用各种模式要作为筛选依据的异常类型和其他条件;下表中概括了选项。


|模式|描述|
|-------|-----------|
|:? *异常类型*|与指定的.NET 异常类型匹配。|
|:? *异常类型*作为*标识符*|匹配指定的.NET 异常类型，但会命名的值的异常。|
|*异常名称*(*参数*)|匹配 F # 异常类型和绑定参数。|
|*identifier*|与任何异常匹配，并绑定到的异常对象的名称。 等效于 **:？作为 System.Exception * * * 标识符*|
|*标识符*时*条件*|如果条件为 true，则匹配的任何异常。|

## <a name="examples"></a>示例
下面的代码示例说明了各种异常处理程序模式的用法。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5602.fs)]
    
>[!NOTE] 
`try...with`构造是从单独的表达式`try...finally`表达式。 因此，如果你的代码同时需要`with`块和一个`finally`块中，你将需要嵌套两个表达式。

>[!NOTE] 
你可以使用`try...with`在异步工作流和其他计算表达式，在这种情况下的自定义的版本`try...with`使用表达式。 有关详细信息，请参阅[异步工作流](../asynchronous-workflows.md)，和[计算表达式](../computation-expressions.md)。


## <a name="see-also"></a>请参阅
[异常处理](index.md)

[异常类型](exception-types.md)

[异常：`try...finally` 表达式](the-try-finally-expression.md)

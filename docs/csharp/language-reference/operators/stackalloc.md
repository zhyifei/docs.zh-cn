---
title: stackalloc 运算符 - C# 参考
ms.custom: seodec18
ms.date: 09/20/2019
f1_keywords:
- stackalloc_CSharpKeyword
helpviewer_keywords:
- stackalloc operator [C#]
ms.openlocfilehash: 82fc1649bac66c0e934db13c50390b977432c34c
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "73036142"
---
# <a name="stackalloc-operator-c-reference"></a>stackalloc 运算符（C# 参考）

`stackalloc` 运算符在堆栈上分配内存块。 该方法返回时，将自动丢弃在方法执行期间创建的堆栈中分配的内存块。 不能显式释放使用 `stackalloc` 运算符分配的内存。 堆栈中分配的内存块不受[垃圾回收](../../../standard/garbage-collection/index.md)的影响，也不必通过 [`fixed` 语句](../keywords/fixed-statement.md)固定。

在表达式 `stackalloc T[E]` 中，`T` 须为[非托管类型](../builtin-types/unmanaged-types.md)，`E` 须为 `int` 类型的表达式。

可以将 `stackalloc` 运算符的结果分配给以下任一类型的变量：

- 从 C# 7.2 开始，<xref:System.Span%601?displayProperty=nameWithType> 或 <xref:System.ReadOnlySpan%601?displayProperty=nameWithType> 将如下例所示：

  [!code-csharp[stackalloc span](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AssignToSpan)]

  将堆栈中分配的内存块分配给 <xref:System.Span%601> 或 <xref:System.ReadOnlySpan%601> 变量时，不必使用 [unsafe](../keywords/unsafe.md) 上下文。

  使用这些类型时，可以在[条件表达式](conditional-operator.md)或赋值表达式中使用 `stackalloc` 表达式，如以下示例所示：

  [!code-csharp[stackalloc expression](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AsExpression)]

  从 C#8.0 开始，只要允许使用 <xref:System.Span%601> 或 <xref:System.ReadOnlySpan%601> 变量，就可以在其他表达式中使用 `stackalloc` 表达式，如下例所示：

  [!code-csharp[stackalloc in nested expressions](~/samples/csharp/language-reference/operators/StackallocOperator.cs#Nested)]

  > [!NOTE]
  > 建议尽可能使用 <xref:System.Span%601> 或 <xref:System.ReadOnlySpan%601> 类型来处理堆栈中分配的内存。

- [指针类型](../../programming-guide/unsafe-code-pointers/pointer-types.md)，如以下示例所示：

  [!code-csharp[stackalloc pointer](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AssignToPointer)]

  如前面的示例所示，在使用指针类型时必须使用 `unsafe` 上下文。

  对于指针类型，只能在局部变量声明中使用 `stackalloc` 表达式来初始化变量。

新分配的内存的内容未定义。 从 C# 7.3 开始，可以使用数组初始值设定项语法来定义新分配内存的内容。 下面的示例演示执行此操作的各种方法：

[!code-csharp[stackalloc initialization](~/samples/csharp/language-reference/operators/StackallocOperator.cs#StackallocInit)]

## <a name="security"></a>安全性

使用 `stackalloc` 会自动启用公共语言运行时 (CLR) 中的缓冲区溢出检测功能。 如果检测到缓冲区溢出，则将尽快终止进程，以便将执行恶意代码的可能性降到最低。

## <a name="c-language-specification"></a>C# 语言规范

有关详细信息，请参阅 [C# 语言规范](~/_csharplang/spec/introduction.md)中的[堆栈分配](~/_csharplang/spec/unsafe-code.md#stack-allocation)部分。

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 运算符](index.md)
- [指针相关的运算符](pointer-related-operators.md)
- [指针类型](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [内存和跨度相关类型](../../../standard/memory-and-spans/index.md)

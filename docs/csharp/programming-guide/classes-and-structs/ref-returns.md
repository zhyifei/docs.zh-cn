---
title: ref 返回值和 ref 局部变量（C# 指南）
description: 了解如何定义和使用 ref 返回值和 ref 局部变量
author: rpetrusha
ms.author: ronpet
ms.date: 01/23/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.openlocfilehash: c37c6dd61ae02813bcc467982f3b175da9136e4a
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="ref-returns-and-ref-locals"></a>ref 返回值和局部变量

从 C# 7 开始，C# 支持引用返回值（ref 返回值）。 借助引用返回值，方法可以将对变量的引用（而不是值）返回给调用方。 然后，调用方可以选择将返回的变量视为按值返回或按引用返回。 调用方可以新建称为“引用本地”的变量，其本身就是对返回值的引用。

## <a name="what-is-a-reference-return-value"></a>什么是引用返回值？

绝大多数开发者都很熟悉将参数按引用传递给被调用的方法。 被调用方法的参数列表包括按引用传递的变量，并且被调用方法对值所做的任何更改均由调用方观察。 “引用返回值”是指方法返回对某变量的引用（或别名），变量范围包括方法，且生存期必须长于方法的返回值。 调用方对方法的返回值进行的修改应用于方法返回的变量。

如果声明方法返回引用返回值，表明方法返回变量别名。 这样做通常是为了让调用代码有权通过别名访问此变量（包括修改它）。 遵循的原则是，按引用返回变量的方法不能有返回类型 `void`。

对于方法能以引用返回值的形式返回的表达式，存在一些限制。 这些方法包括：

- 返回值的生存期必须长于方法执行时间。 换言之，它不能是返回自身的方法中的本地变量。 它可以是实例或类的静态字段，也可是传递给方法的参数。 尝试返回局部变量将生成编译器错误 CS8168：“无法按引用返回局部 "obj"，因为它不是 ref 局部变量”。

- 返回值不得为文本 `null`。 尝试返回 `null` 将生成编译器错误 CS8156：“无法在此上下文中使用表达式，因为它可能没有按引用返回”。

   使用引用返回值的方法可以返回值当前为 null（未实例化）或[可以为 null 的类型](../nullable-types/index.md)的变量别名。
 
- 返回值不得为常量、枚举成员、通过属性的按值返回值或 `class`/`struct` 方法。 尝试返回它们将生成编译器错误 CS8156：“无法在此上下文中使用表达式，因为它可能没有按引用返回”。

此外，由于异步方法可能在完成执行前就返回，虽然它的返回值仍未知，但也不允许对异步方法使用引用返回值。
 
## <a name="defining-a-ref-return-value"></a>定义 ref 返回值

通过向方法签名的返回类型添加 [ref](../../language-reference/keywords/ref.md) 关键字来定义 ref 返回值。 例如下列签名表示，`GetContactInformation` 属性将对 `Person` 对象的引用返回给调用方：

```csharp
public ref Person GetContactInformation(string fname, string lname);
```

此外，方法正文中每个 [return](../../language-reference/keywords/return.md) 语句所返回对象的名称前面须有 [ref](../../language-reference/keywords/ref.md) 关键字。 例如，下面的 `return` 语句返回对 `Person` 对象的引用 `p`：

```csharp
return ref p;
```

## <a name="consuming-a-ref-return-value"></a>使用 ref 返回值

引用返回值是被调用方法范围中另一个变量的别名。 可以将引用返回值的所有使用都解释为，使用它取别名的变量：

- 分配值时，就是将值分配到它取别名的变量。
- 读取值时，就是读取它取别名的变量的值。
- 如果按引用返回它，就是返回相同变量的别名。
- 如果按引用将它传递到另一个方法，就是传递对它取别名的变量的引用。
- 如果返回[引用本地](#ref-local)别名，就是返回相同变量的新别名。


## <a name="ref-locals"></a>ref 局部变量

假设 `GetContactInformation` 方法声明为引用返回：

```csharp
public ref Person GetContactInformation(string fname, string lname)
```

按值分配会读取变量值，并将它分配给新变量：

```csharp
Person p = contacts.GetContactInformation("Brandie", "Best");
```

上面的分配将 `p` 声明为本地变量。 它的初始值是通过读取 `GetContactInformation` 返回的值进行复制。 之后对 `p` 的任何分配都不会更改 `GetContactInformation` 返回的变量值。 变量 `p` 不再是返回的变量的别名。

声明引用本地变量，复制原始值的别名。 在下面的分配中，`p` 是从 `GetContactInformation` 返回的变量的别名。

```csharp
ref Person p = ref contacts.GetContactInformation("Brandie", "Best");
```

后续使用 `p` 等同于使用 `GetContactInformation` 返回的变量，因为 `p` 是此变量的别名。 对 `p` 所做的更改也会更改从 `GetContactInformation` 返回的变量。

注意，请同时在局部变量声明前和方法调用前使用 `ref` 关键字。 

可通过相同方式按引用访问值。 在某些情况下，按引用访问值可避免潜在的高开销复制操作，从而提高性能。 例如，以下语句显示用户可如何定义一个用于引用值的 ref 局部变量值。

```csharp
ref VeryLargeStruct reflocal = ref veryLargeStruct;
```

注意，请同时在局部变量声明前和第二个示例中的值前使用 `ref` 关键字。 在这两个示例中，如果无法同时将 `ref` 关键字包含在变量声明和赋值中，则会导致编译器错误 CS8172：“无法使用值对按引用变量进行初始化”。 
 
## <a name="ref-returns-and-ref-locals-an-example"></a>ref 返回结果和 ref 局部变量：示例

下列示例定义存储整数值数组的 `NumberStore` 类。 `FindNumber` 方法按引用返回第一个大于或等于作为参数传递的数字的数字。 如果没有大于或等于该参数的数字，则方法返回索引 0 中的数字。 

[!code-csharp[ref-returns](../../../../samples/snippets/csharp/programming-guide/ref-returns/ref-returns1.cs#1)]

下列示例调用 `NumberStore.FindNumber` 方法来检索大于或等于 16 的第一个值。 然后，调用方将该方法返回的值加倍。 如示例中的输出所示，此更改将反映在 `NumberStore` 实例的数组元素的值中。

[!code-csharp[ref-returns](../../../../samples/snippets/csharp/programming-guide/ref-returns/ref-returns1.cs#2)]

在不支持引用返回值的情况下，此类操作通常通过返回数组元素的索引和它的值来执行。 然后，调用方可使用此索引修改单个方法调用中的值。 但调用方也可修改要访问的索引，还可修改其他数组值。  
 
## <a name="see-also"></a>请参阅

[ref 关键字](../../language-reference/keywords/ref.md)  
[具有值类型的引用语义](../../../csharp/reference-semantics-with-value-types.md)

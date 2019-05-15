---
title: 详细语法
description: 了解中的详细和轻量语法之间的区别F#编程语言。
ms.date: 05/16/2016
ms.openlocfilehash: c95965d7d9d18a0fca11663a474dbbc9375a9494
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641667"
---
# <a name="verbose-syntax"></a><span data-ttu-id="36f2b-103">详细语法</span><span class="sxs-lookup"><span data-stu-id="36f2b-103">Verbose Syntax</span></span>

<span data-ttu-id="36f2b-104">有两种形式的语法可用于在许多构造F#语言：*详细语法*并*轻量语法*。</span><span class="sxs-lookup"><span data-stu-id="36f2b-104">There are two forms of syntax available for many constructs in the F# language: *verbose syntax* and *lightweight syntax*.</span></span> <span data-ttu-id="36f2b-105">详细语法不常使用，但具有的优势在于到缩进的敏感程度较低。</span><span class="sxs-lookup"><span data-stu-id="36f2b-105">The verbose syntax is not as commonly used, but has the advantage of being less sensitive to indentation.</span></span> <span data-ttu-id="36f2b-106">轻量语法为较短，并使用缩进发出信号的开头和结尾的构造，而不是其他关键字，例如`begin`， `end`， `in`，依次类推。</span><span class="sxs-lookup"><span data-stu-id="36f2b-106">The lightweight syntax is shorter and uses indentation to signal the beginning and end of constructs, rather than additional keywords like `begin`, `end`, `in`, and so on.</span></span> <span data-ttu-id="36f2b-107">默认语法为轻量语法。</span><span class="sxs-lookup"><span data-stu-id="36f2b-107">The default syntax is the lightweight syntax.</span></span> <span data-ttu-id="36f2b-108">本主题介绍的语法F#构造时未启用轻量语法。</span><span class="sxs-lookup"><span data-stu-id="36f2b-108">This topic describes the syntax for F# constructs when lightweight syntax is not enabled.</span></span> <span data-ttu-id="36f2b-109">详细语法始终处于启用状态，因此即使您启用轻量语法，仍然可以为某些构造使用详细语法。</span><span class="sxs-lookup"><span data-stu-id="36f2b-109">Verbose syntax is always enabled, so even if you enable lightweight syntax, you can still use verbose syntax for some constructs.</span></span> <span data-ttu-id="36f2b-110">可以使用禁用轻量语法`#light "off"`指令。</span><span class="sxs-lookup"><span data-stu-id="36f2b-110">You can disable lightweight syntax by using the `#light "off"` directive.</span></span>

## <a name="table-of-constructs"></a><span data-ttu-id="36f2b-111">构造表</span><span class="sxs-lookup"><span data-stu-id="36f2b-111">Table of Constructs</span></span>

<span data-ttu-id="36f2b-112">下表显示了的轻量和详细语法F#语言构造大大降低在上下文中存在两种形式之间的差异的。</span><span class="sxs-lookup"><span data-stu-id="36f2b-112">The following table shows the lightweight and verbose syntax for F# language constructs in contexts where there is a difference between the two forms.</span></span> <span data-ttu-id="36f2b-113">在此表中，角度方括号 (&lt;&gt;) 括起来的用户提供的语法元素。</span><span class="sxs-lookup"><span data-stu-id="36f2b-113">In this table, angle brackets (&lt;&gt;) enclose user-supplied syntax elements.</span></span> <span data-ttu-id="36f2b-114">请参阅有关使用这些构造中的语法的更多详细信息每种语言构造的文档。</span><span class="sxs-lookup"><span data-stu-id="36f2b-114">Refer to the documentation for each language construct for more detailed information about the syntax used within these constructs.</span></span>

<table>
<tr>
<th><span data-ttu-id="36f2b-115">语言构造</span><span class="sxs-lookup"><span data-stu-id="36f2b-115">Language construct</span></span></th>
<th><span data-ttu-id="36f2b-116">轻量语法</span><span class="sxs-lookup"><span data-stu-id="36f2b-116">Lightweight syntax</span></span></th>
<th><span data-ttu-id="36f2b-117">详细语法</span><span class="sxs-lookup"><span data-stu-id="36f2b-117">Verbose syntax</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="36f2b-118">复合表达式</span><span class="sxs-lookup"><span data-stu-id="36f2b-118">compound expressions</span></span>
</td>
<td>

```xml
<expression1>
<expression2>
```

</td><td>

```fsharp
<expression1>; <expression2>
```

</td>
</tr>
<tr><td>

<span data-ttu-id="36f2b-119">嵌套`let`绑定</span><span class="sxs-lookup"><span data-stu-id="36f2b-119">nested `let` bindings</span></span>

</td><td>

```fsharp
let f x =
    let a = 1
    let b = 2
    x + a + b
```

</td><td>

```fsharp
let f x =
    let a = 1 in
    let b = 2 in
    x + a + b
```

</td>
</tr>
<tr><td>
<span data-ttu-id="36f2b-120">代码块</span><span class="sxs-lookup"><span data-stu-id="36f2b-120">code block</span></span>
</td><td>

```fsharp
(
    <expression1>
    <expression2>
)
```

</td><td>

```fsharp
begin
    <expression1>;
    <expression2>;
end
```

</td>
</tr>
<tr><td>
`for...do`
</td><td>

```fsharp
for counter = start to finish do
    ...
```

</td><td>

```
for counter = start to finish do
    ...
done
```

</td>
</tr>
<tr><td>
`while...do`
</td><td>

```fsharp
while <condition> do
    ...
```

</td><td>

```fsharp
while <condition> do
    ...
done
```

</td>
</tr>
<tr><td>
`for...in`
</td><td>

```fsharp
for var in start .. finish do
    ...
```

</td><td>

```fsharp
for var in start .. finish do
    ...
done
```

</td>
</tr>
<tr><td>
`do`
</td><td>

```fsharp
do
    ...
```

</td><td>

```fsharp
do
    ...
in
```

</td>
</tr>
<tr><td><span data-ttu-id="36f2b-121">记录</span><span class="sxs-lookup"><span data-stu-id="36f2b-121">record</span></span>
</td><td>

```fsharp
type <record-name> =
    {
        <field-declarations>
    }
    <value-or-member-definitions>
```

</td><td>

```fsharp
type <record-name> =
    {
        <field-declarations>
    }
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="36f2b-122">class</span><span class="sxs-lookup"><span data-stu-id="36f2b-122">class</span></span>
</td><td>

```fsharp
type <class-name>(<params>) =
    ...
```

</td><td>

```fsharp
type <class-name>(<params>) =
    class
        ...
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="36f2b-123">结构</span><span class="sxs-lookup"><span data-stu-id="36f2b-123">structure</span></span></td><td>

```fsharp
[<StructAttribute>]
type <structure-name> =
    ...
```

</td><td>

```fsharp
type <structure-name> =
    struct
        ...
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="36f2b-124">可区分的联合</span><span class="sxs-lookup"><span data-stu-id="36f2b-124">discriminated union</span></span></td><td>

```fsharp
type <union-name> =
    | ...
    | ...
    ...
    <value-or-member definitions>
```

</td><td>

```fsharp
type <union-name> =
    | ...
    | ...
    ...
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="36f2b-125">interface</span><span class="sxs-lookup"><span data-stu-id="36f2b-125">interface</span></span></td><td>

```fsharp
type <interface-name> =
    ...
```

</td><td>

```fsharp
type <interface-name> =
    interface
        ...
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="36f2b-126">对象表达式</span><span class="sxs-lookup"><span data-stu-id="36f2b-126">object expression</span></span></td><td>

```fsharp
{ new <type-name>
    with
        <value-or-member-definitions>
        <interface-implementations>
}
```

</td><td>

```fsharp
{ new <type-name>
    with
        <value-or-member-definitions>
    end
    <interface-implementations>
}
```

</td>
</tr>
<tr><td><span data-ttu-id="36f2b-127">接口实现</span><span class="sxs-lookup"><span data-stu-id="36f2b-127">interface implementation</span></span></td><td>

```fsharp
interface <interface-name>
    with
        <value-or-member-definitions>
```

</td><td>

```fsharp
interface <interface-name>
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="36f2b-128">类型扩展</span><span class="sxs-lookup"><span data-stu-id="36f2b-128">type extension</span></span></td><td>

```fsharp
type <type-name>
    with
        <value-or-member-definitions>
```

</td><td>

```fsharp
type <type-name>
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="36f2b-129">name</span><span class="sxs-lookup"><span data-stu-id="36f2b-129">module</span></span></td><td>

```fsharp
module <module-name> =
    ...
```

</td><td>

```fsharp
module <module-name> =
    begin
        ...
    end
```

</td>
</tr>
</table>

## <a name="see-also"></a><span data-ttu-id="36f2b-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="36f2b-130">See also</span></span>

- [<span data-ttu-id="36f2b-131">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="36f2b-131">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="36f2b-132">编译器指令</span><span class="sxs-lookup"><span data-stu-id="36f2b-132">Compiler Directives</span></span>](compiler-directives.md)
- [<span data-ttu-id="36f2b-133">代码格式设置准则</span><span class="sxs-lookup"><span data-stu-id="36f2b-133">Code Formatting Guidelines</span></span>](code-formatting-guidelines.md)

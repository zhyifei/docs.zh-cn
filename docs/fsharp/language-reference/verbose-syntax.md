---
title: 详细语法
description: 了解F#编程语言中的详细和轻型语法之间的差异。
ms.date: 05/16/2016
ms.openlocfilehash: d2459da60bba5d88bd23615c8bf09ba64f7c22c4
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2019
ms.locfileid: "71214035"
---
# <a name="verbose-syntax"></a><span data-ttu-id="6e01c-103">详细语法</span><span class="sxs-lookup"><span data-stu-id="6e01c-103">Verbose Syntax</span></span>

<span data-ttu-id="6e01c-104">以下语言提供了两种形式的语法： " F# *详细语法*" 和 "*轻量语法*"。</span><span class="sxs-lookup"><span data-stu-id="6e01c-104">There are two forms of syntax available for many constructs in the F# language: *verbose syntax* and *lightweight syntax*.</span></span> <span data-ttu-id="6e01c-105">详细语法并不常用，但优点在于缩进不太敏感。</span><span class="sxs-lookup"><span data-stu-id="6e01c-105">The verbose syntax is not as commonly used, but has the advantage of being less sensitive to indentation.</span></span> <span data-ttu-id="6e01c-106">轻型语法较短，并使用缩进来表示构造的开始和结束，而不是使用`begin` `in`、 `end`、等其他关键字。</span><span class="sxs-lookup"><span data-stu-id="6e01c-106">The lightweight syntax is shorter and uses indentation to signal the beginning and end of constructs, rather than additional keywords like `begin`, `end`, `in`, and so on.</span></span> <span data-ttu-id="6e01c-107">默认语法为轻型语法。</span><span class="sxs-lookup"><span data-stu-id="6e01c-107">The default syntax is the lightweight syntax.</span></span> <span data-ttu-id="6e01c-108">本主题介绍未启用轻型F#语法时构造的语法。</span><span class="sxs-lookup"><span data-stu-id="6e01c-108">This topic describes the syntax for F# constructs when lightweight syntax is not enabled.</span></span> <span data-ttu-id="6e01c-109">详细语法始终处于启用状态，因此即使启用了轻型语法，仍可对某些构造使用详细语法。</span><span class="sxs-lookup"><span data-stu-id="6e01c-109">Verbose syntax is always enabled, so even if you enable lightweight syntax, you can still use verbose syntax for some constructs.</span></span> <span data-ttu-id="6e01c-110">您可以使用`#light "off"`指令禁用轻型语法。</span><span class="sxs-lookup"><span data-stu-id="6e01c-110">You can disable lightweight syntax by using the `#light "off"` directive.</span></span>

## <a name="table-of-constructs"></a><span data-ttu-id="6e01c-111">构造表</span><span class="sxs-lookup"><span data-stu-id="6e01c-111">Table of Constructs</span></span>

<span data-ttu-id="6e01c-112">下表显示了在这两种形式之间F#存在差异的上下文中语言构造的轻型和详细语法。</span><span class="sxs-lookup"><span data-stu-id="6e01c-112">The following table shows the lightweight and verbose syntax for F# language constructs in contexts where there is a difference between the two forms.</span></span> <span data-ttu-id="6e01c-113">在此表中，尖括号（&lt;&gt;）将用户提供的语法元素括起来。</span><span class="sxs-lookup"><span data-stu-id="6e01c-113">In this table, angle brackets (&lt;&gt;) enclose user-supplied syntax elements.</span></span> <span data-ttu-id="6e01c-114">有关这些构造中使用的语法的更多详细信息，请参阅每个语言构造的文档。</span><span class="sxs-lookup"><span data-stu-id="6e01c-114">Refer to the documentation for each language construct for more detailed information about the syntax used within these constructs.</span></span>

<table>
<tr>
<th><span data-ttu-id="6e01c-115">语言构造</span><span class="sxs-lookup"><span data-stu-id="6e01c-115">Language construct</span></span></th>
<th><span data-ttu-id="6e01c-116">轻型语法</span><span class="sxs-lookup"><span data-stu-id="6e01c-116">Lightweight syntax</span></span></th>
<th><span data-ttu-id="6e01c-117">详细语法</span><span class="sxs-lookup"><span data-stu-id="6e01c-117">Verbose syntax</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="6e01c-118">复合表达式</span><span class="sxs-lookup"><span data-stu-id="6e01c-118">compound expressions</span></span>
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

<span data-ttu-id="6e01c-119">嵌套`let`绑定</span><span class="sxs-lookup"><span data-stu-id="6e01c-119">nested `let` bindings</span></span>

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
<span data-ttu-id="6e01c-120">代码块</span><span class="sxs-lookup"><span data-stu-id="6e01c-120">code block</span></span>
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

```fsharp
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
<tr><td><span data-ttu-id="6e01c-121">记录</span><span class="sxs-lookup"><span data-stu-id="6e01c-121">record</span></span>
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
<tr><td><span data-ttu-id="6e01c-122">class</span><span class="sxs-lookup"><span data-stu-id="6e01c-122">class</span></span>
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
<tr><td><span data-ttu-id="6e01c-123">结构</span><span class="sxs-lookup"><span data-stu-id="6e01c-123">structure</span></span></td><td>

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
<tr><td><span data-ttu-id="6e01c-124">可区分联合</span><span class="sxs-lookup"><span data-stu-id="6e01c-124">discriminated union</span></span></td><td>

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
<tr><td><span data-ttu-id="6e01c-125">interface</span><span class="sxs-lookup"><span data-stu-id="6e01c-125">interface</span></span></td><td>

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
<tr><td><span data-ttu-id="6e01c-126">对象表达式</span><span class="sxs-lookup"><span data-stu-id="6e01c-126">object expression</span></span></td><td>

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
<tr><td><span data-ttu-id="6e01c-127">接口实现</span><span class="sxs-lookup"><span data-stu-id="6e01c-127">interface implementation</span></span></td><td>

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
<tr><td><span data-ttu-id="6e01c-128">类型扩展</span><span class="sxs-lookup"><span data-stu-id="6e01c-128">type extension</span></span></td><td>

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
<tr><td><span data-ttu-id="6e01c-129">name</span><span class="sxs-lookup"><span data-stu-id="6e01c-129">module</span></span></td><td>

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

## <a name="see-also"></a><span data-ttu-id="6e01c-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="6e01c-130">See also</span></span>

- [<span data-ttu-id="6e01c-131">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="6e01c-131">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="6e01c-132">编译器指令</span><span class="sxs-lookup"><span data-stu-id="6e01c-132">Compiler Directives</span></span>](compiler-directives.md)
- [<span data-ttu-id="6e01c-133">代码格式设置准则</span><span class="sxs-lookup"><span data-stu-id="6e01c-133">Code Formatting Guidelines</span></span>](code-formatting-guidelines.md)

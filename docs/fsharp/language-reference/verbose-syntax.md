---
title: "详细语法 (F#)"
description: "了解在 F # 编程语言的详细和轻量语法之间的差异。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 0a6792b3-b312-4453-a025-21d9760eee5d
ms.openlocfilehash: 2cef359a879897825733a3186be97b38896f5953
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="verbose-syntax"></a><span data-ttu-id="34ce4-104">详细语法</span><span class="sxs-lookup"><span data-stu-id="34ce4-104">Verbose Syntax</span></span>

<span data-ttu-id="34ce4-105">有两种形式的语法可用于对 F # 语言中的许多构造：*详细语法*和*轻量语法*。</span><span class="sxs-lookup"><span data-stu-id="34ce4-105">There are two forms of syntax available for many constructs in the F# language: *verbose syntax* and *lightweight syntax*.</span></span> <span data-ttu-id="34ce4-106">详细语法不常使用，但具有到缩进的敏感程度较低的优点。</span><span class="sxs-lookup"><span data-stu-id="34ce4-106">The verbose syntax is not as commonly used, but has the advantage of being less sensitive to indentation.</span></span> <span data-ttu-id="34ce4-107">轻量语法更简短，缩进用于表示的开头和末尾构造，而不是其他关键字，例如`begin`， `end`， `in`，依次类推。</span><span class="sxs-lookup"><span data-stu-id="34ce4-107">The lightweight syntax is shorter and uses indentation to signal the beginning and end of constructs, rather than additional keywords like `begin`, `end`, `in`, and so on.</span></span> <span data-ttu-id="34ce4-108">默认语法是轻量语法。</span><span class="sxs-lookup"><span data-stu-id="34ce4-108">The default syntax is the lightweight syntax.</span></span> <span data-ttu-id="34ce4-109">本主题介绍对 F # 构造语法时不启用轻量语法。</span><span class="sxs-lookup"><span data-stu-id="34ce4-109">This topic describes the syntax for F# constructs when lightweight syntax is not enabled.</span></span> <span data-ttu-id="34ce4-110">详细语法始终处于启用状态，因此即使启用轻量语法，仍可以对某些构造使用详细语法。</span><span class="sxs-lookup"><span data-stu-id="34ce4-110">Verbose syntax is always enabled, so even if you enable lightweight syntax, you can still use verbose syntax for some constructs.</span></span> <span data-ttu-id="34ce4-111">你可以通过使用禁用轻量语法`#light "off"`指令。</span><span class="sxs-lookup"><span data-stu-id="34ce4-111">You can disable lightweight syntax by using the `#light "off"` directive.</span></span>


## <a name="table-of-constructs"></a><span data-ttu-id="34ce4-112">构造表</span><span class="sxs-lookup"><span data-stu-id="34ce4-112">Table of Constructs</span></span>
<span data-ttu-id="34ce4-113">下表显示 F # 语言构造的轻量和详细语法在上下文中的两种形式之间的区别所在。</span><span class="sxs-lookup"><span data-stu-id="34ce4-113">The following table shows the lightweight and verbose syntax for F# language constructs in contexts where there is a difference between the two forms.</span></span> <span data-ttu-id="34ce4-114">在此表中，尖括号 (&lt;&gt;) 括起用户提供的语法元素。</span><span class="sxs-lookup"><span data-stu-id="34ce4-114">In this table, angle brackets (&lt;&gt;) enclose user-supplied syntax elements.</span></span> <span data-ttu-id="34ce4-115">请参阅每个语言构造，它用于在这些构造中使用的语法的更多详细信息的文档。</span><span class="sxs-lookup"><span data-stu-id="34ce4-115">Refer to the documentation for each language construct for more detailed information about the syntax used within these constructs.</span></span>



<table>
<tr>
<th><span data-ttu-id="34ce4-116">语言构造</span><span class="sxs-lookup"><span data-stu-id="34ce4-116">Language construct</span></span></th>
<th><span data-ttu-id="34ce4-117">轻量语法</span><span class="sxs-lookup"><span data-stu-id="34ce4-117">Lightweight syntax</span></span></th>
<th><span data-ttu-id="34ce4-118">详细语法</span><span class="sxs-lookup"><span data-stu-id="34ce4-118">Verbose syntax</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="34ce4-119">复合表达式</span><span class="sxs-lookup"><span data-stu-id="34ce4-119">compound expressions</span></span>
</td>
<td>

```xml
<expression1>
<expression2>
```
</td><td>

```
<expression1>; <expression2>
```

</td>
</tr>
<tr><td>


<span data-ttu-id="34ce4-120">嵌套`let`绑定</span><span class="sxs-lookup"><span data-stu-id="34ce4-120">nested `let` bindings</span></span>

</td><td>
```
let f x =
    let a = 1
    let b = 2
    x + a + b
```

</td><td>

```
let f x =
    let a = 1 in
    let b = 2 in
    x + a + b
```

</td>
</tr>
<tr><td>
<span data-ttu-id="34ce4-121">代码块</span><span class="sxs-lookup"><span data-stu-id="34ce4-121">code block</span></span>
</td><td>

```
(
    <expression1>
    <expression2>
)
```

</td><td>

```
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

```
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

```
while <condition> do
    ...
```

</td><td>

```
while <condition> do
    ...
done
```

</td>
</tr>
<tr><td>
`for...in`
</td><td>

```
for var in start .. finish do
    ...
```

</td><td>

```
for var in start .. finish do
    ...
done
```

</td>
</tr>
<tr><td>
`do`
</td><td>

```
do
    ...
```

</td><td>

```
do
    ...
in
```

</td>
</tr>
<tr><td><span data-ttu-id="34ce4-122">记录</span><span class="sxs-lookup"><span data-stu-id="34ce4-122">record</span></span>
</td><td>

```
type <record-name> =
    {
        <field-declarations>
    }
    <value-or-member-definitions>
```

</td><td>

```
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
<tr><td><span data-ttu-id="34ce4-123">类</span><span class="sxs-lookup"><span data-stu-id="34ce4-123">class</span></span>
</td><td><span data-ttu-id="34ce4-124">
```
type <class-name>(<params>) = ... ```

</span><span class="sxs-lookup"><span data-stu-id="34ce4-124">
```
type <class-name>(<params>) = ... ```

</span></span></td><td>

```
type <class-name>(<params>) =
    class
        ...
    end
```
</td>
</tr>
<tr><td><span data-ttu-id="34ce4-125">结构</span><span class="sxs-lookup"><span data-stu-id="34ce4-125">structure</span></span></td><td>

```
[<StructAttribute>]
type <structure-name> =
    ...
```
</td><td>

```
type <structure-name> =
    struct
        ...
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="34ce4-126">可区分的联合</span><span class="sxs-lookup"><span data-stu-id="34ce4-126">discriminated union</span></span></td><td>

```
type <union-name> =
    | ...
    | ...
    ...
    <value-or-member definitions>
```
</td><td>

```
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
<tr><td><span data-ttu-id="34ce4-127">接口</span><span class="sxs-lookup"><span data-stu-id="34ce4-127">interface</span></span></td><td>

```
type <interface-name> =
    ...
```
</td><td>

```
type <interface-name> =
    interface
        ...
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="34ce4-128">对象表达式</span><span class="sxs-lookup"><span data-stu-id="34ce4-128">object expression</span></span></td><td>

```
{ new <type-name>
    with
        <value-or-member-definitions>
        <interface-implementations>
}
```

</td><td>

```
{ new <type-name>
    with
        <value-or-member-definitions>
    end
    <interface-implementations>
}
```

</td>
</tr>
<tr><td><span data-ttu-id="34ce4-129">接口实现</span><span class="sxs-lookup"><span data-stu-id="34ce4-129">interface implementation</span></span></td><td>

```
interface <interface-name>
    with
        <value-or-member-definitions>
```

</td><td>

```
interface <interface-name>
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="34ce4-130">类型扩展</span><span class="sxs-lookup"><span data-stu-id="34ce4-130">type extension</span></span></td><td>

```
type <type-name>
    with
        <value-or-member-definitions>
```

</td><td>

```
type <type-name>
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="34ce4-131">name</span><span class="sxs-lookup"><span data-stu-id="34ce4-131">module</span></span></td><td>

```
module <module-name> =
    ...
```

</td><td>

```
module <module-name> =
    begin
        ...
    end
```

</td>
</tr>
</table>



## <a name="see-also"></a><span data-ttu-id="34ce4-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="34ce4-132">See Also</span></span>
[<span data-ttu-id="34ce4-133">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="34ce4-133">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="34ce4-134">编译器指令</span><span class="sxs-lookup"><span data-stu-id="34ce4-134">Compiler Directives</span></span>](compiler-directives.md)

[<span data-ttu-id="34ce4-135">代码格式设置准则</span><span class="sxs-lookup"><span data-stu-id="34ce4-135">Code Formatting Guidelines</span></span>](code-formatting-guidelines.md)

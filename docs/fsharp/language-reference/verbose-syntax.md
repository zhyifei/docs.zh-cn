---
title: 详细语法 (F#)
description: '了解 F # 编程语言中的详细和轻量语法之间的差异。'
ms.date: 05/16/2016
ms.openlocfilehash: b4f2354738da4692cb444e5e7dd9531d80d26664
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44193154"
---
# <a name="verbose-syntax"></a><span data-ttu-id="8042c-103">详细语法</span><span class="sxs-lookup"><span data-stu-id="8042c-103">Verbose Syntax</span></span>

<span data-ttu-id="8042c-104">有两种形式的语法可用于 F # 语言中的许多构造：*详细语法*并*轻量语法*。</span><span class="sxs-lookup"><span data-stu-id="8042c-104">There are two forms of syntax available for many constructs in the F# language: *verbose syntax* and *lightweight syntax*.</span></span> <span data-ttu-id="8042c-105">详细语法不常使用，但具有的优势在于到缩进的敏感程度较低。</span><span class="sxs-lookup"><span data-stu-id="8042c-105">The verbose syntax is not as commonly used, but has the advantage of being less sensitive to indentation.</span></span> <span data-ttu-id="8042c-106">轻量语法为较短，并使用缩进发出信号的开头和结尾的构造，而不是其他关键字，例如`begin`， `end`， `in`，依次类推。</span><span class="sxs-lookup"><span data-stu-id="8042c-106">The lightweight syntax is shorter and uses indentation to signal the beginning and end of constructs, rather than additional keywords like `begin`, `end`, `in`, and so on.</span></span> <span data-ttu-id="8042c-107">默认语法为轻量语法。</span><span class="sxs-lookup"><span data-stu-id="8042c-107">The default syntax is the lightweight syntax.</span></span> <span data-ttu-id="8042c-108">未启用轻量语法时，本主题介绍对 F # 构造的语法。</span><span class="sxs-lookup"><span data-stu-id="8042c-108">This topic describes the syntax for F# constructs when lightweight syntax is not enabled.</span></span> <span data-ttu-id="8042c-109">详细语法始终处于启用状态，因此即使您启用轻量语法，仍然可以为某些构造使用详细语法。</span><span class="sxs-lookup"><span data-stu-id="8042c-109">Verbose syntax is always enabled, so even if you enable lightweight syntax, you can still use verbose syntax for some constructs.</span></span> <span data-ttu-id="8042c-110">可以使用禁用轻量语法`#light "off"`指令。</span><span class="sxs-lookup"><span data-stu-id="8042c-110">You can disable lightweight syntax by using the `#light "off"` directive.</span></span>

## <a name="table-of-constructs"></a><span data-ttu-id="8042c-111">构造表</span><span class="sxs-lookup"><span data-stu-id="8042c-111">Table of Constructs</span></span>

<span data-ttu-id="8042c-112">下表显示了 F # 语言构造的轻量和详细语法，在上下文中存在两种形式之间的差异的。</span><span class="sxs-lookup"><span data-stu-id="8042c-112">The following table shows the lightweight and verbose syntax for F# language constructs in contexts where there is a difference between the two forms.</span></span> <span data-ttu-id="8042c-113">在此表中，角度方括号 (&lt;&gt;) 括起来的用户提供的语法元素。</span><span class="sxs-lookup"><span data-stu-id="8042c-113">In this table, angle brackets (&lt;&gt;) enclose user-supplied syntax elements.</span></span> <span data-ttu-id="8042c-114">请参阅有关使用这些构造中的语法的更多详细信息每种语言构造的文档。</span><span class="sxs-lookup"><span data-stu-id="8042c-114">Refer to the documentation for each language construct for more detailed information about the syntax used within these constructs.</span></span>

<table>
<tr>
<th><span data-ttu-id="8042c-115">语言构造</span><span class="sxs-lookup"><span data-stu-id="8042c-115">Language construct</span></span></th>
<th><span data-ttu-id="8042c-116">轻量语法</span><span class="sxs-lookup"><span data-stu-id="8042c-116">Lightweight syntax</span></span></th>
<th><span data-ttu-id="8042c-117">详细语法</span><span class="sxs-lookup"><span data-stu-id="8042c-117">Verbose syntax</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="8042c-118">复合表达式</span><span class="sxs-lookup"><span data-stu-id="8042c-118">compound expressions</span></span>
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


<span data-ttu-id="8042c-119">嵌套`let`绑定</span><span class="sxs-lookup"><span data-stu-id="8042c-119">nested `let` bindings</span></span>

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
<span data-ttu-id="8042c-120">代码块</span><span class="sxs-lookup"><span data-stu-id="8042c-120">code block</span></span>
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
<tr><td><span data-ttu-id="8042c-121">记录</span><span class="sxs-lookup"><span data-stu-id="8042c-121">record</span></span>
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
<tr><td><span data-ttu-id="8042c-122">class</span><span class="sxs-lookup"><span data-stu-id="8042c-122">class</span></span>
</td><td><span data-ttu-id="8042c-123">
```
type <class-name>(<params>) = ... ```

</span><span class="sxs-lookup"><span data-stu-id="8042c-123">
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
<tr><td><span data-ttu-id="8042c-124">结构</span><span class="sxs-lookup"><span data-stu-id="8042c-124">structure</span></span></td><td>

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
<tr><td><span data-ttu-id="8042c-125">可区分的联合</span><span class="sxs-lookup"><span data-stu-id="8042c-125">discriminated union</span></span></td><td>

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
<tr><td><span data-ttu-id="8042c-126">interface</span><span class="sxs-lookup"><span data-stu-id="8042c-126">interface</span></span></td><td>

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
<tr><td><span data-ttu-id="8042c-127">对象表达式</span><span class="sxs-lookup"><span data-stu-id="8042c-127">object expression</span></span></td><td>

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
<tr><td><span data-ttu-id="8042c-128">接口实现</span><span class="sxs-lookup"><span data-stu-id="8042c-128">interface implementation</span></span></td><td>

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
<tr><td><span data-ttu-id="8042c-129">类型扩展</span><span class="sxs-lookup"><span data-stu-id="8042c-129">type extension</span></span></td><td>

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
<tr><td><span data-ttu-id="8042c-130">name</span><span class="sxs-lookup"><span data-stu-id="8042c-130">module</span></span></td><td>

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

## <a name="see-also"></a><span data-ttu-id="8042c-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="8042c-131">See also</span></span>

- [<span data-ttu-id="8042c-132">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="8042c-132">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="8042c-133">编译器指令</span><span class="sxs-lookup"><span data-stu-id="8042c-133">Compiler Directives</span></span>](compiler-directives.md)
- [<span data-ttu-id="8042c-134">代码格式设置准则</span><span class="sxs-lookup"><span data-stu-id="8042c-134">Code Formatting Guidelines</span></span>](code-formatting-guidelines.md)

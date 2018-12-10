---
title: C# 表达式 - C# 语言介绍
description: 表达式、操作数和运算符是 C# 语言的构建基块
ms.date: 11/06/2016
ms.assetid: 20d5eb10-7381-47b9-ad90-f1cc895aa27e
ms.openlocfilehash: 28e1d6952975c6932dc9ae40af28c7201d61d778
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53154929"
---
# <a name="expressions"></a><span data-ttu-id="e76cb-103">表达式</span><span class="sxs-lookup"><span data-stu-id="e76cb-103">Expressions</span></span>

<span data-ttu-id="e76cb-104">*表达式*是在*操作数*和*运算符*的基础之上构造而成。</span><span class="sxs-lookup"><span data-stu-id="e76cb-104">*Expressions* are constructed from *operands* and *operators*.</span></span> <span data-ttu-id="e76cb-105">表达式的运算符指明了向操作数应用的运算。</span><span class="sxs-lookup"><span data-stu-id="e76cb-105">The operators of an expression indicate which operations to apply to the operands.</span></span> <span data-ttu-id="e76cb-106">运算符的示例包括 `+`、`-`、`*`、`/` 和 `new`。</span><span class="sxs-lookup"><span data-stu-id="e76cb-106">Examples of operators include `+`, `-`, `*`, `/`, and `new`.</span></span> <span data-ttu-id="e76cb-107">操作数的示例包括文本、字段、局部变量和表达式。</span><span class="sxs-lookup"><span data-stu-id="e76cb-107">Examples of operands include literals, fields, local variables, and expressions.</span></span>

<span data-ttu-id="e76cb-108">如果表达式包含多个运算符，那么运算符的*优先级*决定了各个运算符的计算顺序。</span><span class="sxs-lookup"><span data-stu-id="e76cb-108">When an expression contains multiple operators, the *precedence* of the operators controls the order in which the individual operators are evaluated.</span></span> <span data-ttu-id="e76cb-109">例如，表达式 `x + y * z` 相当于计算 `x + (y * z)`，因为 `*` 运算符的优先级高于 `+` 运算符。</span><span class="sxs-lookup"><span data-stu-id="e76cb-109">For example, the expression `x + y * z` is evaluated as `x + (y * z)` because the `*` operator has higher precedence than the `+` operator.</span></span>

<span data-ttu-id="e76cb-110">如果操作数两边的两个运算符的优先级相同，那么运算符的*结合性*决定了运算的执行顺序：</span><span class="sxs-lookup"><span data-stu-id="e76cb-110">When an operand occurs between two operators with the same precedence, the *associativity* of the operators controls the order in which the operations are performed:</span></span>

*   <span data-ttu-id="e76cb-111">除了赋值运算符之外，所有二元运算符均为*左结合*运算符，即从左向右执行运算。</span><span class="sxs-lookup"><span data-stu-id="e76cb-111">Except for the assignment operators, all binary operators are *left-associative*, meaning that operations are performed from left to right.</span></span> <span data-ttu-id="e76cb-112">例如，`x + y + z` 将计算为 `(x + y) + z`。</span><span class="sxs-lookup"><span data-stu-id="e76cb-112">For example, `x + y + z` is evaluated as `(x + y) + z`.</span></span>
*   <span data-ttu-id="e76cb-113">赋值运算符和条件运算符 (`?:`) 为*右结合*运算符，即从右向左执行运算。</span><span class="sxs-lookup"><span data-stu-id="e76cb-113">The assignment operators and the conditional operator (`?:`) are *right-associative*, meaning that operations are performed from right to left.</span></span> <span data-ttu-id="e76cb-114">例如，`x = y = z` 将计算为 `x = (y = z)`。</span><span class="sxs-lookup"><span data-stu-id="e76cb-114">For example, `x = y = z` is evaluated as `x = (y = z)`.</span></span>

<span data-ttu-id="e76cb-115">可以使用括号控制优先级和结合性。</span><span class="sxs-lookup"><span data-stu-id="e76cb-115">Precedence and associativity can be controlled using parentheses.</span></span> <span data-ttu-id="e76cb-116">例如，`x + y * z` 先计算 `y` 乘 `z`，并将结果与 `x` 相加，而 `(x + y) * z` 则先计算 `x` 加 `y`，然后将结果与 `z` 相乘。</span><span class="sxs-lookup"><span data-stu-id="e76cb-116">For example, `x + y * z` first multiplies `y` by `z` and then adds the result to `x`, but `(x + y) * z` first adds `x` and `y` and then multiplies the result by `z`.</span></span>

<span data-ttu-id="e76cb-117">大多数运算符都可以*重载*。</span><span class="sxs-lookup"><span data-stu-id="e76cb-117">Most operators can be *overloaded*.</span></span> <span data-ttu-id="e76cb-118">借助运算符重载，可以为一个或两个操作数为用户定义类或结构类型的运算指定用户定义运算符实现代码。</span><span class="sxs-lookup"><span data-stu-id="e76cb-118">Operator overloading permits user-defined operator implementations to be specified for operations where one or both of the operands are of a user-defined class or struct type.</span></span>

<span data-ttu-id="e76cb-119">下面总结了 C# 运算符，按优先级从高到低的顺序列出了各类运算符。</span><span class="sxs-lookup"><span data-stu-id="e76cb-119">The following summarizes C#’s operators, listing the operator categories in order of precedence from highest to lowest.</span></span> <span data-ttu-id="e76cb-120">同一类别的运算符的优先级也相同。</span><span class="sxs-lookup"><span data-stu-id="e76cb-120">Operators in the same category have equal precedence.</span></span> <span data-ttu-id="e76cb-121">每个类别下均列出了相应类别的表达式，以及对每种表达式类型的说明。</span><span class="sxs-lookup"><span data-stu-id="e76cb-121">Under each category is a list of expressions in that category along with the description of that expression type.</span></span>

* <span data-ttu-id="e76cb-122">基本</span><span class="sxs-lookup"><span data-stu-id="e76cb-122">Primary</span></span>
    - <span data-ttu-id="e76cb-123">`x.m`：成员访问</span><span class="sxs-lookup"><span data-stu-id="e76cb-123">`x.m`: Member access</span></span>
    - <span data-ttu-id="e76cb-124">`x(...)`：方法和委托调用</span><span class="sxs-lookup"><span data-stu-id="e76cb-124">`x(...)`: Method and delegate invocation</span></span>
    - <span data-ttu-id="e76cb-125">`x[...]`：数组和索引器访问</span><span class="sxs-lookup"><span data-stu-id="e76cb-125">`x[...]`: Array and indexer access</span></span>
    - <span data-ttu-id="e76cb-126">`x++`：后置递增</span><span class="sxs-lookup"><span data-stu-id="e76cb-126">`x++`: Post-increment</span></span>
    - <span data-ttu-id="e76cb-127">`x--`：后置递减</span><span class="sxs-lookup"><span data-stu-id="e76cb-127">`x--`: Post-decrement</span></span>
    - <span data-ttu-id="e76cb-128">`new T(...)`：创建对象和委托</span><span class="sxs-lookup"><span data-stu-id="e76cb-128">`new T(...)`: Object and delegate creation</span></span>
    - <span data-ttu-id="e76cb-129">`new T(...){...}`：使用初始值设定项的对象创建</span><span class="sxs-lookup"><span data-stu-id="e76cb-129">`new T(...){...}`: Object creation with initializer</span></span>
    - <span data-ttu-id="e76cb-130">`new {...}`：匿名对象初始值设定项</span><span class="sxs-lookup"><span data-stu-id="e76cb-130">`new {...}`:  Anonymous object initializer</span></span>
    - <span data-ttu-id="e76cb-131">`new T[...]`：数组创建</span><span class="sxs-lookup"><span data-stu-id="e76cb-131">`new T[...]`: Array creation</span></span>
    - <span data-ttu-id="e76cb-132">`typeof(T)`：获取 `T` 的 <xref:System.Type> 对象</span><span class="sxs-lookup"><span data-stu-id="e76cb-132">`typeof(T)`: Obtain <xref:System.Type> object for `T`</span></span>
    - <span data-ttu-id="e76cb-133">`checked(x)`：在已检查的上下文中计算表达式</span><span class="sxs-lookup"><span data-stu-id="e76cb-133">`checked(x)`: Evaluate expression in checked context</span></span>
    - <span data-ttu-id="e76cb-134">`unchecked(x)`：在未检查的上下文中计算表达式</span><span class="sxs-lookup"><span data-stu-id="e76cb-134">`unchecked(x)`: Evaluate expression in unchecked context</span></span>
    - <span data-ttu-id="e76cb-135">`default(T)`：获取类型为 `T` 的默认值</span><span class="sxs-lookup"><span data-stu-id="e76cb-135">`default(T)`: Obtain default value of type `T`</span></span>
    - <span data-ttu-id="e76cb-136">`delegate {...}`：匿名函数（匿名方法）</span><span class="sxs-lookup"><span data-stu-id="e76cb-136">`delegate {...}`: Anonymous function (anonymous method)</span></span>
* <span data-ttu-id="e76cb-137">一元</span><span class="sxs-lookup"><span data-stu-id="e76cb-137">Unary</span></span>
    - <span data-ttu-id="e76cb-138">`+x`：标识</span><span class="sxs-lookup"><span data-stu-id="e76cb-138">`+x`: Identity</span></span>
    - <span data-ttu-id="e76cb-139">`-x`：取反</span><span class="sxs-lookup"><span data-stu-id="e76cb-139">`-x`: Negation</span></span>
    - <span data-ttu-id="e76cb-140">`!x`：逻辑取反</span><span class="sxs-lookup"><span data-stu-id="e76cb-140">`!x`: Logical negation</span></span>
    - <span data-ttu-id="e76cb-141">`~x`：按位取反</span><span class="sxs-lookup"><span data-stu-id="e76cb-141">`~x`: Bitwise negation</span></span>
    - <span data-ttu-id="e76cb-142">`++x`：前置递增</span><span class="sxs-lookup"><span data-stu-id="e76cb-142">`++x`: Pre-increment</span></span>
    - <span data-ttu-id="e76cb-143">`--x`：前置递减</span><span class="sxs-lookup"><span data-stu-id="e76cb-143">`--x`: Pre-decrement</span></span>
    - <span data-ttu-id="e76cb-144">`(T)x`：将 `x` 显式转换成类型 `T`</span><span class="sxs-lookup"><span data-stu-id="e76cb-144">`(T)x`: Explicitly convert `x` to type `T`</span></span>
    - <span data-ttu-id="e76cb-145">`await x`：异步等待 `x` 完成</span><span class="sxs-lookup"><span data-stu-id="e76cb-145">`await x`: Asynchronously wait for `x` to complete</span></span>
* <span data-ttu-id="e76cb-146">乘法</span><span class="sxs-lookup"><span data-stu-id="e76cb-146">Multiplicative</span></span>
    - <span data-ttu-id="e76cb-147">`x * y`：乘法</span><span class="sxs-lookup"><span data-stu-id="e76cb-147">`x * y`: Multiplication</span></span>
    - <span data-ttu-id="e76cb-148">`x / y`：除法</span><span class="sxs-lookup"><span data-stu-id="e76cb-148">`x / y`: Division</span></span>
    - <span data-ttu-id="e76cb-149">`x % y`：求余</span><span class="sxs-lookup"><span data-stu-id="e76cb-149">`x % y`: Remainder</span></span>
* <span data-ttu-id="e76cb-150">加法</span><span class="sxs-lookup"><span data-stu-id="e76cb-150">Additive</span></span>
    - <span data-ttu-id="e76cb-151">`x + y`：加法、字符串串联、委托组合</span><span class="sxs-lookup"><span data-stu-id="e76cb-151">`x + y`: Addition, string concatenation, delegate combination</span></span>
    - <span data-ttu-id="e76cb-152">`x – y`：减法、委托删除</span><span class="sxs-lookup"><span data-stu-id="e76cb-152">`x – y`: Subtraction, delegate removal</span></span>
* <span data-ttu-id="e76cb-153">移位</span><span class="sxs-lookup"><span data-stu-id="e76cb-153">Shift</span></span>
    - <span data-ttu-id="e76cb-154">`x << y`：左移位</span><span class="sxs-lookup"><span data-stu-id="e76cb-154">`x << y`: Shift left</span></span>
    - <span data-ttu-id="e76cb-155">`x >> y`：右移位</span><span class="sxs-lookup"><span data-stu-id="e76cb-155">`x >> y`: Shift right</span></span>
* <span data-ttu-id="e76cb-156">关系和类型测试</span><span class="sxs-lookup"><span data-stu-id="e76cb-156">Relational and type testing</span></span>
    - <span data-ttu-id="e76cb-157">`x < y`：小于</span><span class="sxs-lookup"><span data-stu-id="e76cb-157">`x < y`: Less than</span></span>
    - <span data-ttu-id="e76cb-158">`x > y`：大于</span><span class="sxs-lookup"><span data-stu-id="e76cb-158">`x > y`: Greater than</span></span>
    - <span data-ttu-id="e76cb-159">`x <= y`：小于或等于</span><span class="sxs-lookup"><span data-stu-id="e76cb-159">`x <= y`: Less than or equal</span></span>
    - <span data-ttu-id="e76cb-160">`x >= y`：大于或等于</span><span class="sxs-lookup"><span data-stu-id="e76cb-160">`x >= y`: Greater than or equal</span></span>
    - <span data-ttu-id="e76cb-161">`x is T`：如果 `x` 是 `T`，返回 `true`；否则，返回 `false`</span><span class="sxs-lookup"><span data-stu-id="e76cb-161">`x is T`: Return `true` if `x` is a `T`, `false` otherwise</span></span>
    - <span data-ttu-id="e76cb-162">`x as T`：返回类型为 `T` 的 `x`；如果 `x` 的类型不是 `T`，返回 `null`</span><span class="sxs-lookup"><span data-stu-id="e76cb-162">`x as T`: Return `x` typed as `T`, or `null` if `x` is not a `T`</span></span>
* <span data-ttu-id="e76cb-163">相等</span><span class="sxs-lookup"><span data-stu-id="e76cb-163">Equality</span></span>
    - <span data-ttu-id="e76cb-164">`x == y`：等于</span><span class="sxs-lookup"><span data-stu-id="e76cb-164">`x == y`: Equal</span></span>
    - <span data-ttu-id="e76cb-165">`x != y`：不等于</span><span class="sxs-lookup"><span data-stu-id="e76cb-165">`x != y`: Not equal</span></span>
* <span data-ttu-id="e76cb-166">逻辑“与”</span><span class="sxs-lookup"><span data-stu-id="e76cb-166">Logical AND</span></span>
    - <span data-ttu-id="e76cb-167">`x & y`：整数型位AND，布尔型逻辑 AND</span><span class="sxs-lookup"><span data-stu-id="e76cb-167">`x & y`: Integer bitwise AND, boolean logical AND</span></span>
* <span data-ttu-id="e76cb-168">逻辑 XOR</span><span class="sxs-lookup"><span data-stu-id="e76cb-168">Logical XOR</span></span>
    - <span data-ttu-id="e76cb-169">`x ^ y`：整数型位 XOR，布尔型逻辑 XOR</span><span class="sxs-lookup"><span data-stu-id="e76cb-169">`x ^ y`: Integer bitwise XOR, boolean logical XOR</span></span>
* <span data-ttu-id="e76cb-170">逻辑“或”</span><span class="sxs-lookup"><span data-stu-id="e76cb-170">Logical OR</span></span>
    - <span data-ttu-id="e76cb-171">`x | y`：整数型位 OR，布尔型逻辑 OR</span><span class="sxs-lookup"><span data-stu-id="e76cb-171">`x | y`: Integer bitwise OR, boolean logical OR</span></span>
* <span data-ttu-id="e76cb-172">条件“与”</span><span class="sxs-lookup"><span data-stu-id="e76cb-172">Conditional AND</span></span>
    - <span data-ttu-id="e76cb-173">`x && y`：仅当 `x` 不是 `false` 时，才计算 `y`</span><span class="sxs-lookup"><span data-stu-id="e76cb-173">`x && y`: Evaluates `y` only if `x` is not `false`</span></span>
* <span data-ttu-id="e76cb-174">条件“或”</span><span class="sxs-lookup"><span data-stu-id="e76cb-174">Conditional OR</span></span>
    - <span data-ttu-id="e76cb-175">`x || y`：仅当 `x` 不是 `true` 时，才计算 `y`</span><span class="sxs-lookup"><span data-stu-id="e76cb-175">`x || y`: Evaluates `y` only if `x` is not `true`</span></span>
* <span data-ttu-id="e76cb-176">null 合并</span><span class="sxs-lookup"><span data-stu-id="e76cb-176">Null coalescing</span></span>
    - <span data-ttu-id="e76cb-177">`x ?? y`：如果 `x` 为 null，计算结果为 `y`；否则，计算结果为 `x`</span><span class="sxs-lookup"><span data-stu-id="e76cb-177">`x ?? y`: Evaluates to `y` if `x` is null, to `x` otherwise</span></span>
* <span data-ttu-id="e76cb-178">条件运算</span><span class="sxs-lookup"><span data-stu-id="e76cb-178">Conditional</span></span>
    - <span data-ttu-id="e76cb-179">`x ? y : z`：如果 `x` 为 `true`，计算 `y`；如果 `x` 为 `false`，计算 `z`</span><span class="sxs-lookup"><span data-stu-id="e76cb-179">`x ? y : z`: Evaluates `y` if `x` is `true`, `z` if `x` is `false`</span></span>
* <span data-ttu-id="e76cb-180">赋值或匿名函数</span><span class="sxs-lookup"><span data-stu-id="e76cb-180">Assignment or anonymous function</span></span>
    - <span data-ttu-id="e76cb-181">`x = y`：赋值</span><span class="sxs-lookup"><span data-stu-id="e76cb-181">`x = y`: Assignment</span></span>
    - <span data-ttu-id="e76cb-182">`x op= y`：复合赋值；支持以下运算符</span><span class="sxs-lookup"><span data-stu-id="e76cb-182">`x op= y`: Compound assignment; supported operators are</span></span>
        - <span data-ttu-id="e76cb-183">`*=`   `/=`   `%=`   `+=`   `-=`   `<<=`   `>>=`   `&=`  `^=`  `|=`</span><span class="sxs-lookup"><span data-stu-id="e76cb-183">`*=`   `/=`   `%=`   `+=`   `-=`   `<<=`   `>>=`   `&=`  `^=`  `|=`</span></span>
    - <span data-ttu-id="e76cb-184">`(T x) => y`：匿名函数（lambda 表达式）</span><span class="sxs-lookup"><span data-stu-id="e76cb-184">`(T x) => y`: Anonymous function (lambda expression)</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e76cb-185">[上一页](types-and-variables.md)
>[下一页](statements.md)</span><span class="sxs-lookup"><span data-stu-id="e76cb-185">[Previous](types-and-variables.md)
[Next](statements.md)</span></span>
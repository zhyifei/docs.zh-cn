---
title: C# 表达式 - C# 语言介绍
description: 表达式、操作数和运算符是 C# 语言的构建基块
ms.date: 11/06/2016
ms.assetid: 20d5eb10-7381-47b9-ad90-f1cc895aa27e
ms.openlocfilehash: 4ffe947a4cb8c36a5925a4b3846486e44a9d8ec4
ms.sourcegitcommit: 859b2ba0c74a1a5a4ad0d59a3c3af23450995981
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2019
ms.locfileid: "59480750"
---
# <a name="expressions"></a><span data-ttu-id="0d341-103">表达式</span><span class="sxs-lookup"><span data-stu-id="0d341-103">Expressions</span></span>

<span data-ttu-id="0d341-104">*表达式*是在*操作数*和*运算符*的基础之上构造而成。</span><span class="sxs-lookup"><span data-stu-id="0d341-104">*Expressions* are constructed from *operands* and *operators*.</span></span> <span data-ttu-id="0d341-105">表达式的运算符指明了向操作数应用的运算。</span><span class="sxs-lookup"><span data-stu-id="0d341-105">The operators of an expression indicate which operations to apply to the operands.</span></span> <span data-ttu-id="0d341-106">运算符的示例包括 `+`、`-`、`*`、`/` 和 `new`。</span><span class="sxs-lookup"><span data-stu-id="0d341-106">Examples of operators include `+`, `-`, `*`, `/`, and `new`.</span></span> <span data-ttu-id="0d341-107">操作数的示例包括文本、字段、局部变量和表达式。</span><span class="sxs-lookup"><span data-stu-id="0d341-107">Examples of operands include literals, fields, local variables, and expressions.</span></span>

<span data-ttu-id="0d341-108">如果表达式包含多个运算符，那么运算符的*优先级*决定了各个运算符的计算顺序。</span><span class="sxs-lookup"><span data-stu-id="0d341-108">When an expression contains multiple operators, the *precedence* of the operators controls the order in which the individual operators are evaluated.</span></span> <span data-ttu-id="0d341-109">例如，表达式 `x + y * z` 相当于计算 `x + (y * z)`，因为 `*` 运算符的优先级高于 `+` 运算符。</span><span class="sxs-lookup"><span data-stu-id="0d341-109">For example, the expression `x + y * z` is evaluated as `x + (y * z)` because the `*` operator has higher precedence than the `+` operator.</span></span>

<span data-ttu-id="0d341-110">如果操作数两边的两个运算符的优先级相同，那么运算符的*结合性*决定了运算的执行顺序：</span><span class="sxs-lookup"><span data-stu-id="0d341-110">When an operand occurs between two operators with the same precedence, the *associativity* of the operators controls the order in which the operations are performed:</span></span>

* <span data-ttu-id="0d341-111">除了赋值运算符之外，所有二元运算符均为*左结合*运算符，即从左向右执行运算。</span><span class="sxs-lookup"><span data-stu-id="0d341-111">Except for the assignment operators, all binary operators are *left-associative*, meaning that operations are performed from left to right.</span></span> <span data-ttu-id="0d341-112">例如，`x + y + z` 将计算为 `(x + y) + z`。</span><span class="sxs-lookup"><span data-stu-id="0d341-112">For example, `x + y + z` is evaluated as `(x + y) + z`.</span></span>
* <span data-ttu-id="0d341-113">赋值运算符和条件运算符 (`?:`) 为*右结合*运算符，即从右向左执行运算。</span><span class="sxs-lookup"><span data-stu-id="0d341-113">The assignment operators and the conditional operator (`?:`) are *right-associative*, meaning that operations are performed from right to left.</span></span> <span data-ttu-id="0d341-114">例如，`x = y = z` 将计算为 `x = (y = z)`。</span><span class="sxs-lookup"><span data-stu-id="0d341-114">For example, `x = y = z` is evaluated as `x = (y = z)`.</span></span>

<span data-ttu-id="0d341-115">可以使用括号控制优先级和结合性。</span><span class="sxs-lookup"><span data-stu-id="0d341-115">Precedence and associativity can be controlled using parentheses.</span></span> <span data-ttu-id="0d341-116">例如，`x + y * z` 先计算 `y` 乘 `z`，并将结果与 `x` 相加，而 `(x + y) * z` 则先计算 `x` 加 `y`，然后将结果与 `z` 相乘。</span><span class="sxs-lookup"><span data-stu-id="0d341-116">For example, `x + y * z` first multiplies `y` by `z` and then adds the result to `x`, but `(x + y) * z` first adds `x` and `y` and then multiplies the result by `z`.</span></span>

<span data-ttu-id="0d341-117">大多数运算符都可以*重载*。</span><span class="sxs-lookup"><span data-stu-id="0d341-117">Most operators can be *overloaded*.</span></span> <span data-ttu-id="0d341-118">借助运算符重载，可以为一个或两个操作数为用户定义类或结构类型的运算指定用户定义运算符实现代码。</span><span class="sxs-lookup"><span data-stu-id="0d341-118">Operator overloading permits user-defined operator implementations to be specified for operations where one or both of the operands are of a user-defined class or struct type.</span></span>

<span data-ttu-id="0d341-119">下面总结了 C# 运算符，按优先级从高到低的顺序列出了各类运算符。</span><span class="sxs-lookup"><span data-stu-id="0d341-119">The following summarizes C#’s operators, listing the operator categories in order of precedence from highest to lowest.</span></span> <span data-ttu-id="0d341-120">同一类别的运算符的优先级也相同。</span><span class="sxs-lookup"><span data-stu-id="0d341-120">Operators in the same category have equal precedence.</span></span> <span data-ttu-id="0d341-121">每个类别下均列出了相应类别的表达式，以及对每种表达式类型的说明。</span><span class="sxs-lookup"><span data-stu-id="0d341-121">Under each category is a list of expressions in that category along with the description of that expression type.</span></span>

* <span data-ttu-id="0d341-122">基本</span><span class="sxs-lookup"><span data-stu-id="0d341-122">Primary</span></span>
  - `x.m`<span data-ttu-id="0d341-123">:成员访问</span><span class="sxs-lookup"><span data-stu-id="0d341-123">: Member access</span></span>
  - `x(...)`<span data-ttu-id="0d341-124">:方法和委托调用</span><span class="sxs-lookup"><span data-stu-id="0d341-124">: Method and delegate invocation</span></span>
  - `x[...]`<span data-ttu-id="0d341-125">:数组和索引器访问</span><span class="sxs-lookup"><span data-stu-id="0d341-125">: Array and indexer access</span></span>
  - `x++`<span data-ttu-id="0d341-126">:后递增</span><span class="sxs-lookup"><span data-stu-id="0d341-126">: Post-increment</span></span>
  - `x--`<span data-ttu-id="0d341-127">:后递减</span><span class="sxs-lookup"><span data-stu-id="0d341-127">: Post-decrement</span></span>
  - `new T(...)`<span data-ttu-id="0d341-128">:对象和委托创建</span><span class="sxs-lookup"><span data-stu-id="0d341-128">: Object and delegate creation</span></span>
  - `new T(...){...}`<span data-ttu-id="0d341-129">:使用初始值设定项创建对象</span><span class="sxs-lookup"><span data-stu-id="0d341-129">: Object creation with initializer</span></span>
  - `new {...}`<span data-ttu-id="0d341-130">:匿名对象初始值设定项</span><span class="sxs-lookup"><span data-stu-id="0d341-130">:  Anonymous object initializer</span></span>
  - `new T[...]`<span data-ttu-id="0d341-131">:数组创建</span><span class="sxs-lookup"><span data-stu-id="0d341-131">: Array creation</span></span>
  - `typeof(T)`<span data-ttu-id="0d341-132">:获取 <xref:System.Type> 对象</span><span class="sxs-lookup"><span data-stu-id="0d341-132">: Obtain <xref:System.Type> object for</span></span> `T`
  - `checked(x)`<span data-ttu-id="0d341-133">:在已检查的上下文中计算表达式</span><span class="sxs-lookup"><span data-stu-id="0d341-133">: Evaluate expression in checked context</span></span>
  - `unchecked(x)`<span data-ttu-id="0d341-134">:在未检查的上下文中计算表达式</span><span class="sxs-lookup"><span data-stu-id="0d341-134">: Evaluate expression in unchecked context</span></span>
  - `default(T)`<span data-ttu-id="0d341-135">:获取类型的默认值</span><span class="sxs-lookup"><span data-stu-id="0d341-135">: Obtain default value of type</span></span> `T`
  - `delegate {...}`<span data-ttu-id="0d341-136">:匿名函数（匿名方法）</span><span class="sxs-lookup"><span data-stu-id="0d341-136">: Anonymous function (anonymous method)</span></span>
* <span data-ttu-id="0d341-137">一元</span><span class="sxs-lookup"><span data-stu-id="0d341-137">Unary</span></span>
  - `+x`<span data-ttu-id="0d341-138">:标识</span><span class="sxs-lookup"><span data-stu-id="0d341-138">: Identity</span></span>
  - `-x`<span data-ttu-id="0d341-139">:求反</span><span class="sxs-lookup"><span data-stu-id="0d341-139">: Negation</span></span>
  - `!x`<span data-ttu-id="0d341-140">:逻辑求反</span><span class="sxs-lookup"><span data-stu-id="0d341-140">: Logical negation</span></span>
  - `~x`<span data-ttu-id="0d341-141">:按位求反</span><span class="sxs-lookup"><span data-stu-id="0d341-141">: Bitwise negation</span></span>
  - `++x`<span data-ttu-id="0d341-142">:前递增</span><span class="sxs-lookup"><span data-stu-id="0d341-142">: Pre-increment</span></span>
  - `--x`<span data-ttu-id="0d341-143">:前递减</span><span class="sxs-lookup"><span data-stu-id="0d341-143">: Pre-decrement</span></span>
  - `(T)x`<span data-ttu-id="0d341-144">:将 `x` 显式转换为类型</span><span class="sxs-lookup"><span data-stu-id="0d341-144">: Explicitly convert `x` to type</span></span> `T`
  - `await x`<span data-ttu-id="0d341-145">:异步等待 `x` 完成</span><span class="sxs-lookup"><span data-stu-id="0d341-145">: Asynchronously wait for `x` to complete</span></span>
* <span data-ttu-id="0d341-146">乘法</span><span class="sxs-lookup"><span data-stu-id="0d341-146">Multiplicative</span></span>
  - `x * y`<span data-ttu-id="0d341-147">:乘法</span><span class="sxs-lookup"><span data-stu-id="0d341-147">: Multiplication</span></span>
  - `x / y`<span data-ttu-id="0d341-148">:除号</span><span class="sxs-lookup"><span data-stu-id="0d341-148">: Division</span></span>
  - `x % y`<span data-ttu-id="0d341-149">:余数</span><span class="sxs-lookup"><span data-stu-id="0d341-149">: Remainder</span></span>
* <span data-ttu-id="0d341-150">加法</span><span class="sxs-lookup"><span data-stu-id="0d341-150">Additive</span></span>
  - `x + y`<span data-ttu-id="0d341-151">:相加、字符串串联、委托组合</span><span class="sxs-lookup"><span data-stu-id="0d341-151">: Addition, string concatenation, delegate combination</span></span>
  - `x – y`<span data-ttu-id="0d341-152">:相减、委托移除</span><span class="sxs-lookup"><span data-stu-id="0d341-152">: Subtraction, delegate removal</span></span>
* <span data-ttu-id="0d341-153">移位</span><span class="sxs-lookup"><span data-stu-id="0d341-153">Shift</span></span>
  - `x << y`<span data-ttu-id="0d341-154">:左移</span><span class="sxs-lookup"><span data-stu-id="0d341-154">: Shift left</span></span>
  - `x >> y`<span data-ttu-id="0d341-155">:右移</span><span class="sxs-lookup"><span data-stu-id="0d341-155">: Shift right</span></span>
* <span data-ttu-id="0d341-156">关系和类型测试</span><span class="sxs-lookup"><span data-stu-id="0d341-156">Relational and type testing</span></span>
  - `x < y`<span data-ttu-id="0d341-157">:小于</span><span class="sxs-lookup"><span data-stu-id="0d341-157">: Less than</span></span>
  - `x > y`<span data-ttu-id="0d341-158">:大于</span><span class="sxs-lookup"><span data-stu-id="0d341-158">: Greater than</span></span>
  - `x <= y`<span data-ttu-id="0d341-159">:小于或等于</span><span class="sxs-lookup"><span data-stu-id="0d341-159">: Less than or equal</span></span>
  - `x >= y`<span data-ttu-id="0d341-160">:大于或等于</span><span class="sxs-lookup"><span data-stu-id="0d341-160">: Greater than or equal</span></span>
  - `x is T`<span data-ttu-id="0d341-161">:如果 `x` 是 `T`，则返回 `true`；否则，返回 `false`</span><span class="sxs-lookup"><span data-stu-id="0d341-161">: Return `true` if `x` is a `T`, `false` otherwise</span></span>
  - `x as T`<span data-ttu-id="0d341-162">:返回类型化为 `T` 的 `x`；或返回 `null`，前提是 `x` 不是</span><span class="sxs-lookup"><span data-stu-id="0d341-162">: Return `x` typed as `T`, or `null` if `x` is not a</span></span> `T`
* <span data-ttu-id="0d341-163">相等</span><span class="sxs-lookup"><span data-stu-id="0d341-163">Equality</span></span>
  - `x == y`<span data-ttu-id="0d341-164">:等于</span><span class="sxs-lookup"><span data-stu-id="0d341-164">: Equal</span></span>
  - `x != y`<span data-ttu-id="0d341-165">:不等于</span><span class="sxs-lookup"><span data-stu-id="0d341-165">: Not equal</span></span>
* <span data-ttu-id="0d341-166">逻辑“与”</span><span class="sxs-lookup"><span data-stu-id="0d341-166">Logical AND</span></span>
  - `x & y`<span data-ttu-id="0d341-167">:整型按位 AND，布尔型逻辑 AND</span><span class="sxs-lookup"><span data-stu-id="0d341-167">: Integer bitwise AND, boolean logical AND</span></span>
* <span data-ttu-id="0d341-168">逻辑 XOR</span><span class="sxs-lookup"><span data-stu-id="0d341-168">Logical XOR</span></span>
  - `x ^ y`<span data-ttu-id="0d341-169">:整型按位 XOR，布尔型逻辑 XOR</span><span class="sxs-lookup"><span data-stu-id="0d341-169">: Integer bitwise XOR, boolean logical XOR</span></span>
* <span data-ttu-id="0d341-170">逻辑“或”</span><span class="sxs-lookup"><span data-stu-id="0d341-170">Logical OR</span></span>
  - `x | y`<span data-ttu-id="0d341-171">:整型按位“或”，布尔型逻辑“或”</span><span class="sxs-lookup"><span data-stu-id="0d341-171">: Integer bitwise OR, boolean logical OR</span></span>
* <span data-ttu-id="0d341-172">条件“与”</span><span class="sxs-lookup"><span data-stu-id="0d341-172">Conditional AND</span></span>
  - `x && y`<span data-ttu-id="0d341-173">:计算 `y`，前提是 `x` 不是</span><span class="sxs-lookup"><span data-stu-id="0d341-173">: Evaluates `y` only if `x` is not</span></span> `false`
* <span data-ttu-id="0d341-174">条件“或”</span><span class="sxs-lookup"><span data-stu-id="0d341-174">Conditional OR</span></span>
  - `x || y`<span data-ttu-id="0d341-175">:计算 `y`，前提是 `x` 不是</span><span class="sxs-lookup"><span data-stu-id="0d341-175">: Evaluates `y` only if `x` is not</span></span> `true`
* <span data-ttu-id="0d341-176">null 合并</span><span class="sxs-lookup"><span data-stu-id="0d341-176">Null coalescing</span></span>
  - `x ?? y`<span data-ttu-id="0d341-177">:如果 `x` 为 null，计算结果为 `y`；否则，计算结果为 `x`</span><span class="sxs-lookup"><span data-stu-id="0d341-177">: Evaluates to `y` if `x` is null, to `x` otherwise</span></span>
* <span data-ttu-id="0d341-178">条件运算</span><span class="sxs-lookup"><span data-stu-id="0d341-178">Conditional</span></span>
  - `x ? y : z`<span data-ttu-id="0d341-179">:计算 `y`，前提是 `x` 为 `true`；或计算 `z`，前提是 `x` 为</span><span class="sxs-lookup"><span data-stu-id="0d341-179">: Evaluates `y` if `x` is `true`, `z` if `x` is</span></span> `false`
* <span data-ttu-id="0d341-180">赋值或匿名函数</span><span class="sxs-lookup"><span data-stu-id="0d341-180">Assignment or anonymous function</span></span>
  - `x = y`<span data-ttu-id="0d341-181">:赋值</span><span class="sxs-lookup"><span data-stu-id="0d341-181">: Assignment</span></span>
  - `x op= y`<span data-ttu-id="0d341-182">:复合赋值；支持以下运算符：</span><span class="sxs-lookup"><span data-stu-id="0d341-182">: Compound assignment; supported operators are</span></span>
    - `*=`   `/=`   `%=`   `+=`   `-=`   `<<=`   `>>=`   `&=`  `^=`  `|=`
  - `(T x) => y`<span data-ttu-id="0d341-183">:匿名函数（lambda 表达式）</span><span class="sxs-lookup"><span data-stu-id="0d341-183">: Anonymous function (lambda expression)</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="0d341-184">[上一页](types-and-variables.md)
> [下一页](statements.md)</span><span class="sxs-lookup"><span data-stu-id="0d341-184">[Previous](types-and-variables.md)
[Next](statements.md)</span></span>

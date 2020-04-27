---
ms.openlocfilehash: 87ada29e70a94c39e7ffb74767b99d49c52444af
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021611"
---
### <a name="floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception"></a><span data-ttu-id="cc732-101">浮点分析操作不再失败或引发 OverflowException</span><span class="sxs-lookup"><span data-stu-id="cc732-101">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>

<span data-ttu-id="cc732-102">浮点分析方法在分析数值超出 <xref:System.Single> 或 <xref:System.Double> 浮点类型范围的字符串时，不再引发 <xref:System.OverflowException> 或返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="cc732-102">The floating-point parsing methods no longer throw an <xref:System.OverflowException> or return `false` when they parse a string whose numeric value is outside the range of the <xref:System.Single> or <xref:System.Double> floating-point type.</span></span>

#### <a name="change-description"></a><span data-ttu-id="cc732-103">更改描述</span><span class="sxs-lookup"><span data-stu-id="cc732-103">Change description</span></span>

<span data-ttu-id="cc732-104">在 .NET Core2.2 和早期版本中，<xref:System.Double.Parse%2A?displayProperty=nameWithType> 和 <xref:System.Single.Parse%2A?displayProperty=nameWithType> 方法对超出其各自类型范围的值会引发 <xref:System.OverflowException>。</span><span class="sxs-lookup"><span data-stu-id="cc732-104">In .NET Core 2.2 and earlier versions, the <xref:System.Double.Parse%2A?displayProperty=nameWithType> and <xref:System.Single.Parse%2A?displayProperty=nameWithType> methods throw an <xref:System.OverflowException> for values that outside the range of their respective type.</span></span> <span data-ttu-id="cc732-105">对于超出范围的数值的字符串表示形式，<xref:System.Double.TryParse%2A?displayProperty=nameWithType> 和 <xref:System.Single.TryParse%2A?displayProperty=nameWithType> 方法返回 `false`。</span><span class="sxs-lookup"><span data-stu-id="cc732-105">The <xref:System.Double.TryParse%2A?displayProperty=nameWithType> and <xref:System.Single.TryParse%2A?displayProperty=nameWithType> methods return `false` for the string representations of out-of-range numeric values.</span></span>

<span data-ttu-id="cc732-106">从 .NET Core 3.0 开始，分析超出范围的数值字符串时，<xref:System.Double.Parse%2A?displayProperty=nameWithType>、<xref:System.Double.TryParse%2A?displayProperty=nameWithType>、<xref:System.Single.Parse%2A?displayProperty=nameWithType> 和 <xref:System.Single.TryParse%2A?displayProperty=nameWithType> 方法不再失败。</span><span class="sxs-lookup"><span data-stu-id="cc732-106">Starting with .NET Core 3.0, the <xref:System.Double.Parse%2A?displayProperty=nameWithType>, <xref:System.Double.TryParse%2A?displayProperty=nameWithType>, <xref:System.Single.Parse%2A?displayProperty=nameWithType>, and <xref:System.Single.TryParse%2A?displayProperty=nameWithType> methods no longer fail when parsing out-of-range numeric strings.</span></span> <span data-ttu-id="cc732-107">相反，<xref:System.Double> 分析方法对于超过 <xref:System.Double.MaxValue?displayProperty=nameWithType> 的值返回 <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>，对于小于 <xref:System.Double.MinValue?displayProperty=nameWithType> 的值返回 <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="cc732-107">Instead, the <xref:System.Double> parsing methods return <xref:System.Double.PositiveInfinity?displayProperty=nameWithType> for values that exceed <xref:System.Double.MaxValue?displayProperty=nameWithType>, and they return <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> for values that are less than <xref:System.Double.MinValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="cc732-108">同样，<xref:System.Single> 分析方法对于超过 <xref:System.Single.MaxValue?displayProperty=nameWithType> 的值返回 <xref:System.Single.PositiveInfinity?displayProperty=nameWithType>，对于小于 <xref:System.Single.MinValue?displayProperty=nameWithType> 的值返回 <xref:System.Single.NegativeInfinity?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="cc732-108">Similarly, the <xref:System.Single> parsing methods return <xref:System.Single.PositiveInfinity?displayProperty=nameWithType> for values that exceed <xref:System.Single.MaxValue?displayProperty=nameWithType>, and they return <xref:System.Single.NegativeInfinity?displayProperty=nameWithType> for values that are less than <xref:System.Single.MinValue?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="cc732-109">此更改是为了改进 IEEE 754:2008 的符合性。</span><span class="sxs-lookup"><span data-stu-id="cc732-109">This change was made for improved IEEE 754:2008 compliance.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="cc732-110">引入的版本</span><span class="sxs-lookup"><span data-stu-id="cc732-110">Version introduced</span></span>

<span data-ttu-id="cc732-111">3.0</span><span class="sxs-lookup"><span data-stu-id="cc732-111">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="cc732-112">建议操作</span><span class="sxs-lookup"><span data-stu-id="cc732-112">Recommended action</span></span>

<span data-ttu-id="cc732-113">此更改会以两种方式之一影响你的代码：</span><span class="sxs-lookup"><span data-stu-id="cc732-113">This change can affect your code in either of two ways:</span></span>

- <span data-ttu-id="cc732-114">你的代码依赖于 <xref:System.OverflowException> 在发生溢出时执行的处理程序。</span><span class="sxs-lookup"><span data-stu-id="cc732-114">Your code depends on the handler for the <xref:System.OverflowException> to execute when an overflow occurs.</span></span> <span data-ttu-id="cc732-115">在这种情况下，应删除 `catch` 语句，并在 `If` 语句中放置必要的代码，以测试 <xref:System.Double.IsInfinity%2A?displayProperty=nameWithType> 或 <xref:System.Single.IsInfinity%2A?displayProperty=nameWithType> 是否为 `true`。</span><span class="sxs-lookup"><span data-stu-id="cc732-115">In this case, you should remove the `catch` statement and place any necessary code in an `If` statement that tests whether <xref:System.Double.IsInfinity%2A?displayProperty=nameWithType> or <xref:System.Single.IsInfinity%2A?displayProperty=nameWithType> is `true`.</span></span>

- <span data-ttu-id="cc732-116">代码假设浮点值不是 `Infinity`。</span><span class="sxs-lookup"><span data-stu-id="cc732-116">Your code assumes that floating-point values are not `Infinity`.</span></span> <span data-ttu-id="cc732-117">在这种情况下，应添加必要的代码来检查 `PositiveInfinity` 和 `NegativeInfinity` 的浮点值。</span><span class="sxs-lookup"><span data-stu-id="cc732-117">In this case, you should add the necessary code to check for floating-point values of `PositiveInfinity` and `NegativeInfinity`.</span></span>

#### <a name="category"></a><span data-ttu-id="cc732-118">类别</span><span class="sxs-lookup"><span data-stu-id="cc732-118">Category</span></span>

<span data-ttu-id="cc732-119">Core .NET 库</span><span class="sxs-lookup"><span data-stu-id="cc732-119">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="cc732-120">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="cc732-120">Affected APIs</span></span>

- <xref:System.Double.Parse%2A?displayProperty=nameWithType>
- <xref:System.Double.TryParse%2A?displayProperty=nameWithType>
- <xref:System.Single.Parse%2A?displayProperty=nameWithType>
- <xref:System.Single.TryParse%2A?displayProperty=nameWithType>

<!--

### Affected APIs

- `Overload:System.Double.Parse`
- `Overload:System.Double.TryParse`
- `Overload:System.Single.Parse`
- `Overload:System.Single.TryParse`

-->

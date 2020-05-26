---
ms.openlocfilehash: 02c9305a36f47dfaf0b1fa8d19b07cd2d34badae
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721264"
---
### <a name="fieldinfosetvalue-throws-exception-for-static-init-only-fields"></a><span data-ttu-id="a50d9-101">FieldInfo.SetValue 将对静态、仅初始化字段引发异常</span><span class="sxs-lookup"><span data-stu-id="a50d9-101">FieldInfo.SetValue throws exception for static, init-only fields</span></span>

<span data-ttu-id="a50d9-102">从 .NET Core 3.0 开始，当你尝试通过调用 <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=fullName> 在静态 <xref:System.Reflection.FieldAttributes.InitOnly> 字段上设置值时，将引发异常。</span><span class="sxs-lookup"><span data-stu-id="a50d9-102">Starting in .NET Core 3.0, an exception is thrown when you attempt to set a value on a static, <xref:System.Reflection.FieldAttributes.InitOnly> field by calling <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=fullName>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="a50d9-103">更改描述</span><span class="sxs-lookup"><span data-stu-id="a50d9-103">Change description</span></span>

<span data-ttu-id="a50d9-104">在 .NET Framework 和 3.0 之前的 .NET Core 版本中，你可以通过调用 <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=fullName> 来设置初始化后为常量的静态字段的值（[C# 中的 readonly](~/docs/csharp/language-reference/keywords/readonly.md)）。</span><span class="sxs-lookup"><span data-stu-id="a50d9-104">In .NET Framework and versions of .NET Core prior to 3.0, you could set the value of a static field that's constant after it is initialized ([readonly in C#](~/docs/csharp/language-reference/keywords/readonly.md)) by calling <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=fullName>.</span></span> <span data-ttu-id="a50d9-105">但是，以这种方式设置此类字段导致了不可预测的行为，具体取决于目标框架和优化设置。</span><span class="sxs-lookup"><span data-stu-id="a50d9-105">However, setting such a field in this way resulted in unpredictable behavior based on the target framework and optimization settings.</span></span>

<span data-ttu-id="a50d9-106">在 .NET Core 3.0 及更高版本中，当对静态 <xref:System.Reflection.FieldAttributes.InitOnly> 字段调用 <xref:System.Reflection.FieldInfo.SetValue%2A> 时，将引发 <xref:System.FieldAccessException?displayProperty=nameWithType> 异常。</span><span class="sxs-lookup"><span data-stu-id="a50d9-106">In .NET Core 3.0 and later versions, when you call <xref:System.Reflection.FieldInfo.SetValue%2A> on a static, <xref:System.Reflection.FieldAttributes.InitOnly> field, a <xref:System.FieldAccessException?displayProperty=nameWithType> exception is thrown.</span></span>

> [!TIP]
> <span data-ttu-id="a50d9-107"><xref:System.Reflection.FieldAttributes.InitOnly> 字段是只能在声明它时或位于包含类的构造函数中时设置的字段。</span><span class="sxs-lookup"><span data-stu-id="a50d9-107">An <xref:System.Reflection.FieldAttributes.InitOnly> field is one that can only be set at the time it's declared or in the constructor for the containing class.</span></span> <span data-ttu-id="a50d9-108">换句话说，它在初始化后为常量。</span><span class="sxs-lookup"><span data-stu-id="a50d9-108">In other words, it's constant after it is initialized.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a50d9-109">引入的版本</span><span class="sxs-lookup"><span data-stu-id="a50d9-109">Version introduced</span></span>

<span data-ttu-id="a50d9-110">3.0</span><span class="sxs-lookup"><span data-stu-id="a50d9-110">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a50d9-111">建议操作</span><span class="sxs-lookup"><span data-stu-id="a50d9-111">Recommended action</span></span>

<span data-ttu-id="a50d9-112">初始化静态构造函数中的静态 <xref:System.Reflection.FieldAttributes.InitOnly> 字段。</span><span class="sxs-lookup"><span data-stu-id="a50d9-112">Initialize static, <xref:System.Reflection.FieldAttributes.InitOnly> fields in a static constructor.</span></span> <span data-ttu-id="a50d9-113">这同时适用于动态和非动态类型。</span><span class="sxs-lookup"><span data-stu-id="a50d9-113">This applies to both dynamic and non-dynamic types.</span></span>

<span data-ttu-id="a50d9-114">或者，可以从字段中删除 <xref:System.Reflection.FieldAttributes.InitOnly?displayProperty=nameWithType> 属性，然后调用 <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="a50d9-114">Alternatively, you can remove the <xref:System.Reflection.FieldAttributes.InitOnly?displayProperty=nameWithType> attribute from the field, and then call <xref:System.Reflection.FieldInfo.SetValue%2A?displayProperty=nameWithType>.</span></span>

#### <a name="category"></a><span data-ttu-id="a50d9-115">类别</span><span class="sxs-lookup"><span data-stu-id="a50d9-115">Category</span></span>

<span data-ttu-id="a50d9-116">Core .NET 库</span><span class="sxs-lookup"><span data-stu-id="a50d9-116">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a50d9-117">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="a50d9-117">Affected APIs</span></span>

- <xref:System.Reflection.FieldInfo.SetValue(System.Object,System.Object)?displayProperty=nameWithType>
- <xref:System.Reflection.FieldInfo.SetValue(System.Object,System.Object,System.Reflection.BindingFlags,System.Reflection.Binder,System.Globalization.CultureInfo)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Reflection.FieldInfo.SetValue(System.Object,System.Object)`
- `M:System.Reflection.FieldInfo.SetValue(System.Object,System.Object,System.Reflection.BindingFlags,System.Reflection.Binder,System.Globalization.CultureInfo)`

-->

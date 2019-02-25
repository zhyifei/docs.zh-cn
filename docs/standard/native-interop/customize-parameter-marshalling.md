---
title: 自定义参数封送 - .NET
description: 了解如何自定义 .NET 将参数封送到本机表示形式的方式。
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: 7821da546e0ed0ab5fa97d00a638aa5cc1a3089c
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2019
ms.locfileid: "56411365"
---
# <a name="customizing-parameter-marshalling"></a><span data-ttu-id="c7941-103">自定义参数封送</span><span class="sxs-lookup"><span data-stu-id="c7941-103">Customizing parameter marshalling</span></span>

<span data-ttu-id="c7941-104">当 .NET 运行时的默认参数封送行为不满足要求时，可以使用 <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=nameWithType> 属性自定义参数的封送方式。</span><span class="sxs-lookup"><span data-stu-id="c7941-104">When the .NET runtime's default parameter marshalling behavior doesn't do what you want, use can use the <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=nameWithType> attribute to customize how your parameters are marshaled.</span></span>

## <a name="customizing-string-parameters"></a><span data-ttu-id="c7941-105">自定义字符串参数</span><span class="sxs-lookup"><span data-stu-id="c7941-105">Customizing string parameters</span></span>

<span data-ttu-id="c7941-106">.NET 具有各种格式可用来封送字符串。</span><span class="sxs-lookup"><span data-stu-id="c7941-106">.NET has a variety of formats for marshalling strings.</span></span> <span data-ttu-id="c7941-107">这些方法分为有关 C 样式字符串和以 Windows 为中心的字符串的不同格式部分。</span><span class="sxs-lookup"><span data-stu-id="c7941-107">These methods are split into distinct sections on C-style strings and Windows-centric string formats.</span></span>

### <a name="c-style-strings"></a><span data-ttu-id="c7941-108">C 样式字符串</span><span class="sxs-lookup"><span data-stu-id="c7941-108">C-Style strings</span></span>

<span data-ttu-id="c7941-109">其中每个格式都会将以 null 结尾的字符串传递到本机代码。</span><span class="sxs-lookup"><span data-stu-id="c7941-109">Each of these formats passes a null-terminated string to native code.</span></span> <span data-ttu-id="c7941-110">它们的差别在于本机字符串的编码。</span><span class="sxs-lookup"><span data-stu-id="c7941-110">They differ by the encoding of the native string.</span></span>

| <span data-ttu-id="c7941-111">`System.Runtime.InteropServices.UnmanagedType` 值</span><span class="sxs-lookup"><span data-stu-id="c7941-111">`System.Runtime.InteropServices.UnmanagedType` value</span></span> | <span data-ttu-id="c7941-112">编码</span><span class="sxs-lookup"><span data-stu-id="c7941-112">Encoding</span></span> |
|------------------------------------------------------|----------|
| <span data-ttu-id="c7941-113">LPStr</span><span class="sxs-lookup"><span data-stu-id="c7941-113">LPStr</span></span> | <span data-ttu-id="c7941-114">ANSI</span><span class="sxs-lookup"><span data-stu-id="c7941-114">ANSI</span></span> |
| <span data-ttu-id="c7941-115">LPUTF8Str</span><span class="sxs-lookup"><span data-stu-id="c7941-115">LPUTF8Str</span></span> | <span data-ttu-id="c7941-116">UTF-8</span><span class="sxs-lookup"><span data-stu-id="c7941-116">UTF-8</span></span> | 
| <span data-ttu-id="c7941-117">LPWStr</span><span class="sxs-lookup"><span data-stu-id="c7941-117">LPWStr</span></span> | <span data-ttu-id="c7941-118">UTF-16</span><span class="sxs-lookup"><span data-stu-id="c7941-118">UTF-16</span></span> |

<span data-ttu-id="c7941-119"><xref:System.Runtime.InteropServices.UnmanagedType.VBByRefStr?displayProperty=nameWithType> 格式稍有不同。</span><span class="sxs-lookup"><span data-stu-id="c7941-119">The <xref:System.Runtime.InteropServices.UnmanagedType.VBByRefStr?displayProperty=nameWithType> format is slightly different.</span></span> <span data-ttu-id="c7941-120">与 `LPWStr` 一样，该格式会将字符串封送到采用 UTF-16 编码的本机 C 样式字符串。</span><span class="sxs-lookup"><span data-stu-id="c7941-120">Like `LPWStr`, it marshals the string to a native C-style string encoded in UTF-16.</span></span> <span data-ttu-id="c7941-121">但是，托管签名允许你按引用传入字符串，而匹配的本机签名会按值获取字符串。</span><span class="sxs-lookup"><span data-stu-id="c7941-121">However, the managed signature has you pass in the string by reference and the matching native signature takes the string by value.</span></span> <span data-ttu-id="c7941-122">这一区别允许你使用按值获取字符串的本机 API，并对其进行就地修改而无需使用 `StringBuilder`。</span><span class="sxs-lookup"><span data-stu-id="c7941-122">This distinction allows you to use a native API that takes a string by value and modifies it in-place without having to use a `StringBuilder`.</span></span> <span data-ttu-id="c7941-123">我们建议不要手动使用此格式，因为很容易导致与不匹配的本机和托管签名混淆。</span><span class="sxs-lookup"><span data-stu-id="c7941-123">We recommend against manually using this format since it's prone to cause confusion with the mismatching native and managed signatures.</span></span>

### <a name="windows-centric-string-formats"></a><span data-ttu-id="c7941-124">以 Windows 为中心的字符串格式</span><span class="sxs-lookup"><span data-stu-id="c7941-124">Windows-centric string formats</span></span>

<span data-ttu-id="c7941-125">与 COM 或 OLE 接口交互时，可能会发现本机函数将字符串用作 `BSTR` 参数。</span><span class="sxs-lookup"><span data-stu-id="c7941-125">When interacting with COM or OLE interfaces, you'll likely find that the native functions take strings as `BSTR` arguments.</span></span> <span data-ttu-id="c7941-126">可以使用 <xref:System.Runtime.InteropServices.UnmanagedType.BStr?displayProperty=nameWithType> 非托管类型将字符串作为 `BSTR` 进行封送。</span><span class="sxs-lookup"><span data-stu-id="c7941-126">You can use the <xref:System.Runtime.InteropServices.UnmanagedType.BStr?displayProperty=nameWithType> unmanaged type to marshal a string as a `BSTR`.</span></span>

<span data-ttu-id="c7941-127">如果要与 WinRT API 交互，则可以使用 <xref:System.Runtime.InteropServices.UnmanagedType.HString?displayProperty=nameWithType> 格式将字符串作为 `HSTRING` 进行封送。</span><span class="sxs-lookup"><span data-stu-id="c7941-127">If you're interacting with WinRT APIs, you can use the <xref:System.Runtime.InteropServices.UnmanagedType.HString?displayProperty=nameWithType> format to marshal a string as an `HSTRING`.</span></span>

## <a name="customizing-array-parameters"></a><span data-ttu-id="c7941-128">自定义数组参数</span><span class="sxs-lookup"><span data-stu-id="c7941-128">Customizing array parameters</span></span>

<span data-ttu-id="c7941-129">.NET 还提供多种方式来封送数组参数。</span><span class="sxs-lookup"><span data-stu-id="c7941-129">.NET also provides you multiple ways to marshal array parameters.</span></span> <span data-ttu-id="c7941-130">如果要调用获取 C 样式数组的 API，则使用 <xref:System.Runtime.InteropServices.UnmanagedType.LPArray?displayProperty=nameWithType> 非托管类型。</span><span class="sxs-lookup"><span data-stu-id="c7941-130">If you're calling an API that takes a C-style array, use the <xref:System.Runtime.InteropServices.UnmanagedType.LPArray?displayProperty=nameWithType> unmanaged type.</span></span> <span data-ttu-id="c7941-131">如果数组中的值需要进行自定义封送，则可以为其使用 `[MarshalAs]` 属性上的 <xref:System.Runtime.InteropServices.MarshalAsAttribute.ArraySubType> 字段。</span><span class="sxs-lookup"><span data-stu-id="c7941-131">If the values in the array need customized marshalling, you can use the <xref:System.Runtime.InteropServices.MarshalAsAttribute.ArraySubType> field on the `[MarshalAs]` attribute for that.</span></span>

<span data-ttu-id="c7941-132">如果使用的是 COM API，则可能必须将数组参数作为 `SAFEARRAY*` 进行封送。</span><span class="sxs-lookup"><span data-stu-id="c7941-132">If you're using COM APIs, you'll likely have to marshal your array parameters as `SAFEARRAY*`s.</span></span> <span data-ttu-id="c7941-133">为此，可以使用 <xref:System.Runtime.InteropServices.UnmanagedType.SafeArray?displayProperty=nameWithType> 非托管类型。</span><span class="sxs-lookup"><span data-stu-id="c7941-133">To do so, you can use the <xref:System.Runtime.InteropServices.UnmanagedType.SafeArray?displayProperty=nameWithType> unmanaged type.</span></span> <span data-ttu-id="c7941-134">[自定义 `object` 字段](./customize-struct-marshalling.md#marshalling-systemobjects)上的表中显示了 `SAFEARRAY` 的元素的默认类型。</span><span class="sxs-lookup"><span data-stu-id="c7941-134">The default type of the elements of the `SAFEARRAY` can be seen in the table on [customizing `object` fields](./customize-struct-marshalling.md#marshalling-systemobjects).</span></span> <span data-ttu-id="c7941-135">可以使用 <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArraySubType?displayProperty=nameWithType> 和 <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArrayUserDefinedSubType?displayProperty=nameWithType> 字段自定义 `SAFEARRAY` 的确切元素类型。</span><span class="sxs-lookup"><span data-stu-id="c7941-135">You can use the <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArraySubType?displayProperty=nameWithType> and <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArrayUserDefinedSubType?displayProperty=nameWithType> fields to customize the exact element type of the `SAFEARRAY`.</span></span>

## <a name="customizing-boolean-or-decimal-parameters"></a><span data-ttu-id="c7941-136">自定义布尔或十进制参数</span><span class="sxs-lookup"><span data-stu-id="c7941-136">Customizing boolean or decimal parameters</span></span>

<span data-ttu-id="c7941-137">有关封送布尔或十进制参数的信息，请参阅[自定义结构封送](customize-struct-marshalling.md)。</span><span class="sxs-lookup"><span data-stu-id="c7941-137">For information on marshalling boolean or decimal parameters, see [Customizing structure marshalling](customize-struct-marshalling.md).</span></span>

## <a name="customizing-object-parameters-windows-only"></a><span data-ttu-id="c7941-138">自定义对象参数（仅适用于 Windows）</span><span class="sxs-lookup"><span data-stu-id="c7941-138">Customizing object parameters (Windows-only)</span></span>

<span data-ttu-id="c7941-139">在 Windows 上，.NET 运行时提供多种不同方式，将对象参数封送到本机代码。</span><span class="sxs-lookup"><span data-stu-id="c7941-139">On Windows, the .NET runtime provides a number of different ways to marshal object parameters to native code.</span></span>

### <a name="marshalling-as-specific-com-interfaces"></a><span data-ttu-id="c7941-140">作为特定的 COM 接口进行封送</span><span class="sxs-lookup"><span data-stu-id="c7941-140">Marshalling as specific COM interfaces</span></span>

<span data-ttu-id="c7941-141">如果 API 使用指向 COM 对象的指针，则可以使用类型为 `object` 的参数上的以下任一 `UnmanagedType` 格式告知 .NET 作为这些特定接口进行封送：</span><span class="sxs-lookup"><span data-stu-id="c7941-141">If your API takes a pointer to a COM object, you can use any of the following `UnmanagedType` formats on an `object`-typed parameter to tell .NET to marshal as these specific interfaces:</span></span>

- `IUnknown`
- `IDispatch`
- `IInspectable`

<span data-ttu-id="c7941-142">此外，如果类型标记为 `[ComVisible(true)]`，或如果要封送 `object` 类型，则可以使用 <xref:System.Runtime.InteropServices.UnmanagedType.Interface?displayProperty=nameWithType> 格式将对象作为类型的 COM 视图的 COM 可调用包装器进行封送。</span><span class="sxs-lookup"><span data-stu-id="c7941-142">Additionally, if your type is marked `[ComVisible(true)]` or you're marshalling the `object` type, you can use the <xref:System.Runtime.InteropServices.UnmanagedType.Interface?displayProperty=nameWithType> format to marshal your object as a COM callable wrapper for the COM view of your type.</span></span>

### <a name="marshalling-to-a-variant"></a><span data-ttu-id="c7941-143">封送到 `VARIANT`</span><span class="sxs-lookup"><span data-stu-id="c7941-143">Marshalling to a `VARIANT`</span></span>

<span data-ttu-id="c7941-144">如果本机 API 采用 Win32 `VARIANT`，则可以使用 `object` 参数上的 <xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType> 格式将对象作为 `VARIANT` 进行封送。</span><span class="sxs-lookup"><span data-stu-id="c7941-144">If your native API takes a Win32 `VARIANT`, you can use the <xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType> format on your `object` parameter to marshal your objects as `VARIANT`s.</span></span> <span data-ttu-id="c7941-145">如需了解 .NET 类型与 `VARIANT` 类型之间的映射，请参阅有关[自定义 `object` 字段](customize-struct-marshalling.md#marshalling-systemobjects)的文档。</span><span class="sxs-lookup"><span data-stu-id="c7941-145">See the documentation on [customizing `object` fields](customize-struct-marshalling.md#marshalling-systemobjects) for a mapping between .NET types and `VARIANT` types.</span></span>

### <a name="custom-marshalers"></a><span data-ttu-id="c7941-146">自定义封送处理程序</span><span class="sxs-lookup"><span data-stu-id="c7941-146">Custom marshalers</span></span>

<span data-ttu-id="c7941-147">如果要将本机 COM 接口投影到其他托管类型，则可以使用 `UnmanagedType.CustomMarshaler` 格式和 <xref:System.Runtime.InteropServices.ICustomMarshaler> 的实现来提供自己的自定义封送处理代码。</span><span class="sxs-lookup"><span data-stu-id="c7941-147">If you want to project a native COM interface into a different managed type, you can use the `UnmanagedType.CustomMarshaler` format and an implementation of <xref:System.Runtime.InteropServices.ICustomMarshaler> to provide your own custom marshalling code.</span></span>

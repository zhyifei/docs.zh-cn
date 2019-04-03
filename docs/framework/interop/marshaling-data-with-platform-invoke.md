---
title: 用平台调用封送数据
ms.date: 03/20/2019
dev_langs:
- cpp
helpviewer_keywords:
- platform invoke, marshaling data
- data marshaling, platform invoke
- marshaling, platform invoke
ms.assetid: dc5c76cf-7b12-406f-b79c-d1a023ec245d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3cb310dc6d786c3c7711f4c194c6623324c777dd
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2019
ms.locfileid: "58412391"
---
# <a name="marshaling-data-with-platform-invoke"></a><span data-ttu-id="7a1e1-102">用平台调用封送数据</span><span class="sxs-lookup"><span data-stu-id="7a1e1-102">Marshaling Data with Platform Invoke</span></span>

<span data-ttu-id="7a1e1-103">若要调用从非托管库中导出的函数，.NET Framework 应用程序需要托管代码中表示非托管函数的函数原型。</span><span class="sxs-lookup"><span data-stu-id="7a1e1-103">To call functions exported from an unmanaged library, a .NET Framework application requires a function prototype in managed code that represents the unmanaged function.</span></span> <span data-ttu-id="7a1e1-104">若要创建使平台调用能正确封送数据的原型，必须执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7a1e1-104">To create a prototype that enables platform invoke to marshal data correctly, you must do the following:</span></span>

- <span data-ttu-id="7a1e1-105">将 <xref:System.Runtime.InteropServices.DllImportAttribute> 特性应用于托管代码中的静态函数或方法。</span><span class="sxs-lookup"><span data-stu-id="7a1e1-105">Apply the <xref:System.Runtime.InteropServices.DllImportAttribute> attribute to the static function or method in managed code.</span></span>

- <span data-ttu-id="7a1e1-106">用托管数据类型替换非托管数据类型。</span><span class="sxs-lookup"><span data-stu-id="7a1e1-106">Substitute managed data types for unmanaged data types.</span></span>

<span data-ttu-id="7a1e1-107">通过应用具有可选字段的特性以及用托管数据类型替换非托管数据类型，可用附有非托管函数的文档来构造等效的托管原型。</span><span class="sxs-lookup"><span data-stu-id="7a1e1-107">You can use the documentation supplied with an unmanaged function to construct an equivalent managed prototype by applying the attribute with its optional fields and substituting managed data types for unmanaged types.</span></span> <span data-ttu-id="7a1e1-108">有关如何应用 <xref:System.Runtime.InteropServices.DllImportAttribute> 的说明，请参阅[使用非托管 DLL 函数](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="7a1e1-108">For instructions about how to apply the <xref:System.Runtime.InteropServices.DllImportAttribute>, see [Consuming Unmanaged DLL Functions](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md).</span></span>

<span data-ttu-id="7a1e1-109">本节提供一些示例，演示如何创建托管函数原型，以便将参数传递到由非托管库导出的函数或接收来自这些函数的返回值。</span><span class="sxs-lookup"><span data-stu-id="7a1e1-109">This section provides samples that demonstrate how to create managed function prototypes for passing arguments to and receiving return values from functions exported by unmanaged libraries.</span></span> <span data-ttu-id="7a1e1-110">该示例还演示了何时使用 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 特性和 <xref:System.Runtime.InteropServices.Marshal> 类来显式封送数据。</span><span class="sxs-lookup"><span data-stu-id="7a1e1-110">The samples also demonstrate when to use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute and the <xref:System.Runtime.InteropServices.Marshal> class to explicitly marshal data.</span></span>

## <a name="platform-invoke-data-types"></a><span data-ttu-id="7a1e1-111">平台调用数据类型</span><span class="sxs-lookup"><span data-stu-id="7a1e1-111">Platform invoke data types</span></span>

<span data-ttu-id="7a1e1-112">下表列出了 Windows API 和 C 样式函数中使用的数据类型。</span><span class="sxs-lookup"><span data-stu-id="7a1e1-112">The following table lists data types used in the Windows APIs and C-style functions.</span></span> <span data-ttu-id="7a1e1-113">许多非托管库包含将这些数据类型作为参数和返回值传递的函数。</span><span class="sxs-lookup"><span data-stu-id="7a1e1-113">Many unmanaged libraries contain functions that pass these data types as parameters and return values.</span></span> <span data-ttu-id="7a1e1-114">第三列列出了相应的 .NET Framework 内置值类型或可在托管代码中使用的类。</span><span class="sxs-lookup"><span data-stu-id="7a1e1-114">The third column lists the corresponding .NET Framework built-in value type or class that you use in managed code.</span></span> <span data-ttu-id="7a1e1-115">在某些情况下，你用相同大小的类型替代表中列出的类型。</span><span class="sxs-lookup"><span data-stu-id="7a1e1-115">In some cases, you can substitute a type of the same size for the type listed in the table.</span></span>

|<span data-ttu-id="7a1e1-116">Windows API 中的非托管类型</span><span class="sxs-lookup"><span data-stu-id="7a1e1-116">Unmanaged type in Windows APIs</span></span>|<span data-ttu-id="7a1e1-117">非托管 C 语言类型</span><span class="sxs-lookup"><span data-stu-id="7a1e1-117">Unmanaged C language type</span></span>|<span data-ttu-id="7a1e1-118">托管类型</span><span class="sxs-lookup"><span data-stu-id="7a1e1-118">Managed type</span></span>|<span data-ttu-id="7a1e1-119">说明</span><span class="sxs-lookup"><span data-stu-id="7a1e1-119">Description</span></span>|
|--------------------------------|-------------------------------|------------------------|-----------------|
|`VOID`|`void`|<xref:System.Void?displayProperty=nameWithType>|<span data-ttu-id="7a1e1-120">应用于不返回值的函数。</span><span class="sxs-lookup"><span data-stu-id="7a1e1-120">Applied to a function that does not return a value.</span></span>|
|`HANDLE`|`void *`|<span data-ttu-id="7a1e1-121"><xref:System.IntPtr?displayProperty=nameWithType> 或 <xref:System.UIntPtr?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="7a1e1-121"><xref:System.IntPtr?displayProperty=nameWithType> or <xref:System.UIntPtr?displayProperty=nameWithType></span></span>|<span data-ttu-id="7a1e1-122">在 32 位 Windows 操作系统上为 32 位、在 64 位 Windows 操作系统上为 64 位。</span><span class="sxs-lookup"><span data-stu-id="7a1e1-122">32 bits on 32-bit Windows operating systems, 64 bits on 64-bit Windows operating systems.</span></span>|
|`BYTE`|`unsigned char`|<xref:System.Byte?displayProperty=nameWithType>|<span data-ttu-id="7a1e1-123">8 位</span><span class="sxs-lookup"><span data-stu-id="7a1e1-123">8 bits</span></span>|
|`SHORT`|`short`|<xref:System.Int16?displayProperty=nameWithType>|<span data-ttu-id="7a1e1-124">16 位</span><span class="sxs-lookup"><span data-stu-id="7a1e1-124">16 bits</span></span>|
|`WORD`|`unsigned short`|<xref:System.UInt16?displayProperty=nameWithType>|<span data-ttu-id="7a1e1-125">16 位</span><span class="sxs-lookup"><span data-stu-id="7a1e1-125">16 bits</span></span>|
|`INT`|`int`|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="7a1e1-126">32 位</span><span class="sxs-lookup"><span data-stu-id="7a1e1-126">32 bits</span></span>|
|`UINT`|`unsigned int`|<xref:System.UInt32?displayProperty=nameWithType>|<span data-ttu-id="7a1e1-127">32 位</span><span class="sxs-lookup"><span data-stu-id="7a1e1-127">32 bits</span></span>|
|`LONG`|`long`|<xref:System.Int32?displayProperty=nameWithType>|<span data-ttu-id="7a1e1-128">32 位</span><span class="sxs-lookup"><span data-stu-id="7a1e1-128">32 bits</span></span>|
|`BOOL`|`long`|<span data-ttu-id="7a1e1-129"><xref:System.Boolean?displayProperty=nameWithType> 或 <xref:System.Int32?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="7a1e1-129"><xref:System.Boolean?displayProperty=nameWithType> or <xref:System.Int32?displayProperty=nameWithType></span></span>|<span data-ttu-id="7a1e1-130">32 位</span><span class="sxs-lookup"><span data-stu-id="7a1e1-130">32 bits</span></span>|
|`DWORD`|`unsigned long`|<xref:System.UInt32?displayProperty=nameWithType>|<span data-ttu-id="7a1e1-131">32 位</span><span class="sxs-lookup"><span data-stu-id="7a1e1-131">32 bits</span></span>|
|`ULONG`|`unsigned long`|<xref:System.UInt32?displayProperty=nameWithType>|<span data-ttu-id="7a1e1-132">32 位</span><span class="sxs-lookup"><span data-stu-id="7a1e1-132">32 bits</span></span>|
|`CHAR`|`char`|<xref:System.Char?displayProperty=nameWithType>|<span data-ttu-id="7a1e1-133">使用 ANSI 修饰。</span><span class="sxs-lookup"><span data-stu-id="7a1e1-133">Decorate with ANSI.</span></span>|
|`WCHAR`|`wchar_t`|<xref:System.Char?displayProperty=nameWithType>|<span data-ttu-id="7a1e1-134">使用 Unicode 修饰。</span><span class="sxs-lookup"><span data-stu-id="7a1e1-134">Decorate with Unicode.</span></span>|
|`LPSTR`|`char *`|<span data-ttu-id="7a1e1-135"><xref:System.String?displayProperty=nameWithType> 或 <xref:System.Text.StringBuilder?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="7a1e1-135"><xref:System.String?displayProperty=nameWithType> or <xref:System.Text.StringBuilder?displayProperty=nameWithType></span></span>|<span data-ttu-id="7a1e1-136">使用 ANSI 修饰。</span><span class="sxs-lookup"><span data-stu-id="7a1e1-136">Decorate with ANSI.</span></span>|
|`LPCSTR`|`const char *`|<span data-ttu-id="7a1e1-137"><xref:System.String?displayProperty=nameWithType> 或 <xref:System.Text.StringBuilder?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="7a1e1-137"><xref:System.String?displayProperty=nameWithType> or <xref:System.Text.StringBuilder?displayProperty=nameWithType></span></span>|<span data-ttu-id="7a1e1-138">使用 ANSI 修饰。</span><span class="sxs-lookup"><span data-stu-id="7a1e1-138">Decorate with ANSI.</span></span>|
|`LPWSTR`|`wchar_t *`|<span data-ttu-id="7a1e1-139"><xref:System.String?displayProperty=nameWithType> 或 <xref:System.Text.StringBuilder?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="7a1e1-139"><xref:System.String?displayProperty=nameWithType> or <xref:System.Text.StringBuilder?displayProperty=nameWithType></span></span>|<span data-ttu-id="7a1e1-140">使用 Unicode 修饰。</span><span class="sxs-lookup"><span data-stu-id="7a1e1-140">Decorate with Unicode.</span></span>|
|`LPCWSTR`|`const wchar_t *`|<span data-ttu-id="7a1e1-141"><xref:System.String?displayProperty=nameWithType> 或 <xref:System.Text.StringBuilder?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="7a1e1-141"><xref:System.String?displayProperty=nameWithType> or <xref:System.Text.StringBuilder?displayProperty=nameWithType></span></span>|<span data-ttu-id="7a1e1-142">使用 Unicode 修饰。</span><span class="sxs-lookup"><span data-stu-id="7a1e1-142">Decorate with Unicode.</span></span>|
|`FLOAT`|`float`|<xref:System.Single?displayProperty=nameWithType>|<span data-ttu-id="7a1e1-143">32 位</span><span class="sxs-lookup"><span data-stu-id="7a1e1-143">32 bits</span></span>|
|`DOUBLE`|`double`|<xref:System.Double?displayProperty=nameWithType>|<span data-ttu-id="7a1e1-144">64 位</span><span class="sxs-lookup"><span data-stu-id="7a1e1-144">64 bits</span></span>|

<span data-ttu-id="7a1e1-145">有关 Visual Basic、C# 和 C++ 中的相应类型，请参阅 [.NET Framework 类库简介](../../standard/class-library-overview.md#system-namespace)。</span><span class="sxs-lookup"><span data-stu-id="7a1e1-145">For corresponding types in Visual Basic, C#, and C++, see the [Introduction to the .NET Framework Class Library](../../standard/class-library-overview.md#system-namespace).</span></span>

## <a name="pinvokelibdll"></a><span data-ttu-id="7a1e1-146">PinvokeLib.dll</span><span class="sxs-lookup"><span data-stu-id="7a1e1-146">PinvokeLib.dll</span></span>

<span data-ttu-id="7a1e1-147">下面的代码定义由 Pinvoke.dll 提供的库函数。</span><span class="sxs-lookup"><span data-stu-id="7a1e1-147">The following code defines the library functions provided by Pinvoke.dll.</span></span> <span data-ttu-id="7a1e1-148">本节中介绍的许多示例都调用此库。</span><span class="sxs-lookup"><span data-stu-id="7a1e1-148">Many samples described in this section call this library.</span></span>

### <a name="example"></a><span data-ttu-id="7a1e1-149">示例</span><span class="sxs-lookup"><span data-stu-id="7a1e1-149">Example</span></span>

[!code-cpp[PInvokeLib#1](../../../samples/snippets/cpp/VS_Snippets_CLR/pinvokelib/cpp/pinvokelib.cpp#1)]

[!code-cpp[PInvokeLib#2](../../../samples/snippets/cpp/VS_Snippets_CLR/pinvokelib/cpp/pinvokelib.h#2)]

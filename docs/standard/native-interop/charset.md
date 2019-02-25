---
title: 字符集和封送 - .NET
description: 了解字符集的不同值如何更改 .NET 将数据封送到本机代码的方式。
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: 2ff6c485906db481cb5236f83e885ba9fd46450b
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2019
ms.locfileid: "56411359"
---
# <a name="charsets-and-marshalling"></a><span data-ttu-id="8e35f-103">字符集和封送</span><span class="sxs-lookup"><span data-stu-id="8e35f-103">Charsets and marshalling</span></span>

<span data-ttu-id="8e35f-104">`char` 值、`string` 对象和 `System.Text.StringBuilder` 对象的封送方式取决于 P/Invoke 或结构上的 `CharSet` 字段的值。</span><span class="sxs-lookup"><span data-stu-id="8e35f-104">The way `char` values, `string` objects, and `System.Text.StringBuilder` objects are marshalled depends on the value of the `CharSet` field on either the P/Invoke or structure.</span></span> <span data-ttu-id="8e35f-105">可以通过在声明 P/Invoke 时设置 <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> 字段来设置 P/Invoke 的 `CharSet`。</span><span class="sxs-lookup"><span data-stu-id="8e35f-105">You can set the `CharSet` of a P/Invoke by setting the <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field when declaring your P/Invoke.</span></span> <span data-ttu-id="8e35f-106">若要设置结构的 `CharSet`，请在声明结构时设置 <xref:System.Runtime.InteropServices.StructLayoutAttribute.CharSet?displayProperty=nameWithType> 字段。</span><span class="sxs-lookup"><span data-stu-id="8e35f-106">To set the `CharSet` for a structure, set the <xref:System.Runtime.InteropServices.StructLayoutAttribute.CharSet?displayProperty=nameWithType> field on your struct declaration.</span></span> <span data-ttu-id="8e35f-107">未设置这些属性字段时，将由语言编译器确定使用哪些 `CharSet`。</span><span class="sxs-lookup"><span data-stu-id="8e35f-107">When these attribute fields are not set, it is up to the language compiler to determine which `CharSet` to use.</span></span> <span data-ttu-id="8e35f-108">默认情况下，C# 使用 <xref:System.Runtime.InteropServices.CharSet.Ansi> 字符集。</span><span class="sxs-lookup"><span data-stu-id="8e35f-108">C# uses the <xref:System.Runtime.InteropServices.CharSet.Ansi> charset by default.</span></span>

<span data-ttu-id="8e35f-109">下表显示了每个字符集之间的映射以及字符或字符串在使用该字符集封送时的表示形式：</span><span class="sxs-lookup"><span data-stu-id="8e35f-109">The following table shows a mapping between each charset and how a character or string is represented when marshalled with that charset:</span></span>

| <span data-ttu-id="8e35f-110">CharSet</span><span class="sxs-lookup"><span data-stu-id="8e35f-110">CharSet</span></span> | <span data-ttu-id="8e35f-111">Windows</span><span class="sxs-lookup"><span data-stu-id="8e35f-111">Windows</span></span> | <span data-ttu-id="8e35f-112">Unix</span><span class="sxs-lookup"><span data-stu-id="8e35f-112">Unix</span></span> | <span data-ttu-id="8e35f-113">在 Unix 上为 Mono</span><span class="sxs-lookup"><span data-stu-id="8e35f-113">Mono on Unix</span></span> |
|---------|---------|-------|-------|
| <span data-ttu-id="8e35f-114">Ansi</span><span class="sxs-lookup"><span data-stu-id="8e35f-114">Ansi</span></span>    | <span data-ttu-id="8e35f-115">`char` (ANSI)</span><span class="sxs-lookup"><span data-stu-id="8e35f-115">`char` (ANSI)</span></span>  | <span data-ttu-id="8e35f-116">`char`（在 macOS 上为 ANSI，在 Linux 上为 UTF-8）</span><span class="sxs-lookup"><span data-stu-id="8e35f-116">`char` (ANSI on macOS, UTF-8 on Linux)</span></span> | <span data-ttu-id="8e35f-117">`char` (UTF-8)</span><span class="sxs-lookup"><span data-stu-id="8e35f-117">`char` (UTF-8)</span></span> |
| <span data-ttu-id="8e35f-118">Unicode</span><span class="sxs-lookup"><span data-stu-id="8e35f-118">Unicode</span></span> | <span data-ttu-id="8e35f-119">`wchar_t` (UTF-16)</span><span class="sxs-lookup"><span data-stu-id="8e35f-119">`wchar_t` (UTF-16)</span></span> | <span data-ttu-id="8e35f-120">`char16_t` (UTF-16)</span><span class="sxs-lookup"><span data-stu-id="8e35f-120">`char16_t` (UTF-16)</span></span> | <span data-ttu-id="8e35f-121">`char16_t` (UTF-16)</span><span class="sxs-lookup"><span data-stu-id="8e35f-121">`char16_t` (UTF-16)</span></span> |
| <span data-ttu-id="8e35f-122">自动</span><span class="sxs-lookup"><span data-stu-id="8e35f-122">Auto</span></span> | <span data-ttu-id="8e35f-123">`wchar_t` (UTF-16)</span><span class="sxs-lookup"><span data-stu-id="8e35f-123">`wchar_t` (UTF-16)</span></span> | <span data-ttu-id="8e35f-124">`char16_t` (UTF-16)</span><span class="sxs-lookup"><span data-stu-id="8e35f-124">`char16_t` (UTF-16)</span></span> | <span data-ttu-id="8e35f-125">`char` (UTF-8)</span><span class="sxs-lookup"><span data-stu-id="8e35f-125">`char` (UTF-8)</span></span> |

<span data-ttu-id="8e35f-126">确保了解选择字符集时所需的本机表示形式。</span><span class="sxs-lookup"><span data-stu-id="8e35f-126">Make sure you know what representation your native representation expects when picking your charset.</span></span>

---
title: CoreFx 中断性变更 - .NET Core
description: 列出 .NET CoreFx（基类库）中的中断性变更。
ms.date: 09/20/2019
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7681dadbbbae737cb1cbc260613baea9d34527a8
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002456"
---
# <a name="corefx-breaking-changes"></a><span data-ttu-id="afb79-103">CoreFx 中断性变更</span><span class="sxs-lookup"><span data-stu-id="afb79-103">CoreFx breaking changes</span></span>

> [!IMPORTANT]
> <span data-ttu-id="afb79-104">本文正在构建中。</span><span class="sxs-lookup"><span data-stu-id="afb79-104">This article is under construction.</span></span> <span data-ttu-id="afb79-105">这并不是 .NET Core 中断性变更的完整列表。</span><span class="sxs-lookup"><span data-stu-id="afb79-105">This is not a complete list of .NET Core breaking changes.</span></span> <span data-ttu-id="afb79-106">如需详细了解 .NET Core 重大变更，请参阅 GitHub 上 dotnet/docs 存储库中的各个[重大变更问题](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change)。</span><span class="sxs-lookup"><span data-stu-id="afb79-106">For more information on .NET Core breaking changes, you can examine individual [breaking changes issues](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change) in the dotnet/docs repository on GitHub.</span></span>

<span data-ttu-id="afb79-107">下表按 .NET Core 版本列出了 CoreFx 中断性变更。</span><span class="sxs-lookup"><span data-stu-id="afb79-107">The following is a list of CoreFx breaking changes by .NET Core version.</span></span> <span data-ttu-id="afb79-108">CoreFx 提供了 .NET Core 使用的基元和其他常规类型。</span><span class="sxs-lookup"><span data-stu-id="afb79-108">CoreFx provides the primitives and other general types used by .NET Core.</span></span>

## <a name="net-core-30-preview-7"></a><span data-ttu-id="afb79-109">.NET Core 3.0 预览版 7</span><span class="sxs-lookup"><span data-stu-id="afb79-109">.NET Core 3.0 Preview 7</span></span>

[!INCLUDE[JsonElement API changes](~/includes/core-changes/corefx/jsonelement-api-changes.md)]

## <a name="net-core-30-preview-8"></a><span data-ttu-id="afb79-110">.NET Core 3.0 预览版 8</span><span class="sxs-lookup"><span data-stu-id="afb79-110">.NET Core 3.0 Preview 8</span></span>

[!INCLUDE[Change in semantics of (string)null in Utf8JsonWriter](~/includes/core-changes/corefx/change-in-null-in-utf8jsonwriter.md)]

***

[!INCLUDE[JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument](~/includes/core-changes/corefx/jsonencodedtext-encode-has-additional-argument.md)]

***

[!INCLUDE[JsonFactoryConverter.CreateConverter signature changed](~/includes/core-changes/corefx/jsonfactoryconverter-createconverter.md)]

## <a name="net-core-30-preview-9"></a><span data-ttu-id="afb79-111">.NET Core 3.0 预览版 9</span><span class="sxs-lookup"><span data-stu-id="afb79-111">.NET Core 3.0 Preview 9</span></span>

[!INCLUDE[Json serializer exception type changed from JsonException to NotSupportedException](~/includes/core-changes/corefx/serializer-throws-notsupportedexception.md)]

## <a name="net-core-30"></a><span data-ttu-id="afb79-112">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="afb79-112">.NET Core 3.0</span></span>

[!INCLUDE[APIs that report version now report product and not file version](~/includes/core-changes/corefx/version-information-changes.md)]

***

[!INCLUDE[Custom EncoderFallbackBuffer instances cannot fall back recursively](~/includes/core-changes/corefx/custom-encoderfallbackbuffer-cannot-be-recursive.md)]

***

[!INCLUDE[Floating point formatting and parsing behavior changes](~/includes/core-changes/corefx/floating-point-changes.md)]

***

[!INCLUDE[Floating-point parsing operations no longer fail or throw an OverflowException](~/includes/core-changes/corefx/floating-point-parsing-does-not-overflow.md)]

***

[!INCLUDE[InvalidAsynchronousStateException moved to another assembly](~/includes/core-changes/corefx/move-invalidasynchronousstateexception.md)]

***

[!INCLUDE[NET Core 3.0 follows Unicode best practices when replacing ill-formed UTF-8 byte sequences](~/includes/core-changes/corefx/net-core-3-0-follows-unicode-utf8-best-practices.md)]

***

[!INCLUDE[TypeDescriptionProviderAttribute moved to another assembly](~/includes/core-changes/corefx/move-typedescriptionproviderattribute.md)]

***

[!INCLUDE[ZipArchiveEntry no longer handles archives with inconsistent entry sizes](~/includes/core-changes/corefx/ziparchiveentry-and-inconsistent-entry-sizes.md)]

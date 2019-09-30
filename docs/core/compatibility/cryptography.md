---
title: 加密中断性变更 - .NET Core
description: 列出 .NET Core 中与加密相关的中断性变更。
ms.date: 09/20/2019
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 80b62f9b32487e88a309ea7686f78d68af8f2e0a
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216983"
---
# <a name="cryptography-breaking-changes"></a><span data-ttu-id="3736b-103">加密中断性变更</span><span class="sxs-lookup"><span data-stu-id="3736b-103">Cryptography breaking changes</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3736b-104">本文正在构建中。</span><span class="sxs-lookup"><span data-stu-id="3736b-104">This article is under construction.</span></span> <span data-ttu-id="3736b-105">这并不是 .NET Core 中断性变更的完整列表。</span><span class="sxs-lookup"><span data-stu-id="3736b-105">This is not a complete list of .NET Core breaking changes.</span></span> <span data-ttu-id="3736b-106">如需详细了解 .NET Core 重大变更，请参阅 GitHub 上 dotnet/docs 存储库中的各个[重大变更问题](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change)。</span><span class="sxs-lookup"><span data-stu-id="3736b-106">For more information on .NET Core breaking changes, you can examine individual [breaking changes issues](https://github.com/dotnet/docs/issues?q=is%3Aissue+is%3Aopen+label%3Abreaking-change) in the dotnet/docs repository on GitHub.</span></span> 

<span data-ttu-id="3736b-107">下表按 .NET Core 版本列出了与加密相关的中断性变更。</span><span class="sxs-lookup"><span data-stu-id="3736b-107">The following is a list of cryptography-related breaking changes by .NET Core version.</span></span>

## <a name="net-core-30-preview-9"></a><span data-ttu-id="3736b-108">.NET Core 3.0 预览版 9</span><span class="sxs-lookup"><span data-stu-id="3736b-108">.NET Core 3.0 Preview 9</span></span>

[!INCLUDE[Better argument validation in the Pkcs8PrivateKeyInfo constructor](~/includes/core-changes/cryptography/better-argument-validation-in-pkcs8privatekeyinfo-ctor.md)]

## <a name="net-core-30"></a><span data-ttu-id="3736b-109">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="3736b-109">.NET Core 3.0</span></span>

[!INCLUDE[EnvelopedCms defaults to AES-256 encryption](~/includes/core-changes/cryptography/envelopedcms-defaults-to-aes256.md)]

***

[!INCLUDE[Minimum size for RSAOpenSsl key generation has increased](~/includes/core-changes/cryptography/minimum-rsaopenssl-key-size-change.md)]

***

[!INCLUDE[.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x](~/includes/core-changes/cryptography/net-core-3-0-prefers-openssl-1-1-x.md)]

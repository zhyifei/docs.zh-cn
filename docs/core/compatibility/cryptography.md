---
title: 加密中断性变更
description: 列出 .NET Core 中与加密相关的中断性变更。
ms.date: 02/10/2020
ms.openlocfilehash: c25eefa8e3ee01ed7a1df4ec4aa9225f2c347a4d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "77449204"
---
# <a name="cryptography-breaking-changes"></a><span data-ttu-id="148ab-103">加密中断性变更</span><span class="sxs-lookup"><span data-stu-id="148ab-103">Cryptography breaking changes</span></span>

<span data-ttu-id="148ab-104">本页记录了以下中断性变更：</span><span class="sxs-lookup"><span data-stu-id="148ab-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="148ab-105">重大更改</span><span class="sxs-lookup"><span data-stu-id="148ab-105">Breaking change</span></span> | <span data-ttu-id="148ab-106">引入的版本</span><span class="sxs-lookup"><span data-stu-id="148ab-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="148ab-107">EnvelopedCms 默认为 AES-256 加密</span><span class="sxs-lookup"><span data-stu-id="148ab-107">EnvelopedCms defaults to AES-256 encryption</span></span>](#envelopedcms-defaults-to-aes-256-encryption) | <span data-ttu-id="148ab-108">3.0</span><span class="sxs-lookup"><span data-stu-id="148ab-108">3.0</span></span> |
| [<span data-ttu-id="148ab-109">RSAOpenSsl 密钥生成的最小大小已增加</span><span class="sxs-lookup"><span data-stu-id="148ab-109">Minimum size for RSAOpenSsl key generation has increased</span></span>](#minimum-size-for-rsaopenssl-key-generation-has-increased) | <span data-ttu-id="148ab-110">3.0</span><span class="sxs-lookup"><span data-stu-id="148ab-110">3.0</span></span> |
| [<span data-ttu-id="148ab-111">.NET Core 3.0 倾向于使用 OpenSSL 1.1.x 而不是 OpenSSL 1.0.x</span><span class="sxs-lookup"><span data-stu-id="148ab-111">.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x</span></span>](#net-core-30-prefers-openssl-11x-to-openssl-10x) | <span data-ttu-id="148ab-112">3.0</span><span class="sxs-lookup"><span data-stu-id="148ab-112">3.0</span></span> |
| [<span data-ttu-id="148ab-113">Pkcs8PrivateKeyInfo 构造函数中更好的参数验证</span><span class="sxs-lookup"><span data-stu-id="148ab-113">Better argument validation in the Pkcs8PrivateKeyInfo constructor</span></span>](#better-argument-validation-in-the-pkcs8privatekeyinfo-constructor) | <span data-ttu-id="148ab-114">3.0</span><span class="sxs-lookup"><span data-stu-id="148ab-114">3.0</span></span> |
| [<span data-ttu-id="148ab-115">已考虑 SignedCms.ComputeSignature 的布尔参数</span><span class="sxs-lookup"><span data-stu-id="148ab-115">Boolean parameter of SignedCms.ComputeSignature is respected</span></span>](#boolean-parameter-of-signedcmscomputesignature-is-respected) | <span data-ttu-id="148ab-116">2.1</span><span class="sxs-lookup"><span data-stu-id="148ab-116">2.1</span></span> |

## <a name="net-core-30"></a><span data-ttu-id="148ab-117">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="148ab-117">.NET Core 3.0</span></span>

[!INCLUDE[EnvelopedCms defaults to AES-256 encryption](~/includes/core-changes/cryptography/3.0/envelopedcms-defaults-to-aes256.md)]

***

[!INCLUDE[Minimum size for RSAOpenSsl key generation has increased](~/includes/core-changes/cryptography/3.0/minimum-rsaopenssl-key-size-change.md)]

***

[!INCLUDE[.NET Core 3.0 prefers OpenSSL 1.1.x to OpenSSL 1.0.x](~/includes/core-changes/cryptography/3.0/net-core-3-0-prefers-openssl-1-1-x.md)]

***

[!INCLUDE[Better argument validation in the Pkcs8PrivateKeyInfo constructor](~/includes/core-changes/cryptography/3.0/better-argument-validation-in-pkcs8privatekeyinfo-ctor.md)]

***

## <a name="net-core-21"></a><span data-ttu-id="148ab-118">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="148ab-118">.NET Core 2.1</span></span>

[!INCLUDE [Boolean parameter of SignedCms.ComputeSignature is respected](~/includes/core-changes/cryptography/2.1/compute-signature-silent-parameter.md)]

***

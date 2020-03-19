---
ms.openlocfilehash: 6a5cd260a2820e2a81142f6d55e32e91173ca503
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "79147446"
---
### <a name="openssl-versions-on-macos"></a><span data-ttu-id="f4a40-101">macOS 上的 OpenSSL 版本</span><span class="sxs-lookup"><span data-stu-id="f4a40-101">OpenSSL versions on macOS</span></span>

<span data-ttu-id="f4a40-102">对于 <xref:System.Security.Cryptography.AesCcm>、<xref:System.Security.Cryptography.AesGcm>、<xref:System.Security.Cryptography.DSAOpenSsl>、<xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl>、<xref:System.Security.Cryptography.ECDsaOpenSsl>、<xref:System.Security.Cryptography.RSAOpenSsl> 和 <xref:System.Security.Cryptography.SafeEvpPKeyHandle> 类型，macOS 上的 .NET Core 3.0 及更高版本的运行时现在首选 OpenSSL 1.1.x 版而非 OpenSSL 1.0.x 版。</span><span class="sxs-lookup"><span data-stu-id="f4a40-102">The .NET Core 3.0 and later runtimes on macOS now prefer OpenSSL 1.1.x versions to OpenSSL 1.0.x versions for the <xref:System.Security.Cryptography.AesCcm>, <xref:System.Security.Cryptography.AesGcm>, <xref:System.Security.Cryptography.DSAOpenSsl>, <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl>, <xref:System.Security.Cryptography.ECDsaOpenSsl>, <xref:System.Security.Cryptography.RSAOpenSsl>, and <xref:System.Security.Cryptography.SafeEvpPKeyHandle> types.</span></span>

<span data-ttu-id="f4a40-103">.NET Core 2.1 运行时现在支持 OpenSSL 1.1.x 版本，但仍首选 OpenSSL 1.0.x 版。</span><span class="sxs-lookup"><span data-stu-id="f4a40-103">The .NET Core 2.1 runtime now supports OpenSSL 1.1.x versions, but still prefers OpenSSL 1.0.x versions.</span></span>

#### <a name="change-description"></a><span data-ttu-id="f4a40-104">更改描述</span><span class="sxs-lookup"><span data-stu-id="f4a40-104">Change description</span></span>

<span data-ttu-id="f4a40-105">以前，.NET Core 运行时在 macOS 上使用 OpenSSL 1.0.x 版处理与 OpenSSL 交互的类型。</span><span class="sxs-lookup"><span data-stu-id="f4a40-105">Previously, the .NET Core runtime used OpenSSL 1.0.x versions on macOS for types that interact with OpenSSL.</span></span> <span data-ttu-id="f4a40-106">最新的 OpenSSL 1.0.x 版 OpenSSL 1.0.2 现已不受支持。</span><span class="sxs-lookup"><span data-stu-id="f4a40-106">The most recent OpenSSL 1.0.x version, OpenSSL 1.0.2, is now out of support.</span></span> <span data-ttu-id="f4a40-107">若要在支持的 OpenSSL 版本上保留使用 OpenSSL 的类型，.NET Core 3.0 及更高版本的运行时现需在 macOS 上使用较新版本的 OpenSSL。</span><span class="sxs-lookup"><span data-stu-id="f4a40-107">To keep types that use OpenSSL on supported versions of OpenSSL, the .NET Core 3.0 and later runtimes now use newer versions of OpenSSL on macOS.</span></span>

<span data-ttu-id="f4a40-108">通过此更改，macOS 上的 .NET Core 运行时的行为如下所示：</span><span class="sxs-lookup"><span data-stu-id="f4a40-108">With this change, the behavior for the .NET Core runtimes on macOS is as follows:</span></span>

- <span data-ttu-id="f4a40-109">.NET Core 3.0 及更高版本运行时使用 OpenSSL 1.1.x（如果可用），并且仅在没有 1.1.x 版本可用的情况下才回退到 OpenSSL 1.0.x。</span><span class="sxs-lookup"><span data-stu-id="f4a40-109">The .NET Core 3.0 and later version runtimes use OpenSSL 1.1.x, if available, and fall back to OpenSSL 1.0.x only if there's no 1.1.x version available.</span></span>

  <span data-ttu-id="f4a40-110">对于将 OpenSSL 互操作类型与自定义 P/Invoke 一起使用的调用方，请按照 <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> 注释中的指南进行操作。</span><span class="sxs-lookup"><span data-stu-id="f4a40-110">For callers that use the OpenSSL interop types with custom P/Invokes, follow the guidance in the <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> remarks.</span></span> <span data-ttu-id="f4a40-111">如果不检查 <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion> 值，你的应用可能会出现故障。</span><span class="sxs-lookup"><span data-stu-id="f4a40-111">Your app may crash if you don't check the <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion> value.</span></span>

- <span data-ttu-id="f4a40-112">.NET Core 2.1 运行时使用 OpenSSL 1.0.x（如果可用），并且仅在没有 1.0.x 版本可用的情况下才回退到 OpenSSL 1.1.x。</span><span class="sxs-lookup"><span data-stu-id="f4a40-112">The .NET Core 2.1 runtime uses OpenSSL 1.0.x, if available, and falls back to OpenSSL 1.1.x if there's no 1.0.x version available.</span></span>

  <span data-ttu-id="f4a40-113">2.1 运行时首选早期版本的 OpenSSL，因为 .NET Core 2.1 中不存在 <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> 属性，因此无法在运行时可靠地确定 OpenSSL 版本。</span><span class="sxs-lookup"><span data-stu-id="f4a40-113">The 2.1 runtime prefers the earlier version of OpenSSL because the <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> property does not exist in .NET Core 2.1, so the OpenSSL version cannot be reliably determined at run time.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f4a40-114">引入的版本</span><span class="sxs-lookup"><span data-stu-id="f4a40-114">Version introduced</span></span>

- <span data-ttu-id="f4a40-115">.NET Core 2.1.16</span><span class="sxs-lookup"><span data-stu-id="f4a40-115">.NET Core 2.1.16</span></span>
- <span data-ttu-id="f4a40-116">.NET Core 3.0.3</span><span class="sxs-lookup"><span data-stu-id="f4a40-116">.NET Core 3.0.3</span></span>
- <span data-ttu-id="f4a40-117">.NET Core 3.1.2</span><span class="sxs-lookup"><span data-stu-id="f4a40-117">.NET Core 3.1.2</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f4a40-118">建议操作</span><span class="sxs-lookup"><span data-stu-id="f4a40-118">Recommended action</span></span>

- <span data-ttu-id="f4a40-119">如果不再需要 OpenSSL 版本 1.0.2，请将其卸载。</span><span class="sxs-lookup"><span data-stu-id="f4a40-119">Uninstall OpenSSL version 1.0.2 if it's no longer needed.</span></span>

- <span data-ttu-id="f4a40-120">如果你使用 <xref:System.Security.Cryptography.AesCcm>、<xref:System.Security.Cryptography.AesGcm>、<xref:System.Security.Cryptography.DSAOpenSsl>、<xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl>、<xref:System.Security.Cryptography.ECDsaOpenSsl>、<xref:System.Security.Cryptography.RSAOpenSsl> 或 <xref:System.Security.Cryptography.SafeEvpPKeyHandle> 类型，请安装 OpenSSL 1.1.x。</span><span class="sxs-lookup"><span data-stu-id="f4a40-120">Install OpenSSL 1.1.x if you use the <xref:System.Security.Cryptography.AesCcm>, <xref:System.Security.Cryptography.AesGcm>, <xref:System.Security.Cryptography.DSAOpenSsl>, <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl>, <xref:System.Security.Cryptography.ECDsaOpenSsl>, <xref:System.Security.Cryptography.RSAOpenSsl>, or <xref:System.Security.Cryptography.SafeEvpPKeyHandle> types.</span></span>

- <span data-ttu-id="f4a40-121">如果你将 OpenSSL 互操作类型与自定义 P/Invoke 一起使用，请按照 <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> 注释中的指南进行操作。</span><span class="sxs-lookup"><span data-stu-id="f4a40-121">If you use the OpenSSL interop types with custom P/Invokes, follow the guidance in the <xref:System.Security.Cryptography.SafeEvpPKeyHandle.OpenSslVersion?displayProperty=nameWithType> remarks.</span></span>

#### <a name="category"></a><span data-ttu-id="f4a40-122">类别</span><span class="sxs-lookup"><span data-stu-id="f4a40-122">Category</span></span>

<span data-ttu-id="f4a40-123">CoreFx</span><span class="sxs-lookup"><span data-stu-id="f4a40-123">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f4a40-124">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="f4a40-124">Affected APIs</span></span>

- <xref:System.Security.Cryptography.AesCcm?displayProperty=fullName>
- <xref:System.Security.Cryptography.AesGcm?displayProperty=fullName>
- <xref:System.Security.Cryptography.DSAOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDiffieHellmanOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.ECDsaOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.RSAOpenSsl?displayProperty=fullName>
- <xref:System.Security.Cryptography.SafeEvpPKeyHandle?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Security.Cryptography.AesCcm``
- `T:System.Security.Cryptography.AesGcm`
- `T:System.Security.Cryptography.DSAOpenSsl`
- `T:System.Security.Cryptography.ECDiffieHellmanOpenSsl`
- `T:System.Security.Cryptography.ECDsaOpenSsl`
- `T:System.Security.Cryptography.RSAOpenSsl`
- `T:System.Security.Cryptography.SafeEvpPKeyHandle`

-->

---
ms.openlocfilehash: 5ad9c494fd02059e05cc744aad3b06cfc9399995
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "77451873"
---
### <a name="default-value-of-httprequestmessageversion-changed-to-11"></a><span data-ttu-id="4e82c-101">HttpRequestMessage.Version 的默认值已更改为 1.1</span><span class="sxs-lookup"><span data-stu-id="4e82c-101">Default value of HttpRequestMessage.Version changed to 1.1</span></span>

<span data-ttu-id="4e82c-102"><xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> 属性的默认值已从 2.0 更改为 1.1。</span><span class="sxs-lookup"><span data-stu-id="4e82c-102">The default value of the <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> property has changed from 2.0 to 1.1.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="4e82c-103">引入的版本</span><span class="sxs-lookup"><span data-stu-id="4e82c-103">Version introduced</span></span>

<span data-ttu-id="4e82c-104">3.0</span><span class="sxs-lookup"><span data-stu-id="4e82c-104">3.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="4e82c-105">更改描述</span><span class="sxs-lookup"><span data-stu-id="4e82c-105">Change description</span></span>

<span data-ttu-id="4e82c-106">在 .NET Core 1.0 至 2.0 中，<xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> 属性的默认值为 1.1。</span><span class="sxs-lookup"><span data-stu-id="4e82c-106">In .NET Core 1.0 through 2.0, the default value of the <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> property is 1.1.</span></span> <span data-ttu-id="4e82c-107">从 .NET Core 2.1 开始，该值已更改为 2.1。</span><span class="sxs-lookup"><span data-stu-id="4e82c-107">Starting with .NET Core 2.1, it was changed to 2.1.</span></span>

<span data-ttu-id="4e82c-108">从 .NET Core 3.0 开始，<xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> 属性返回的默认版本号再次为 1.1。</span><span class="sxs-lookup"><span data-stu-id="4e82c-108">Starting with .NET Core 3.0, the default version number returned by the <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> property is once again 1.1.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="4e82c-109">建议操作</span><span class="sxs-lookup"><span data-stu-id="4e82c-109">Recommended action</span></span>

<span data-ttu-id="4e82c-110">如果代码依赖于 <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> 属性，则返回默认值 2.0，以更新代码。</span><span class="sxs-lookup"><span data-stu-id="4e82c-110">Update your code if it depends on the <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> property returning a default value of 2.0.</span></span>

#### <a name="category"></a><span data-ttu-id="4e82c-111">类别</span><span class="sxs-lookup"><span data-stu-id="4e82c-111">Category</span></span>

<span data-ttu-id="4e82c-112">网络</span><span class="sxs-lookup"><span data-stu-id="4e82c-112">Networking</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="4e82c-113">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="4e82c-113">Affected APIs</span></span>

- <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Net.Http.HttpRequestMessage.Version`

-->

---
ms.openlocfilehash: ce7e2db3f74ec24f47b1c224335451c997c4c349
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760970"
---
### <a name="wcf-binding-with-the-transportwithmessagecredential-security-mode"></a><span data-ttu-id="f0083-101">与 TransportWithMessageCredential 安全模式绑定的 WCF</span><span class="sxs-lookup"><span data-stu-id="f0083-101">WCF binding with the TransportWithMessageCredential security mode</span></span>

|   |   |
|---|---|
|<span data-ttu-id="f0083-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="f0083-102">Details</span></span>|<span data-ttu-id="f0083-103">从 .NET Framework 4.6.1 开始，可将使用 TransportWithMessageCredential 安全模式的 WCF 绑定设置为接收带有非对称安全密钥的未签名&quot;to&quot;标头的消息。默认情况下，.NET Framework 4.6.1 中将继续拒绝未签名&quot;to&quot;标头。</span><span class="sxs-lookup"><span data-stu-id="f0083-103">Beginning in the .NET Framework 4.6.1, WCF binding that uses the TransportWithMessageCredential security mode can be set up to receive messages with unsigned &quot;to&quot; headers for asymmetric security keys.By default, unsigned &quot;to&quot; headers will continue to be rejected in .NET Framework 4.6.1.</span></span> <span data-ttu-id="f0083-104">仅当应用程序使用 Switch.System.ServiceModel.AllowUnsignedToHeader 配置开关选择启用此新操作模式时，才会接受它们。</span><span class="sxs-lookup"><span data-stu-id="f0083-104">They will only be accepted if an application opts into this new mode of operation using the Switch.System.ServiceModel.AllowUnsignedToHeader configuration switch.</span></span>|
|<span data-ttu-id="f0083-105">建议</span><span class="sxs-lookup"><span data-stu-id="f0083-105">Suggestion</span></span>|<span data-ttu-id="f0083-106">由于这是一项可以选择使用的功能，因此它不应影响现有应用的行为。</span><span class="sxs-lookup"><span data-stu-id="f0083-106">Because this is an opt-in feature, it should not affect the behavior of existing apps.</span></span><br/><span data-ttu-id="f0083-107">要控制是否使用新行为，请使用以下配置设置：</span><span class="sxs-lookup"><span data-stu-id="f0083-107">To control whether the new behavior is used or not, use the following configuration setting:</span></span><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.AllowUnsignedToHeader=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="f0083-108">范围</span><span class="sxs-lookup"><span data-stu-id="f0083-108">Scope</span></span>|<span data-ttu-id="f0083-109">透明</span><span class="sxs-lookup"><span data-stu-id="f0083-109">Transparent</span></span>|
|<span data-ttu-id="f0083-110">版本</span><span class="sxs-lookup"><span data-stu-id="f0083-110">Version</span></span>|<span data-ttu-id="f0083-111">4.6.1</span><span class="sxs-lookup"><span data-stu-id="f0083-111">4.6.1</span></span>|
|<span data-ttu-id="f0083-112">类型</span><span class="sxs-lookup"><span data-stu-id="f0083-112">Type</span></span>|<span data-ttu-id="f0083-113">重定目标</span><span class="sxs-lookup"><span data-stu-id="f0083-113">Retargeting</span></span>|
|<span data-ttu-id="f0083-114">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="f0083-114">Affected APIs</span></span>|<ul><li><xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType></li><li><xref:System.ServiceModel.BasicHttpsSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType></li><li><xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential?displayProperty=nameWithType></li><li><xref:System.ServiceModel.WSFederationHttpSecurityMode.TransportWithMessageCredential?displayProperty=nameWithType></li></ul>|


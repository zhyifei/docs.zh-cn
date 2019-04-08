---
ms.openlocfilehash: 37d771305bb0a4a38eeac9713e8667d158962174
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2019
ms.locfileid: "57788800"
---
### <a name="remove-ssl3-from-the-wcf-transportdefaults"></a><span data-ttu-id="f289e-101">从 WCF TransportDefaults 删除 Ssl3</span><span class="sxs-lookup"><span data-stu-id="f289e-101">Remove Ssl3 from the WCF TransportDefaults</span></span>

|   |   |
|---|---|
|<span data-ttu-id="f289e-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="f289e-102">Details</span></span>|<span data-ttu-id="f289e-103">结合使用 NetTcp 与传输安全性和凭据类型证书时，SSL 3 协议不再是用于协商安全连接的默认协议。</span><span class="sxs-lookup"><span data-stu-id="f289e-103">When using NetTcp with transport security and a credential type of certificate, the SSL 3 protocol is no longer a default protocol used for negotiating a secure connection.</span></span> <span data-ttu-id="f289e-104">在大多数情况下，应该不会对现有应用程序造成任何影响，因为 TLS 1.0 始终包含在 NetTcp 协议列表中。</span><span class="sxs-lookup"><span data-stu-id="f289e-104">In most cases there should be no impact to existing apps as TLS 1.0 has always been included in the protocol list for NetTcp.</span></span> <span data-ttu-id="f289e-105">所有现有客户端应该至少能够使用 TLS 1.0 来协商连接。</span><span class="sxs-lookup"><span data-stu-id="f289e-105">All existing clients should be able to negotiate a connection using at least TLS1.0.</span></span>|
|<span data-ttu-id="f289e-106">建议</span><span class="sxs-lookup"><span data-stu-id="f289e-106">Suggestion</span></span>|<span data-ttu-id="f289e-107">如果 Ssl3 必需，则使用以下配置机制之一将 Ssl3 添加到协商协议的列表。</span><span class="sxs-lookup"><span data-stu-id="f289e-107">If Ssl3 is required, use one of the following configuration mechanisms to add Ssl3 to the list of negotiated protocols.</span></span><ul><li><xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols></li><li><xref:System.ServiceModel.TcpTransportSecurity.SslProtocols></li><li>[<span data-ttu-id="f289e-108">\<netTcpBinding> 的 \<transport></span><span class="sxs-lookup"><span data-stu-id="f289e-108">\<transport> of \<netTcpBinding></span></span>](~/docs/framework/configure-apps/file-schema/wcf/transport-of-nettcpbinding.md)</li><li>[<span data-ttu-id="f289e-109">&lt;customBinding&gt; 的 &lt;sslStreamSecurity&gt; 部分</span><span class="sxs-lookup"><span data-stu-id="f289e-109">&lt;sslStreamSecurity&gt; section of &lt;customBinding&gt;</span></span>](~/docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)</li></ul>|
|<span data-ttu-id="f289e-110">范围</span><span class="sxs-lookup"><span data-stu-id="f289e-110">Scope</span></span>|<span data-ttu-id="f289e-111">边缘</span><span class="sxs-lookup"><span data-stu-id="f289e-111">Edge</span></span>|
|<span data-ttu-id="f289e-112">版本</span><span class="sxs-lookup"><span data-stu-id="f289e-112">Version</span></span>|<span data-ttu-id="f289e-113">4.6.2</span><span class="sxs-lookup"><span data-stu-id="f289e-113">4.6.2</span></span>|
|<span data-ttu-id="f289e-114">类型</span><span class="sxs-lookup"><span data-stu-id="f289e-114">Type</span></span>|<span data-ttu-id="f289e-115">运行时</span><span class="sxs-lookup"><span data-stu-id="f289e-115">Runtime</span></span>|
|<span data-ttu-id="f289e-116">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="f289e-116">Affected APIs</span></span>|<ul><li><xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols?displayProperty=nameWithType></li><li><xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType></li></ul>|


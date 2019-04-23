---
ms.openlocfilehash: a6f93bbdf39a1b525e2daeb12afc3a6392a66e30
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59235206"
---
### <a name="deserialization-of-mailmessage-objects-serialized-under-the-net-framework-45-may-fail"></a><span data-ttu-id="056b6-101">在 .NET Framework 4.5 下序列化的 MailMessage 对象进行反序列化可能会失败</span><span class="sxs-lookup"><span data-stu-id="056b6-101">Deserialization of MailMessage objects serialized under the .NET Framework 4.5 may fail</span></span>

|   |   |
|---|---|
|<span data-ttu-id="056b6-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="056b6-102">Details</span></span>|<span data-ttu-id="056b6-103">从 .NET Framework 4.5 开始，<xref:System.Web.Mail.MailMessage> 对象可以包含非 ASCII 字符。</span><span class="sxs-lookup"><span data-stu-id="056b6-103">Starting with the .NET Framework 4.5, <xref:System.Web.Mail.MailMessage> objects can include non-ASCII characters.</span></span> <span data-ttu-id="056b6-104">在 .NET Framework 4 中，仅支持 ASCII 字符。</span><span class="sxs-lookup"><span data-stu-id="056b6-104">In the .NET Framework 4, only ASCII characters are supported.</span></span> <span data-ttu-id="056b6-105">包含非 ASCII 字符并在 .NET Framework 4.5 或更高版本下序列化的 <xref:System.Web.Mail.MailMessage> 对象不能在 .NET Framework 4 下进行反序列化。</span><span class="sxs-lookup"><span data-stu-id="056b6-105"><xref:System.Web.Mail.MailMessage> objects that contain non-ASCII characters and that are serialized under the .NET Framework 4.5 or later cannot be deserialized under the .NET Framework 4.</span></span>|
|<span data-ttu-id="056b6-106">建议</span><span class="sxs-lookup"><span data-stu-id="056b6-106">Suggestion</span></span>|<span data-ttu-id="056b6-107">请确保在反序列化 <xref:System.Web.Mail.MailMessage> 对象时，代码会提供异常处理。</span><span class="sxs-lookup"><span data-stu-id="056b6-107">Ensure that your code provides exception handling when deserializing a <xref:System.Web.Mail.MailMessage> object.</span></span>|
|<span data-ttu-id="056b6-108">范围</span><span class="sxs-lookup"><span data-stu-id="056b6-108">Scope</span></span>|<span data-ttu-id="056b6-109">次要</span><span class="sxs-lookup"><span data-stu-id="056b6-109">Minor</span></span>|
|<span data-ttu-id="056b6-110">版本</span><span class="sxs-lookup"><span data-stu-id="056b6-110">Version</span></span>|<span data-ttu-id="056b6-111">4.5</span><span class="sxs-lookup"><span data-stu-id="056b6-111">4.5</span></span>|
|<span data-ttu-id="056b6-112">类型</span><span class="sxs-lookup"><span data-stu-id="056b6-112">Type</span></span>|<span data-ttu-id="056b6-113">运行时</span><span class="sxs-lookup"><span data-stu-id="056b6-113">Runtime</span></span>|
|<span data-ttu-id="056b6-114">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="056b6-114">Affected APIs</span></span>|<ul><li><xref:System.Web.Mail.MailMessage?displayProperty=nameWithType></li></ul>|

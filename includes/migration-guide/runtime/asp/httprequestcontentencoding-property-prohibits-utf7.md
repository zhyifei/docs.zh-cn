---
ms.openlocfilehash: 668d047d3247d64cb1400d4a9ea6887795fa0d44
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59803333"
---
### <a name="httprequestcontentencoding-property-prohibits-utf7"></a><span data-ttu-id="87481-101">HttpRequest.ContentEncoding 属性禁止使用 UTF7</span><span class="sxs-lookup"><span data-stu-id="87481-101">HttpRequest.ContentEncoding property prohibits UTF7</span></span>

|   |   |
|---|---|
|<span data-ttu-id="87481-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="87481-102">Details</span></span>|<span data-ttu-id="87481-103">从 .NET Framework 4.5 开始，<xref:System.Web.HttpRequest?displayProperty=name> 正文禁止使用 UTF-7 编码。</span><span class="sxs-lookup"><span data-stu-id="87481-103">Beginning in .NET Framework 4.5, UTF-7 encoding is prohibited in <xref:System.Web.HttpRequest?displayProperty=name>s' bodies.</span></span> <span data-ttu-id="87481-104">在某些情况下，取决于传入的 UTF-7 数据的应用程序数据将不会正确解码。</span><span class="sxs-lookup"><span data-stu-id="87481-104">Data for applications that depend on incoming UTF-7 data will not decode properly in some cases.</span></span>|
|<span data-ttu-id="87481-105">建议</span><span class="sxs-lookup"><span data-stu-id="87481-105">Suggestion</span></span>|<span data-ttu-id="87481-106">理想情况下，应更新应用程序，使其在 <xref:System.Web.HttpRequest?displayProperty=name> 中不使用 UTF-7 编码。</span><span class="sxs-lookup"><span data-stu-id="87481-106">Ideally, applications should be updated to not use UTF-7 encoding in <xref:System.Web.HttpRequest?displayProperty=name>s.</span></span> <span data-ttu-id="87481-107">或者，可以使用 [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) 元素的 <code>aspnet:AllowUtf7RequestContentEncoding</code> 属性还原旧行为。</span><span class="sxs-lookup"><span data-stu-id="87481-107">Alternatively, legacy behavior can be restored by using the <code>aspnet:AllowUtf7RequestContentEncoding</code> attribute of the [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) element.</span></span>|
|<span data-ttu-id="87481-108">范围</span><span class="sxs-lookup"><span data-stu-id="87481-108">Scope</span></span>|<span data-ttu-id="87481-109">边缘</span><span class="sxs-lookup"><span data-stu-id="87481-109">Edge</span></span>|
|<span data-ttu-id="87481-110">版本</span><span class="sxs-lookup"><span data-stu-id="87481-110">Version</span></span>|<span data-ttu-id="87481-111">4.5</span><span class="sxs-lookup"><span data-stu-id="87481-111">4.5</span></span>|
|<span data-ttu-id="87481-112">类型</span><span class="sxs-lookup"><span data-stu-id="87481-112">Type</span></span>|<span data-ttu-id="87481-113">运行时</span><span class="sxs-lookup"><span data-stu-id="87481-113">Runtime</span></span>|
|<span data-ttu-id="87481-114">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="87481-114">Affected APIs</span></span>|<ul><li><xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType></li></ul>|

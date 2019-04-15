---
ms.openlocfilehash: 0056baa1e5f0cdc5bfcf8b0e83c9490ec5722926
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235197"
---
### <a name="httputilityjavascriptstringencode-escapes-ampersand"></a><span data-ttu-id="576b3-101">HttpUtility.JavaScriptStringEncode 转义 & 号</span><span class="sxs-lookup"><span data-stu-id="576b3-101">HttpUtility.JavaScriptStringEncode escapes ampersand</span></span>

|   |   |
|---|---|
|<span data-ttu-id="576b3-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="576b3-102">Details</span></span>|<span data-ttu-id="576b3-103">自 .NET Framework 4.5 起，<xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=name> 转义 &amp; 符号。</span><span class="sxs-lookup"><span data-stu-id="576b3-103">Starting with the .NET Framework 4.5, <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=name> escapes the ampersand (&amp;) character.</span></span>|
|<span data-ttu-id="576b3-104">建议</span><span class="sxs-lookup"><span data-stu-id="576b3-104">Suggestion</span></span>|<span data-ttu-id="576b3-105">如果应用依赖于此方法以前的行为，可将 aspnet:JavaScriptDoNotEncodeAmpersand 设置添加到配置文件中的 [ASP.NET appSettings 元素](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120))。</span><span class="sxs-lookup"><span data-stu-id="576b3-105">If your app depends on the previous behavior of this method, you can add an aspnet:JavaScriptDoNotEncodeAmpersand setting to the [ASP.NET appSettings element](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120)) in your configuration file.</span></span>|
|<span data-ttu-id="576b3-106">范围</span><span class="sxs-lookup"><span data-stu-id="576b3-106">Scope</span></span>|<span data-ttu-id="576b3-107">次要</span><span class="sxs-lookup"><span data-stu-id="576b3-107">Minor</span></span>|
|<span data-ttu-id="576b3-108">版本</span><span class="sxs-lookup"><span data-stu-id="576b3-108">Version</span></span>|<span data-ttu-id="576b3-109">4.5</span><span class="sxs-lookup"><span data-stu-id="576b3-109">4.5</span></span>|
|<span data-ttu-id="576b3-110">类型</span><span class="sxs-lookup"><span data-stu-id="576b3-110">Type</span></span>|<span data-ttu-id="576b3-111">运行时</span><span class="sxs-lookup"><span data-stu-id="576b3-111">Runtime</span></span>|
|<span data-ttu-id="576b3-112">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="576b3-112">Affected APIs</span></span>|<ul><li><xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=nameWithType></li><li><xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)?displayProperty=nameWithType></li></ul>|

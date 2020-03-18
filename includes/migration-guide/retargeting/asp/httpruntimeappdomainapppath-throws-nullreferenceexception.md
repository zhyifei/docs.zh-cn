---
ms.openlocfilehash: e7154919d6a09a04e650d5546feb2ae6c6cc912f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859188"
---
### <a name="httpruntimeappdomainapppath-throws-a-nullreferenceexception"></a><span data-ttu-id="23148-101">HttpRuntime.AppDomainAppPath 引发 NullReferenceException</span><span class="sxs-lookup"><span data-stu-id="23148-101">HttpRuntime.AppDomainAppPath Throws a NullReferenceException</span></span>

|   |   |
|---|---|
|<span data-ttu-id="23148-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="23148-102">Details</span></span>|<span data-ttu-id="23148-103">在 .NET Framework 4.6.2 中，当检索包含空字符的 <code>T:System.NullReferenceException</code> 值时，运行时会引发 <code>P:System.Web.HttpRuntime.AppDomainAppPath</code>。在 .NET Framework 4.6.1 及早期版本中，运行时将引发 <code>T:System.ArgumentNullException</code>。</span><span class="sxs-lookup"><span data-stu-id="23148-103">In the .NET Framework 4.6.2, the runtime throws a <code>T:System.NullReferenceException</code> when retrieving a <code>P:System.Web.HttpRuntime.AppDomainAppPath</code> value that includes null characters.In the .NET Framework 4.6.1 and earlier versions, the runtime throws an <code>T:System.ArgumentNullException</code>.</span></span>|
|<span data-ttu-id="23148-104">建议</span><span class="sxs-lookup"><span data-stu-id="23148-104">Suggestion</span></span>|<span data-ttu-id="23148-105">可执行以下任一操作来应对此更改：</span><span class="sxs-lookup"><span data-stu-id="23148-105">You can do either of the follow to respond to this change:</span></span><ul><li><span data-ttu-id="23148-106">如果应用程序是在 .NET Framework 4.6.2 上运行，请处理 <code>T:System.NullReferenceException</code>。</span><span class="sxs-lookup"><span data-stu-id="23148-106">Handle the <code>T:System.NullReferenceException</code> if you application is running on the .NET Framework 4.6.2.</span></span></li><li><span data-ttu-id="23148-107">升级到 .NET Framework 4.7，这将还原以前的行为并引发 <code>T:System.ArgumentNullException</code>。</span><span class="sxs-lookup"><span data-stu-id="23148-107">Upgrade to the .NET Framework 4.7, which restores the previous behavior and throws an <code>T:System.ArgumentNullException</code>.</span></span></li></ul>|
|<span data-ttu-id="23148-108">范围</span><span class="sxs-lookup"><span data-stu-id="23148-108">Scope</span></span>|<span data-ttu-id="23148-109">边缘</span><span class="sxs-lookup"><span data-stu-id="23148-109">Edge</span></span>|
|<span data-ttu-id="23148-110">Version</span><span class="sxs-lookup"><span data-stu-id="23148-110">Version</span></span>|<span data-ttu-id="23148-111">4.6.2</span><span class="sxs-lookup"><span data-stu-id="23148-111">4.6.2</span></span>|
|<span data-ttu-id="23148-112">类型</span><span class="sxs-lookup"><span data-stu-id="23148-112">Type</span></span>|<span data-ttu-id="23148-113">重定目标</span><span class="sxs-lookup"><span data-stu-id="23148-113">Retargeting</span></span>|
|<span data-ttu-id="23148-114">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="23148-114">Affected APIs</span></span>|<ul><li><xref:System.Web.HttpRuntime.AppDomainAppPath?displayProperty=nameWithType></li></ul>|

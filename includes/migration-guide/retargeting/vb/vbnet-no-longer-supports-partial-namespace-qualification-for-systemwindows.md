---
ms.openlocfilehash: 8db115a46df3fcea103e8fa6896542d0116aa256
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804671"
---
### <a name="vbnet-no-longer-supports-partial-namespace-qualification-for-systemwindows-apis"></a><span data-ttu-id="8870d-101">VB.NET 不再支持 System.Windows API 的部分命名空间限定</span><span class="sxs-lookup"><span data-stu-id="8870d-101">VB.NET no longer supports partial namespace qualification for System.Windows APIs</span></span>

|   |   |
|---|---|
|<span data-ttu-id="8870d-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="8870d-102">Details</span></span>|<span data-ttu-id="8870d-103">从 .NET Framework 4.5.2 开始，VB.NET 项目无法通过部分限定命名空间指定 System.Windows API。</span><span class="sxs-lookup"><span data-stu-id="8870d-103">Beginning in .NET Framework 4.5.2, VB.NET projects cannot specify System.Windows APIs with partially-qualified namespaces.</span></span> <span data-ttu-id="8870d-104">例如，对 <code>Windows.Forms.DialogResult</code> 的引用将失败。</span><span class="sxs-lookup"><span data-stu-id="8870d-104">For example, referring to <code>Windows.Forms.DialogResult</code> will fail.</span></span> <span data-ttu-id="8870d-105">而代码必须引用完全限定名称 (<xref:System.Windows.Forms.DialogResult>)，或导入特定命名空间并仅引用 <xref:System.Windows.Forms.DialogResult?displayProperty=name>。</span><span class="sxs-lookup"><span data-stu-id="8870d-105">Instead, code must refer to the fully qualified name (<xref:System.Windows.Forms.DialogResult>) or import the specific namespace and refer simply to <xref:System.Windows.Forms.DialogResult?displayProperty=name>.</span></span>|
|<span data-ttu-id="8870d-106">建议</span><span class="sxs-lookup"><span data-stu-id="8870d-106">Suggestion</span></span>|<span data-ttu-id="8870d-107">应更新代码，以使用简单名称（并导入相关命名空间）或使用完全限定名称来引用 <code>System.Windows</code> API。</span><span class="sxs-lookup"><span data-stu-id="8870d-107">Code should be updated to refer to <code>System.Windows</code> APIs either with simple names (and importing the relevant namespace) or with fully qualified names.</span></span>|
|<span data-ttu-id="8870d-108">范围</span><span class="sxs-lookup"><span data-stu-id="8870d-108">Scope</span></span>|<span data-ttu-id="8870d-109">次要</span><span class="sxs-lookup"><span data-stu-id="8870d-109">Minor</span></span>|
|<span data-ttu-id="8870d-110">Version</span><span class="sxs-lookup"><span data-stu-id="8870d-110">Version</span></span>|<span data-ttu-id="8870d-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="8870d-111">4.5.2</span></span>|
|<span data-ttu-id="8870d-112">类型</span><span class="sxs-lookup"><span data-stu-id="8870d-112">Type</span></span>|<span data-ttu-id="8870d-113">重定目标</span><span class="sxs-lookup"><span data-stu-id="8870d-113">Retargeting</span></span>|

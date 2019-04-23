---
ms.openlocfilehash: e8c48c4b1031813ce62f576e5bf1f94c082dfe4b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774302"
---
### <a name="obsoleteattribute-exports-as-both-obsoleteattribute-and-deprecatedattribute-in-winmd-scenarios"></a><span data-ttu-id="83ff7-101">ObsoleteAttribute 在 WinMD 方案中导出为 ObsoleteAttribute 和 DeprecatedAttribute</span><span class="sxs-lookup"><span data-stu-id="83ff7-101">ObsoleteAttribute exports as both ObsoleteAttribute and DeprecatedAttribute in WinMD scenarios</span></span>

|   |   |
|---|---|
|<span data-ttu-id="83ff7-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="83ff7-102">Details</span></span>|<span data-ttu-id="83ff7-103">创建 Windows 元数据库（.winmd 文件）时，<xref:System.ObsoleteAttribute?displayProperty=name> 属性将导出为 <xref:System.ObsoleteAttribute?displayProperty=name> 和 [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute)。</span><span class="sxs-lookup"><span data-stu-id="83ff7-103">When you create a Windows Metadata library (.winmd file), the <xref:System.ObsoleteAttribute?displayProperty=name> attribute is exported as both <xref:System.ObsoleteAttribute?displayProperty=name> and [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute).</span></span>|
|<span data-ttu-id="83ff7-104">建议</span><span class="sxs-lookup"><span data-stu-id="83ff7-104">Suggestion</span></span>|<span data-ttu-id="83ff7-105">重新编译使用 <xref:System.ObsoleteAttribute?displayProperty=name> 属性的现有源代码可能会在从 C++/CX 或 JavaScript 使用该代码时生成警告。我们不建议将 <xref:System.ObsoleteAttribute?displayProperty=name> 和 [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute) 同时用于托管程序集中的代码，这可能会导致生成警告。</span><span class="sxs-lookup"><span data-stu-id="83ff7-105">Recompilation of existing source code that uses the <xref:System.ObsoleteAttribute?displayProperty=name> attribute may generate warnings when consuming that code from C++/CX or JavaScript.We do not recommend applying both <xref:System.ObsoleteAttribute?displayProperty=name> and [Windows.Foundation.DeprecatedAttribute](https://docs.microsoft.com/uwp/api/windows.foundation.metadata.deprecatedattribute) to code in managed assemblies; it may result in build warnings.</span></span>|
|<span data-ttu-id="83ff7-106">范围</span><span class="sxs-lookup"><span data-stu-id="83ff7-106">Scope</span></span>|<span data-ttu-id="83ff7-107">边缘</span><span class="sxs-lookup"><span data-stu-id="83ff7-107">Edge</span></span>|
|<span data-ttu-id="83ff7-108">版本</span><span class="sxs-lookup"><span data-stu-id="83ff7-108">Version</span></span>|<span data-ttu-id="83ff7-109">4.5.1</span><span class="sxs-lookup"><span data-stu-id="83ff7-109">4.5.1</span></span>|
|<span data-ttu-id="83ff7-110">类型</span><span class="sxs-lookup"><span data-stu-id="83ff7-110">Type</span></span>|<span data-ttu-id="83ff7-111">重定目标</span><span class="sxs-lookup"><span data-stu-id="83ff7-111">Retargeting</span></span>|

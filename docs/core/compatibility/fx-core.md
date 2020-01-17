---
title: 从 .NET Framework 到 .NET Core 的中断性变更
description: 列出了从 .NET Framework 到 .NET Core 的中断性变更。
ms.date: 12/18/2019
ms.openlocfilehash: 5c29636664632e80e4235e922a3296c34fdbef36
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2020
ms.locfileid: "75900125"
---
# <a name="breaking-changes-for-migration-from-net-framework-to-net-core"></a><span data-ttu-id="5c2df-103">从 .NET Framework 迁移到 .NET Core 的中断性变更</span><span class="sxs-lookup"><span data-stu-id="5c2df-103">Breaking changes for migration from .NET Framework to .NET Core</span></span>

<span data-ttu-id="5c2df-104">若要将应用从 .NET Framework 迁移到 .NET Core，本文中列出的中断性变更可能会影响你。</span><span class="sxs-lookup"><span data-stu-id="5c2df-104">If you're migrating an app from .NET Framework to .NET Core, the breaking changes listed in this article may affect you.</span></span> <span data-ttu-id="5c2df-105">中断性变更按类别分组。</span><span class="sxs-lookup"><span data-stu-id="5c2df-105">Breaking changes are grouped by category.</span></span>

> [!NOTE]
> <span data-ttu-id="5c2df-106">本文不是 .NET Framework 与 .NET Core 之间的中断性变更的完整列表。</span><span class="sxs-lookup"><span data-stu-id="5c2df-106">This article is not a complete list of breaking changes between .NET Framework and .NET Core.</span></span> <span data-ttu-id="5c2df-107">在我们发现最重要的中断性变更时，会将其添加到此处。</span><span class="sxs-lookup"><span data-stu-id="5c2df-107">The most important breaking changes are added here as we become aware of them.</span></span>

## <a name="corefx"></a><span data-ttu-id="5c2df-108">CoreFx</span><span class="sxs-lookup"><span data-stu-id="5c2df-108">CoreFx</span></span>

[!INCLUDE[Process.Start changes](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

## <a name="windows-forms"></a><span data-ttu-id="5c2df-109">Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="5c2df-109">Windows Forms</span></span>

<span data-ttu-id="5c2df-110">有关将 Windows 窗体应用从 .NET Framework 迁移到 .NET Core 3.0 或更高版本时发生的中断性变更的信息，请参阅 [Windows 窗体的中断性变更（从 .NET Framework 到 .NET Core）](../porting/winforms-breaking-changes.md)。</span><span class="sxs-lookup"><span data-stu-id="5c2df-110">For information about breaking changes when you migrate a Windows Forms app from .NET Framework to .NET Core 3.0 or later, see [Breaking changes in Windows Forms (.NET Framework to .NET Core)](../porting/winforms-breaking-changes.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5c2df-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="5c2df-111">See also</span></span>

- [<span data-ttu-id="5c2df-112">始终在 .NET Core 上引发异常的 API</span><span class="sxs-lookup"><span data-stu-id="5c2df-112">APIs that always throw exceptions on .NET Core</span></span>](unsupported-apis.md)
- [<span data-ttu-id="5c2df-113">.NET Framework 技术在 .NET Core 上不可用</span><span class="sxs-lookup"><span data-stu-id="5c2df-113">.NET Framework technologies unavailable on .NET Core</span></span>](../porting/net-framework-tech-unavailable.md)

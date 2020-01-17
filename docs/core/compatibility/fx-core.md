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
# <a name="breaking-changes-for-migration-from-net-framework-to-net-core"></a>从 .NET Framework 迁移到 .NET Core 的中断性变更

若要将应用从 .NET Framework 迁移到 .NET Core，本文中列出的中断性变更可能会影响你。 中断性变更按类别分组。

> [!NOTE]
> 本文不是 .NET Framework 与 .NET Core 之间的中断性变更的完整列表。 在我们发现最重要的中断性变更时，会将其添加到此处。

## <a name="corefx"></a>CoreFx

[!INCLUDE[Process.Start changes](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

## <a name="windows-forms"></a>Windows 窗体

有关将 Windows 窗体应用从 .NET Framework 迁移到 .NET Core 3.0 或更高版本时发生的中断性变更的信息，请参阅 [Windows 窗体的中断性变更（从 .NET Framework 到 .NET Core）](../porting/winforms-breaking-changes.md)。

## <a name="see-also"></a>请参阅

- [始终在 .NET Core 上引发异常的 API](unsupported-apis.md)
- [.NET Framework 技术在 .NET Core 上不可用](../porting/net-framework-tech-unavailable.md)

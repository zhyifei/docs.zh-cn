---
ms.openlocfilehash: 921baed7381fad363cc832c6b6af69068c2c8f43
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "67802481"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a>本地化版本中的 RibbonGroup 背景设置为透明

|   |   |
|---|---|
|详细信息|始终用透明画笔绘制本地化版本上的 <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> 背景，导致 UI 体验不佳。 .NET Framework 4.7 WPF 修复中通过更新 <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> 本地化资源修复了此问题，因而又确保会选中正确的画笔。|
|建议|升级到 .NET Framework 4.7|
|范围|边缘|
|Version|4.6.2|
|类型|运行时|

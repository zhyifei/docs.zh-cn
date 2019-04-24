---
ms.openlocfilehash: 921baed7381fad363cc832c6b6af69068c2c8f43
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59235989"
---
### <a name="ribbongroup-background-is-set-to-transparent-in-localized-builds"></a>本地化版本中的 RibbonGroup 背景设置为透明

|   |   |
|---|---|
|详细信息|始终用透明画笔绘制本地化版本上的 <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> 背景，导致 UI 体验不佳。 .NET Framework 4.7 WPF 修复中通过更新 <xref:System.Windows.Controls.Ribbon.RibbonGroup?displayProperty=name> 本地化资源修复了此问题，因而又确保会选中正确的画笔。|
|建议|升级到 .NET Framework 4.7|
|范围|边缘|
|版本|4.6.2|
|类型|运行时|

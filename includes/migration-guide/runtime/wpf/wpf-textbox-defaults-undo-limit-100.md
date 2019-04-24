---
ms.openlocfilehash: de79182e326082786c1e0691f8888e30cd410f5d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59235072"
---
### <a name="wpf-textbox-defaults-to-undo-limit-of-100"></a>WPF 文本框默认撤消限制是 100

|   |   |
|---|---|
|详细信息|在 .NET Framework 4.5 中，WPF 文本框的默认撤消限制是 100（.NET Framework 4.0 则没有限制）|
|建议|如果 100 的撤消限制过低，可使用 <xref:System.Windows.Controls.Primitives.TextBoxBase.UndoLimit> 显式设置该限制|
|范围|边缘|
|版本|4.5|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType></li></ul>|

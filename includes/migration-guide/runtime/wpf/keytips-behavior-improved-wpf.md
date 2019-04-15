---
ms.openlocfilehash: 946096cb9510ca12bbd2cecd00099142308b072a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236117"
---
### <a name="keytips-behavior-improved-in-wpf"></a>WPF 中改进的 Keytip 行为

|   |   |
|---|---|
|详细信息|已修改 Keytip 行为，以便对 Microsoft Word 和 Windows 资源管理器行为进行奇偶校验。 通过在按下 <xref:System.Windows.Input.KeyEventArgs.SystemKey>（特别是 <xref:System.Windows.Input.Key> 或 <xref:System.Windows.Input.Key.F11>）的情况下检查是否启用 keytip 状态，WPF 可正确地处理 keytip 键。 现在，即使是通过鼠标打开的菜单，keytip 也可将其关闭。|
|建议|不可用|
|范围|边缘|
|版本|4.7.2|
|类型|运行时|

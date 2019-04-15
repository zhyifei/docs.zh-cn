---
ms.openlocfilehash: 8b0617d8f021a9534289fd7ae8539cd054684862
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234606"
---
### <a name="wpf-textboxtext-can-be-out-of-sync-with-databinding"></a>WPF TextBox.Text 可能与数据绑定不同步

|   |   |
|---|---|
|详细信息|在某些情况下，如果在数据绑定的写入操作期间修改属性，则 <xref:System.Windows.Controls.TextBox.Text> 属性会反映数据绑定属性值的以前的值。|
|建议|这不应有负面影响。 不过，你可以通过将 <xref:System.Windows.FrameworkCompatibilityPreferences.KeepTextBoxDisplaySynchronizedWithTextProperty> 属性设置为 <code>false</code> 来还原以前的行为。|
|范围|边缘|
|版本|4.5|
|类型|重定目标|
|受影响的 API|<ul><li><xref:System.Windows.Controls.TextBox.Text?displayProperty=nameWithType></li></ul>|

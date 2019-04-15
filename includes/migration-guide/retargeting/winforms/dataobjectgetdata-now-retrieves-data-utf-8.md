---
ms.openlocfilehash: e39b4e85b47902babac7a22a93aa64c2f86ef01f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236720"
---
### <a name="dataobjectgetdata-now-retrieves-data-as-utf-8"></a>DataObject.GetData 现在将数据检索为 UTF-8

|   |   |
|---|---|
|详细信息|对于面向 .NET Framework 4 或者在 .NET Framework 4.5.1 或更早版本上运行的应用，<code>DataObject.GetData</code> 将 HTML 格式的数据检索为 ASCII 字符串。 因此，非 ASCII 字符（ASCII 代码大于 0x7F 的字符）由两个随机字符表示。<p/>对于面向 .NET Framework 4.5 或更高版本以及在 .NET Framework 4.5.2 上运行的应用，<code>DataObject.GetData</code> 将 HTML 格式的数据检索为 UTF-8，从而可以正确表示大于 0x7F 的字符。|
|建议|如果使用 HTML 格式的字符串实现了编码问题的解决方法（例如，通过将其传递到 <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=name> 来显式编码从剪贴板检索的 HTML 字符串），而且要将应用的目标从版本 4 重定为 4.5，则应该删除该解决方法。如果出于某种原因需要使用以前的版本，该应用可面向 .NET Framework 4.0 来获取该行为。|
|范围|边缘|
|Version|4.5.2|
|类型|重定目标|
|受影响的 API|<ul><li><xref:System.Windows.DataObject.GetData(System.String)?displayProperty=nameWithType></li><li><xref:System.Windows.DataObject.GetData(System.Type)?displayProperty=nameWithType></li><li><xref:System.Windows.DataObject.GetData(System.String,System.Boolean)?displayProperty=nameWithType></li></ul>|

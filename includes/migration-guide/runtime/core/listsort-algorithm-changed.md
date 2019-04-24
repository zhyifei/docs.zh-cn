---
ms.openlocfilehash: d4859629fe3922b71cc90664e1e3304cdb312bae
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59235169"
---
### <a name="listsort-algorithm-changed"></a>List.Sort 算法已更改

|   |   |
|---|---|
|详细信息|从 .NET Framework 4.5 开始，<xref:System.Collections.Generic.List%601?displayProperty=name> 的排序算法就已更改（为内省排序而不是快速排序）。 <xref:System.Collections.Generic.List%601?displayProperty=name> 的排序一直都不稳定，但此更改可能会导致各种方案以不稳定的方式进行排序。 这仅仅意味着等效项目可能会在随后的 API 调用中按不同顺序排序。|
|建议|由于旧的排序算法也不稳定（尽管方式略有不同），因此应该没有代码依赖于始终按特定顺序排序的等效项。 如果有代码实例依赖于此等效项，并且可以幸运地使用旧行为，则此代码应更新为使用按照所需顺序对项进行确定性排序的比较器。|
|范围|透明|
|Version|4.5|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Collections.Generic.List%601.Sort?displayProperty=nameWithType></li><li><xref:System.Collections.Generic.List%601.Sort(System.Collections.Generic.IComparer{%600})?displayProperty=nameWithType></li><li><xref:System.Collections.Generic.List%601.Sort(System.Comparison{%600})?displayProperty=nameWithType></li><li><xref:System.Collections.Generic.List%601.Sort(System.Int32,System.Int32,System.Collections.Generic.IComparer{%600})?displayProperty=nameWithType></li></ul>|

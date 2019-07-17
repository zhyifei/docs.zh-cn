---
ms.openlocfilehash: 770e303ab261b97efb49a3e0865a015d8de33247
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802680"
---
### <a name="improvements-to-grid-star-rows-space-allocating-algorithm"></a>网格星型行空格分配算法的改进

|   |   |
|---|---|
|详细信息|修复了在 .NET Framework 4.7 中引入的 <xref:System.Windows.Controls.Grid> 中[用于分配大小的算法](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md)的问题。  在某些情况下，例如，<code>Height=&quot;Auto&quot;</code> 包含空行的网格，行排列在错误的位置，可能完全在网格之外。|
|建议|为使应用程序从这些更改中获益，它必须在 .NET Framework 4.8 或更高版本上运行。|
|范围|主要|
|Version|4.8|
|类型|运行时|


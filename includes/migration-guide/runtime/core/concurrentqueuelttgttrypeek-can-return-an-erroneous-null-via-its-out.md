---
ms.openlocfilehash: a93fbbd787aa50f080337a6170cf8f56d0d24e31
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236684"
---
### <a name="concurrentqueuettrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a>ConcurrentQueue\<T>.TryPeek 可通过 out 参数返回错误的 null

|   |   |
|---|---|
|详细信息|在某些多线程情况下，<xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=name> 可返回 true，但使用 null 值填充 Out 参数（而非正确的扫视值）。|
|建议|此问题已在 .NET Framework 4.5.1 中解决。 升级到该 Framework 即可解决该问题。|
|范围|主要|
|版本|4.5|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=nameWithType></li></ul>|

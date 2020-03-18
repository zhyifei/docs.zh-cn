---
ms.openlocfilehash: 8433899058c6f569e380999800557dbe8ed0a169
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858394"
---
### <a name="cor_prf_gc_root_handles-are-not-being-enumerated-by-profilers"></a>探查器未枚举 COR_PRF_GC_ROOT_HANDLEs

|   |   |
|---|---|
|详细信息|在 .NET Framework v4.5.1 中，分析 API <code>RootReferences2()</code> 错误地不会返回 <code>COR_PRF_GC_ROOT_HANDLE</code>（而是返回 <code>COR_PRF_GC_ROOT_OTHER</code>）。 此问题已从 .NET Framework 4.6 开始修复。|
|建议|此问题已在 .NET Framework 4.6 中解决，因此升级到该版本的 .NET Framework 即可解决该问题。|
|范围|次要|
|Version|4.5.1|
|类型|运行时|

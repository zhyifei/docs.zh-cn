---
ms.openlocfilehash: 439a4976482639cd2e4e17315ec1a53ca54aa477
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59803372"
---
### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a>分析 ASP.Net MVC4 应用可能导致严重的执行引擎错误

|   |   |
|---|---|
|详细信息|使用 NGEN /Profile 程序集的探查器可能会在启动时使已配置的 ASP.NET MVC4 应用程序出故障，引发“严重的执行引擎异常”|
|建议|此问题已在 .NET Framework 4.5.2 中解决。 或者，探查器可通过在其事件掩码中指定 <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> 来避免此问题。|
|范围|边缘|
|版本|4.5|
|类型|运行时|

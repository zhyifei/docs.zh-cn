---
ms.openlocfilehash: e5d81d791e1a2f1a2dbdafc787dec1227423883d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774245"
---
### <a name="opt-in-break-to-revert-from-different-45-sql-generation-to-simpler-40-sql-generation"></a><span data-ttu-id="f35b5-101">选择中断以从不同的 4.5 SQL 生成还原到更简单的 4.0 SQL 生成</span><span class="sxs-lookup"><span data-stu-id="f35b5-101">Opt-in break to revert from different 4.5 SQL generation to simpler 4.0 SQL generation</span></span>

|   |   |
|---|---|
|<span data-ttu-id="f35b5-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="f35b5-102">Details</span></span>|<span data-ttu-id="f35b5-103">生成 JOIN 语句并包含对限制操作的调用（无需先使用 OrderBy）的查询现在可以生成更简单的 SQL。</span><span class="sxs-lookup"><span data-stu-id="f35b5-103">Queries that produce JOIN statements and contain a call to a limiting operation without first using OrderBy now produce simpler SQL.</span></span> <span data-ttu-id="f35b5-104">升级到 .NET Framework 4.5 后，这些查询生成了比以前版本更复杂的 SQL。</span><span class="sxs-lookup"><span data-stu-id="f35b5-104">After upgrading to .NET Framework 4.5, these queries produced more complicated SQL than previous versions.</span></span>|
|<span data-ttu-id="f35b5-105">建议</span><span class="sxs-lookup"><span data-stu-id="f35b5-105">Suggestion</span></span>|<span data-ttu-id="f35b5-106">在默认情况下，禁用此功能。</span><span class="sxs-lookup"><span data-stu-id="f35b5-106">This feature is disabled by default.</span></span> <span data-ttu-id="f35b5-107">如果实体框架生成可导致性能降低的额外 JOIN 语句，则可以通过将以下项添加到应用程序配置 (app.config) 文件的 <code>&lt;appSettings&gt;</code> 部分来启用此功能：</span><span class="sxs-lookup"><span data-stu-id="f35b5-107">If Entity Framework generates extra JOIN statements that cause performance degradation, you can enable this feature by adding the following entry to the <code>&lt;appSettings&gt;</code> section of the application configuration (app.config) file:</span></span><pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyLimitOperations&quot; value=&quot;true&quot; /&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="f35b5-108">范围</span><span class="sxs-lookup"><span data-stu-id="f35b5-108">Scope</span></span>|<span data-ttu-id="f35b5-109">透明</span><span class="sxs-lookup"><span data-stu-id="f35b5-109">Transparent</span></span>|
|<span data-ttu-id="f35b5-110">Version</span><span class="sxs-lookup"><span data-stu-id="f35b5-110">Version</span></span>|<span data-ttu-id="f35b5-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="f35b5-111">4.5.2</span></span>|
|<span data-ttu-id="f35b5-112">类型</span><span class="sxs-lookup"><span data-stu-id="f35b5-112">Type</span></span>|<span data-ttu-id="f35b5-113">运行时</span><span class="sxs-lookup"><span data-stu-id="f35b5-113">Runtime</span></span>|

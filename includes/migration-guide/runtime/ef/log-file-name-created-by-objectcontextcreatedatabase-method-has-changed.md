---
ms.openlocfilehash: cf1a8169351e29c18d85303fb32d4394877448f4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59803368"
---
### <a name="log-file-name-created-by-the-objectcontextcreatedatabase-method-has-changed-to-match-sql-server-specifications"></a><span data-ttu-id="12f2e-101">ObjectContext.CreateDatabase 方法创建的日志文件名已更改，以匹配 SQL Server 规范</span><span class="sxs-lookup"><span data-stu-id="12f2e-101">Log file name created by the ObjectContext.CreateDatabase method has changed to match SQL Server specifications</span></span>

|   |   |
|---|---|
|<span data-ttu-id="12f2e-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="12f2e-102">Details</span></span>|<span data-ttu-id="12f2e-103">当直接调用 <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=name> 方法或通过使用 Code First 与 SqlClient 提供程序以及连接字符串中的 AttachDBFilename 值来调用此方法时，它将创建一个名为 filename_log.ldf 而非 filename.ldf 的日志文件（其中 filename 是 AttachDBFilename 值指定的文件的名称）。</span><span class="sxs-lookup"><span data-stu-id="12f2e-103">When the <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=name> method is called either directly or by using Code First with the SqlClient provider and an AttachDBFilename value in the connection string, it creates a log file named filename_log.ldf instead of filename.ldf (where filename is the name of the file specified by the AttachDBFilename value).</span></span> <span data-ttu-id="12f2e-104">此更改通过提供根据 SQL Server 规范命名的日志文件来改进调试。</span><span class="sxs-lookup"><span data-stu-id="12f2e-104">This change improves debugging by providing a log file named according to SQL Server specifications.</span></span>|
|<span data-ttu-id="12f2e-105">建议</span><span class="sxs-lookup"><span data-stu-id="12f2e-105">Suggestion</span></span>|<span data-ttu-id="12f2e-106">如果日志文件名对应用而言很重要，应更新该应用，以使用标准的 _log.ldf 文件名格式。</span><span class="sxs-lookup"><span data-stu-id="12f2e-106">If the log file name is important for an app, the app should be updated to expect the standard _log.ldf file name format.</span></span>|
|<span data-ttu-id="12f2e-107">范围</span><span class="sxs-lookup"><span data-stu-id="12f2e-107">Scope</span></span>|<span data-ttu-id="12f2e-108">边缘</span><span class="sxs-lookup"><span data-stu-id="12f2e-108">Edge</span></span>|
|<span data-ttu-id="12f2e-109">版本</span><span class="sxs-lookup"><span data-stu-id="12f2e-109">Version</span></span>|<span data-ttu-id="12f2e-110">4.5</span><span class="sxs-lookup"><span data-stu-id="12f2e-110">4.5</span></span>|
|<span data-ttu-id="12f2e-111">类型</span><span class="sxs-lookup"><span data-stu-id="12f2e-111">Type</span></span>|<span data-ttu-id="12f2e-112">运行时</span><span class="sxs-lookup"><span data-stu-id="12f2e-112">Runtime</span></span>|
|<span data-ttu-id="12f2e-113">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="12f2e-113">Affected APIs</span></span>|<ul><li><xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=nameWithType></li></ul>|

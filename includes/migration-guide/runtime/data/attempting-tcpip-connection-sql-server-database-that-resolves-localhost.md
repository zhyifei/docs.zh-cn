---
ms.openlocfilehash: a4b8a03661650a3ef1d96b656798c3c3d39a5705
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "58467061"
---
### <a name="attempting-a-tcpip-connection-to-a-sql-server-database-that-resolves-to-localhost-fails"></a><span data-ttu-id="6239a-101">与解析为 `localhost` 的 SQL Server 数据库的 TCP/IP 连接尝试失败</span><span class="sxs-lookup"><span data-stu-id="6239a-101">Attempting a TCP/IP connection to a SQL Server database that resolves to `localhost` fails</span></span>

|   |   |
|---|---|
|<span data-ttu-id="6239a-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="6239a-102">Details</span></span>|<span data-ttu-id="6239a-103">在 .NET Framework 4.6 和 4.6.1 中，与解析为 <code>localhost</code> 的 SQL Server 数据库的 TCP/IP 连接尝试失败，出现错误：“在与 SQL Server 建立连接时出现与网络相关的错误或特定于实例的错误。</span><span class="sxs-lookup"><span data-stu-id="6239a-103">In the .NET Framework 4.6 and 4.6.1, attempting a TCP/IP connection to a SQL Server database that resolves to <code>localhost</code> fails with the error, &quot;A network-related or instance-specific error occurred while establishing a connection to SQL Server.</span></span> <span data-ttu-id="6239a-104">未找到或无法访问服务器。</span><span class="sxs-lookup"><span data-stu-id="6239a-104">The server was not found or was not accessible.</span></span> <span data-ttu-id="6239a-105">请验证实例名称是否正确，SQL Server 是否已配置为允许远程连接。</span><span class="sxs-lookup"><span data-stu-id="6239a-105">Verify that the instance name is correct and that SQL Server is configured to allow remote connections.</span></span> <span data-ttu-id="6239a-106">（提供程序：SQL 网络接口，错误：26 - 查找服务器/指定示例时出错）&quot;</span><span class="sxs-lookup"><span data-stu-id="6239a-106">(provider: SQL Network Interfaces, error: 26 - Error Locating Server/Instance Specified)&quot;</span></span>|
|<span data-ttu-id="6239a-107">建议</span><span class="sxs-lookup"><span data-stu-id="6239a-107">Suggestion</span></span>|<span data-ttu-id="6239a-108">在 .NET Framework 4.6.2 中，此问题已得到解决，并已恢复以前的行为。</span><span class="sxs-lookup"><span data-stu-id="6239a-108">This issue has been addressed and the previous behavior restored in the .NET Framework 4.6.2.</span></span> <span data-ttu-id="6239a-109">若要连接到会解析为 <code>localhost</code> 的 SQL Server 数据库，请升级到 .NET Framework 4.6.2。</span><span class="sxs-lookup"><span data-stu-id="6239a-109">To connect to a SQL Server database that resolves to <code>localhost</code>, upgrade to the .NET Framework 4.6.2.</span></span>|
|<span data-ttu-id="6239a-110">范围</span><span class="sxs-lookup"><span data-stu-id="6239a-110">Scope</span></span>|<span data-ttu-id="6239a-111">次要</span><span class="sxs-lookup"><span data-stu-id="6239a-111">Minor</span></span>|
|<span data-ttu-id="6239a-112">版本</span><span class="sxs-lookup"><span data-stu-id="6239a-112">Version</span></span>|<span data-ttu-id="6239a-113">4.6</span><span class="sxs-lookup"><span data-stu-id="6239a-113">4.6</span></span>|
|<span data-ttu-id="6239a-114">类型</span><span class="sxs-lookup"><span data-stu-id="6239a-114">Type</span></span>|<span data-ttu-id="6239a-115">运行时</span><span class="sxs-lookup"><span data-stu-id="6239a-115">Runtime</span></span>|


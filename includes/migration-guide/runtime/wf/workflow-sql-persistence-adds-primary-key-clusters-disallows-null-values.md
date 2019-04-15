---
ms.openlocfilehash: 566a3e0455b30e901b09be88b4256ffe67bdc2b5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236185"
---
### <a name="workflow-sql-persistence-adds-primary-key-clusters-and-disallows-null-values-in-some-columns"></a><span data-ttu-id="ffdf5-101">工作流 SQL 持久性添加主键群集并在某些列中禁止 null 值</span><span class="sxs-lookup"><span data-stu-id="ffdf5-101">Workflow SQL persistence adds primary key clusters and disallows null values in some columns</span></span>

|   |   |
|---|---|
|<span data-ttu-id="ffdf5-102">详细信息</span><span class="sxs-lookup"><span data-stu-id="ffdf5-102">Details</span></span>|<span data-ttu-id="ffdf5-103">从 .NET Framework 4.7 起，SqlWorkflowInstanceStoreSchema.sql 脚本为 SQL 工作流实例存储 (SWIS) 创建的表格使用群集主键。</span><span class="sxs-lookup"><span data-stu-id="ffdf5-103">Starting with the .NET Framework 4.7, the tables created for the SQL Workflow Instance Store (SWIS) by the SqlWorkflowInstanceStoreSchema.sql script use clustered primary keys.</span></span> <span data-ttu-id="ffdf5-104">因此，标识不支持 <code>null</code> 值。</span><span class="sxs-lookup"><span data-stu-id="ffdf5-104">Because of this, identities do not support <code>null</code> values.</span></span> <span data-ttu-id="ffdf5-105">此更改不影响 SWIS 操作。</span><span class="sxs-lookup"><span data-stu-id="ffdf5-105">The operation of SWIS is not impacted by this change.</span></span> <span data-ttu-id="ffdf5-106">进行了更新以支持 SQL Server 事务复制。</span><span class="sxs-lookup"><span data-stu-id="ffdf5-106">The updates were made to support SQL Server Transactional Replication.</span></span>|
|<span data-ttu-id="ffdf5-107">建议</span><span class="sxs-lookup"><span data-stu-id="ffdf5-107">Suggestion</span></span>|<span data-ttu-id="ffdf5-108">若要体验此更改，SQL 文件 SqlWorkflowInstanceStoreSchemaUpgrade.sql 必须应用到现有安装。</span><span class="sxs-lookup"><span data-stu-id="ffdf5-108">The SQL file SqlWorkflowInstanceStoreSchemaUpgrade.sql must be applied to existing installations in order to experience this change.</span></span> <span data-ttu-id="ffdf5-109">新数据库安装自动具有此更改。</span><span class="sxs-lookup"><span data-stu-id="ffdf5-109">New database installations will automatically have the change.</span></span>|
|<span data-ttu-id="ffdf5-110">范围</span><span class="sxs-lookup"><span data-stu-id="ffdf5-110">Scope</span></span>|<span data-ttu-id="ffdf5-111">边缘</span><span class="sxs-lookup"><span data-stu-id="ffdf5-111">Edge</span></span>|
|<span data-ttu-id="ffdf5-112">Version</span><span class="sxs-lookup"><span data-stu-id="ffdf5-112">Version</span></span>|<span data-ttu-id="ffdf5-113">4.7</span><span class="sxs-lookup"><span data-stu-id="ffdf5-113">4.7</span></span>|
|<span data-ttu-id="ffdf5-114">类型</span><span class="sxs-lookup"><span data-stu-id="ffdf5-114">Type</span></span>|<span data-ttu-id="ffdf5-115">运行时</span><span class="sxs-lookup"><span data-stu-id="ffdf5-115">Runtime</span></span>|

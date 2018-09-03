---
title: 安全性
ms.date: 03/30/2017
ms.assetid: 737ec121-bfc5-4b75-a504-2d53c2c8af39
ms.openlocfilehash: 6c4e64e928e3ada4210138878426fea9ffe5bdec
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2018
ms.locfileid: "43466677"
---
# <a name="security"></a><span data-ttu-id="d969b-102">安全性</span><span class="sxs-lookup"><span data-stu-id="d969b-102">Security</span></span>
<span data-ttu-id="d969b-103">SQL 工作流实例存储使用以下数据库安全角色确保安全访问持久性数据库中的实例状态信息。</span><span class="sxs-lookup"><span data-stu-id="d969b-103">The SQL Workflow Instance Store uses the following database security roles to secure access to instance state information in the persistence database.</span></span>  
  
-   <span data-ttu-id="d969b-104">**System.Activities.DurableInstancing.InstanceStoreUsers**。</span><span class="sxs-lookup"><span data-stu-id="d969b-104">**System.Activities.DurableInstancing.InstanceStoreUsers**.</span></span> <span data-ttu-id="d969b-105">此角色具有对公共视图的读写访问权以及对创建、加载和保存实例所涉及的存储过程的执行权限。</span><span class="sxs-lookup"><span data-stu-id="d969b-105">This role has read and write access to public views and execution rights to stored procedures that are involved in creating, loading and saving instances.</span></span>  
  
-   <span data-ttu-id="d969b-106">**System.Activities.DurableInstancing.InstanceStoreObservers**。</span><span class="sxs-lookup"><span data-stu-id="d969b-106">**System.Activities.DurableInstancing.InstanceStoreObservers**.</span></span> <span data-ttu-id="d969b-107">此角色具有对公共视图的只读访问权。</span><span class="sxs-lookup"><span data-stu-id="d969b-107">This role has read-only access to public views.</span></span>  
  
-   <span data-ttu-id="d969b-108">**System.Activities.DurableInstancing.WorkflowActivationUsers**。</span><span class="sxs-lookup"><span data-stu-id="d969b-108">**System.Activities.DurableInstancing.WorkflowActivationUsers**.</span></span> <span data-ttu-id="d969b-109">此角色对在实例激活过程中涉及的存储过程具有执行权限。</span><span class="sxs-lookup"><span data-stu-id="d969b-109">This role has execution rights to stored procedures that are involved in the instance activation process.</span></span> <span data-ttu-id="d969b-110">有关实例激活的详细信息，请参阅[实例激活](../../../docs/framework/windows-workflow-foundation/instance-activation.md)。</span><span class="sxs-lookup"><span data-stu-id="d969b-110">For more information about instance activation, see [Instance Activation](../../../docs/framework/windows-workflow-foundation/instance-activation.md).</span></span> <span data-ttu-id="d969b-111">应将运行泛型宿主（如 [!INCLUDE[dublin](../../../includes/dublin-md.md)] 的工作流管理服务）的用户帐户添加到此数据库角色中。</span><span class="sxs-lookup"><span data-stu-id="d969b-111">The user account under which a generic host (such as the Workflow Management Service of [!INCLUDE[dublin](../../../includes/dublin-md.md)]) runs should be added to this database role.</span></span>  
  
 <span data-ttu-id="d969b-112">有关使用 Windows Server App Fabric 的持久性存储安全性的详细信息，请参阅[App Fabric 中持久性存储的安全配置](https://go.microsoft.com/fwlink/?LinkId=201208)</span><span class="sxs-lookup"><span data-stu-id="d969b-112">For more information about security for persistence stores with Windows Server App Fabric, see [Security Configuration for Persistence Stores in App Fabric](https://go.microsoft.com/fwlink/?LinkId=201208)</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="d969b-113">有权访问自己存在实例存储区中的实例数据的客户端对同一实例存储区中所有其他实例也具有访问权限。</span><span class="sxs-lookup"><span data-stu-id="d969b-113">A client that has access to its own instance data in the instance store has access to all other instances in the same instance store.</span></span> <span data-ttu-id="d969b-114">实例存储区不支持在实例级别指定安全权限。</span><span class="sxs-lookup"><span data-stu-id="d969b-114">The instance store does not support specifying security permissions at the instance level.</span></span> <span data-ttu-id="d969b-115">您应创建单独的实例存储区并映射不同的组/用户，使他们有权访问的存储区有所不同。</span><span class="sxs-lookup"><span data-stu-id="d969b-115">You should create separate instance stores and map different groups/users to have access to different stores.</span></span>

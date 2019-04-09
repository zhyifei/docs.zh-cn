---
title: 自定义操作：概述
ms.date: 03/30/2017
ms.assetid: a3546296-1443-4b88-aa6e-d41011041ba7
ms.openlocfilehash: 29fb75271b7bc324d462078e94e4a28534986fba
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075972"
---
# <a name="customizing-operations-overview"></a><span data-ttu-id="ddf7b-102">自定义操作：概述</span><span class="sxs-lookup"><span data-stu-id="ddf7b-102">Customizing Operations: Overview</span></span>
<span data-ttu-id="ddf7b-103">默认情况下，[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 会根据映射生成动态 SQL 来执行插入、更新和删除操作。</span><span class="sxs-lookup"><span data-stu-id="ddf7b-103">By default, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates dynamic SQL for insert, update, and delete operations based on mapping.</span></span> <span data-ttu-id="ddf7b-104">但在实践中，您通常需要添加您自己的业务逻辑来提供安全、验证等。</span><span class="sxs-lookup"><span data-stu-id="ddf7b-104">However, in practice you typically want to add your own business logic to provide for security, validation, and so forth.</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="ddf7b-105">自定义这些操作的方法包括以下内容。</span><span class="sxs-lookup"><span data-stu-id="ddf7b-105">techniques for customizing these operations include the following.</span></span>  
  
## <a name="loading-options"></a><span data-ttu-id="ddf7b-106">加载选项</span><span class="sxs-lookup"><span data-stu-id="ddf7b-106">Loading Options</span></span>  
 <span data-ttu-id="ddf7b-107">在您的查询中，您可以控制在连接到数据库时检索多少与您的主目标相关的数据。</span><span class="sxs-lookup"><span data-stu-id="ddf7b-107">In your queries, you can control how much data related to your main target is retrieved when you connect to the database.</span></span> <span data-ttu-id="ddf7b-108">此功能主要通过使用 <xref:System.Data.Linq.DataLoadOptions> 实现。</span><span class="sxs-lookup"><span data-stu-id="ddf7b-108">This functionality is implemented largely by using <xref:System.Data.Linq.DataLoadOptions>.</span></span> <span data-ttu-id="ddf7b-109">有关详细信息，请参阅[推迟加载与即时加载](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md)。</span><span class="sxs-lookup"><span data-stu-id="ddf7b-109">For more information, see [Deferred versus Immediate Loading](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).</span></span>  
  
## <a name="partial-methods"></a><span data-ttu-id="ddf7b-110">分部方法</span><span class="sxs-lookup"><span data-stu-id="ddf7b-110">Partial Methods</span></span>  
 <span data-ttu-id="ddf7b-111">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 在其默认映射中提供了分部方法，以帮助您实现自己的业务逻辑。</span><span class="sxs-lookup"><span data-stu-id="ddf7b-111">In its default mapping, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provides partial methods to help you implement your business logic.</span></span> <span data-ttu-id="ddf7b-112">有关详细信息，请参阅[添加业务逻辑通过使用分部方法](../../../../../../docs/framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="ddf7b-112">For more information, see [Adding Business Logic By Using Partial Methods](../../../../../../docs/framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md).</span></span>  
  
## <a name="stored-procedures-and-user-defined-functions"></a><span data-ttu-id="ddf7b-113">存储过程和用户定义的函数</span><span class="sxs-lookup"><span data-stu-id="ddf7b-113">Stored Procedures and User-Defined Functions</span></span>  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="ddf7b-114">支持使用存储的过程和用户定义的函数。</span><span class="sxs-lookup"><span data-stu-id="ddf7b-114">supports the use of stored procedures and user-defined functions.</span></span> <span data-ttu-id="ddf7b-115">存储过程经常用来自定义操作。</span><span class="sxs-lookup"><span data-stu-id="ddf7b-115">Stored procedures are frequently used to customize operations.</span></span> <span data-ttu-id="ddf7b-116">有关详细信息，请参阅[存储过程](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)。</span><span class="sxs-lookup"><span data-stu-id="ddf7b-116">For more information, see [Stored Procedures](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddf7b-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="ddf7b-117">See also</span></span>

- [<span data-ttu-id="ddf7b-118">自定义插入、更新和删除操作</span><span class="sxs-lookup"><span data-stu-id="ddf7b-118">Customizing Insert, Update, and Delete Operations</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)

---
title: 实例完成操作
ms.date: 03/30/2017
ms.assetid: 90cc99d2-9fef-42fd-bcbf-a56917993721
ms.openlocfilehash: 646015fbcdb7c734ae8584c7ca3979d64b81339f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33513196"
---
# <a name="instance-completion-action"></a><span data-ttu-id="a3779-102">实例完成操作</span><span class="sxs-lookup"><span data-stu-id="a3779-102">Instance Completion Action</span></span>
<span data-ttu-id="a3779-103">**实例完成操作**SQL 工作流实例存储的属性，可以指定是否删除数据和元数据的工作流实例是从持久性数据库在实例完成之后。</span><span class="sxs-lookup"><span data-stu-id="a3779-103">The **Instance Completion Action** property of the SQL Workflow Instance Store lets you specify whether the data and metadata of workflow instances is deleted from the persistence database after the instances are completed.</span></span> <span data-ttu-id="a3779-104">此属性允许的值为**DeleteAll**和**DeleteNothing**。</span><span class="sxs-lookup"><span data-stu-id="a3779-104">The allowed values for this property are **DeleteAll** and **DeleteNothing**.</span></span> <span data-ttu-id="a3779-105">以下列表对这两个选项进行了说明：</span><span class="sxs-lookup"><span data-stu-id="a3779-105">The following list describes these options:</span></span>  
  
-   <span data-ttu-id="a3779-106">**DeleteAll （默认值）。**</span><span class="sxs-lookup"><span data-stu-id="a3779-106">**DeleteAll (default).**</span></span> <span data-ttu-id="a3779-107">如果该属性的值设置为 DeleteAll，则在工作流实例完成之后会将从持久性数据库中删除该实例的数据和元数据。</span><span class="sxs-lookup"><span data-stu-id="a3779-107">If the value of the property is set to DeleteAll, the data and metadata of workflow instances is deleted from the persistence database after the instances are completed.</span></span>  
  
-   <span data-ttu-id="a3779-108">**DeleteNothing。**</span><span class="sxs-lookup"><span data-stu-id="a3779-108">**DeleteNothing.**</span></span> <span data-ttu-id="a3779-109">如果该属性的值设置为 DeleteNothing，则即使在工作流实例完成之后也会将该实例的数据和元数据保留在持久性数据库中。</span><span class="sxs-lookup"><span data-stu-id="a3779-109">If the value of the property is set to DeleteNothing, the data and metadata of workflow instances is kept in the persistence database even after the instances are completed.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="a3779-110">实例完成之后继续保留实例状态信息会导致持久性数据库增大。</span><span class="sxs-lookup"><span data-stu-id="a3779-110">Keeping instance state information after the instances are completed causes the persistence database to grow in size.</span></span> <span data-ttu-id="a3779-111">随着数据库的增大，持久性子系统执行数据库操作所花费的时间会越来越长，因此需要定期从持久性数据库中清除实例状态信息，以使服务在满足您的性能需求的级别执行。</span><span class="sxs-lookup"><span data-stu-id="a3779-111">As the size of the database grows the database operations that the persistence subsystem performs take longer, so you need to purge the instance state information from the persistence database periodically to have services perform at the level that satisfy your performance needs.</span></span>

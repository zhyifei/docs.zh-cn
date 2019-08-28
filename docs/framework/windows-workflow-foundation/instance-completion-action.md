---
title: 实例完成操作
ms.date: 03/30/2017
ms.assetid: 90cc99d2-9fef-42fd-bcbf-a56917993721
ms.openlocfilehash: 698ac0ed5a7cbd4f6a5623cf8d9b6fbea1128d0a
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2019
ms.locfileid: "70044332"
---
# <a name="instance-completion-action"></a><span data-ttu-id="245ce-102">实例完成操作</span><span class="sxs-lookup"><span data-stu-id="245ce-102">Instance Completion Action</span></span>

<span data-ttu-id="245ce-103">利用 SQL 工作流实例存储的 "**实例完成操作**" 属性, 您可以指定在实例完成之后是否从持久性数据库中删除工作流实例的数据和元数据。</span><span class="sxs-lookup"><span data-stu-id="245ce-103">The **Instance Completion Action** property of the SQL Workflow Instance Store lets you specify whether the data and metadata of workflow instances is deleted from the persistence database after the instances are completed.</span></span> <span data-ttu-id="245ce-104">此属性的允许值为**DeleteAll**和**DeleteNothing**。</span><span class="sxs-lookup"><span data-stu-id="245ce-104">The allowed values for this property are **DeleteAll** and **DeleteNothing**.</span></span> <span data-ttu-id="245ce-105">以下列表对这两个选项进行了说明：</span><span class="sxs-lookup"><span data-stu-id="245ce-105">The following list describes these options:</span></span>

- <span data-ttu-id="245ce-106">**DeleteAll (默认值)。**</span><span class="sxs-lookup"><span data-stu-id="245ce-106">**DeleteAll (default).**</span></span> <span data-ttu-id="245ce-107">如果该属性的值设置为 DeleteAll，则在工作流实例完成之后会将从持久性数据库中删除该实例的数据和元数据。</span><span class="sxs-lookup"><span data-stu-id="245ce-107">If the value of the property is set to DeleteAll, the data and metadata of workflow instances is deleted from the persistence database after the instances are completed.</span></span>

- <span data-ttu-id="245ce-108">**DeleteNothing.**</span><span class="sxs-lookup"><span data-stu-id="245ce-108">**DeleteNothing.**</span></span> <span data-ttu-id="245ce-109">如果该属性的值设置为 DeleteNothing，则即使在工作流实例完成之后也会将该实例的数据和元数据保留在持久性数据库中。</span><span class="sxs-lookup"><span data-stu-id="245ce-109">If the value of the property is set to DeleteNothing, the data and metadata of workflow instances is kept in the persistence database even after the instances are completed.</span></span>

  > [!CAUTION]
  > <span data-ttu-id="245ce-110">实例完成之后继续保留实例状态信息会导致持久性数据库增大。</span><span class="sxs-lookup"><span data-stu-id="245ce-110">Keeping instance state information after the instances are completed causes the persistence database to grow in size.</span></span> <span data-ttu-id="245ce-111">随着数据库的增大，持久性子系统执行数据库操作所花费的时间会越来越长，因此需要定期从持久性数据库中清除实例状态信息，以使服务在满足您的性能需求的级别执行。</span><span class="sxs-lookup"><span data-stu-id="245ce-111">As the size of the database grows the database operations that the persistence subsystem performs take longer, so you need to purge the instance state information from the persistence database periodically to have services perform at the level that satisfy your performance needs.</span></span>

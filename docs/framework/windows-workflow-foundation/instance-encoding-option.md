---
title: 实例编码选项
ms.date: 03/30/2017
ms.assetid: 89e4b029-4f68-438c-8117-9b21fe094ef4
ms.openlocfilehash: c4de7c45d899f45a7b5b71d563257d9accb8fdbb
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59315616"
---
# <a name="instance-encoding-option"></a><span data-ttu-id="8748b-102">实例编码选项</span><span class="sxs-lookup"><span data-stu-id="8748b-102">Instance Encoding Option</span></span>
<span data-ttu-id="8748b-103">**实例编码选项**SQL 工作流实例存储的属性，可以指定 SQL 持久性提供程序是否应压缩使用 GZip 算法之前保存的工作流实例状态信息到持久性数据库的信息。</span><span class="sxs-lookup"><span data-stu-id="8748b-103">The **Instance Encoding Option** property of the SQL Workflow Instance Store lets you specify whether the SQL persistence provider should compress the workflow instance state information using the GZip algorithm before saving the information into the persistence database.</span></span> <span data-ttu-id="8748b-104">此属性的允许的值包括：GZip 和 None。</span><span class="sxs-lookup"><span data-stu-id="8748b-104">The allowed values for this property are: GZip and None.</span></span> <span data-ttu-id="8748b-105">默认值为 None。</span><span class="sxs-lookup"><span data-stu-id="8748b-105">The default value is None.</span></span> <span data-ttu-id="8748b-106">以下列表对这两个选项进行了说明。</span><span class="sxs-lookup"><span data-stu-id="8748b-106">The following list describes these options.</span></span>  
  
1. <span data-ttu-id="8748b-107">**GZip**。</span><span class="sxs-lookup"><span data-stu-id="8748b-107">**GZip**.</span></span> <span data-ttu-id="8748b-108">在将状态信息持久保存到持久性数据库中之前，持久性提供程序使用 GZip 算法对该状态信息进行编码。</span><span class="sxs-lookup"><span data-stu-id="8748b-108">The persistence provider encodes the state information using the GZip algorithm before persisting the state information in the persistence database.</span></span>  
  
2. <span data-ttu-id="8748b-109">**无**。</span><span class="sxs-lookup"><span data-stu-id="8748b-109">**None**.</span></span> <span data-ttu-id="8748b-110">在将状态信息保存到持久性数据库中之前，持久性提供程序不会对该状态信息进行编码。</span><span class="sxs-lookup"><span data-stu-id="8748b-110">The persistence provider does not encode the state information before saving the information into the persistence database.</span></span>  
  
 <span data-ttu-id="8748b-111">使用 GZip 对工作流实例状态信息进行编码可减少 SQL 数据库中的内存消耗，并且还可减少网络消耗（如果数据库位于网络上的另一台计算机上，而不是位于运行工作流服务宿主的计算机上）。</span><span class="sxs-lookup"><span data-stu-id="8748b-111">Encoding workflow instance state information using the GZip reduces memory consumption in the SQL database and also reduces network consumption if the database resides on a different computer on the network from the computer on which the workflow service host is running.</span></span> <span data-ttu-id="8748b-112">一般指导原则是设置**实例编码选项**属性设置为**None**如果工作流实例状态很小。</span><span class="sxs-lookup"><span data-stu-id="8748b-112">A general guidance is to set the **Instance Encoding Option** property to **None** if the workflow instance state is small.</span></span>

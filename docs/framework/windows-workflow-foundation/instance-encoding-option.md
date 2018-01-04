---
title: "实例编码选项"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 89e4b029-4f68-438c-8117-9b21fe094ef4
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a7664eecb68ff9aec0f5e3e31aa08058700f0e92
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="instance-encoding-option"></a><span data-ttu-id="ebf8e-102">实例编码选项</span><span class="sxs-lookup"><span data-stu-id="ebf8e-102">Instance Encoding Option</span></span>
<span data-ttu-id="ebf8e-103">**实例编码选项**SQL 工作流实例存储的属性，可以指定 SQL 持久性提供程序是否应压缩使用 GZip 算法在保存前的工作流实例状态信息到持久性数据库的信息。</span><span class="sxs-lookup"><span data-stu-id="ebf8e-103">The **Instance Encoding Option** property of the SQL Workflow Instance Store lets you specify whether the SQL persistence provider should compress the workflow instance state information using the GZip algorithm before saving the information into the persistence database.</span></span> <span data-ttu-id="ebf8e-104">此属性的允许值为 GZip 和 None。</span><span class="sxs-lookup"><span data-stu-id="ebf8e-104">The allowed values for this property are: GZip and None.</span></span> <span data-ttu-id="ebf8e-105">默认值为 None。</span><span class="sxs-lookup"><span data-stu-id="ebf8e-105">The default value is None.</span></span> <span data-ttu-id="ebf8e-106">以下列表对这两个选项进行了说明。</span><span class="sxs-lookup"><span data-stu-id="ebf8e-106">The following list describes these options.</span></span>  
  
1.  <span data-ttu-id="ebf8e-107">**GZip**。</span><span class="sxs-lookup"><span data-stu-id="ebf8e-107">**GZip**.</span></span> <span data-ttu-id="ebf8e-108">在将状态信息持久保存到持久性数据库中之前，持久性提供程序使用 GZip 算法对该状态信息进行编码。</span><span class="sxs-lookup"><span data-stu-id="ebf8e-108">The persistence provider encodes the state information using the GZip algorithm before persisting the state information in the persistence database.</span></span>  
  
2.  <span data-ttu-id="ebf8e-109">**无**。</span><span class="sxs-lookup"><span data-stu-id="ebf8e-109">**None**.</span></span> <span data-ttu-id="ebf8e-110">在将状态信息保存到持久性数据库中之前，持久性提供程序不会对该状态信息进行编码。</span><span class="sxs-lookup"><span data-stu-id="ebf8e-110">The persistence provider does not encode the state information before saving the information into the persistence database.</span></span>  
  
 <span data-ttu-id="ebf8e-111">使用 GZip 对工作流实例状态信息进行编码可减少 SQL 数据库中的内存消耗，并且还可减少网络消耗（如果数据库位于网络上的另一台计算机上，而不是位于运行工作流服务主机的计算机上）。</span><span class="sxs-lookup"><span data-stu-id="ebf8e-111">Encoding workflow instance state information using the GZip reduces memory consumption in the SQL database and also reduces network consumption if the database resides on a different computer on the network from the computer on which the workflow service host is running.</span></span> <span data-ttu-id="ebf8e-112">一般原则是设置**实例编码选项**属性**无**如果工作流实例状态很小。</span><span class="sxs-lookup"><span data-stu-id="ebf8e-112">A general guidance is to set the **Instance Encoding Option** property to **None** if the workflow instance state is small.</span></span>

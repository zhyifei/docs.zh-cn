---
title: "可靠性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SQL Server [.NET Framework]
- managed code, reliability
- reliability [.NET Framework]
- writing reliable code
- code, reliability
ms.assetid: 294aa306-0afe-4cbe-b397-86ba9f1860f8
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bd13a09e66c865630b9db3210bbd95bab14cb214
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="reliability"></a><span data-ttu-id="8c08f-102">可靠性</span><span class="sxs-lookup"><span data-stu-id="8c08f-102">Reliability</span></span>
<span data-ttu-id="8c08f-103">在服务器环境（如 SQL Server）中执行的代码防止发生异步异常，这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="8c08f-103">It is important that code executing in server environments such as SQL Server protect against asynchronous exceptions.</span></span> <span data-ttu-id="8c08f-104">文本所讨论的可靠性并不是针对 SQL Server 而言，而是针对为在 .NET Framework 版本 2.0 环境中执行的任何主机编写可靠代码而言。</span><span class="sxs-lookup"><span data-stu-id="8c08f-104">Reliability, as discussed here, is not specific to SQL Server but to writing reliable code for any host executing in a .NET Framework version 2.0 environment.</span></span> <span data-ttu-id="8c08f-105">SQL Server 是第一个广泛使用版本 2.0 的新可靠性功能的服务，所以将其作为示例。</span><span class="sxs-lookup"><span data-stu-id="8c08f-105">However, SQL Server is the first service making extensive use of the new reliability features of version 2.0, so it is used as an example.</span></span>  
  
 <span data-ttu-id="8c08f-106">在 SQL Server 中运行的代码必须使用与其他服务器环境相比更严格的可靠性准则。</span><span class="sxs-lookup"><span data-stu-id="8c08f-106">Code running in SQL Server must deal with more stringent reliability guidelines than other server environments.</span></span> <span data-ttu-id="8c08f-107">这是因为 SQL Server 在资源消耗方面的稳定操作。</span><span class="sxs-lookup"><span data-stu-id="8c08f-107">This is due to SQL Server’s steady operation at the edge of resource consumption.</span></span>  <span data-ttu-id="8c08f-108"><xref:System.OutOfMemoryException> 和 <xref:System.Threading.ThreadAbortException> 异常在 SQL Server 环境中比较常见。</span><span class="sxs-lookup"><span data-stu-id="8c08f-108"><xref:System.OutOfMemoryException> and <xref:System.Threading.ThreadAbortException> exceptions are not uncommon in the SQL Server environment.</span></span> <span data-ttu-id="8c08f-109">这些准则通常较少强调可靠性，更多专注于允许完全信任的托管代码面对 <xref:System.AppDomain> 级别的回收温和地失败，这是服务器维持一致性和可用性的主要方法。</span><span class="sxs-lookup"><span data-stu-id="8c08f-109">These guidelines in general are focused less on reliability and more on allowing fully trusted managed code to fail gracefully in the face of <xref:System.AppDomain>-level recycling, which is the primary way the server maintains consistency and availability.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8c08f-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="8c08f-110">In This Section</span></span>  
 [<span data-ttu-id="8c08f-111">SQL Server 编程和主机保护特性</span><span class="sxs-lookup"><span data-stu-id="8c08f-111">SQL Server Programming and Host Protection Attributes</span></span>](../../../docs/framework/performance/sql-server-programming-and-host-protection-attributes.md)  
 <span data-ttu-id="8c08f-112">介绍 SQL Server 如何使用 <xref:System.Security.Permissions.HostProtectionAttribute> 属性限制托管代码的执行。</span><span class="sxs-lookup"><span data-stu-id="8c08f-112">Describes how the <xref:System.Security.Permissions.HostProtectionAttribute> attribute is used by SQL Server to restrict the execution of managed code.</span></span>  
  
 [<span data-ttu-id="8c08f-113">可靠性最佳做法</span><span class="sxs-lookup"><span data-stu-id="8c08f-113">Reliability Best Practices</span></span>](../../../docs/framework/performance/reliability-best-practices.md)  
 <span data-ttu-id="8c08f-114">提供用于编写符合可靠性要求的代码的准则。</span><span class="sxs-lookup"><span data-stu-id="8c08f-114">Provides guidelines for writing code that meets reliability requirements.</span></span>  
  
 <span data-ttu-id="8c08f-115">[Constrained Execution Regions](../../../docs/framework/performance/constrained-execution-regions.md)（受约束的执行区域）</span><span class="sxs-lookup"><span data-stu-id="8c08f-115">[Constrained Execution Regions](../../../docs/framework/performance/constrained-execution-regions.md)</span></span>  
 <span data-ttu-id="8c08f-116">介绍受约束的执行区域 (CER) 的功能和行为。</span><span class="sxs-lookup"><span data-stu-id="8c08f-116">Describes the function and behavior of constrained execution regions (CERs).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="8c08f-117">参考</span><span class="sxs-lookup"><span data-stu-id="8c08f-117">Reference</span></span>  
 <xref:System.Security.Permissions.HostProtectionAttribute>  
  
 <xref:System.Security.Permissions.HostProtectionResource>

---
title: "部分信任"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 489b1587-9909-4d0e-8c1a-5e83c8f8292b
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ac76f092d5583519220d2d1b7a8d6d1bbb665632
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="partial-trust"></a><span data-ttu-id="3a264-102">部分信任</span><span class="sxs-lookup"><span data-stu-id="3a264-102">Partial Trust</span></span>
<span data-ttu-id="3a264-103">从 [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] 开始，部分受信任的调用方可以访问在 <xref:System.ServiceModel>, <xref:System.Runtime.Serialization> 和 <xref:System.ServiceModel.Web> 中实现的公共类型和方法。</span><span class="sxs-lookup"><span data-stu-id="3a264-103">Starting with the [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)], partially trusted callers can access public types and methods implemented in <xref:System.ServiceModel>, <xref:System.Runtime.Serialization>, and <xref:System.ServiceModel.Web>.</span></span> <span data-ttu-id="3a264-104">本节描述了在部分受信任的应用程序中使用 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 的支持方案，以及可供通过简化的代码访问安全性 (CAS) 权限来运行的应用程序使用的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 功能的有限子集。</span><span class="sxs-lookup"><span data-stu-id="3a264-104">This section describes supported scenarios for using [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] within a partially trusted application as well as the limited subset of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] functionality available to applications running with reduced code access security (CAS) permissions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3a264-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="3a264-105">In This Section</span></span>  
 [<span data-ttu-id="3a264-106">支持的部署方案</span><span class="sxs-lookup"><span data-stu-id="3a264-106">Supported Deployment Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/supported-deployment-scenarios.md)  
 <span data-ttu-id="3a264-107">描述用于运行 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 的主要部分信任方案。</span><span class="sxs-lookup"><span data-stu-id="3a264-107">Describes the main partial trust scenarios for running [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="3a264-108">部分信任功能兼容性</span><span class="sxs-lookup"><span data-stu-id="3a264-108">Partial Trust Feature Compatibility</span></span>](../../../../docs/framework/wcf/feature-details/partial-trust-feature-compatibility.md)  
 <span data-ttu-id="3a264-109">描述不能用于部分信任的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 功能。</span><span class="sxs-lookup"><span data-stu-id="3a264-109">Describes the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] features that cannot be used with partial trust.</span></span>  
  
 [<span data-ttu-id="3a264-110">部分信任最佳做法</span><span class="sxs-lookup"><span data-stu-id="3a264-110">Partial Trust Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/partial-trust-best-practices.md)  
 <span data-ttu-id="3a264-111">包含在部分受信任的应用程序中使用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="3a264-111">Contains best practices for using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in partially trusted applications.</span></span>

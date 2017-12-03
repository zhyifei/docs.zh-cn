---
title: ServiceTimeoutsBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4412525d-a3cc-4eae-b3e8-a50ce766d09d
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a65104a6fe76c22fca308091cc02e9496912129c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="servicetimeoutsbehavior"></a><span data-ttu-id="9e11d-102">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="9e11d-102">ServiceTimeoutsBehavior</span></span>
<span data-ttu-id="9e11d-103">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="9e11d-103">ServiceTimeoutsBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e11d-104">语法</span><span class="sxs-lookup"><span data-stu-id="9e11d-104">Syntax</span></span>  
  
```  
class ServiceTimeoutsBehavior : Behavior  
{  
  datetime TransactionTimeout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="9e11d-105">方法</span><span class="sxs-lookup"><span data-stu-id="9e11d-105">Methods</span></span>  
 <span data-ttu-id="9e11d-106">ServiceTimeoutsBehavior 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="9e11d-106">The ServiceTimeoutsBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9e11d-107">属性</span><span class="sxs-lookup"><span data-stu-id="9e11d-107">Properties</span></span>  
 <span data-ttu-id="9e11d-108">ServiceTimeoutsBehavior 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="9e11d-108">The ServiceTimeoutsBehavior class has the following property:</span></span>  
  
### <a name="transactiontimeout"></a><span data-ttu-id="9e11d-109">TransactionTimeout</span><span class="sxs-lookup"><span data-stu-id="9e11d-109">TransactionTimeout</span></span>  
 <span data-ttu-id="9e11d-110">数据类型：DateTime</span><span class="sxs-lookup"><span data-stu-id="9e11d-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="9e11d-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="9e11d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9e11d-112">事务必须在此期间完成的时间段。</span><span class="sxs-lookup"><span data-stu-id="9e11d-112">The period within which a transaction must complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e11d-113">要求</span><span class="sxs-lookup"><span data-stu-id="9e11d-113">Requirements</span></span>  
  
|<span data-ttu-id="9e11d-114">MOF</span><span class="sxs-lookup"><span data-stu-id="9e11d-114">MOF</span></span>|<span data-ttu-id="9e11d-115">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="9e11d-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9e11d-116">命名空间</span><span class="sxs-lookup"><span data-stu-id="9e11d-116">Namespace</span></span>|<span data-ttu-id="9e11d-117">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="9e11d-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9e11d-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9e11d-118">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>

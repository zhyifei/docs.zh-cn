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
ms.workload: dotnet
ms.openlocfilehash: 4828b9a6b20c11f1f234f0ef521686164c7f8c66
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="servicetimeoutsbehavior"></a><span data-ttu-id="ffb80-102">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="ffb80-102">ServiceTimeoutsBehavior</span></span>
<span data-ttu-id="ffb80-103">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="ffb80-103">ServiceTimeoutsBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffb80-104">语法</span><span class="sxs-lookup"><span data-stu-id="ffb80-104">Syntax</span></span>  
  
```  
class ServiceTimeoutsBehavior : Behavior  
{  
  datetime TransactionTimeout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ffb80-105">方法</span><span class="sxs-lookup"><span data-stu-id="ffb80-105">Methods</span></span>  
 <span data-ttu-id="ffb80-106">ServiceTimeoutsBehavior 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="ffb80-106">The ServiceTimeoutsBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ffb80-107">属性</span><span class="sxs-lookup"><span data-stu-id="ffb80-107">Properties</span></span>  
 <span data-ttu-id="ffb80-108">ServiceTimeoutsBehavior 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="ffb80-108">The ServiceTimeoutsBehavior class has the following property:</span></span>  
  
### <a name="transactiontimeout"></a><span data-ttu-id="ffb80-109">TransactionTimeout</span><span class="sxs-lookup"><span data-stu-id="ffb80-109">TransactionTimeout</span></span>  
 <span data-ttu-id="ffb80-110">数据类型：DateTime</span><span class="sxs-lookup"><span data-stu-id="ffb80-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="ffb80-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ffb80-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ffb80-112">事务必须在此期间完成的时间段。</span><span class="sxs-lookup"><span data-stu-id="ffb80-112">The period within which a transaction must complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffb80-113">惠?</span><span class="sxs-lookup"><span data-stu-id="ffb80-113">Requirements</span></span>  
  
|<span data-ttu-id="ffb80-114">MOF</span><span class="sxs-lookup"><span data-stu-id="ffb80-114">MOF</span></span>|<span data-ttu-id="ffb80-115">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="ffb80-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ffb80-116">命名空间</span><span class="sxs-lookup"><span data-stu-id="ffb80-116">Namespace</span></span>|<span data-ttu-id="ffb80-117">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="ffb80-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ffb80-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="ffb80-118">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>

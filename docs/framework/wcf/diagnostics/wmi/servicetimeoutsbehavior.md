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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d4b597dbdd8dfea1cab35c717f416d91677c5987
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="servicetimeoutsbehavior"></a><span data-ttu-id="041fb-102">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="041fb-102">ServiceTimeoutsBehavior</span></span>
<span data-ttu-id="041fb-103">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="041fb-103">ServiceTimeoutsBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="041fb-104">语法</span><span class="sxs-lookup"><span data-stu-id="041fb-104">Syntax</span></span>  
  
```  
class ServiceTimeoutsBehavior : Behavior  
{  
  datetime TransactionTimeout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="041fb-105">方法</span><span class="sxs-lookup"><span data-stu-id="041fb-105">Methods</span></span>  
 <span data-ttu-id="041fb-106">ServiceTimeoutsBehavior 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="041fb-106">The ServiceTimeoutsBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="041fb-107">属性</span><span class="sxs-lookup"><span data-stu-id="041fb-107">Properties</span></span>  
 <span data-ttu-id="041fb-108">ServiceTimeoutsBehavior 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="041fb-108">The ServiceTimeoutsBehavior class has the following property:</span></span>  
  
### <a name="transactiontimeout"></a><span data-ttu-id="041fb-109">TransactionTimeout</span><span class="sxs-lookup"><span data-stu-id="041fb-109">TransactionTimeout</span></span>  
 <span data-ttu-id="041fb-110">数据类型：DateTime</span><span class="sxs-lookup"><span data-stu-id="041fb-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="041fb-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="041fb-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="041fb-112">事务必须在此期间完成的时间段。</span><span class="sxs-lookup"><span data-stu-id="041fb-112">The period within which a transaction must complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="041fb-113">要求</span><span class="sxs-lookup"><span data-stu-id="041fb-113">Requirements</span></span>  
  
|<span data-ttu-id="041fb-114">MOF</span><span class="sxs-lookup"><span data-stu-id="041fb-114">MOF</span></span>|<span data-ttu-id="041fb-115">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="041fb-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="041fb-116">命名空间</span><span class="sxs-lookup"><span data-stu-id="041fb-116">Namespace</span></span>|<span data-ttu-id="041fb-117">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="041fb-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="041fb-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="041fb-118">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>

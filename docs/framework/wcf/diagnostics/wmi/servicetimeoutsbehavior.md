---
title: ServiceTimeoutsBehavior
ms.date: 03/30/2017
ms.assetid: 4412525d-a3cc-4eae-b3e8-a50ce766d09d
ms.openlocfilehash: 1a5284915de739e95325234318842a4d1ab607be
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2018
ms.locfileid: "50196960"
---
# <a name="servicetimeoutsbehavior"></a><span data-ttu-id="6a2ae-102">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="6a2ae-102">ServiceTimeoutsBehavior</span></span>
<span data-ttu-id="6a2ae-103">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="6a2ae-103">ServiceTimeoutsBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a2ae-104">语法</span><span class="sxs-lookup"><span data-stu-id="6a2ae-104">Syntax</span></span>  
  
```csharp
class ServiceTimeoutsBehavior : Behavior  
{  
  datetime TransactionTimeout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="6a2ae-105">方法</span><span class="sxs-lookup"><span data-stu-id="6a2ae-105">Methods</span></span>  
 <span data-ttu-id="6a2ae-106">ServiceTimeoutsBehavior 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="6a2ae-106">The ServiceTimeoutsBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="6a2ae-107">属性</span><span class="sxs-lookup"><span data-stu-id="6a2ae-107">Properties</span></span>  
 <span data-ttu-id="6a2ae-108">ServiceTimeoutsBehavior 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="6a2ae-108">The ServiceTimeoutsBehavior class has the following property:</span></span>  
  
### <a name="transactiontimeout"></a><span data-ttu-id="6a2ae-109">TransactionTimeout</span><span class="sxs-lookup"><span data-stu-id="6a2ae-109">TransactionTimeout</span></span>  
 <span data-ttu-id="6a2ae-110">数据类型：DateTime</span><span class="sxs-lookup"><span data-stu-id="6a2ae-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="6a2ae-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="6a2ae-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="6a2ae-112">事务必须在此期间完成的时间段。</span><span class="sxs-lookup"><span data-stu-id="6a2ae-112">The period within which a transaction must complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a2ae-113">要求</span><span class="sxs-lookup"><span data-stu-id="6a2ae-113">Requirements</span></span>  
  
|<span data-ttu-id="6a2ae-114">MOF</span><span class="sxs-lookup"><span data-stu-id="6a2ae-114">MOF</span></span>|<span data-ttu-id="6a2ae-115">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="6a2ae-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="6a2ae-116">命名空间</span><span class="sxs-lookup"><span data-stu-id="6a2ae-116">Namespace</span></span>|<span data-ttu-id="6a2ae-117">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="6a2ae-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6a2ae-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="6a2ae-118">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>

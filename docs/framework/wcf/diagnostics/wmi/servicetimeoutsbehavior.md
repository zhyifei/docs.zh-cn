---
title: ServiceTimeoutsBehavior
ms.date: 03/30/2017
ms.assetid: 4412525d-a3cc-4eae-b3e8-a50ce766d09d
ms.openlocfilehash: 58e872f2b15776d65bccdcc47c353ce566cd9d2f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59116007"
---
# <a name="servicetimeoutsbehavior"></a><span data-ttu-id="ee921-102">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="ee921-102">ServiceTimeoutsBehavior</span></span>
<span data-ttu-id="ee921-103">ServiceTimeoutsBehavior</span><span class="sxs-lookup"><span data-stu-id="ee921-103">ServiceTimeoutsBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee921-104">语法</span><span class="sxs-lookup"><span data-stu-id="ee921-104">Syntax</span></span>  
  
```csharp
class ServiceTimeoutsBehavior : Behavior  
{  
  datetime TransactionTimeout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ee921-105">方法</span><span class="sxs-lookup"><span data-stu-id="ee921-105">Methods</span></span>  
 <span data-ttu-id="ee921-106">ServiceTimeoutsBehavior 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="ee921-106">The ServiceTimeoutsBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ee921-107">属性</span><span class="sxs-lookup"><span data-stu-id="ee921-107">Properties</span></span>  
 <span data-ttu-id="ee921-108">ServiceTimeoutsBehavior 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="ee921-108">The ServiceTimeoutsBehavior class has the following property:</span></span>  
  
### <a name="transactiontimeout"></a><span data-ttu-id="ee921-109">TransactionTimeout</span><span class="sxs-lookup"><span data-stu-id="ee921-109">TransactionTimeout</span></span>  
 <span data-ttu-id="ee921-110">数据类型：DateTime</span><span class="sxs-lookup"><span data-stu-id="ee921-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="ee921-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ee921-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ee921-112">事务必须在此期间完成的时间段。</span><span class="sxs-lookup"><span data-stu-id="ee921-112">The period within which a transaction must complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee921-113">要求</span><span class="sxs-lookup"><span data-stu-id="ee921-113">Requirements</span></span>  
  
|<span data-ttu-id="ee921-114">MOF</span><span class="sxs-lookup"><span data-stu-id="ee921-114">MOF</span></span>|<span data-ttu-id="ee921-115">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="ee921-115">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ee921-116">命名空间</span><span class="sxs-lookup"><span data-stu-id="ee921-116">Namespace</span></span>|<span data-ttu-id="ee921-117">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="ee921-117">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ee921-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="ee921-118">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>

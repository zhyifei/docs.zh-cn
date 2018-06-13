---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: 480670f19407321eb0928d07752936b2ece1f7e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33484183"
---
# <a name="activitytransfer"></a><span data-ttu-id="553f6-102">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="553f6-102">ActivityTransfer</span></span>
<span data-ttu-id="553f6-103">活动传输事件</span><span class="sxs-lookup"><span data-stu-id="553f6-103">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="553f6-104">语法</span><span class="sxs-lookup"><span data-stu-id="553f6-104">Syntax</span></span>  
  
```  
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="553f6-105">方法</span><span class="sxs-lookup"><span data-stu-id="553f6-105">Methods</span></span>  
 <span data-ttu-id="553f6-106">ActivityTransfer 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="553f6-106">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="553f6-107">属性</span><span class="sxs-lookup"><span data-stu-id="553f6-107">Properties</span></span>  
 <span data-ttu-id="553f6-108">ActivityTransfer 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="553f6-108">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="553f6-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="553f6-109">ActivityID</span></span>  
  
-   <span data-ttu-id="553f6-110">数据类型：object</span><span class="sxs-lookup"><span data-stu-id="553f6-110">Data type: object</span></span>  
    <span data-ttu-id="553f6-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="553f6-111">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="553f6-112">活动 ID</span><span class="sxs-lookup"><span data-stu-id="553f6-112">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="553f6-113">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="553f6-113">RelatedActivityID</span></span>  
  
-   <span data-ttu-id="553f6-114">数据类型：object</span><span class="sxs-lookup"><span data-stu-id="553f6-114">Data type: object</span></span>  
    <span data-ttu-id="553f6-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="553f6-115">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="553f6-116">相关活动 ID</span><span class="sxs-lookup"><span data-stu-id="553f6-116">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="553f6-117">要求</span><span class="sxs-lookup"><span data-stu-id="553f6-117">Requirements</span></span>  
  
|<span data-ttu-id="553f6-118">MOF</span><span class="sxs-lookup"><span data-stu-id="553f6-118">MOF</span></span>|<span data-ttu-id="553f6-119">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="553f6-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="553f6-120">命名空间</span><span class="sxs-lookup"><span data-stu-id="553f6-120">Namespace</span></span>|<span data-ttu-id="553f6-121">已在 root\ServiceModel 中定义。</span><span class="sxs-lookup"><span data-stu-id="553f6-121">Defined in root\ServiceModel.</span></span>|

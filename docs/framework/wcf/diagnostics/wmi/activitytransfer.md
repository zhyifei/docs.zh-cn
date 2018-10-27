---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: 936e870c1ec991e2e33acf8a08ccc93975989679
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/25/2018
ms.locfileid: "50034413"
---
# <a name="activitytransfer"></a><span data-ttu-id="67821-102">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="67821-102">ActivityTransfer</span></span>
<span data-ttu-id="67821-103">活动传输事件</span><span class="sxs-lookup"><span data-stu-id="67821-103">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67821-104">语法</span><span class="sxs-lookup"><span data-stu-id="67821-104">Syntax</span></span>  
  
```csharp
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="67821-105">方法</span><span class="sxs-lookup"><span data-stu-id="67821-105">Methods</span></span>  
 <span data-ttu-id="67821-106">ActivityTransfer 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="67821-106">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="67821-107">属性</span><span class="sxs-lookup"><span data-stu-id="67821-107">Properties</span></span>  
 <span data-ttu-id="67821-108">ActivityTransfer 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="67821-108">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="67821-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="67821-109">ActivityID</span></span>  
  
-   <span data-ttu-id="67821-110">数据类型：object</span><span class="sxs-lookup"><span data-stu-id="67821-110">Data type: object</span></span>  
    <span data-ttu-id="67821-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="67821-111">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="67821-112">活动 ID</span><span class="sxs-lookup"><span data-stu-id="67821-112">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="67821-113">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="67821-113">RelatedActivityID</span></span>  
  
-   <span data-ttu-id="67821-114">数据类型：object</span><span class="sxs-lookup"><span data-stu-id="67821-114">Data type: object</span></span>  
    <span data-ttu-id="67821-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="67821-115">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="67821-116">相关活动 ID</span><span class="sxs-lookup"><span data-stu-id="67821-116">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67821-117">要求</span><span class="sxs-lookup"><span data-stu-id="67821-117">Requirements</span></span>  
  
|<span data-ttu-id="67821-118">MOF</span><span class="sxs-lookup"><span data-stu-id="67821-118">MOF</span></span>|<span data-ttu-id="67821-119">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="67821-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="67821-120">命名空间</span><span class="sxs-lookup"><span data-stu-id="67821-120">Namespace</span></span>|<span data-ttu-id="67821-121">已在 root\ServiceModel 中定义。</span><span class="sxs-lookup"><span data-stu-id="67821-121">Defined in root\ServiceModel.</span></span>|

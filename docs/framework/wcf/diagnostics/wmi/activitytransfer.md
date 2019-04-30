---
title: ActivityTransfer
ms.date: 03/30/2017
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
ms.openlocfilehash: 936e870c1ec991e2e33acf8a08ccc93975989679
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61964289"
---
# <a name="activitytransfer"></a><span data-ttu-id="1275c-102">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="1275c-102">ActivityTransfer</span></span>
<span data-ttu-id="1275c-103">活动传输事件</span><span class="sxs-lookup"><span data-stu-id="1275c-103">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1275c-104">语法</span><span class="sxs-lookup"><span data-stu-id="1275c-104">Syntax</span></span>  
  
```csharp
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="1275c-105">方法</span><span class="sxs-lookup"><span data-stu-id="1275c-105">Methods</span></span>  
 <span data-ttu-id="1275c-106">ActivityTransfer 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="1275c-106">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1275c-107">属性</span><span class="sxs-lookup"><span data-stu-id="1275c-107">Properties</span></span>  
 <span data-ttu-id="1275c-108">ActivityTransfer 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="1275c-108">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="1275c-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="1275c-109">ActivityID</span></span>  
  
- <span data-ttu-id="1275c-110">数据类型：object</span><span class="sxs-lookup"><span data-stu-id="1275c-110">Data type: object</span></span>  
    <span data-ttu-id="1275c-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="1275c-111">Access type: Read-only</span></span>  
  
- <span data-ttu-id="1275c-112">活动 ID</span><span class="sxs-lookup"><span data-stu-id="1275c-112">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="1275c-113">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="1275c-113">RelatedActivityID</span></span>  
  
- <span data-ttu-id="1275c-114">数据类型：object</span><span class="sxs-lookup"><span data-stu-id="1275c-114">Data type: object</span></span>  
    <span data-ttu-id="1275c-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="1275c-115">Access type: Read-only</span></span>  
  
- <span data-ttu-id="1275c-116">相关活动 ID</span><span class="sxs-lookup"><span data-stu-id="1275c-116">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1275c-117">要求</span><span class="sxs-lookup"><span data-stu-id="1275c-117">Requirements</span></span>  
  
|<span data-ttu-id="1275c-118">MOF</span><span class="sxs-lookup"><span data-stu-id="1275c-118">MOF</span></span>|<span data-ttu-id="1275c-119">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="1275c-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="1275c-120">命名空间</span><span class="sxs-lookup"><span data-stu-id="1275c-120">Namespace</span></span>|<span data-ttu-id="1275c-121">已在 root\ServiceModel 中定义。</span><span class="sxs-lookup"><span data-stu-id="1275c-121">Defined in root\ServiceModel.</span></span>|

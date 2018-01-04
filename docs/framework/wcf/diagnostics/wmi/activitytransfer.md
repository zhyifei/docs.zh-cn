---
title: ActivityTransfer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc40ef17-2a92-4ce2-853c-6ba8e5d571f3
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7f3db50a32fabc117c79eef5ac086a7798f86ed3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="activitytransfer"></a><span data-ttu-id="a5b62-102">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="a5b62-102">ActivityTransfer</span></span>
<span data-ttu-id="a5b62-103">活动传输事件</span><span class="sxs-lookup"><span data-stu-id="a5b62-103">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5b62-104">语法</span><span class="sxs-lookup"><span data-stu-id="a5b62-104">Syntax</span></span>  
  
```  
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="a5b62-105">方法</span><span class="sxs-lookup"><span data-stu-id="a5b62-105">Methods</span></span>  
 <span data-ttu-id="a5b62-106">ActivityTransfer 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="a5b62-106">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a5b62-107">属性</span><span class="sxs-lookup"><span data-stu-id="a5b62-107">Properties</span></span>  
 <span data-ttu-id="a5b62-108">ActivityTransfer 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="a5b62-108">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="a5b62-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="a5b62-109">ActivityID</span></span>  
  
-   <span data-ttu-id="a5b62-110">数据类型：object</span><span class="sxs-lookup"><span data-stu-id="a5b62-110">Data type: object</span></span>  
    <span data-ttu-id="a5b62-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="a5b62-111">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="a5b62-112">活动 ID</span><span class="sxs-lookup"><span data-stu-id="a5b62-112">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="a5b62-113">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="a5b62-113">RelatedActivityID</span></span>  
  
-   <span data-ttu-id="a5b62-114">数据类型：object</span><span class="sxs-lookup"><span data-stu-id="a5b62-114">Data type: object</span></span>  
    <span data-ttu-id="a5b62-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="a5b62-115">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="a5b62-116">相关活动 ID</span><span class="sxs-lookup"><span data-stu-id="a5b62-116">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5b62-117">要求</span><span class="sxs-lookup"><span data-stu-id="a5b62-117">Requirements</span></span>  
  
|<span data-ttu-id="a5b62-118">MOF</span><span class="sxs-lookup"><span data-stu-id="a5b62-118">MOF</span></span>|<span data-ttu-id="a5b62-119">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="a5b62-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a5b62-120">命名空间</span><span class="sxs-lookup"><span data-stu-id="a5b62-120">Namespace</span></span>|<span data-ttu-id="a5b62-121">已在 root\ServiceModel 中定义。</span><span class="sxs-lookup"><span data-stu-id="a5b62-121">Defined in root\ServiceModel.</span></span>|

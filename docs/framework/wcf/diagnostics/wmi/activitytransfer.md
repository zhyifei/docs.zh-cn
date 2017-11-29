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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: acbc346da940caf933868a03295744132bda4733
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="activitytransfer"></a><span data-ttu-id="6a68a-102">ActivityTransfer</span><span class="sxs-lookup"><span data-stu-id="6a68a-102">ActivityTransfer</span></span>
<span data-ttu-id="6a68a-103">活动传输事件</span><span class="sxs-lookup"><span data-stu-id="6a68a-103">Activity Transfer Event</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a68a-104">语法</span><span class="sxs-lookup"><span data-stu-id="6a68a-104">Syntax</span></span>  
  
```  
class ActivityTransfer : WSAT_TraceEvent  
{  
  object ActivityID;  
  object RelatedActivityID;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="6a68a-105">方法</span><span class="sxs-lookup"><span data-stu-id="6a68a-105">Methods</span></span>  
 <span data-ttu-id="6a68a-106">ActivityTransfer 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="6a68a-106">The ActivityTransfer class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="6a68a-107">属性</span><span class="sxs-lookup"><span data-stu-id="6a68a-107">Properties</span></span>  
 <span data-ttu-id="6a68a-108">ActivityTransfer 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="6a68a-108">The ActivityTransfer class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="6a68a-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="6a68a-109">ActivityID</span></span>  
  
-   <span data-ttu-id="6a68a-110">数据类型：object</span><span class="sxs-lookup"><span data-stu-id="6a68a-110">Data type: object</span></span>  
    <span data-ttu-id="6a68a-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="6a68a-111">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="6a68a-112">活动 ID</span><span class="sxs-lookup"><span data-stu-id="6a68a-112">Activity ID</span></span>  
  
### <a name="relatedactivityid"></a><span data-ttu-id="6a68a-113">RelatedActivityID</span><span class="sxs-lookup"><span data-stu-id="6a68a-113">RelatedActivityID</span></span>  
  
-   <span data-ttu-id="6a68a-114">数据类型：object</span><span class="sxs-lookup"><span data-stu-id="6a68a-114">Data type: object</span></span>  
    <span data-ttu-id="6a68a-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="6a68a-115">Access type: Read-only</span></span>  
  
-   <span data-ttu-id="6a68a-116">相关活动 ID</span><span class="sxs-lookup"><span data-stu-id="6a68a-116">Related Activity ID</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a68a-117">要求</span><span class="sxs-lookup"><span data-stu-id="6a68a-117">Requirements</span></span>  
  
|<span data-ttu-id="6a68a-118">MOF</span><span class="sxs-lookup"><span data-stu-id="6a68a-118">MOF</span></span>|<span data-ttu-id="6a68a-119">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="6a68a-119">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="6a68a-120">命名空间</span><span class="sxs-lookup"><span data-stu-id="6a68a-120">Namespace</span></span>|<span data-ttu-id="6a68a-121">已在 root\ServiceModel 中定义。</span><span class="sxs-lookup"><span data-stu-id="6a68a-121">Defined in root\ServiceModel.</span></span>|

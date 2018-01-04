---
title: WSAT_TraceRecord
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d24f74d4086a5499d3bfd4ef6183d377528acc21
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="wsattracerecord"></a><span data-ttu-id="e0ea2-102">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="e0ea2-102">WSAT_TraceRecord</span></span>
<span data-ttu-id="e0ea2-103">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="e0ea2-103">WSAT_TraceRecord</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0ea2-104">语法</span><span class="sxs-lookup"><span data-stu-id="e0ea2-104">Syntax</span></span>  
  
```  
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e0ea2-105">方法</span><span class="sxs-lookup"><span data-stu-id="e0ea2-105">Methods</span></span>  
 <span data-ttu-id="e0ea2-106">WSAT_TraceRecord 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="e0ea2-106">The WSAT_TraceRecord class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e0ea2-107">属性</span><span class="sxs-lookup"><span data-stu-id="e0ea2-107">Properties</span></span>  
 <span data-ttu-id="e0ea2-108">WSAT_TraceRecord 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="e0ea2-108">The WSAT_TraceRecord class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="e0ea2-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="e0ea2-109">ActivityID</span></span>  
 <span data-ttu-id="e0ea2-110">数据类型：object</span><span class="sxs-lookup"><span data-stu-id="e0ea2-110">Data type: object</span></span>  
<span data-ttu-id="e0ea2-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="e0ea2-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e0ea2-112">跟踪记录的活动 ID。</span><span class="sxs-lookup"><span data-stu-id="e0ea2-112">The activity ID of the trace record.</span></span>  
  
### <a name="eventid"></a><span data-ttu-id="e0ea2-113">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e0ea2-113">EventID</span></span>  
 <span data-ttu-id="e0ea2-114">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="e0ea2-114">Data type: sint32</span></span>  
<span data-ttu-id="e0ea2-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="e0ea2-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e0ea2-116">跟踪记录的事件 ID。</span><span class="sxs-lookup"><span data-stu-id="e0ea2-116">The event ID of the trace record.</span></span>  
  
### <a name="tracerecord"></a><span data-ttu-id="e0ea2-117">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="e0ea2-117">TraceRecord</span></span>  
 <span data-ttu-id="e0ea2-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="e0ea2-118">Data type: string</span></span>  
<span data-ttu-id="e0ea2-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="e0ea2-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e0ea2-120">跟踪记录</span><span class="sxs-lookup"><span data-stu-id="e0ea2-120">Trace Record</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0ea2-121">惠?</span><span class="sxs-lookup"><span data-stu-id="e0ea2-121">Requirements</span></span>  
  
|<span data-ttu-id="e0ea2-122">MOF</span><span class="sxs-lookup"><span data-stu-id="e0ea2-122">MOF</span></span>|<span data-ttu-id="e0ea2-123">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="e0ea2-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e0ea2-124">命名空间</span><span class="sxs-lookup"><span data-stu-id="e0ea2-124">Namespace</span></span>|<span data-ttu-id="e0ea2-125">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="e0ea2-125">Defined in root\ServiceModel</span></span>|

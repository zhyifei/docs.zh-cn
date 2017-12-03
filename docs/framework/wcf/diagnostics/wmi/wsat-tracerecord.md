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
ms.openlocfilehash: b4e701c2f0d669a04be7f7235c8ab1edb8ce1612
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="wsattracerecord"></a><span data-ttu-id="e9cc2-102">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="e9cc2-102">WSAT_TraceRecord</span></span>
<span data-ttu-id="e9cc2-103">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="e9cc2-103">WSAT_TraceRecord</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9cc2-104">语法</span><span class="sxs-lookup"><span data-stu-id="e9cc2-104">Syntax</span></span>  
  
```  
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e9cc2-105">方法</span><span class="sxs-lookup"><span data-stu-id="e9cc2-105">Methods</span></span>  
 <span data-ttu-id="e9cc2-106">WSAT_TraceRecord 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="e9cc2-106">The WSAT_TraceRecord class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e9cc2-107">属性</span><span class="sxs-lookup"><span data-stu-id="e9cc2-107">Properties</span></span>  
 <span data-ttu-id="e9cc2-108">WSAT_TraceRecord 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="e9cc2-108">The WSAT_TraceRecord class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="e9cc2-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="e9cc2-109">ActivityID</span></span>  
 <span data-ttu-id="e9cc2-110">数据类型：object</span><span class="sxs-lookup"><span data-stu-id="e9cc2-110">Data type: object</span></span>  
<span data-ttu-id="e9cc2-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="e9cc2-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e9cc2-112">跟踪记录的活动 ID。</span><span class="sxs-lookup"><span data-stu-id="e9cc2-112">The activity ID of the trace record.</span></span>  
  
### <a name="eventid"></a><span data-ttu-id="e9cc2-113">EventID</span><span class="sxs-lookup"><span data-stu-id="e9cc2-113">EventID</span></span>  
 <span data-ttu-id="e9cc2-114">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="e9cc2-114">Data type: sint32</span></span>  
<span data-ttu-id="e9cc2-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="e9cc2-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e9cc2-116">跟踪记录的事件 ID。</span><span class="sxs-lookup"><span data-stu-id="e9cc2-116">The event ID of the trace record.</span></span>  
  
### <a name="tracerecord"></a><span data-ttu-id="e9cc2-117">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="e9cc2-117">TraceRecord</span></span>  
 <span data-ttu-id="e9cc2-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="e9cc2-118">Data type: string</span></span>  
<span data-ttu-id="e9cc2-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="e9cc2-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e9cc2-120">跟踪记录</span><span class="sxs-lookup"><span data-stu-id="e9cc2-120">Trace Record</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9cc2-121">要求</span><span class="sxs-lookup"><span data-stu-id="e9cc2-121">Requirements</span></span>  
  
|<span data-ttu-id="e9cc2-122">MOF</span><span class="sxs-lookup"><span data-stu-id="e9cc2-122">MOF</span></span>|<span data-ttu-id="e9cc2-123">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="e9cc2-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e9cc2-124">命名空间</span><span class="sxs-lookup"><span data-stu-id="e9cc2-124">Namespace</span></span>|<span data-ttu-id="e9cc2-125">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="e9cc2-125">Defined in root\ServiceModel</span></span>|

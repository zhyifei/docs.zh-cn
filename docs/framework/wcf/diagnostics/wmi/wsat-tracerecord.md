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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3966311bc10b5ad2ee401ef9e3e13c8f36e14505
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="wsattracerecord"></a><span data-ttu-id="bd751-102">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="bd751-102">WSAT_TraceRecord</span></span>
<span data-ttu-id="bd751-103">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="bd751-103">WSAT_TraceRecord</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd751-104">语法</span><span class="sxs-lookup"><span data-stu-id="bd751-104">Syntax</span></span>  
  
```  
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="bd751-105">方法</span><span class="sxs-lookup"><span data-stu-id="bd751-105">Methods</span></span>  
 <span data-ttu-id="bd751-106">WSAT_TraceRecord 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="bd751-106">The WSAT_TraceRecord class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="bd751-107">属性</span><span class="sxs-lookup"><span data-stu-id="bd751-107">Properties</span></span>  
 <span data-ttu-id="bd751-108">WSAT_TraceRecord 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="bd751-108">The WSAT_TraceRecord class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="bd751-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="bd751-109">ActivityID</span></span>  
 <span data-ttu-id="bd751-110">数据类型：object</span><span class="sxs-lookup"><span data-stu-id="bd751-110">Data type: object</span></span>  
<span data-ttu-id="bd751-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="bd751-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bd751-112">跟踪记录的活动 ID。</span><span class="sxs-lookup"><span data-stu-id="bd751-112">The activity ID of the trace record.</span></span>  
  
### <a name="eventid"></a><span data-ttu-id="bd751-113">EventID</span><span class="sxs-lookup"><span data-stu-id="bd751-113">EventID</span></span>  
 <span data-ttu-id="bd751-114">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="bd751-114">Data type: sint32</span></span>  
<span data-ttu-id="bd751-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="bd751-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bd751-116">跟踪记录的事件 ID。</span><span class="sxs-lookup"><span data-stu-id="bd751-116">The event ID of the trace record.</span></span>  
  
### <a name="tracerecord"></a><span data-ttu-id="bd751-117">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="bd751-117">TraceRecord</span></span>  
 <span data-ttu-id="bd751-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="bd751-118">Data type: string</span></span>  
<span data-ttu-id="bd751-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="bd751-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bd751-120">跟踪记录</span><span class="sxs-lookup"><span data-stu-id="bd751-120">Trace Record</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd751-121">要求</span><span class="sxs-lookup"><span data-stu-id="bd751-121">Requirements</span></span>  
  
|<span data-ttu-id="bd751-122">MOF</span><span class="sxs-lookup"><span data-stu-id="bd751-122">MOF</span></span>|<span data-ttu-id="bd751-123">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="bd751-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="bd751-124">命名空间</span><span class="sxs-lookup"><span data-stu-id="bd751-124">Namespace</span></span>|<span data-ttu-id="bd751-125">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="bd751-125">Defined in root\ServiceModel</span></span>|

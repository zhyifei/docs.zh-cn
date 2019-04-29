---
title: WSAT_TraceRecord
ms.date: 03/30/2017
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
ms.openlocfilehash: 907e764cf032e595c7aba455fd4808a640f68016
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61923404"
---
# <a name="wsattracerecord"></a><span data-ttu-id="2556d-102">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="2556d-102">WSAT_TraceRecord</span></span>
<span data-ttu-id="2556d-103">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="2556d-103">WSAT_TraceRecord</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2556d-104">语法</span><span class="sxs-lookup"><span data-stu-id="2556d-104">Syntax</span></span>  
  
```csharp
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="2556d-105">方法</span><span class="sxs-lookup"><span data-stu-id="2556d-105">Methods</span></span>  
 <span data-ttu-id="2556d-106">WSAT_TraceRecord 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="2556d-106">The WSAT_TraceRecord class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="2556d-107">属性</span><span class="sxs-lookup"><span data-stu-id="2556d-107">Properties</span></span>  
 <span data-ttu-id="2556d-108">WSAT_TraceRecord 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="2556d-108">The WSAT_TraceRecord class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="2556d-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="2556d-109">ActivityID</span></span>  
 <span data-ttu-id="2556d-110">数据类型：object</span><span class="sxs-lookup"><span data-stu-id="2556d-110">Data type: object</span></span>  
<span data-ttu-id="2556d-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="2556d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2556d-112">跟踪记录的活动 ID。</span><span class="sxs-lookup"><span data-stu-id="2556d-112">The activity ID of the trace record.</span></span>  
  
### <a name="eventid"></a><span data-ttu-id="2556d-113">事件 ID</span><span class="sxs-lookup"><span data-stu-id="2556d-113">EventID</span></span>  
 <span data-ttu-id="2556d-114">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="2556d-114">Data type: sint32</span></span>  
<span data-ttu-id="2556d-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="2556d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2556d-116">跟踪记录的事件 ID。</span><span class="sxs-lookup"><span data-stu-id="2556d-116">The event ID of the trace record.</span></span>  
  
### <a name="tracerecord"></a><span data-ttu-id="2556d-117">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="2556d-117">TraceRecord</span></span>  
 <span data-ttu-id="2556d-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="2556d-118">Data type: string</span></span>  
<span data-ttu-id="2556d-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="2556d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2556d-120">跟踪记录</span><span class="sxs-lookup"><span data-stu-id="2556d-120">Trace Record</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2556d-121">要求</span><span class="sxs-lookup"><span data-stu-id="2556d-121">Requirements</span></span>  
  
|<span data-ttu-id="2556d-122">MOF</span><span class="sxs-lookup"><span data-stu-id="2556d-122">MOF</span></span>|<span data-ttu-id="2556d-123">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="2556d-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="2556d-124">命名空间</span><span class="sxs-lookup"><span data-stu-id="2556d-124">Namespace</span></span>|<span data-ttu-id="2556d-125">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="2556d-125">Defined in root\ServiceModel</span></span>|

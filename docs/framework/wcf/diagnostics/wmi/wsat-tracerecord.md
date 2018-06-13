---
title: WSAT_TraceRecord
ms.date: 03/30/2017
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
ms.openlocfilehash: 1136647ce668dbb69bdb8acf8ed62343831464b3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33487771"
---
# <a name="wsattracerecord"></a><span data-ttu-id="b60bc-102">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="b60bc-102">WSAT_TraceRecord</span></span>
<span data-ttu-id="b60bc-103">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="b60bc-103">WSAT_TraceRecord</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b60bc-104">语法</span><span class="sxs-lookup"><span data-stu-id="b60bc-104">Syntax</span></span>  
  
```  
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b60bc-105">方法</span><span class="sxs-lookup"><span data-stu-id="b60bc-105">Methods</span></span>  
 <span data-ttu-id="b60bc-106">WSAT_TraceRecord 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="b60bc-106">The WSAT_TraceRecord class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b60bc-107">属性</span><span class="sxs-lookup"><span data-stu-id="b60bc-107">Properties</span></span>  
 <span data-ttu-id="b60bc-108">WSAT_TraceRecord 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="b60bc-108">The WSAT_TraceRecord class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="b60bc-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="b60bc-109">ActivityID</span></span>  
 <span data-ttu-id="b60bc-110">数据类型：object</span><span class="sxs-lookup"><span data-stu-id="b60bc-110">Data type: object</span></span>  
<span data-ttu-id="b60bc-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b60bc-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b60bc-112">跟踪记录的活动 ID。</span><span class="sxs-lookup"><span data-stu-id="b60bc-112">The activity ID of the trace record.</span></span>  
  
### <a name="eventid"></a><span data-ttu-id="b60bc-113">事件 ID</span><span class="sxs-lookup"><span data-stu-id="b60bc-113">EventID</span></span>  
 <span data-ttu-id="b60bc-114">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="b60bc-114">Data type: sint32</span></span>  
<span data-ttu-id="b60bc-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b60bc-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b60bc-116">跟踪记录的事件 ID。</span><span class="sxs-lookup"><span data-stu-id="b60bc-116">The event ID of the trace record.</span></span>  
  
### <a name="tracerecord"></a><span data-ttu-id="b60bc-117">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="b60bc-117">TraceRecord</span></span>  
 <span data-ttu-id="b60bc-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="b60bc-118">Data type: string</span></span>  
<span data-ttu-id="b60bc-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b60bc-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b60bc-120">跟踪记录</span><span class="sxs-lookup"><span data-stu-id="b60bc-120">Trace Record</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b60bc-121">要求</span><span class="sxs-lookup"><span data-stu-id="b60bc-121">Requirements</span></span>  
  
|<span data-ttu-id="b60bc-122">MOF</span><span class="sxs-lookup"><span data-stu-id="b60bc-122">MOF</span></span>|<span data-ttu-id="b60bc-123">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="b60bc-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b60bc-124">命名空间</span><span class="sxs-lookup"><span data-stu-id="b60bc-124">Namespace</span></span>|<span data-ttu-id="b60bc-125">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="b60bc-125">Defined in root\ServiceModel</span></span>|

---
title: WSAT_TraceRecord
ms.date: 03/30/2017
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
ms.openlocfilehash: 907e764cf032e595c7aba455fd4808a640f68016
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/25/2018
ms.locfileid: "50046274"
---
# <a name="wsattracerecord"></a><span data-ttu-id="f2dd8-102">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="f2dd8-102">WSAT_TraceRecord</span></span>
<span data-ttu-id="f2dd8-103">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="f2dd8-103">WSAT_TraceRecord</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2dd8-104">语法</span><span class="sxs-lookup"><span data-stu-id="f2dd8-104">Syntax</span></span>  
  
```csharp
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f2dd8-105">方法</span><span class="sxs-lookup"><span data-stu-id="f2dd8-105">Methods</span></span>  
 <span data-ttu-id="f2dd8-106">WSAT_TraceRecord 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="f2dd8-106">The WSAT_TraceRecord class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f2dd8-107">属性</span><span class="sxs-lookup"><span data-stu-id="f2dd8-107">Properties</span></span>  
 <span data-ttu-id="f2dd8-108">WSAT_TraceRecord 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="f2dd8-108">The WSAT_TraceRecord class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="f2dd8-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="f2dd8-109">ActivityID</span></span>  
 <span data-ttu-id="f2dd8-110">数据类型：object</span><span class="sxs-lookup"><span data-stu-id="f2dd8-110">Data type: object</span></span>  
<span data-ttu-id="f2dd8-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="f2dd8-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f2dd8-112">跟踪记录的活动 ID。</span><span class="sxs-lookup"><span data-stu-id="f2dd8-112">The activity ID of the trace record.</span></span>  
  
### <a name="eventid"></a><span data-ttu-id="f2dd8-113">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f2dd8-113">EventID</span></span>  
 <span data-ttu-id="f2dd8-114">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="f2dd8-114">Data type: sint32</span></span>  
<span data-ttu-id="f2dd8-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="f2dd8-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f2dd8-116">跟踪记录的事件 ID。</span><span class="sxs-lookup"><span data-stu-id="f2dd8-116">The event ID of the trace record.</span></span>  
  
### <a name="tracerecord"></a><span data-ttu-id="f2dd8-117">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="f2dd8-117">TraceRecord</span></span>  
 <span data-ttu-id="f2dd8-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="f2dd8-118">Data type: string</span></span>  
<span data-ttu-id="f2dd8-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="f2dd8-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f2dd8-120">跟踪记录</span><span class="sxs-lookup"><span data-stu-id="f2dd8-120">Trace Record</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f2dd8-121">要求</span><span class="sxs-lookup"><span data-stu-id="f2dd8-121">Requirements</span></span>  
  
|<span data-ttu-id="f2dd8-122">MOF</span><span class="sxs-lookup"><span data-stu-id="f2dd8-122">MOF</span></span>|<span data-ttu-id="f2dd8-123">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="f2dd8-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f2dd8-124">命名空间</span><span class="sxs-lookup"><span data-stu-id="f2dd8-124">Namespace</span></span>|<span data-ttu-id="f2dd8-125">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="f2dd8-125">Defined in root\ServiceModel</span></span>|

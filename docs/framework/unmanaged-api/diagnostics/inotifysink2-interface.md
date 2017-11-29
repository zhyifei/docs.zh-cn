---
title: "INotifySink2 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: INotifySink2
api_location: diasymreader.dll
api_type: COM
f1_keywords: INotifySink2
helpviewer_keywords: INotifySink2 interface [.NET Framework debugging]
ms.assetid: c1018789-4206-455d-aacc-2d876fc0d0bb
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e73daf26a6d3620cde75a24d44c75b0f09d4d8cd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="inotifysink2-interface"></a><span data-ttu-id="a9514-102">INotifySink2 接口</span><span class="sxs-lookup"><span data-stu-id="a9514-102">INotifySink2 Interface</span></span>
<span data-ttu-id="a9514-103">声明用于接收器通知方法。</span><span class="sxs-lookup"><span data-stu-id="a9514-103">Declares methods for sink notification.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a9514-104">方法</span><span class="sxs-lookup"><span data-stu-id="a9514-104">Methods</span></span>  
  
|<span data-ttu-id="a9514-105">方法</span><span class="sxs-lookup"><span data-stu-id="a9514-105">Method</span></span>|<span data-ttu-id="a9514-106">描述</span><span class="sxs-lookup"><span data-stu-id="a9514-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a9514-107">OnSyncCallEnter 方法</span><span class="sxs-lookup"><span data-stu-id="a9514-107">OnSyncCallEnter Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md)|<span data-ttu-id="a9514-108">输入调用时调用。</span><span class="sxs-lookup"><span data-stu-id="a9514-108">Gets invoked when entering a call.</span></span>|  
|[<span data-ttu-id="a9514-109">OnSyncCallExit 方法</span><span class="sxs-lookup"><span data-stu-id="a9514-109">OnSyncCallExit Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md)|<span data-ttu-id="a9514-110">退出调用时调用。</span><span class="sxs-lookup"><span data-stu-id="a9514-110">Gets invoked when exiting a call.</span></span>|  
|[<span data-ttu-id="a9514-111">OnSyncCallOut 方法</span><span class="sxs-lookup"><span data-stu-id="a9514-111">OnSyncCallOut Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md)|<span data-ttu-id="a9514-112">调用超时时被调用。</span><span class="sxs-lookup"><span data-stu-id="a9514-112">Gets invoked when a call is out.</span></span>|  
|[<span data-ttu-id="a9514-113">OnSyncCallReturn 方法</span><span class="sxs-lookup"><span data-stu-id="a9514-113">OnSyncCallReturn Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md)|<span data-ttu-id="a9514-114">当调用返回时调用。</span><span class="sxs-lookup"><span data-stu-id="a9514-114">Gets invoked when a call returns.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a9514-115">要求</span><span class="sxs-lookup"><span data-stu-id="a9514-115">Requirements</span></span>  
 <span data-ttu-id="a9514-116">**标头：** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="a9514-116">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9514-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a9514-117">See Also</span></span>  
 [<span data-ttu-id="a9514-118">INotifyConnection2 接口</span><span class="sxs-lookup"><span data-stu-id="a9514-118">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 [<span data-ttu-id="a9514-119">INotifySource2 接口</span><span class="sxs-lookup"><span data-stu-id="a9514-119">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 [<span data-ttu-id="a9514-120">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="a9514-120">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)

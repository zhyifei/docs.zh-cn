---
title: INotifySink2 接口
ms.date: 03/30/2017
api_name:
- INotifySink2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2
helpviewer_keywords:
- INotifySink2 interface [.NET Framework debugging]
ms.assetid: c1018789-4206-455d-aacc-2d876fc0d0bb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 52246ac531853eea87464e265f731ece0d350e22
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426031"
---
# <a name="inotifysink2-interface"></a><span data-ttu-id="3bafb-102">INotifySink2 接口</span><span class="sxs-lookup"><span data-stu-id="3bafb-102">INotifySink2 Interface</span></span>
<span data-ttu-id="3bafb-103">声明用于接收器通知方法。</span><span class="sxs-lookup"><span data-stu-id="3bafb-103">Declares methods for sink notification.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3bafb-104">方法</span><span class="sxs-lookup"><span data-stu-id="3bafb-104">Methods</span></span>  
  
|<span data-ttu-id="3bafb-105">方法</span><span class="sxs-lookup"><span data-stu-id="3bafb-105">Method</span></span>|<span data-ttu-id="3bafb-106">描述</span><span class="sxs-lookup"><span data-stu-id="3bafb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3bafb-107">OnSyncCallEnter 方法</span><span class="sxs-lookup"><span data-stu-id="3bafb-107">OnSyncCallEnter Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md)|<span data-ttu-id="3bafb-108">输入调用时调用。</span><span class="sxs-lookup"><span data-stu-id="3bafb-108">Gets invoked when entering a call.</span></span>|  
|[<span data-ttu-id="3bafb-109">OnSyncCallExit 方法</span><span class="sxs-lookup"><span data-stu-id="3bafb-109">OnSyncCallExit Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md)|<span data-ttu-id="3bafb-110">退出调用时调用。</span><span class="sxs-lookup"><span data-stu-id="3bafb-110">Gets invoked when exiting a call.</span></span>|  
|[<span data-ttu-id="3bafb-111">OnSyncCallOut 方法</span><span class="sxs-lookup"><span data-stu-id="3bafb-111">OnSyncCallOut Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md)|<span data-ttu-id="3bafb-112">调用超时时被调用。</span><span class="sxs-lookup"><span data-stu-id="3bafb-112">Gets invoked when a call is out.</span></span>|  
|[<span data-ttu-id="3bafb-113">OnSyncCallReturn 方法</span><span class="sxs-lookup"><span data-stu-id="3bafb-113">OnSyncCallReturn Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md)|<span data-ttu-id="3bafb-114">当调用返回时调用。</span><span class="sxs-lookup"><span data-stu-id="3bafb-114">Gets invoked when a call returns.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3bafb-115">要求</span><span class="sxs-lookup"><span data-stu-id="3bafb-115">Requirements</span></span>  
 <span data-ttu-id="3bafb-116">**标头：** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="3bafb-116">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bafb-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="3bafb-117">See Also</span></span>  
 [<span data-ttu-id="3bafb-118">INotifyConnection2 接口</span><span class="sxs-lookup"><span data-stu-id="3bafb-118">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 [<span data-ttu-id="3bafb-119">INotifySource2 接口</span><span class="sxs-lookup"><span data-stu-id="3bafb-119">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 [<span data-ttu-id="3bafb-120">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="3bafb-120">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)

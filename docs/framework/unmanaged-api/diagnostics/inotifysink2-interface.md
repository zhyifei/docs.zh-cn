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
ms.openlocfilehash: 4f5307ce00160bb4151a7559daac4724367c6497
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157725"
---
# <a name="inotifysink2-interface"></a><span data-ttu-id="598f0-102">INotifySink2 接口</span><span class="sxs-lookup"><span data-stu-id="598f0-102">INotifySink2 Interface</span></span>
<span data-ttu-id="598f0-103">声明用于接收器通知的方法。</span><span class="sxs-lookup"><span data-stu-id="598f0-103">Declares methods for sink notification.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="598f0-104">方法</span><span class="sxs-lookup"><span data-stu-id="598f0-104">Methods</span></span>  
  
|<span data-ttu-id="598f0-105">方法</span><span class="sxs-lookup"><span data-stu-id="598f0-105">Method</span></span>|<span data-ttu-id="598f0-106">描述</span><span class="sxs-lookup"><span data-stu-id="598f0-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="598f0-107">OnSyncCallEnter 方法</span><span class="sxs-lookup"><span data-stu-id="598f0-107">OnSyncCallEnter Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md)|<span data-ttu-id="598f0-108">输入调用时调用。</span><span class="sxs-lookup"><span data-stu-id="598f0-108">Gets invoked when entering a call.</span></span>|  
|[<span data-ttu-id="598f0-109">OnSyncCallExit 方法</span><span class="sxs-lookup"><span data-stu-id="598f0-109">OnSyncCallExit Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md)|<span data-ttu-id="598f0-110">退出调用时调用。</span><span class="sxs-lookup"><span data-stu-id="598f0-110">Gets invoked when exiting a call.</span></span>|  
|[<span data-ttu-id="598f0-111">OnSyncCallOut 方法</span><span class="sxs-lookup"><span data-stu-id="598f0-111">OnSyncCallOut Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md)|<span data-ttu-id="598f0-112">调用超时时被调用。</span><span class="sxs-lookup"><span data-stu-id="598f0-112">Gets invoked when a call is out.</span></span>|  
|[<span data-ttu-id="598f0-113">OnSyncCallReturn 方法</span><span class="sxs-lookup"><span data-stu-id="598f0-113">OnSyncCallReturn Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md)|<span data-ttu-id="598f0-114">当调用返回时调用。</span><span class="sxs-lookup"><span data-stu-id="598f0-114">Gets invoked when a call returns.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="598f0-115">要求</span><span class="sxs-lookup"><span data-stu-id="598f0-115">Requirements</span></span>  
 <span data-ttu-id="598f0-116">**标头：** ProtocolNotify2.idl</span><span class="sxs-lookup"><span data-stu-id="598f0-116">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="598f0-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="598f0-117">See also</span></span>

- [<span data-ttu-id="598f0-118">INotifyConnection2 接口</span><span class="sxs-lookup"><span data-stu-id="598f0-118">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
- [<span data-ttu-id="598f0-119">INotifySource2 接口</span><span class="sxs-lookup"><span data-stu-id="598f0-119">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="598f0-120">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="598f0-120">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)

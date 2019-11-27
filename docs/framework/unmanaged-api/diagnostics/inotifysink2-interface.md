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
ms.openlocfilehash: af50c82974b779b901135795f37e3bd4c8b8c156
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440969"
---
# <a name="inotifysink2-interface"></a><span data-ttu-id="35c47-102">INotifySink2 接口</span><span class="sxs-lookup"><span data-stu-id="35c47-102">INotifySink2 Interface</span></span>
<span data-ttu-id="35c47-103">声明接收器通知的方法。</span><span class="sxs-lookup"><span data-stu-id="35c47-103">Declares methods for sink notification.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="35c47-104">方法</span><span class="sxs-lookup"><span data-stu-id="35c47-104">Methods</span></span>  
  
|<span data-ttu-id="35c47-105">方法</span><span class="sxs-lookup"><span data-stu-id="35c47-105">Method</span></span>|<span data-ttu-id="35c47-106">说明</span><span class="sxs-lookup"><span data-stu-id="35c47-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="35c47-107">OnSyncCallEnter 方法</span><span class="sxs-lookup"><span data-stu-id="35c47-107">OnSyncCallEnter Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallenter-method.md)|<span data-ttu-id="35c47-108">在输入调用时调用。</span><span class="sxs-lookup"><span data-stu-id="35c47-108">Gets invoked when entering a call.</span></span>|  
|[<span data-ttu-id="35c47-109">OnSyncCallExit 方法</span><span class="sxs-lookup"><span data-stu-id="35c47-109">OnSyncCallExit Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallexit-method.md)|<span data-ttu-id="35c47-110">在退出调用时调用。</span><span class="sxs-lookup"><span data-stu-id="35c47-110">Gets invoked when exiting a call.</span></span>|  
|[<span data-ttu-id="35c47-111">OnSyncCallOut 方法</span><span class="sxs-lookup"><span data-stu-id="35c47-111">OnSyncCallOut Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallout-method.md)|<span data-ttu-id="35c47-112">在调用时调用。</span><span class="sxs-lookup"><span data-stu-id="35c47-112">Gets invoked when a call is out.</span></span>|  
|[<span data-ttu-id="35c47-113">OnSyncCallReturn 方法</span><span class="sxs-lookup"><span data-stu-id="35c47-113">OnSyncCallReturn Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-onsynccallreturn-method.md)|<span data-ttu-id="35c47-114">当调用返回时调用。</span><span class="sxs-lookup"><span data-stu-id="35c47-114">Gets invoked when a call returns.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="35c47-115">要求</span><span class="sxs-lookup"><span data-stu-id="35c47-115">Requirements</span></span>  
 <span data-ttu-id="35c47-116">**标头：** ProtocolNotify2 .idl</span><span class="sxs-lookup"><span data-stu-id="35c47-116">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35c47-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="35c47-117">See also</span></span>

- [<span data-ttu-id="35c47-118">INotifyConnection2 接口</span><span class="sxs-lookup"><span data-stu-id="35c47-118">INotifyConnection2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)
- [<span data-ttu-id="35c47-119">INotifySource2 接口</span><span class="sxs-lookup"><span data-stu-id="35c47-119">INotifySource2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)
- [<span data-ttu-id="35c47-120">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="35c47-120">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)

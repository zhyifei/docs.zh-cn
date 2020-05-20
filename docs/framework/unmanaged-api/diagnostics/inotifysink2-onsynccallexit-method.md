---
title: INotifySink2::OnSyncCallExit 方法
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallExit
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallExit
helpviewer_keywords:
- INotifySink2::OnSyncCallExit method [.NET Framework debugging]
- OnSyncCallExit method [.NET Framework debugging]
ms.assetid: d9d7600e-a8f5-443a-96de-67d26e130f2d
topic_type:
- apiref
ms.openlocfilehash: f81ef3f5959e279b3fbbd94d6c5e8a2d86a38e7f
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442015"
---
# <a name="inotifysink2onsynccallexit-method"></a><span data-ttu-id="0c8c2-102">INotifySink2::OnSyncCallExit 方法</span><span class="sxs-lookup"><span data-stu-id="0c8c2-102">INotifySink2::OnSyncCallExit Method</span></span>
<span data-ttu-id="0c8c2-103">在退出调用时调用。</span><span class="sxs-lookup"><span data-stu-id="0c8c2-103">Gets invoked when exiting a call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c8c2-104">语法</span><span class="sxs-lookup"><span data-stu-id="0c8c2-104">Syntax</span></span>  
  
```cpp  
HRESULT OnSyncCallExit  
(  
    [in]  CALL_ID   in_CallID,  
    [out, size_is(, *out_pBufferSize)] BYTE**  out_ppBuffer,  
    [out] DWORD*    out_pBufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c8c2-105">参数</span><span class="sxs-lookup"><span data-stu-id="0c8c2-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="0c8c2-106">中正在退出的调用的 ID。</span><span class="sxs-lookup"><span data-stu-id="0c8c2-106">[in] ID of the call being exited.</span></span> <span data-ttu-id="0c8c2-107">请参阅[CALL_ID 结构](call-id-structure.md)。</span><span class="sxs-lookup"><span data-stu-id="0c8c2-107">See [CALL_ID Structure](call-id-structure.md).</span></span>  
  
 `out_ppBuffer`  
 <span data-ttu-id="0c8c2-108">弄调用缓冲区。</span><span class="sxs-lookup"><span data-stu-id="0c8c2-108">[out] Call buffer.</span></span>  
  
 `out_pBufferSize`  
 <span data-ttu-id="0c8c2-109">弄调用缓冲区的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="0c8c2-109">[out] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0c8c2-110">返回值</span><span class="sxs-lookup"><span data-stu-id="0c8c2-110">Return Value</span></span>  
 <span data-ttu-id="0c8c2-111">如果方法成功，则 S_OK。</span><span class="sxs-lookup"><span data-stu-id="0c8c2-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c8c2-112">要求</span><span class="sxs-lookup"><span data-stu-id="0c8c2-112">Requirements</span></span>  
 <span data-ttu-id="0c8c2-113">**标头：** ProtocolNotify2 .idl</span><span class="sxs-lookup"><span data-stu-id="0c8c2-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c8c2-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c8c2-114">See also</span></span>

- [<span data-ttu-id="0c8c2-115">INotifySink2 接口</span><span class="sxs-lookup"><span data-stu-id="0c8c2-115">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="0c8c2-116">INotifySource2 接口</span><span class="sxs-lookup"><span data-stu-id="0c8c2-116">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="0c8c2-117">INotifyConnection2 接口</span><span class="sxs-lookup"><span data-stu-id="0c8c2-117">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)

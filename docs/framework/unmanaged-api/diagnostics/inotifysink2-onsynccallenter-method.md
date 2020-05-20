---
title: INotifySink2::OnSyncCallEnter 方法
ms.date: 03/30/2017
api_name:
- INotifySink2.OnSyncCallEnter
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- INotifySink2::OnSyncCallEnter
helpviewer_keywords:
- INotifySink2::OnSyncCallEnter method [.NET Framework debugging]
- OnSyncCallEnter method [.NET Framework debugging]
ms.assetid: e33265be-c25d-4145-ad02-c3e89d6f26c1
topic_type:
- apiref
ms.openlocfilehash: 85f00698f42f120b209cca14f293a58ae4c65f6f
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442028"
---
# <a name="inotifysink2onsynccallenter-method"></a><span data-ttu-id="90736-102">INotifySink2::OnSyncCallEnter 方法</span><span class="sxs-lookup"><span data-stu-id="90736-102">INotifySink2::OnSyncCallEnter Method</span></span>
<span data-ttu-id="90736-103">在输入调用时调用。</span><span class="sxs-lookup"><span data-stu-id="90736-103">Gets invoked when entering a call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90736-104">语法</span><span class="sxs-lookup"><span data-stu-id="90736-104">Syntax</span></span>  
  
```cpp  
HRESULT OnSyncCallEnter  
(  
    [in]  CALL_ID   in_CallID,  
    [in, size_is(in_BufferSize)] BYTE*  in_pBuffer,  
    [in]  DWORD     in_BufferSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90736-105">参数</span><span class="sxs-lookup"><span data-stu-id="90736-105">Parameters</span></span>  
 `in_CallID`  
 <span data-ttu-id="90736-106">中正在输入的调用的 ID。</span><span class="sxs-lookup"><span data-stu-id="90736-106">[in] ID of the call being entered.</span></span> <span data-ttu-id="90736-107">请参阅[CALL_ID 结构](call-id-structure.md)。</span><span class="sxs-lookup"><span data-stu-id="90736-107">See [CALL_ID Structure](call-id-structure.md).</span></span>  
  
 `in_pBuffer`  
 <span data-ttu-id="90736-108">中调用缓冲区。</span><span class="sxs-lookup"><span data-stu-id="90736-108">[in] Call buffer.</span></span>  
  
 `in_BufferSize`  
 <span data-ttu-id="90736-109">中调用缓冲区的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="90736-109">[in] Size of the call buffer, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="90736-110">返回值</span><span class="sxs-lookup"><span data-stu-id="90736-110">Return Value</span></span>  
 <span data-ttu-id="90736-111">如果方法成功，则 S_OK。</span><span class="sxs-lookup"><span data-stu-id="90736-111">S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90736-112">要求</span><span class="sxs-lookup"><span data-stu-id="90736-112">Requirements</span></span>  
 <span data-ttu-id="90736-113">**标头：** ProtocolNotify2 .idl</span><span class="sxs-lookup"><span data-stu-id="90736-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90736-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="90736-114">See also</span></span>

- [<span data-ttu-id="90736-115">INotifySink2 接口</span><span class="sxs-lookup"><span data-stu-id="90736-115">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="90736-116">INotifySource2 接口</span><span class="sxs-lookup"><span data-stu-id="90736-116">INotifySource2 Interface</span></span>](inotifysource2-interface.md)
- [<span data-ttu-id="90736-117">INotifyConnection2 接口</span><span class="sxs-lookup"><span data-stu-id="90736-117">INotifyConnection2 Interface</span></span>](inotifyconnection2-interface.md)

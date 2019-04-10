---
title: ICLRDataTarget3::GetExceptionThreadID 方法
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICLRDataTarget3.GetExceptionThreadID
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 307d6ac7-4a86-45f3-999d-6b47004a68f2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c6503efbaa4db89b243a85b69f60b091c6bb49ef
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59215295"
---
# <a name="iclrdatatarget3getexceptionthreadid-method"></a><span data-ttu-id="3d9fc-102">ICLRDataTarget3::GetExceptionThreadID 方法</span><span class="sxs-lookup"><span data-stu-id="3d9fc-102">ICLRDataTarget3::GetExceptionThreadID Method</span></span>
<span data-ttu-id="3d9fc-103">由公共语言运行时 (CLR) 数据访问服务调用，从而获取引发异常的线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="3d9fc-103">Called by the common language runtime (CLR) data access services to get the ID of the thread that threw the exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d9fc-104">语法</span><span class="sxs-lookup"><span data-stu-id="3d9fc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionThreadID(  
    [out] ULONG32* threadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d9fc-105">参数</span><span class="sxs-lookup"><span data-stu-id="3d9fc-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="3d9fc-106">[out] 引发异常的线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="3d9fc-106">[out] The ID of the thread that threw the exception.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3d9fc-107">返回值</span><span class="sxs-lookup"><span data-stu-id="3d9fc-107">Return Value</span></span>  
 <span data-ttu-id="3d9fc-108">如果成功，则返回值是 `S_OK`；如果失败，则返回失败 `HRESULT` 代码。</span><span class="sxs-lookup"><span data-stu-id="3d9fc-108">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="3d9fc-109">`HRESULT` 代码可以包括但不限于以下代码：</span><span class="sxs-lookup"><span data-stu-id="3d9fc-109">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="3d9fc-110">返回代码</span><span class="sxs-lookup"><span data-stu-id="3d9fc-110">Return code</span></span>|<span data-ttu-id="3d9fc-111">描述</span><span class="sxs-lookup"><span data-stu-id="3d9fc-111">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="3d9fc-112">方法成功。</span><span class="sxs-lookup"><span data-stu-id="3d9fc-112">Method succeeded.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="3d9fc-113">找不到该异常的有效线程 ID。</span><span class="sxs-lookup"><span data-stu-id="3d9fc-113">Could not find a valid thread ID for the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d9fc-114">备注</span><span class="sxs-lookup"><span data-stu-id="3d9fc-114">Remarks</span></span>  
 <span data-ttu-id="3d9fc-115">此方法由调试应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="3d9fc-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d9fc-116">要求</span><span class="sxs-lookup"><span data-stu-id="3d9fc-116">Requirements</span></span>  
 <span data-ttu-id="3d9fc-117">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3d9fc-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d9fc-118">**标头：** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="3d9fc-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="3d9fc-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d9fc-119">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3d9fc-120">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="3d9fc-120">.NET Framework Versions:</span></span>** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3d9fc-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="3d9fc-121">See also</span></span>

- [<span data-ttu-id="3d9fc-122">ICLRDataTarget3 接口</span><span class="sxs-lookup"><span data-stu-id="3d9fc-122">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)
- [<span data-ttu-id="3d9fc-123">GetExceptionContextRecord 方法</span><span class="sxs-lookup"><span data-stu-id="3d9fc-123">GetExceptionContextRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)
- [<span data-ttu-id="3d9fc-124">GetExceptionRecord 方法</span><span class="sxs-lookup"><span data-stu-id="3d9fc-124">GetExceptionRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionrecord-method.md)

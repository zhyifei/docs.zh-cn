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
ms.openlocfilehash: 63c92e3f34527f895552f45d43f332f778470b13
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860424"
---
# <a name="iclrdatatarget3getexceptionthreadid-method"></a><span data-ttu-id="7716d-102">ICLRDataTarget3::GetExceptionThreadID 方法</span><span class="sxs-lookup"><span data-stu-id="7716d-102">ICLRDataTarget3::GetExceptionThreadID Method</span></span>
<span data-ttu-id="7716d-103">由公共语言运行时 (CLR) 数据访问服务调用，从而获取引发异常的线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="7716d-103">Called by the common language runtime (CLR) data access services to get the ID of the thread that threw the exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7716d-104">语法</span><span class="sxs-lookup"><span data-stu-id="7716d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionThreadID(  
    [out] ULONG32* threadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7716d-105">参数</span><span class="sxs-lookup"><span data-stu-id="7716d-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="7716d-106">[out] 引发异常的线程的 ID。</span><span class="sxs-lookup"><span data-stu-id="7716d-106">[out] The ID of the thread that threw the exception.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7716d-107">返回值</span><span class="sxs-lookup"><span data-stu-id="7716d-107">Return Value</span></span>  
 <span data-ttu-id="7716d-108">如果成功，则返回值是 `S_OK`；如果失败，则返回失败 `HRESULT` 代码。</span><span class="sxs-lookup"><span data-stu-id="7716d-108">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="7716d-109">`HRESULT` 代码可以包括但不限于以下代码：</span><span class="sxs-lookup"><span data-stu-id="7716d-109">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="7716d-110">返回代码</span><span class="sxs-lookup"><span data-stu-id="7716d-110">Return code</span></span>|<span data-ttu-id="7716d-111">说明</span><span class="sxs-lookup"><span data-stu-id="7716d-111">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="7716d-112">方法成功。</span><span class="sxs-lookup"><span data-stu-id="7716d-112">Method succeeded.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="7716d-113">找不到该异常的有效线程 ID。</span><span class="sxs-lookup"><span data-stu-id="7716d-113">Could not find a valid thread ID for the exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7716d-114">备注</span><span class="sxs-lookup"><span data-stu-id="7716d-114">Remarks</span></span>  
 <span data-ttu-id="7716d-115">此方法由调试应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="7716d-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7716d-116">要求</span><span class="sxs-lookup"><span data-stu-id="7716d-116">Requirements</span></span>  
 <span data-ttu-id="7716d-117">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7716d-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7716d-118">**标头：** ClrData，ClrData</span><span class="sxs-lookup"><span data-stu-id="7716d-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="7716d-119">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7716d-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7716d-120">**.NET Framework 版本：**[!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7716d-120">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7716d-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7716d-121">See also</span></span>

- [<span data-ttu-id="7716d-122">ICLRDataTarget3 接口</span><span class="sxs-lookup"><span data-stu-id="7716d-122">ICLRDataTarget3 Interface</span></span>](iclrdatatarget3-interface.md)
- [<span data-ttu-id="7716d-123">GetExceptionContextRecord 方法</span><span class="sxs-lookup"><span data-stu-id="7716d-123">GetExceptionContextRecord Method</span></span>](iclrdatatarget3-getexceptioncontextrecord-method.md)
- [<span data-ttu-id="7716d-124">GetExceptionRecord 方法</span><span class="sxs-lookup"><span data-stu-id="7716d-124">GetExceptionRecord Method</span></span>](iclrdatatarget3-getexceptionrecord-method.md)

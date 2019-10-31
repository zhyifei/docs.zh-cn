---
title: ICLRDataTarget::Request 方法
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.Request
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::Request
helpviewer_keywords:
- ICLRDataTarget::Request method [.NET Framework debugging]
- Request method [.NET Framework debugging]
ms.assetid: 4723bd1c-eddb-4ed2-897a-010024a47e01
topic_type:
- apiref
ms.openlocfilehash: e5d7a6b9826a734363d6beeb2e3fab8422964558
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73113357"
---
# <a name="iclrdatatargetrequest-method"></a><span data-ttu-id="6ffe0-102">ICLRDataTarget::Request 方法</span><span class="sxs-lookup"><span data-stu-id="6ffe0-102">ICLRDataTarget::Request Method</span></span>
<span data-ttu-id="6ffe0-103">由公共语言运行时（CLR）数据访问服务调用，用来请求操作，如实现所定义。</span><span class="sxs-lookup"><span data-stu-id="6ffe0-103">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ffe0-104">语法</span><span class="sxs-lookup"><span data-stu-id="6ffe0-104">Syntax</span></span>  
  
```cpp  
HRESULT Request (  
    [in] ULONG32            reqCode,  
    [in] ULONG32            inBufferSize,  
    [in, size_is(inBufferSize)]   
        BYTE                *inBuffer,  
    [in] ULONG32            outBufferSize,  
    [out, size_is(outBufferSize)]   
        BYTE                *outBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6ffe0-105">参数</span><span class="sxs-lookup"><span data-stu-id="6ffe0-105">Parameters</span></span>  
 `reqCode`  
 <span data-ttu-id="6ffe0-106">中用户定义的。</span><span class="sxs-lookup"><span data-stu-id="6ffe0-106">[in] User-defined.</span></span>  
  
 `inBufferSize`  
 <span data-ttu-id="6ffe0-107">中输入缓冲区的大小，该大小用于传入的请求。</span><span class="sxs-lookup"><span data-stu-id="6ffe0-107">[in] The size of the input buffer, which is used for the incoming request.</span></span>  
  
 `inBuffer`  
 <span data-ttu-id="6ffe0-108">中包含请求的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="6ffe0-108">[in] A buffer containing the request.</span></span>  
  
 `outBufferSize`  
 <span data-ttu-id="6ffe0-109">中用于响应的输出缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="6ffe0-109">[in] The size of the output buffer, which is used for the response.</span></span>  
  
 `outBuffer`  
 <span data-ttu-id="6ffe0-110">弄包含响应的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="6ffe0-110">[out] A Buffer containing the response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ffe0-111">备注</span><span class="sxs-lookup"><span data-stu-id="6ffe0-111">Remarks</span></span>  
 <span data-ttu-id="6ffe0-112">`Request` 方法便于添加未指定的自定义操作。</span><span class="sxs-lookup"><span data-stu-id="6ffe0-112">The `Request` method facilitates the addition of unspecified custom operations.</span></span> <span data-ttu-id="6ffe0-113">也就是说，此方法提供了扩展性，无需版本的接口定义。</span><span class="sxs-lookup"><span data-stu-id="6ffe0-113">That is, this method provides extensibility without requiring revision of the interface definition.</span></span>  
  
 <span data-ttu-id="6ffe0-114">此方法由调试应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="6ffe0-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ffe0-115">要求</span><span class="sxs-lookup"><span data-stu-id="6ffe0-115">Requirements</span></span>  
 <span data-ttu-id="6ffe0-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6ffe0-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ffe0-117">**标头：** ClrData，ClrData</span><span class="sxs-lookup"><span data-stu-id="6ffe0-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="6ffe0-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6ffe0-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6ffe0-119">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ffe0-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ffe0-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="6ffe0-120">See also</span></span>

- [<span data-ttu-id="6ffe0-121">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="6ffe0-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)

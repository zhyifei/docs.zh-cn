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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dc79277c75118b11766e66137284bd5655eed091
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405367"
---
# <a name="iclrdatatargetrequest-method"></a><span data-ttu-id="2bb7c-102">ICLRDataTarget::Request 方法</span><span class="sxs-lookup"><span data-stu-id="2bb7c-102">ICLRDataTarget::Request Method</span></span>
<span data-ttu-id="2bb7c-103">调用由公共语言运行时 (CLR) 数据访问服务以请求操作，如由实现定义。</span><span class="sxs-lookup"><span data-stu-id="2bb7c-103">Called by the common language runtime (CLR) data access services to request an operation, as defined by the implementation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bb7c-104">语法</span><span class="sxs-lookup"><span data-stu-id="2bb7c-104">Syntax</span></span>  
  
```  
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
  
#### <a name="parameters"></a><span data-ttu-id="2bb7c-105">参数</span><span class="sxs-lookup"><span data-stu-id="2bb7c-105">Parameters</span></span>  
 `reqCode`  
 <span data-ttu-id="2bb7c-106">[in]用户定义。</span><span class="sxs-lookup"><span data-stu-id="2bb7c-106">[in] User-defined.</span></span>  
  
 `inBufferSize`  
 <span data-ttu-id="2bb7c-107">[in]输入缓冲区，用于传入请求的大小。</span><span class="sxs-lookup"><span data-stu-id="2bb7c-107">[in] The size of the input buffer, which is used for the incoming request.</span></span>  
  
 `inBuffer`  
 <span data-ttu-id="2bb7c-108">[in]包含请求的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="2bb7c-108">[in] A buffer containing the request.</span></span>  
  
 `outBufferSize`  
 <span data-ttu-id="2bb7c-109">[in]输出缓冲区，用于响应的大小。</span><span class="sxs-lookup"><span data-stu-id="2bb7c-109">[in] The size of the output buffer, which is used for the response.</span></span>  
  
 `outBuffer`  
 <span data-ttu-id="2bb7c-110">[out]包含响应的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="2bb7c-110">[out] A Buffer containing the response.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2bb7c-111">备注</span><span class="sxs-lookup"><span data-stu-id="2bb7c-111">Remarks</span></span>  
 <span data-ttu-id="2bb7c-112">`Request`方法方便了添加的未指定自定义操作。</span><span class="sxs-lookup"><span data-stu-id="2bb7c-112">The `Request` method facilitates the addition of unspecified custom operations.</span></span> <span data-ttu-id="2bb7c-113">也就是说，此方法还提供扩展性而无需的接口定义的修订版本。</span><span class="sxs-lookup"><span data-stu-id="2bb7c-113">That is, this method provides extensibility without requiring revision of the interface definition.</span></span>  
  
 <span data-ttu-id="2bb7c-114">此方法由调试应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="2bb7c-114">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bb7c-115">要求</span><span class="sxs-lookup"><span data-stu-id="2bb7c-115">Requirements</span></span>  
 <span data-ttu-id="2bb7c-116">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2bb7c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bb7c-117">**标头：** ClrData.idl、 ClrData.h</span><span class="sxs-lookup"><span data-stu-id="2bb7c-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="2bb7c-118">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2bb7c-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2bb7c-119">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bb7c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bb7c-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="2bb7c-120">See Also</span></span>  
 [<span data-ttu-id="2bb7c-121">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="2bb7c-121">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)

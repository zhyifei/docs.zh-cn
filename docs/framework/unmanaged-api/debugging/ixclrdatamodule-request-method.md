---
title: IXCLRDataModule::Request 方法
ms.date: 01/16/2019
api.name:
- IXCLRDataModule::Request Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule::Request Method
helpviewer.keywords:
- IXCLRDataModule::Request Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 2cc712e6560fc58af7526428ba40c424be388eee
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746656"
---
# <a name="ixclrdatamodulerequest-method"></a><span data-ttu-id="27556-102">IXCLRDataModule::Request 方法</span><span class="sxs-lookup"><span data-stu-id="27556-102">IXCLRDataModule::Request Method</span></span>

<span data-ttu-id="27556-103">若要填充缓冲区中提供了模块的数据的请求。</span><span class="sxs-lookup"><span data-stu-id="27556-103">Requests to populate the buffer given with the module's data.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="27556-104">语法</span><span class="sxs-lookup"><span data-stu-id="27556-104">Syntax</span></span>
```
HRESULT Request([in] ULONG32 reqCode,
    [in] ULONG32 inBufferSize,
    [in, size_is(inBufferSize)] BYTE* inBuffer,
    [in] ULONG32 outBufferSize,
    [out, size_is(outBufferSize)] BYTE* outBuffer);
```

### <a name="parameters"></a><span data-ttu-id="27556-105">参数</span><span class="sxs-lookup"><span data-stu-id="27556-105">Parameters</span></span>

<span data-ttu-id="27556-106">`reqCode` [in]请求类型发送。</span><span class="sxs-lookup"><span data-stu-id="27556-106">`reqCode` [in] Request type to be sent.</span></span>

<span data-ttu-id="27556-107">`inBufferSize` [in] 要传入的输入缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="27556-107">`inBufferSize` [in] size of the input buffer to be passed in.</span></span>

<span data-ttu-id="27556-108">`inBuffer` [in，size_is(inBufferSize)]要在请求中发送的原始数据的缓冲区指针。</span><span class="sxs-lookup"><span data-stu-id="27556-108">`inBuffer` [in, size_is(inBufferSize)] Buffer pointer for the raw data to be sent in the request.</span></span>

<span data-ttu-id="27556-109">`outBufferSize` [in]输出缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="27556-109">`outBufferSize` [in] Size of the output buffer.</span></span>

<span data-ttu-id="27556-110">`outBuffer` [out，size_is(outBufferSize)]要用于存储请求响应的缓冲区指针。</span><span class="sxs-lookup"><span data-stu-id="27556-110">`outBuffer` [out, size_is(outBufferSize)] Buffer pointer to used to store the request response.</span></span>

## <a name="remarks"></a><span data-ttu-id="27556-111">备注</span><span class="sxs-lookup"><span data-stu-id="27556-111">Remarks</span></span>

<span data-ttu-id="27556-112">提供的方法属于`IXCLRDataModule`接口，并对应于虚拟方法表 36th 槽。</span><span class="sxs-lookup"><span data-stu-id="27556-112">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 36th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="27556-113">要求</span><span class="sxs-lookup"><span data-stu-id="27556-113">Requirements</span></span>

<span data-ttu-id="27556-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="27556-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="27556-115">**标头：** 无</span><span class="sxs-lookup"><span data-stu-id="27556-115">**Header:** None</span></span>   
<span data-ttu-id="27556-116">**库：** 无</span><span class="sxs-lookup"><span data-stu-id="27556-116">**Library:** None</span></span>  
<span data-ttu-id="27556-117">**.NET Framework 版本：**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="27556-117">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="27556-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="27556-118">See also</span></span>
- [<span data-ttu-id="27556-119">调试</span><span class="sxs-lookup"><span data-stu-id="27556-119">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="27556-120">IXCLRDataModule 接口</span><span class="sxs-lookup"><span data-stu-id="27556-120">IXCLRDataModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/ixclrdatamodule-interface.md)

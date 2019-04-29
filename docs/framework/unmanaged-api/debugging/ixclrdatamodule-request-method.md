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
ms.openlocfilehash: 755063ca6da29a2e4733dd653306192ac0434ec0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775448"
---
# <a name="ixclrdatamodulerequest-method"></a><span data-ttu-id="037d7-102">IXCLRDataModule::Request 方法</span><span class="sxs-lookup"><span data-stu-id="037d7-102">IXCLRDataModule::Request Method</span></span>

<span data-ttu-id="037d7-103">若要填充缓冲区中提供了模块的数据的请求。</span><span class="sxs-lookup"><span data-stu-id="037d7-103">Requests to populate the buffer given with the module's data.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="037d7-104">语法</span><span class="sxs-lookup"><span data-stu-id="037d7-104">Syntax</span></span>

```cpp
HRESULT Request([in] ULONG32 reqCode,
    [in] ULONG32 inBufferSize,
    [in, size_is(inBufferSize)] BYTE* inBuffer,
    [in] ULONG32 outBufferSize,
    [out, size_is(outBufferSize)] BYTE* outBuffer);
```

## <a name="parameters"></a><span data-ttu-id="037d7-105">参数</span><span class="sxs-lookup"><span data-stu-id="037d7-105">Parameters</span></span>

`reqCode`\
<span data-ttu-id="037d7-106">[in]请求类型发送。</span><span class="sxs-lookup"><span data-stu-id="037d7-106">[in] Request type to be sent.</span></span>

`inBufferSize`\
<span data-ttu-id="037d7-107">[in] 要传入的输入缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="037d7-107">[in] size of the input buffer to be passed in.</span></span>

`inBuffer`\
<span data-ttu-id="037d7-108">[in，size_is(inBufferSize)]要在请求中发送的原始数据的缓冲区指针。</span><span class="sxs-lookup"><span data-stu-id="037d7-108">[in, size_is(inBufferSize)] Buffer pointer for the raw data to be sent in the request.</span></span>

`outBufferSize`\
<span data-ttu-id="037d7-109">[in]输出缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="037d7-109">[in] Size of the output buffer.</span></span>

`outBuffer`\
<span data-ttu-id="037d7-110">[out，size_is(outBufferSize)]要用于存储请求响应的缓冲区指针。</span><span class="sxs-lookup"><span data-stu-id="037d7-110">[out, size_is(outBufferSize)] Buffer pointer to used to store the request response.</span></span>

## <a name="remarks"></a><span data-ttu-id="037d7-111">备注</span><span class="sxs-lookup"><span data-stu-id="037d7-111">Remarks</span></span>

<span data-ttu-id="037d7-112">提供的方法属于`IXCLRDataModule`接口，并对应于虚拟方法表 36th 槽。</span><span class="sxs-lookup"><span data-stu-id="037d7-112">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 36th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="037d7-113">要求</span><span class="sxs-lookup"><span data-stu-id="037d7-113">Requirements</span></span>

<span data-ttu-id="037d7-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="037d7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>
<span data-ttu-id="037d7-115">**标头：** 无**库：** 无 **.NET Framework 版本：** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="037d7-115">**Header:** None **Library:** None **.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="037d7-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="037d7-116">See also</span></span>

- [<span data-ttu-id="037d7-117">调试</span><span class="sxs-lookup"><span data-stu-id="037d7-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="037d7-118">IXCLRDataModule 接口</span><span class="sxs-lookup"><span data-stu-id="037d7-118">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
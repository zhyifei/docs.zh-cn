---
title: ICLRDataTarget::SetTLSValue 方法
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.SetTLSValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::SetTLSValue
helpviewer_keywords:
- ICLRDataTarget::SetTLSValue method [.NET Framework debugging]
- SetTLSValue method [.NET Framework debugging]
ms.assetid: 4a2d6a24-749a-47ad-9f01-4517203d3f35
topic_type:
- apiref
ms.openlocfilehash: 1425d48bb18d4161a1c96239b76b8315ae258705
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73112782"
---
# <a name="iclrdatatargetsettlsvalue-method"></a><span data-ttu-id="9f00c-102">ICLRDataTarget::SetTLSValue 方法</span><span class="sxs-lookup"><span data-stu-id="9f00c-102">ICLRDataTarget::SetTLSValue Method</span></span>
<span data-ttu-id="9f00c-103">在目标进程中指定线程的线程本地存储（TLS）中设置一个值。</span><span class="sxs-lookup"><span data-stu-id="9f00c-103">Sets a value in the thread local storage (TLS) of the specified thread in the target process.</span></span> <span data-ttu-id="9f00c-104">此方法由公共语言运行时（CLR）数据访问服务调用。</span><span class="sxs-lookup"><span data-stu-id="9f00c-104">This method is called by the common language runtime (CLR) data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f00c-105">语法</span><span class="sxs-lookup"><span data-stu-id="9f00c-105">Syntax</span></span>  
  
```cpp  
HRESULT SetTLSValue (  
    [in] ULONG32            threadID,  
    [in] ULONG32            index,  
    [in] CLRDATA_ADDRESS    value  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f00c-106">参数</span><span class="sxs-lookup"><span data-stu-id="9f00c-106">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="9f00c-107">中目标进程中的线程的操作系统标识符。</span><span class="sxs-lookup"><span data-stu-id="9f00c-107">[in] The operating system identifier of a thread in the target process.</span></span>  
  
 `index`  
 <span data-ttu-id="9f00c-108">中位置的索引。</span><span class="sxs-lookup"><span data-stu-id="9f00c-108">[in] The index of the location.</span></span> <span data-ttu-id="9f00c-109">此值必须是指定线程的本地存储区中的有效索引。</span><span class="sxs-lookup"><span data-stu-id="9f00c-109">This value must be a valid index in the local store of the specified thread.</span></span>  
  
 `value`  
 <span data-ttu-id="9f00c-110">中一个 `CLRDATA_ADDRESS` 值，该值指定要置于给定 TLS 位置的值。</span><span class="sxs-lookup"><span data-stu-id="9f00c-110">[in] A `CLRDATA_ADDRESS` value that specifies the value to place in the given TLS location.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f00c-111">备注</span><span class="sxs-lookup"><span data-stu-id="9f00c-111">Remarks</span></span>  
 <span data-ttu-id="9f00c-112">此方法由调试应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="9f00c-112">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f00c-113">要求</span><span class="sxs-lookup"><span data-stu-id="9f00c-113">Requirements</span></span>  
 <span data-ttu-id="9f00c-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9f00c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f00c-115">**标头：** ClrData，ClrData</span><span class="sxs-lookup"><span data-stu-id="9f00c-115">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="9f00c-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f00c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f00c-117">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f00c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f00c-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="9f00c-118">See also</span></span>

- [<span data-ttu-id="9f00c-119">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="9f00c-119">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)

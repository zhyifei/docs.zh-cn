---
title: ICLRDataTarget::GetPointerSize 方法
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetPointerSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetPointerSize
helpviewer_keywords:
- GetPointerSize method [.NET Framework debugging]
- ICLRDataTarget::GetPointerSize method [.NET Framework debugging]
ms.assetid: 51d9f4a4-81a7-4527-8537-5212bdb05c70
topic_type:
- apiref
ms.openlocfilehash: 7a274aaec4919b86f32f98e4d8278dc12748fb2b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785477"
---
# <a name="iclrdatatargetgetpointersize-method"></a><span data-ttu-id="b06de-102">ICLRDataTarget::GetPointerSize 方法</span><span class="sxs-lookup"><span data-stu-id="b06de-102">ICLRDataTarget::GetPointerSize Method</span></span>
<span data-ttu-id="b06de-103">获取目标进程使用的指针类型的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="b06de-103">Gets the size, in bytes, of the pointer type that the target process uses.</span></span> <span data-ttu-id="b06de-104">此方法由公共语言运行时数据访问服务调用。</span><span class="sxs-lookup"><span data-stu-id="b06de-104">This method is called by the common language runtime data access services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b06de-105">语法</span><span class="sxs-lookup"><span data-stu-id="b06de-105">Syntax</span></span>  
  
```cpp  
HRESULT GetPointerSize (  
    [out] ULONG32     *pointerSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b06de-106">参数</span><span class="sxs-lookup"><span data-stu-id="b06de-106">Parameters</span></span>  
 `pointerSize`  
 <span data-ttu-id="b06de-107">弄指向一个整数值的指针，该整数值指定目标进程上的指针的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="b06de-107">[out] A pointer to an integer value that specifies the size, in bytes, of a pointer on the target process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b06de-108">备注</span><span class="sxs-lookup"><span data-stu-id="b06de-108">Remarks</span></span>  
 <span data-ttu-id="b06de-109">此方法由调试应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="b06de-109">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b06de-110">需求</span><span class="sxs-lookup"><span data-stu-id="b06de-110">Requirements</span></span>  
 <span data-ttu-id="b06de-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b06de-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b06de-112">**标头：** ClrData，ClrData</span><span class="sxs-lookup"><span data-stu-id="b06de-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="b06de-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b06de-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b06de-114">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b06de-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b06de-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b06de-115">See also</span></span>

- [<span data-ttu-id="b06de-116">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="b06de-116">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)

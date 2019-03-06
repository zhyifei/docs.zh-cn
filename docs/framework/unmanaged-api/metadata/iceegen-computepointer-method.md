---
title: ICeeGen::ComputePointer 方法
ms.date: 03/30/2017
api_name:
- ICeeGen.ComputePointer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::ComputePointer
helpviewer_keywords:
- ICeeGen::ComputePointer method [.NET Framework metadata]
- ComputePointer method [.NET Framework metadata]
ms.assetid: b6b95c04-0f2c-4fcc-a8bc-3b1dcbdba731
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5fb63d4fe1e736ca1ff0c729d8d83cfe092eaaf5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57465525"
---
# <a name="iceegencomputepointer-method"></a><span data-ttu-id="83e7a-102">ICeeGen::ComputePointer 方法</span><span class="sxs-lookup"><span data-stu-id="83e7a-102">ICeeGen::ComputePointer Method</span></span>
<span data-ttu-id="83e7a-103">确定指定的代码部分的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="83e7a-103">Determines the buffer for the specified code section.</span></span>  
  
 <span data-ttu-id="83e7a-104">此方法已过时，不应使用。</span><span class="sxs-lookup"><span data-stu-id="83e7a-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83e7a-105">语法</span><span class="sxs-lookup"><span data-stu-id="83e7a-105">Syntax</span></span>  
  
```  
HRESULT ComputePointer (  
    [in]  HCEESECTION  section,  
    [in]  ULONG        RVA,   
    [out] UCHAR        **lpBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83e7a-106">参数</span><span class="sxs-lookup"><span data-stu-id="83e7a-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="83e7a-107">[in]要为其返回缓冲区在代码部分。</span><span class="sxs-lookup"><span data-stu-id="83e7a-107">[in] The code section for which to return a buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="83e7a-108">[in]要为其获取一个指针，该方法相对虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="83e7a-108">[in] The relative virtual address of the method for which to get a pointer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="83e7a-109">[out]指向返回的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="83e7a-109">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83e7a-110">要求</span><span class="sxs-lookup"><span data-stu-id="83e7a-110">Requirements</span></span>  
 <span data-ttu-id="83e7a-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="83e7a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83e7a-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="83e7a-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="83e7a-113">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="83e7a-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="83e7a-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83e7a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83e7a-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="83e7a-115">See also</span></span>
- [<span data-ttu-id="83e7a-116">ICeeGen 接口</span><span class="sxs-lookup"><span data-stu-id="83e7a-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

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
ms.openlocfilehash: 9587bbe8f087fd9a51bba67492af1d5acb53ae4a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176092"
---
# <a name="iceegencomputepointer-method"></a><span data-ttu-id="340b9-102">ICeeGen::ComputePointer 方法</span><span class="sxs-lookup"><span data-stu-id="340b9-102">ICeeGen::ComputePointer Method</span></span>
<span data-ttu-id="340b9-103">确定指定代码部分的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="340b9-103">Determines the buffer for the specified code section.</span></span>  
  
 <span data-ttu-id="340b9-104">此方法已过时，不应使用。</span><span class="sxs-lookup"><span data-stu-id="340b9-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="340b9-105">语法</span><span class="sxs-lookup"><span data-stu-id="340b9-105">Syntax</span></span>  
  
```cpp  
HRESULT ComputePointer (  
    [in]  HCEESECTION  section,  
    [in]  ULONG        RVA,
    [out] UCHAR        **lpBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="340b9-106">parameters</span><span class="sxs-lookup"><span data-stu-id="340b9-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="340b9-107">[在]要为其返回缓冲区的代码部分。</span><span class="sxs-lookup"><span data-stu-id="340b9-107">[in] The code section for which to return a buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="340b9-108">[在]要为其获取指针的方法的相对虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="340b9-108">[in] The relative virtual address of the method for which to get a pointer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="340b9-109">[出]指向返回的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="340b9-109">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="340b9-110">要求</span><span class="sxs-lookup"><span data-stu-id="340b9-110">Requirements</span></span>  
 <span data-ttu-id="340b9-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="340b9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="340b9-112">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="340b9-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="340b9-113">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="340b9-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="340b9-114">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="340b9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="340b9-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="340b9-115">See also</span></span>

- [<span data-ttu-id="340b9-116">ICeeGen 接口</span><span class="sxs-lookup"><span data-stu-id="340b9-116">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

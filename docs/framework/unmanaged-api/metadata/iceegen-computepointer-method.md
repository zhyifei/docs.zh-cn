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
ms.openlocfilehash: 206dcd3a0a82da9b6211c8c2045e4e9d3d991973
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008867"
---
# <a name="iceegencomputepointer-method"></a><span data-ttu-id="86a0f-102">ICeeGen::ComputePointer 方法</span><span class="sxs-lookup"><span data-stu-id="86a0f-102">ICeeGen::ComputePointer Method</span></span>
<span data-ttu-id="86a0f-103">确定指定代码节的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="86a0f-103">Determines the buffer for the specified code section.</span></span>  
  
 <span data-ttu-id="86a0f-104">此方法已过时，不应使用。</span><span class="sxs-lookup"><span data-stu-id="86a0f-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86a0f-105">语法</span><span class="sxs-lookup"><span data-stu-id="86a0f-105">Syntax</span></span>  
  
```cpp  
HRESULT ComputePointer (  
    [in]  HCEESECTION  section,  
    [in]  ULONG        RVA,
    [out] UCHAR        **lpBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86a0f-106">参数</span><span class="sxs-lookup"><span data-stu-id="86a0f-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="86a0f-107">中要为其返回缓冲区的代码部分。</span><span class="sxs-lookup"><span data-stu-id="86a0f-107">[in] The code section for which to return a buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="86a0f-108">中要为其获取指针的方法的相对虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="86a0f-108">[in] The relative virtual address of the method for which to get a pointer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="86a0f-109">弄指向返回的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="86a0f-109">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86a0f-110">要求</span><span class="sxs-lookup"><span data-stu-id="86a0f-110">Requirements</span></span>  
 <span data-ttu-id="86a0f-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="86a0f-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86a0f-112">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="86a0f-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="86a0f-113">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="86a0f-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="86a0f-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86a0f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86a0f-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86a0f-115">See also</span></span>

- [<span data-ttu-id="86a0f-116">ICeeGen 接口</span><span class="sxs-lookup"><span data-stu-id="86a0f-116">ICeeGen Interface</span></span>](iceegen-interface.md)

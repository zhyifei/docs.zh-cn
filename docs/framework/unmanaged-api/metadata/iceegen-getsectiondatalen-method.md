---
title: ICeeGen::GetSectionDataLen 方法
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionDataLen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionDataLen
helpviewer_keywords:
- ICeeGen::GetSectionDataLen method [.NET Framework metadata]
- GetSectionDataLen method [.NET Framework metadata]
ms.assetid: e2a06ee4-b8ee-49c7-935a-c1031a29eef2
topic_type:
- apiref
ms.openlocfilehash: 277e2584049fae397cf91281a65d05b0b49d9454
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448088"
---
# <a name="iceegengetsectiondatalen-method"></a><span data-ttu-id="dc4f0-102">ICeeGen::GetSectionDataLen 方法</span><span class="sxs-lookup"><span data-stu-id="dc4f0-102">ICeeGen::GetSectionDataLen Method</span></span>
<span data-ttu-id="dc4f0-103">获取指定节的长度。</span><span class="sxs-lookup"><span data-stu-id="dc4f0-103">Gets the length of the specified section.</span></span>  
  
 <span data-ttu-id="dc4f0-104">此方法已过时，不应使用。</span><span class="sxs-lookup"><span data-stu-id="dc4f0-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc4f0-105">语法</span><span class="sxs-lookup"><span data-stu-id="dc4f0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSectionDataLen (  
    [in]  HCEESECTION  section,  
    [out] ULONG        *dataLen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc4f0-106">参数</span><span class="sxs-lookup"><span data-stu-id="dc4f0-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="dc4f0-107">中将检索其长度的数据部分。</span><span class="sxs-lookup"><span data-stu-id="dc4f0-107">[in] The data section whose length will be retrieved.</span></span>  
  
 `dataLen`  
 <span data-ttu-id="dc4f0-108">弄指定节的返回长度。</span><span class="sxs-lookup"><span data-stu-id="dc4f0-108">[out] The returned length of the specified section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc4f0-109">备注</span><span class="sxs-lookup"><span data-stu-id="dc4f0-109">Remarks</span></span>  
 <span data-ttu-id="dc4f0-110">仅当你有其他方法未处理的特殊部分要求时，才调用 `GetSectionDataLen`。</span><span class="sxs-lookup"><span data-stu-id="dc4f0-110">Call `GetSectionDataLen` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc4f0-111">要求</span><span class="sxs-lookup"><span data-stu-id="dc4f0-111">Requirements</span></span>  
 <span data-ttu-id="dc4f0-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dc4f0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc4f0-113">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="dc4f0-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dc4f0-114">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="dc4f0-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dc4f0-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc4f0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc4f0-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc4f0-116">See also</span></span>

- [<span data-ttu-id="dc4f0-117">ICeeGen 接口</span><span class="sxs-lookup"><span data-stu-id="dc4f0-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)

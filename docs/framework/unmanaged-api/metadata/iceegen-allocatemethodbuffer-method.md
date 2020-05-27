---
title: ICeeGen::AllocateMethodBuffer 方法
ms.date: 03/30/2017
api_name:
- ICeeGen.AllocateMethodBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::AllocateMethodBuffer
helpviewer_keywords:
- AllocateMethodBuffer method [.NET Framework metadata]
- ICeeGen::AllocateMethodBuffer method [.NET Framework metadata]
ms.assetid: 845ab77e-9639-47f5-99fb-f3b619e3e779
topic_type:
- apiref
ms.openlocfilehash: 8dc7f439cac56c2d55916ff8631ec3095c67680d
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008880"
---
# <a name="iceegenallocatemethodbuffer-method"></a><span data-ttu-id="71ca6-102">ICeeGen::AllocateMethodBuffer 方法</span><span class="sxs-lookup"><span data-stu-id="71ca6-102">ICeeGen::AllocateMethodBuffer Method</span></span>
<span data-ttu-id="71ca6-103">为方法创建指定大小的缓冲区，并获取该方法的相对虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="71ca6-103">Creates a buffer of the specified size for a method, and gets the relative virtual address of the method.</span></span>  
  
 <span data-ttu-id="71ca6-104">此方法已过时，不应使用。</span><span class="sxs-lookup"><span data-stu-id="71ca6-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71ca6-105">语法</span><span class="sxs-lookup"><span data-stu-id="71ca6-105">Syntax</span></span>  
  
```cpp  
HRESULT AllocateMethodBuffer (
    [in]  ULONG    cchBuffer,
    [out] UCHAR    **lpBuffer,  
    [out] ULONG    *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71ca6-106">参数</span><span class="sxs-lookup"><span data-stu-id="71ca6-106">Parameters</span></span>  
 `cchBuffer`  
 <span data-ttu-id="71ca6-107">中要创建的缓冲区的长度。</span><span class="sxs-lookup"><span data-stu-id="71ca6-107">[in] The length of the buffer to create.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="71ca6-108">弄返回的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="71ca6-108">[out] The returned buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="71ca6-109">弄方法的相对虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="71ca6-109">[out] The relative virtual address of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71ca6-110">要求</span><span class="sxs-lookup"><span data-stu-id="71ca6-110">Requirements</span></span>  
 <span data-ttu-id="71ca6-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="71ca6-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71ca6-112">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="71ca6-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="71ca6-113">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="71ca6-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="71ca6-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71ca6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71ca6-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="71ca6-115">See also</span></span>

- [<span data-ttu-id="71ca6-116">ICeeGen 接口</span><span class="sxs-lookup"><span data-stu-id="71ca6-116">ICeeGen Interface</span></span>](iceegen-interface.md)

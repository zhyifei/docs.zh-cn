---
title: ICLRDataTarget::GetImageBase 方法
ms.date: 03/30/2017
api_name:
- ICLRDataTarget.GetImageBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget::GetImageBase
helpviewer_keywords:
- ICLRDataTarget::GetImageBase method [.NET Framework debugging]
- GetImageBase method [.NET Framework debugging]
ms.assetid: 091c5f32-c160-49e3-a75f-4692e084c8e4
topic_type:
- apiref
ms.openlocfilehash: 71b07e11cd3fec1a0dbebe986d98067c2e6f18e1
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860630"
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="1d738-102">ICLRDataTarget::GetImageBase 方法</span><span class="sxs-lookup"><span data-stu-id="1d738-102">ICLRDataTarget::GetImageBase Method</span></span>
<span data-ttu-id="1d738-103">获取指定的图像的基本内存地址。</span><span class="sxs-lookup"><span data-stu-id="1d738-103">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d738-104">语法</span><span class="sxs-lookup"><span data-stu-id="1d738-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d738-105">参数</span><span class="sxs-lookup"><span data-stu-id="1d738-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="1d738-106">中图像的文件名，包括其路径。</span><span class="sxs-lookup"><span data-stu-id="1d738-106">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="1d738-107">弄指向存储图像基址的 CLRDATA_ADDRESS 的指针。</span><span class="sxs-lookup"><span data-stu-id="1d738-107">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1d738-108">备注</span><span class="sxs-lookup"><span data-stu-id="1d738-108">Remarks</span></span>  
 <span data-ttu-id="1d738-109">图像文件名可以是也可以没有路径。</span><span class="sxs-lookup"><span data-stu-id="1d738-109">The image file name may or may not have a path.</span></span> <span data-ttu-id="1d738-110">如果指定了路径，则在整个路径上完成匹配;否则，仅对文件名执行匹配。</span><span class="sxs-lookup"><span data-stu-id="1d738-110">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d738-111">要求</span><span class="sxs-lookup"><span data-stu-id="1d738-111">Requirements</span></span>  
 <span data-ttu-id="1d738-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1d738-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d738-113">**标头：** ClrData，ClrData</span><span class="sxs-lookup"><span data-stu-id="1d738-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="1d738-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d738-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d738-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d738-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d738-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1d738-116">See also</span></span>

- [<span data-ttu-id="1d738-117">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="1d738-117">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)

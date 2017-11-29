---
title: "ICLRDataTarget::GetImageBase 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget.GetImageBase
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget::GetImageBase
helpviewer_keywords:
- ICLRDataTarget::GetImageBase method [.NET Framework debugging]
- GetImageBase method [.NET Framework debugging]
ms.assetid: 091c5f32-c160-49e3-a75f-4692e084c8e4
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1d397995266d6063164510a4b563ba94f7f54950
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="dbe6d-102">ICLRDataTarget::GetImageBase 方法</span><span class="sxs-lookup"><span data-stu-id="dbe6d-102">ICLRDataTarget::GetImageBase Method</span></span>
<span data-ttu-id="dbe6d-103">获取指定的映像的基的内存地址。</span><span class="sxs-lookup"><span data-stu-id="dbe6d-103">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbe6d-104">语法</span><span class="sxs-lookup"><span data-stu-id="dbe6d-104">Syntax</span></span>  
  
```  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dbe6d-105">参数</span><span class="sxs-lookup"><span data-stu-id="dbe6d-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="dbe6d-106">[in]映像，包括其路径的文件名称。</span><span class="sxs-lookup"><span data-stu-id="dbe6d-106">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="dbe6d-107">[out]指向将存储映像的基址 CLRDATA_ADDRESS 的指针。</span><span class="sxs-lookup"><span data-stu-id="dbe6d-107">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dbe6d-108">备注</span><span class="sxs-lookup"><span data-stu-id="dbe6d-108">Remarks</span></span>  
 <span data-ttu-id="dbe6d-109">图像文件名称可能或可能不包含路径。</span><span class="sxs-lookup"><span data-stu-id="dbe6d-109">The image file name may or may not have a path.</span></span> <span data-ttu-id="dbe6d-110">如果指定的路径，在整个路径; 上完成匹配否则，匹配仅对进行的文件名称。</span><span class="sxs-lookup"><span data-stu-id="dbe6d-110">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbe6d-111">要求</span><span class="sxs-lookup"><span data-stu-id="dbe6d-111">Requirements</span></span>  
 <span data-ttu-id="dbe6d-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="dbe6d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbe6d-113">**标头：** ClrData.idl、 ClrData.h</span><span class="sxs-lookup"><span data-stu-id="dbe6d-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="dbe6d-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dbe6d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dbe6d-115">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbe6d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbe6d-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dbe6d-116">See Also</span></span>  
 [<span data-ttu-id="dbe6d-117">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="dbe6d-117">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)

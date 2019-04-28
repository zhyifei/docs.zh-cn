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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e823911280f52e16c745c9c77fe17b49bd35dc0b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61698273"
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="95656-102">ICLRDataTarget::GetImageBase 方法</span><span class="sxs-lookup"><span data-stu-id="95656-102">ICLRDataTarget::GetImageBase Method</span></span>
<span data-ttu-id="95656-103">获取指定的图像的基础内存地址。</span><span class="sxs-lookup"><span data-stu-id="95656-103">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95656-104">语法</span><span class="sxs-lookup"><span data-stu-id="95656-104">Syntax</span></span>  
  
```  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95656-105">参数</span><span class="sxs-lookup"><span data-stu-id="95656-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="95656-106">[in]映像，包括其路径的文件名。</span><span class="sxs-lookup"><span data-stu-id="95656-106">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="95656-107">[out]指向将存储映像的基址 CLRDATA_ADDRESS 的指针。</span><span class="sxs-lookup"><span data-stu-id="95656-107">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="95656-108">备注</span><span class="sxs-lookup"><span data-stu-id="95656-108">Remarks</span></span>  
 <span data-ttu-id="95656-109">图像文件名称可能或可能不具有路径。</span><span class="sxs-lookup"><span data-stu-id="95656-109">The image file name may or may not have a path.</span></span> <span data-ttu-id="95656-110">如果指定了路径，则整个路径; 上执行匹配否则，匹配仅上完成的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="95656-110">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95656-111">要求</span><span class="sxs-lookup"><span data-stu-id="95656-111">Requirements</span></span>  
 <span data-ttu-id="95656-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="95656-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95656-113">**标头：** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="95656-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="95656-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95656-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95656-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95656-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95656-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="95656-116">See also</span></span>

- [<span data-ttu-id="95656-117">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="95656-117">ICLRDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)

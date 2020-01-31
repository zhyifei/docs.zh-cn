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
ms.openlocfilehash: fcf0ab73c79a5fa116a89cdfcc2e73b17d9eabfc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76785497"
---
# <a name="iclrdatatargetgetimagebase-method"></a><span data-ttu-id="4754d-102">ICLRDataTarget::GetImageBase 方法</span><span class="sxs-lookup"><span data-stu-id="4754d-102">ICLRDataTarget::GetImageBase Method</span></span>
<span data-ttu-id="4754d-103">获取指定的图像的基本内存地址。</span><span class="sxs-lookup"><span data-stu-id="4754d-103">Gets the base memory address of the specified image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4754d-104">语法</span><span class="sxs-lookup"><span data-stu-id="4754d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageBase (  
    [in, string] LPCWSTR    imagePath,  
    [out] CLRDATA_ADDRESS   *baseAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4754d-105">参数</span><span class="sxs-lookup"><span data-stu-id="4754d-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="4754d-106">中图像的文件名，包括其路径。</span><span class="sxs-lookup"><span data-stu-id="4754d-106">[in] The file name of the image, including its path.</span></span>  
  
 `baseAddress`  
 <span data-ttu-id="4754d-107">弄指向存储图像基址的 CLRDATA_ADDRESS 的指针。</span><span class="sxs-lookup"><span data-stu-id="4754d-107">[out] A pointer to a CLRDATA_ADDRESS that stores the base address of the image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4754d-108">备注</span><span class="sxs-lookup"><span data-stu-id="4754d-108">Remarks</span></span>  
 <span data-ttu-id="4754d-109">图像文件名可以是也可以没有路径。</span><span class="sxs-lookup"><span data-stu-id="4754d-109">The image file name may or may not have a path.</span></span> <span data-ttu-id="4754d-110">如果指定了路径，则在整个路径上完成匹配;否则，仅对文件名执行匹配。</span><span class="sxs-lookup"><span data-stu-id="4754d-110">If a path is specified, matching is done on the whole path; otherwise, matching is done only on the file name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4754d-111">需求</span><span class="sxs-lookup"><span data-stu-id="4754d-111">Requirements</span></span>  
 <span data-ttu-id="4754d-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4754d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4754d-113">**标头：** ClrData，ClrData</span><span class="sxs-lookup"><span data-stu-id="4754d-113">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="4754d-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4754d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4754d-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4754d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4754d-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4754d-116">See also</span></span>

- [<span data-ttu-id="4754d-117">ICLRDataTarget 接口</span><span class="sxs-lookup"><span data-stu-id="4754d-117">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)

---
title: ICLRMetadataLocator::GetMetadata 方法
ms.date: 03/30/2017
api_name:
- ICLRMetadataLocator.GetMetadata
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRMetadataLocator::GetMetadata
helpviewer_keywords:
- GetMetadata method, ICLRMetadataLocator interface [.NET Framework debugging]
- ICLRMetadataLocator::GetMetadata method [.NET Framework debugging]
ms.assetid: 704a8893-ac56-43b4-90ea-715f38ccb40e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4338619414c9c9ac8c5fe85479562410d1678698
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403853"
---
# <a name="iclrmetadatalocatorgetmetadata-method"></a><span data-ttu-id="8b1c5-102">ICLRMetadataLocator::GetMetadata 方法</span><span class="sxs-lookup"><span data-stu-id="8b1c5-102">ICLRMetadataLocator::GetMetadata Method</span></span>
<span data-ttu-id="8b1c5-103">调用由公共语言运行时 (CLR) 数据访问服务以检索图像的元数据。</span><span class="sxs-lookup"><span data-stu-id="8b1c5-103">Called by the common language runtime (CLR) data access services to retrieve the metadata of an image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b1c5-104">语法</span><span class="sxs-lookup"><span data-stu-id="8b1c5-104">Syntax</span></span>  
  
```  
HRESULT GetMetadata(  
    [in]  LPCWSTR         imagePath,  
    [in]  ULONG32         imageTimestamp,  
    [in]  ULONG32         imageSize,  
    [in]  GUID*           mvid,  
    [in]  ULONG32         mdRva,  
    [in]  ULONG32         flags,  
    [in]  ULONG32         bufferSize,  
    [out, size_is(bufferSize), length_is(*dataSize)]  
          BYTE*           buffer,  
    [out] ULONG32*        dataSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8b1c5-105">参数</span><span class="sxs-lookup"><span data-stu-id="8b1c5-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="8b1c5-106">[in]一个字符串，指定图像文件的路径。</span><span class="sxs-lookup"><span data-stu-id="8b1c5-106">[in] A string that specifies the path of the image file.</span></span>  
  
 `imageTimestamp`  
 <span data-ttu-id="8b1c5-107">[in]图像文件的时间戳。</span><span class="sxs-lookup"><span data-stu-id="8b1c5-107">[in] The time stamp of the image file.</span></span>  
  
 `imageSize`  
 <span data-ttu-id="8b1c5-108">[in]图像文件的大小。</span><span class="sxs-lookup"><span data-stu-id="8b1c5-108">[in] The size of the image file.</span></span>  
  
 `mvid`  
 <span data-ttu-id="8b1c5-109">[in]图像的全局唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="8b1c5-109">[in] The globally unique identifier of the image.</span></span>  
  
 `mdRva`  
 <span data-ttu-id="8b1c5-110">[in]相对虚拟地址 (RVA) 的元数据。</span><span class="sxs-lookup"><span data-stu-id="8b1c5-110">[in] The relative virtual address (RVA) of the metadata.</span></span> <span data-ttu-id="8b1c5-111">该地址是相对于映像的基址。</span><span class="sxs-lookup"><span data-stu-id="8b1c5-111">The address is relative to the image base address.</span></span>  
  
 `flags`  
 <span data-ttu-id="8b1c5-112">[in]留待将来使用。</span><span class="sxs-lookup"><span data-stu-id="8b1c5-112">[in] Reserved for future use.</span></span>  
  
 `bufferSize`  
 <span data-ttu-id="8b1c5-113">[in]要在其中放置元数据缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="8b1c5-113">[in] The size of the buffer in which to place the metadata.</span></span>  
  
 `buffer`  
 <span data-ttu-id="8b1c5-114">[out]要在其中放置元数据缓冲区。</span><span class="sxs-lookup"><span data-stu-id="8b1c5-114">[out] The buffer in which to place the metadata.</span></span>  
  
 `dataSize`  
 <span data-ttu-id="8b1c5-115">[out]返回的元数据的大小。</span><span class="sxs-lookup"><span data-stu-id="8b1c5-115">[out] The size of the metadata that is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b1c5-116">备注</span><span class="sxs-lookup"><span data-stu-id="8b1c5-116">Remarks</span></span>  
 <span data-ttu-id="8b1c5-117">此方法由调试应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="8b1c5-117">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b1c5-118">要求</span><span class="sxs-lookup"><span data-stu-id="8b1c5-118">Requirements</span></span>  
 <span data-ttu-id="8b1c5-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8b1c5-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b1c5-120">**标头：** ClrData.idl、 ClrData.h</span><span class="sxs-lookup"><span data-stu-id="8b1c5-120">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="8b1c5-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8b1c5-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8b1c5-122">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b1c5-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b1c5-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="8b1c5-123">See Also</span></span>  
 [<span data-ttu-id="8b1c5-124">ICLRMetadataLocator 接口</span><span class="sxs-lookup"><span data-stu-id="8b1c5-124">ICLRMetadataLocator Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-interface.md)

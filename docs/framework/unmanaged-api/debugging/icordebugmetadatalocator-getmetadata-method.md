---
title: ICorDebugMetaDataLocator::GetMetaData 方法
ms.date: 03/30/2017
api_name:
- ICorDebugMetaDataLocator.GetMetaData
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMetaDataLocator::GetMetaData
helpviewer_keywords:
- ICorDebugMetaDataLocator::GetMetaData method [.NET Framework debugging]
- GetMetaData method, ICorDebugMetaDataLocator interface [.NET Framework debugging]
ms.assetid: f9b0ff22-54db-45eb-9cc3-508000a3141d
topic_type:
- apiref
ms.openlocfilehash: 43f3c1dd866b98bff51b375a11e28727e41d3ead
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793053"
---
# <a name="icordebugmetadatalocatorgetmetadata-method"></a><span data-ttu-id="975cc-102">ICorDebugMetaDataLocator::GetMetaData 方法</span><span class="sxs-lookup"><span data-stu-id="975cc-102">ICorDebugMetaDataLocator::GetMetaData Method</span></span>
<span data-ttu-id="975cc-103">要求调试器返回模块（完成该调试器请求的操作需要其元数据）的完整路径。</span><span class="sxs-lookup"><span data-stu-id="975cc-103">Asks the debugger to return the full path to a module whose metadata is needed to complete an operation the debugger requested.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="975cc-104">语法</span><span class="sxs-lookup"><span data-stu-id="975cc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaData(  
      [in] LPCWSTR wszImagePath,  
      [in] DWORD   dwImageTimeStamp,  
      [in] DWORD   dwImageSize,  
      [in] ULONG32 cchPathBuffer,  
      [out] ULONG32 * pcchPathBuffer,  
      [out, size_is(cchPathBuffer), length_is(*pcchPathBuffer)]  
               WCHAR wszPathBuffer[]  
      );  
```  
  
## <a name="parameters"></a><span data-ttu-id="975cc-105">参数</span><span class="sxs-lookup"><span data-stu-id="975cc-105">Parameters</span></span>  
 `wszImagePath`  
 <span data-ttu-id="975cc-106">[in] 以 null 结尾的字符串，表示文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="975cc-106">[in] A null-terminated string that represents the full path to the file.</span></span> <span data-ttu-id="975cc-107">如果完整路径不可用，则为该文件的名称和扩展名（*文件名*）。*扩展名*）。</span><span class="sxs-lookup"><span data-stu-id="975cc-107">If the full path is not available, the name and extension of the file (*filename*.*extension*).</span></span>  
  
 `dwImageTimeStamp`  
 <span data-ttu-id="975cc-108">[in] 来自图像 PE 文件头的时间戳。</span><span class="sxs-lookup"><span data-stu-id="975cc-108">[in] The time stamp from the image's PE file headers.</span></span> <span data-ttu-id="975cc-109">此参数可能用于符号服务器（[SymSrv](/windows/desktop/debug/using-symsrv)）查找。</span><span class="sxs-lookup"><span data-stu-id="975cc-109">This parameter can potentially be used for a symbol server ([SymSrv](/windows/desktop/debug/using-symsrv)) lookup.</span></span>  
  
 `dwImageSize`  
 <span data-ttu-id="975cc-110">[in] PE 文件头中的图像大小。</span><span class="sxs-lookup"><span data-stu-id="975cc-110">[in] The image size from PE file headers.</span></span> <span data-ttu-id="975cc-111">此参数可能可以用于 SymSrv 查找。</span><span class="sxs-lookup"><span data-stu-id="975cc-111">This parameter can potentially be used for a SymSrv lookup.</span></span>  
  
 `cchPathBuffer`  
 <span data-ttu-id="975cc-112">[in] `wszPathBuffer` 中的字符计数。</span><span class="sxs-lookup"><span data-stu-id="975cc-112">[in] The character count in `wszPathBuffer`.</span></span>  
  
 `pcchPathBuffer`  
 <span data-ttu-id="975cc-113">[out] 写入 `wszPathBuffer` 的 `WCHAR` 的计数。</span><span class="sxs-lookup"><span data-stu-id="975cc-113">[out] The count of `WCHAR`s written to `wszPathBuffer`.</span></span>  
  
 <span data-ttu-id="975cc-114">如果该方法返回 E_NOT_SUFFICIENT_BUFFER，则包含存储路径所需的 `WCHAR` 计数。</span><span class="sxs-lookup"><span data-stu-id="975cc-114">If the method returns E_NOT_SUFFICIENT_BUFFER, contains the count of `WCHAR`s needed to store the path.</span></span>  
  
 `wszPathBuffer`  
 <span data-ttu-id="975cc-115">[out] 指向一个缓冲区的指针，调试器会将包含请求的元数据的文件的完整路径复制到该缓冲区中。</span><span class="sxs-lookup"><span data-stu-id="975cc-115">[out] Pointer to a buffer into which the debugger will copy the full path of the file that contains the requested metadata.</span></span>  
  
 <span data-ttu-id="975cc-116">[CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md)枚举中的 `ofReadOnly` 标志用于请求对此文件中元数据的只读访问。</span><span class="sxs-lookup"><span data-stu-id="975cc-116">The `ofReadOnly` flag from the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration is used to request read-only access to the metadata in this file.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="975cc-117">返回值</span><span class="sxs-lookup"><span data-stu-id="975cc-117">Return Value</span></span>  
 <span data-ttu-id="975cc-118">此方法返回以下特定 HRESULT 以及表示方法失败的 HRESULT 错误。</span><span class="sxs-lookup"><span data-stu-id="975cc-118">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span> <span data-ttu-id="975cc-119">所有其他失败的 HRESULT 均指示文件不可检索。</span><span class="sxs-lookup"><span data-stu-id="975cc-119">All other failure HRESULTs indicate that the file is not retrievable.</span></span>  
  
|<span data-ttu-id="975cc-120">HRESULT</span><span class="sxs-lookup"><span data-stu-id="975cc-120">HRESULT</span></span>|<span data-ttu-id="975cc-121">描述</span><span class="sxs-lookup"><span data-stu-id="975cc-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="975cc-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="975cc-122">S_OK</span></span>|<span data-ttu-id="975cc-123">该方法成功完成。</span><span class="sxs-lookup"><span data-stu-id="975cc-123">The method completed successfully.</span></span> <span data-ttu-id="975cc-124">`wszPathBuffer` 包含文件的完整路径，以 null 结尾。</span><span class="sxs-lookup"><span data-stu-id="975cc-124">`wszPathBuffer` contains the full path to the file and is null-terminated.</span></span>|  
|<span data-ttu-id="975cc-125">E_NOT_SUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="975cc-125">E_NOT_SUFFICIENT_BUFFER</span></span>|<span data-ttu-id="975cc-126">`wszPathBuffer` 的当前大小不足以容纳完整路径。</span><span class="sxs-lookup"><span data-stu-id="975cc-126">The current size of `wszPathBuffer` is not sufficient to hold the full path.</span></span> <span data-ttu-id="975cc-127">在这种情况下，`pcchPathBuffer` 包含所需的 `WCHAR` 计数（包括终止 null 字符），并且使用请求的缓冲区大小第二次调用 `GetMetaData`。</span><span class="sxs-lookup"><span data-stu-id="975cc-127">In this case, `pcchPathBuffer` contains the needed count of `WCHAR`s, including the terminating null character, and `GetMetaData` is called a second time with the requested buffer size.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="975cc-128">备注</span><span class="sxs-lookup"><span data-stu-id="975cc-128">Remarks</span></span>  
 <span data-ttu-id="975cc-129">如果 `wszImagePath` 包含转储中模块的完整路径，则它从收集转储的计算机指定路径。</span><span class="sxs-lookup"><span data-stu-id="975cc-129">If `wszImagePath` contains a full path for a module from a dump, it specifies the path from the computer where the dump was collected.</span></span> <span data-ttu-id="975cc-130">文件可能不位于此位置，或者具有相同名称的不正确文件可能存储在该路径上。</span><span class="sxs-lookup"><span data-stu-id="975cc-130">The file may not exist at this location, or an incorrect file with the same name may be stored on the path.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="975cc-131">需求</span><span class="sxs-lookup"><span data-stu-id="975cc-131">Requirements</span></span>  
 <span data-ttu-id="975cc-132">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="975cc-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="975cc-133">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="975cc-133">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="975cc-134">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="975cc-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="975cc-135">**.NET Framework 版本：** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="975cc-135">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="975cc-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="975cc-136">See also</span></span>

- [<span data-ttu-id="975cc-137">ICorDebugThread4 接口</span><span class="sxs-lookup"><span data-stu-id="975cc-137">ICorDebugThread4 Interface</span></span>](icordebugthread4-interface.md)
- [<span data-ttu-id="975cc-138">调试接口</span><span class="sxs-lookup"><span data-stu-id="975cc-138">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="975cc-139">调试</span><span class="sxs-lookup"><span data-stu-id="975cc-139">Debugging</span></span>](index.md)

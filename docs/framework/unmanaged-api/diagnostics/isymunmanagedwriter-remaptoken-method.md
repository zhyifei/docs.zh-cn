---
title: "ISymUnmanagedWriter::RemapToken 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.RemapToken
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::RemapToken
helpviewer_keywords:
- ISymUnmanagedWriter::RemapToken method [.NET Framework debugging]
- RemapToken method [.NET Framework debugging]
ms.assetid: bca92682-ee1e-467f-8fb0-d8d4617f82fe
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 857b68c0443e7b23af30ed64ecc9b78af0b40880
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriterremaptoken-method"></a><span data-ttu-id="c32f1-102">ISymUnmanagedWriter::RemapToken 方法</span><span class="sxs-lookup"><span data-stu-id="c32f1-102">ISymUnmanagedWriter::RemapToken Method</span></span>
<span data-ttu-id="c32f1-103">通知符号编写器元数据标记在发出元数据已被重新映射。</span><span class="sxs-lookup"><span data-stu-id="c32f1-103">Notifies the symbol writer that a metadata token has been remapped as the metadata was emitted.</span></span> <span data-ttu-id="c32f1-104">如果符号编写器已存储在符号存储区中旧的令牌，则它必须的更新使用新值，它存储的令牌必须保存的相应的符号读取器，若要在读取阶段重新映射的映射。</span><span class="sxs-lookup"><span data-stu-id="c32f1-104">If the symbol writer has stored the old token within the symbol store, it must either update the stored token with the new value, or it must save the map for the corresponding symbol reader to remap during the read phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c32f1-105">语法</span><span class="sxs-lookup"><span data-stu-id="c32f1-105">Syntax</span></span>  
  
```  
HRESULT RemapToken(  
    [in] mdToken  oldToken,  
    [in] mdToken  newToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c32f1-106">参数</span><span class="sxs-lookup"><span data-stu-id="c32f1-106">Parameters</span></span>  
 `oldToken`  
 <span data-ttu-id="c32f1-107">[in]已重新映射元数据标记。</span><span class="sxs-lookup"><span data-stu-id="c32f1-107">[in] The metadata token that was remapped.</span></span>  
  
 `newToken`  
 <span data-ttu-id="c32f1-108">[in]到新的元数据标记`oldToken`已重新映射。</span><span class="sxs-lookup"><span data-stu-id="c32f1-108">[in] The new metadata token to which `oldToken` was remapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c32f1-109">返回值</span><span class="sxs-lookup"><span data-stu-id="c32f1-109">Return Value</span></span>  
 <span data-ttu-id="c32f1-110">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="c32f1-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c32f1-111">要求</span><span class="sxs-lookup"><span data-stu-id="c32f1-111">Requirements</span></span>  
 <span data-ttu-id="c32f1-112">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c32f1-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c32f1-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c32f1-113">See Also</span></span>  
 [<span data-ttu-id="c32f1-114">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="c32f1-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

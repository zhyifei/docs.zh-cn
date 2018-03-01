---
title: "ISymUnmanagedWriter::RemapToken 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedWriter.RemapToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::RemapToken
helpviewer_keywords:
- ISymUnmanagedWriter::RemapToken method [.NET Framework debugging]
- RemapToken method [.NET Framework debugging]
ms.assetid: bca92682-ee1e-467f-8fb0-d8d4617f82fe
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 86d6c78a49c55bdc9093241952bee00ee331696e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterremaptoken-method"></a><span data-ttu-id="35d19-102">ISymUnmanagedWriter::RemapToken 方法</span><span class="sxs-lookup"><span data-stu-id="35d19-102">ISymUnmanagedWriter::RemapToken Method</span></span>
<span data-ttu-id="35d19-103">通知符号编写器元数据标记在发出元数据已被重新映射。</span><span class="sxs-lookup"><span data-stu-id="35d19-103">Notifies the symbol writer that a metadata token has been remapped as the metadata was emitted.</span></span> <span data-ttu-id="35d19-104">如果符号编写器已存储在符号存储区中旧的令牌，则它必须的更新使用新值，它存储的令牌必须保存的相应的符号读取器，若要在读取阶段重新映射的映射。</span><span class="sxs-lookup"><span data-stu-id="35d19-104">If the symbol writer has stored the old token within the symbol store, it must either update the stored token with the new value, or it must save the map for the corresponding symbol reader to remap during the read phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35d19-105">语法</span><span class="sxs-lookup"><span data-stu-id="35d19-105">Syntax</span></span>  
  
```  
HRESULT RemapToken(  
    [in] mdToken  oldToken,  
    [in] mdToken  newToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="35d19-106">参数</span><span class="sxs-lookup"><span data-stu-id="35d19-106">Parameters</span></span>  
 `oldToken`  
 <span data-ttu-id="35d19-107">[in]已重新映射元数据标记。</span><span class="sxs-lookup"><span data-stu-id="35d19-107">[in] The metadata token that was remapped.</span></span>  
  
 `newToken`  
 <span data-ttu-id="35d19-108">[in]到新的元数据标记`oldToken`已重新映射。</span><span class="sxs-lookup"><span data-stu-id="35d19-108">[in] The new metadata token to which `oldToken` was remapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="35d19-109">返回值</span><span class="sxs-lookup"><span data-stu-id="35d19-109">Return Value</span></span>  
 <span data-ttu-id="35d19-110">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="35d19-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35d19-111">惠?</span><span class="sxs-lookup"><span data-stu-id="35d19-111">Requirements</span></span>  
 <span data-ttu-id="35d19-112">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="35d19-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35d19-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="35d19-113">See Also</span></span>  
 [<span data-ttu-id="35d19-114">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="35d19-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)

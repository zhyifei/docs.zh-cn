---
title: ISymUnmanagedSymbolSearchInfo::GetSearchPath 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo.GetSearchPath
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetSearchPath
helpviewer_keywords:
- GetSearchPath method [.NET Framework debugging]
- ISymUnmanagedSymbolSearchInfo::GetSearchPath method [.NET Framework debugging]
ms.assetid: b588d470-53c2-4492-be8c-957323eaca0b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c490ee97a1a74cc6fe29a5b0bbece366db6025a4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpath-method"></a><span data-ttu-id="1176a-102">ISymUnmanagedSymbolSearchInfo::GetSearchPath 方法</span><span class="sxs-lookup"><span data-stu-id="1176a-102">ISymUnmanagedSymbolSearchInfo::GetSearchPath Method</span></span>
<span data-ttu-id="1176a-103">获取搜索路径。</span><span class="sxs-lookup"><span data-stu-id="1176a-103">Gets the search path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1176a-104">语法</span><span class="sxs-lookup"><span data-stu-id="1176a-104">Syntax</span></span>  
  
```  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1176a-105">参数</span><span class="sxs-lookup"><span data-stu-id="1176a-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="1176a-106">[out]指向的指针`ULONG32`接收大小，以字符为单位，包含的搜索路径所需的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="1176a-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1176a-107">返回值</span><span class="sxs-lookup"><span data-stu-id="1176a-107">Return Value</span></span>  
 <span data-ttu-id="1176a-108">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="1176a-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1176a-109">要求</span><span class="sxs-lookup"><span data-stu-id="1176a-109">Requirements</span></span>  
 <span data-ttu-id="1176a-110">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="1176a-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1176a-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="1176a-111">See Also</span></span>  
 [<span data-ttu-id="1176a-112">ISymUnmanagedSymbolSearchInfo 接口</span><span class="sxs-lookup"><span data-stu-id="1176a-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)

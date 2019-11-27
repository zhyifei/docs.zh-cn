---
title: ISymENCUnmanagedMethod::GetFileNameFromOffset 方法
ms.date: 03/30/2017
api_name:
- ISymENCUnmanagedMethod.GetFileNameFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymENCUnmanagedMethod::GetFileNameFromOffset
helpviewer_keywords:
- GetFileNameFromOffset method [.NET Framework debugging]
- ISymENCUnmanagedMethod::GetFileNameFromOffset method [.NET Framework debugging]
ms.assetid: 00e2e194-12f5-436e-a997-2b9d3e844d4f
topic_type:
- apiref
ms.openlocfilehash: 74002ce9c76eebaa3ea5860b09cd3e7c9a884f8d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448653"
---
# <a name="isymencunmanagedmethodgetfilenamefromoffset-method"></a><span data-ttu-id="3b3fd-102">ISymENCUnmanagedMethod::GetFileNameFromOffset 方法</span><span class="sxs-lookup"><span data-stu-id="3b3fd-102">ISymENCUnmanagedMethod::GetFileNameFromOffset Method</span></span>
<span data-ttu-id="3b3fd-103">获取与偏移量关联的行的文件名。</span><span class="sxs-lookup"><span data-stu-id="3b3fd-103">Gets the file name for the line associated with an offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b3fd-104">语法</span><span class="sxs-lookup"><span data-stu-id="3b3fd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFileNameFromOffset(  
    [in]  ULONG32  dwOffset,  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
       length_is(*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b3fd-105">参数</span><span class="sxs-lookup"><span data-stu-id="3b3fd-105">Parameters</span></span>  
 `dwOffset`  
 <span data-ttu-id="3b3fd-106">中一个包含偏移量的 `ULONG32`。</span><span class="sxs-lookup"><span data-stu-id="3b3fd-106">[in] A `ULONG32` that contains the offset.</span></span>  
  
 `cchName`  
 <span data-ttu-id="3b3fd-107">中一个 `ULONG32`，指示 `szName` 缓冲区的大小。</span><span class="sxs-lookup"><span data-stu-id="3b3fd-107">[in] A `ULONG32` that indicates the size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="3b3fd-108">弄指向 `ULONG32` 的指针，该指针接收包含文件名所需的缓冲区大小（以字符数表示）。</span><span class="sxs-lookup"><span data-stu-id="3b3fd-108">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the file names.</span></span>  
  
 `szName`  
 <span data-ttu-id="3b3fd-109">弄包含文件名的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="3b3fd-109">[out] The buffer that contains the file names.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3b3fd-110">返回值</span><span class="sxs-lookup"><span data-stu-id="3b3fd-110">Return Value</span></span>  
 <span data-ttu-id="3b3fd-111">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="3b3fd-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b3fd-112">要求</span><span class="sxs-lookup"><span data-stu-id="3b3fd-112">Requirements</span></span>  
 <span data-ttu-id="3b3fd-113">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="3b3fd-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b3fd-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3b3fd-114">See also</span></span>

- [<span data-ttu-id="3b3fd-115">ISymENCUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="3b3fd-115">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)

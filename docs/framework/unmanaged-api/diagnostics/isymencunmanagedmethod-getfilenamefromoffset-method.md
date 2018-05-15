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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: db3e9cfa73672920ff70d9128541a8f513fca00f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="isymencunmanagedmethodgetfilenamefromoffset-method"></a><span data-ttu-id="05086-102">ISymENCUnmanagedMethod::GetFileNameFromOffset 方法</span><span class="sxs-lookup"><span data-stu-id="05086-102">ISymENCUnmanagedMethod::GetFileNameFromOffset Method</span></span>
<span data-ttu-id="05086-103">获取与偏移量关联的行的文件名称。</span><span class="sxs-lookup"><span data-stu-id="05086-103">Gets the file name for the line associated with an offset.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05086-104">语法</span><span class="sxs-lookup"><span data-stu-id="05086-104">Syntax</span></span>  
  
```  
HRESULT GetFileNameFromOffset(  
    [in]  ULONG32  dwOffset,  
    [in]  ULONG32  cchName,  
    [out] ULONG32  *pcchName,  
    [out, size_is(cchName),  
       length_is(*pcchName)] WCHAR szName[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="05086-105">参数</span><span class="sxs-lookup"><span data-stu-id="05086-105">Parameters</span></span>  
 `dwOffset`  
 <span data-ttu-id="05086-106">[in]A`ULONG32`包含的偏移量。</span><span class="sxs-lookup"><span data-stu-id="05086-106">[in] A `ULONG32` that contains the offset.</span></span>  
  
 `cchName`  
 <span data-ttu-id="05086-107">[in]A `ULONG32` ，该值指示的大小`szName`缓冲区。</span><span class="sxs-lookup"><span data-stu-id="05086-107">[in] A `ULONG32` that indicates the size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="05086-108">[out]指向的指针`ULONG32`接收大小，以字符为单位，以包含的文件名称所需的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="05086-108">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the file names.</span></span>  
  
 `szName`  
 <span data-ttu-id="05086-109">[out]包含文件的文件名的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="05086-109">[out] The buffer that contains the file names.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="05086-110">返回值</span><span class="sxs-lookup"><span data-stu-id="05086-110">Return Value</span></span>  
 <span data-ttu-id="05086-111">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="05086-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05086-112">要求</span><span class="sxs-lookup"><span data-stu-id="05086-112">Requirements</span></span>  
 <span data-ttu-id="05086-113">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="05086-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05086-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="05086-114">See Also</span></span>  
 [<span data-ttu-id="05086-115">ISymENCUnmanagedMethod 接口</span><span class="sxs-lookup"><span data-stu-id="05086-115">ISymENCUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)

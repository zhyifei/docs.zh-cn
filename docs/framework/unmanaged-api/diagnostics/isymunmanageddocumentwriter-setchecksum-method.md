---
title: ISymUnmanagedDocumentWriter::SetCheckSum 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocumentWriter.SetCheckSum
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocumentWriter::SetCheckSum
helpviewer_keywords:
- ISymUnmanagedDocumentWriter::SetCheckSum method [.NET Framework debugging]
- SetCheckSum method [.NET Framework debugging]
ms.assetid: c7e99879-421f-43ce-b193-34733cf30085
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d7a3fcd34f8cab6fa3c2949a4ee3270189b3dc77
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730030"
---
# <a name="isymunmanageddocumentwritersetchecksum-method"></a><span data-ttu-id="de3e1-102">ISymUnmanagedDocumentWriter::SetCheckSum 方法</span><span class="sxs-lookup"><span data-stu-id="de3e1-102">ISymUnmanagedDocumentWriter::SetCheckSum Method</span></span>
<span data-ttu-id="de3e1-103">设置校验和信息。</span><span class="sxs-lookup"><span data-stu-id="de3e1-103">Sets checksum information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de3e1-104">语法</span><span class="sxs-lookup"><span data-stu-id="de3e1-104">Syntax</span></span>  
  
```  
HRESULT SetCheckSum(  
    [in]  GUID     algorithmId,  
    [in]  ULONG32  checkSumSize,  
    [in, size_is(checkSumSize)]  BYTE checkSum[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="de3e1-105">参数</span><span class="sxs-lookup"><span data-stu-id="de3e1-105">Parameters</span></span>  
 `algorithmId`  
 <span data-ttu-id="de3e1-106">[in]表示算法标识符的 GUID。</span><span class="sxs-lookup"><span data-stu-id="de3e1-106">[in] The GUID that represents the algorithm identifier.</span></span>  
  
 `checkSumSize`  
 <span data-ttu-id="de3e1-107">[in]一个`ULONG32`指示的大小，以字节为单位，`checkSum`缓冲区。</span><span class="sxs-lookup"><span data-stu-id="de3e1-107">[in] A `ULONG32` that indicates the size, in bytes, of the `checkSum` buffer.</span></span>  
  
 `checkSum`  
 <span data-ttu-id="de3e1-108">[in]存储的校验和信息的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="de3e1-108">[in] The buffer that stores the checksum information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="de3e1-109">返回值</span><span class="sxs-lookup"><span data-stu-id="de3e1-109">Return Value</span></span>  
 <span data-ttu-id="de3e1-110">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="de3e1-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de3e1-111">要求</span><span class="sxs-lookup"><span data-stu-id="de3e1-111">Requirements</span></span>  
 <span data-ttu-id="de3e1-112">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="de3e1-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de3e1-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="de3e1-113">See also</span></span>
- [<span data-ttu-id="de3e1-114">ISymUnmanagedDocumentWriter 接口</span><span class="sxs-lookup"><span data-stu-id="de3e1-114">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)

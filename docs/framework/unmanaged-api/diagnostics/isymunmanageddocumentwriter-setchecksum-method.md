---
title: "ISymUnmanagedDocumentWriter::SetCheckSum 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocumentWriter.SetCheckSum
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocumentWriter::SetCheckSum
helpviewer_keywords:
- ISymUnmanagedDocumentWriter::SetCheckSum method [.NET Framework debugging]
- SetCheckSum method [.NET Framework debugging]
ms.assetid: c7e99879-421f-43ce-b193-34733cf30085
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9693b21c2b3819096ec4aeb0a275fccf76307de0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanageddocumentwritersetchecksum-method"></a><span data-ttu-id="5d19b-102">ISymUnmanagedDocumentWriter::SetCheckSum 方法</span><span class="sxs-lookup"><span data-stu-id="5d19b-102">ISymUnmanagedDocumentWriter::SetCheckSum Method</span></span>
<span data-ttu-id="5d19b-103">设置校验和信息。</span><span class="sxs-lookup"><span data-stu-id="5d19b-103">Sets checksum information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d19b-104">语法</span><span class="sxs-lookup"><span data-stu-id="5d19b-104">Syntax</span></span>  
  
```  
HRESULT SetCheckSum(  
    [in]  GUID     algorithmId,  
    [in]  ULONG32  checkSumSize,  
    [in, size_is(checkSumSize)]  BYTE checkSum[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5d19b-105">参数</span><span class="sxs-lookup"><span data-stu-id="5d19b-105">Parameters</span></span>  
 `algorithmId`  
 <span data-ttu-id="5d19b-106">[in]表示算法标识符的 GUID。</span><span class="sxs-lookup"><span data-stu-id="5d19b-106">[in] The GUID that represents the algorithm identifier.</span></span>  
  
 `checkSumSize`  
 <span data-ttu-id="5d19b-107">[in]A`ULONG32`指示的大小，以字节为单位，`checkSum`缓冲区。</span><span class="sxs-lookup"><span data-stu-id="5d19b-107">[in] A `ULONG32` that indicates the size, in bytes, of the `checkSum` buffer.</span></span>  
  
 `checkSum`  
 <span data-ttu-id="5d19b-108">[in]存储的校验和信息的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="5d19b-108">[in] The buffer that stores the checksum information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d19b-109">返回值</span><span class="sxs-lookup"><span data-stu-id="5d19b-109">Return Value</span></span>  
 <span data-ttu-id="5d19b-110">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="5d19b-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d19b-111">要求</span><span class="sxs-lookup"><span data-stu-id="5d19b-111">Requirements</span></span>  
 <span data-ttu-id="5d19b-112">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5d19b-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d19b-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5d19b-113">See Also</span></span>  
 [<span data-ttu-id="5d19b-114">ISymUnmanagedDocumentWriter 接口</span><span class="sxs-lookup"><span data-stu-id="5d19b-114">ISymUnmanagedDocumentWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)

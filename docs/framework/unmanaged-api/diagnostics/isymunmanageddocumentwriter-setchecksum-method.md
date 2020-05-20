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
ms.openlocfilehash: 06a331e24622e0a155d974ca869818a6532baa1f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615535"
---
# <a name="isymunmanageddocumentwritersetchecksum-method"></a><span data-ttu-id="703a4-102">ISymUnmanagedDocumentWriter::SetCheckSum 方法</span><span class="sxs-lookup"><span data-stu-id="703a4-102">ISymUnmanagedDocumentWriter::SetCheckSum Method</span></span>
<span data-ttu-id="703a4-103">设置校验和信息。</span><span class="sxs-lookup"><span data-stu-id="703a4-103">Sets checksum information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="703a4-104">语法</span><span class="sxs-lookup"><span data-stu-id="703a4-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCheckSum(  
    [in]  GUID     algorithmId,  
    [in]  ULONG32  checkSumSize,  
    [in, size_is(checkSumSize)]  BYTE checkSum[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="703a4-105">参数</span><span class="sxs-lookup"><span data-stu-id="703a4-105">Parameters</span></span>  
 `algorithmId`  
 <span data-ttu-id="703a4-106">中表示算法标识符的 GUID。</span><span class="sxs-lookup"><span data-stu-id="703a4-106">[in] The GUID that represents the algorithm identifier.</span></span>  
  
 `checkSumSize`  
 <span data-ttu-id="703a4-107">中一个 `ULONG32` ，该值指示缓冲区的大小（以字节为单位） `checkSum` 。</span><span class="sxs-lookup"><span data-stu-id="703a4-107">[in] A `ULONG32` that indicates the size, in bytes, of the `checkSum` buffer.</span></span>  
  
 `checkSum`  
 <span data-ttu-id="703a4-108">中存储校验和信息的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="703a4-108">[in] The buffer that stores the checksum information.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="703a4-109">返回值</span><span class="sxs-lookup"><span data-stu-id="703a4-109">Return Value</span></span>  
 <span data-ttu-id="703a4-110">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="703a4-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="703a4-111">要求</span><span class="sxs-lookup"><span data-stu-id="703a4-111">Requirements</span></span>  
 <span data-ttu-id="703a4-112">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="703a4-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="703a4-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="703a4-113">See also</span></span>

- [<span data-ttu-id="703a4-114">ISymUnmanagedDocumentWriter 接口</span><span class="sxs-lookup"><span data-stu-id="703a4-114">ISymUnmanagedDocumentWriter Interface</span></span>](isymunmanageddocumentwriter-interface.md)

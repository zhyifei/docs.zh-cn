---
title: ISymUnmanagedDocument::GetCheckSum 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetCheckSum
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetCheckSum
helpviewer_keywords:
- ISymUnmanagedDocument::GetCheckSum method [.NET Framework debugging]
- GetCheckSum method [.NET Framework debugging]
ms.assetid: 9bc881b3-e2ce-48a7-ad69-17eaaa304120
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 406fdfcfc0b6db988b317245aaaa4f4a643b2079
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54561395"
---
# <a name="isymunmanageddocumentgetchecksum-method"></a><span data-ttu-id="d34f2-102">ISymUnmanagedDocument::GetCheckSum 方法</span><span class="sxs-lookup"><span data-stu-id="d34f2-102">ISymUnmanagedDocument::GetCheckSum Method</span></span>
<span data-ttu-id="d34f2-103">获取校验和。</span><span class="sxs-lookup"><span data-stu-id="d34f2-103">Gets the checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d34f2-104">语法</span><span class="sxs-lookup"><span data-stu-id="d34f2-104">Syntax</span></span>  
  
```  
HRESULT GetCheckSum(  
    [in]  ULONG32  cData,  
    [out] ULONG32  *pcData,  
    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d34f2-105">参数</span><span class="sxs-lookup"><span data-stu-id="d34f2-105">Parameters</span></span>  
 `cData`  
 <span data-ttu-id="d34f2-106">[in]提供的缓冲区的长度`data`参数</span><span class="sxs-lookup"><span data-stu-id="d34f2-106">[in] The length of the buffer provided by the `data` parameter</span></span>  
  
 `pcData`  
 <span data-ttu-id="d34f2-107">[out]大小和校验和，以字节为单位的长度。</span><span class="sxs-lookup"><span data-stu-id="d34f2-107">[out] The size and length of the checksum, in bytes.</span></span>  
  
 `data`  
 <span data-ttu-id="d34f2-108">[out]该缓冲区用于接收校验和。</span><span class="sxs-lookup"><span data-stu-id="d34f2-108">[out] The buffer that receives the checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d34f2-109">返回值</span><span class="sxs-lookup"><span data-stu-id="d34f2-109">Return Value</span></span>  
 <span data-ttu-id="d34f2-110">如果方法成功，则为 S_OK否则为错误代码。</span><span class="sxs-lookup"><span data-stu-id="d34f2-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d34f2-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="d34f2-111">See also</span></span>
- [<span data-ttu-id="d34f2-112">ISymUnmanagedDocument 接口</span><span class="sxs-lookup"><span data-stu-id="d34f2-112">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)

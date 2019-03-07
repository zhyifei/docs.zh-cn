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
ms.openlocfilehash: 80cda4c31ca78e0350639df809ec1e9f1dcbbaea
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498245"
---
# <a name="isymunmanageddocumentgetchecksum-method"></a><span data-ttu-id="4bce7-102">ISymUnmanagedDocument::GetCheckSum 方法</span><span class="sxs-lookup"><span data-stu-id="4bce7-102">ISymUnmanagedDocument::GetCheckSum Method</span></span>
<span data-ttu-id="4bce7-103">获取校验和。</span><span class="sxs-lookup"><span data-stu-id="4bce7-103">Gets the checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bce7-104">语法</span><span class="sxs-lookup"><span data-stu-id="4bce7-104">Syntax</span></span>  
  
```  
HRESULT GetCheckSum(  
    [in]  ULONG32  cData,  
    [out] ULONG32  *pcData,  
    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4bce7-105">参数</span><span class="sxs-lookup"><span data-stu-id="4bce7-105">Parameters</span></span>  
 `cData`  
 <span data-ttu-id="4bce7-106">[in]提供的缓冲区的长度`data`参数</span><span class="sxs-lookup"><span data-stu-id="4bce7-106">[in] The length of the buffer provided by the `data` parameter</span></span>  
  
 `pcData`  
 <span data-ttu-id="4bce7-107">[out]大小和校验和，以字节为单位的长度。</span><span class="sxs-lookup"><span data-stu-id="4bce7-107">[out] The size and length of the checksum, in bytes.</span></span>  
  
 `data`  
 <span data-ttu-id="4bce7-108">[out]该缓冲区用于接收校验和。</span><span class="sxs-lookup"><span data-stu-id="4bce7-108">[out] The buffer that receives the checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4bce7-109">返回值</span><span class="sxs-lookup"><span data-stu-id="4bce7-109">Return Value</span></span>  
 <span data-ttu-id="4bce7-110">如果方法成功，则为 S_OK否则为错误代码。</span><span class="sxs-lookup"><span data-stu-id="4bce7-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bce7-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="4bce7-111">See also</span></span>
- [<span data-ttu-id="4bce7-112">ISymUnmanagedDocument 接口</span><span class="sxs-lookup"><span data-stu-id="4bce7-112">ISymUnmanagedDocument Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)

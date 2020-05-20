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
ms.openlocfilehash: 543bd208e5492460435663c32f276472a763f613
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441092"
---
# <a name="isymunmanageddocumentgetchecksum-method"></a><span data-ttu-id="b57b5-102">ISymUnmanagedDocument::GetCheckSum 方法</span><span class="sxs-lookup"><span data-stu-id="b57b5-102">ISymUnmanagedDocument::GetCheckSum Method</span></span>
<span data-ttu-id="b57b5-103">获取校验和。</span><span class="sxs-lookup"><span data-stu-id="b57b5-103">Gets the checksum.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b57b5-104">语法</span><span class="sxs-lookup"><span data-stu-id="b57b5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCheckSum(  
    [in]  ULONG32  cData,  
    [out] ULONG32  *pcData,  
    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b57b5-105">参数</span><span class="sxs-lookup"><span data-stu-id="b57b5-105">Parameters</span></span>  
 `cData`  
 <span data-ttu-id="b57b5-106">中参数所提供的缓冲区的长度 `data`</span><span class="sxs-lookup"><span data-stu-id="b57b5-106">[in] The length of the buffer provided by the `data` parameter</span></span>  
  
 `pcData`  
 <span data-ttu-id="b57b5-107">弄校验和的大小和长度（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="b57b5-107">[out] The size and length of the checksum, in bytes.</span></span>  
  
 `data`  
 <span data-ttu-id="b57b5-108">弄接收校验和的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="b57b5-108">[out] The buffer that receives the checksum.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b57b5-109">返回值</span><span class="sxs-lookup"><span data-stu-id="b57b5-109">Return Value</span></span>  
 <span data-ttu-id="b57b5-110">如果该方法成功，则 S_OK;否则为错误代码。</span><span class="sxs-lookup"><span data-stu-id="b57b5-110">S_OK if the method succeeds; otherwise, an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b57b5-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b57b5-111">See also</span></span>

- [<span data-ttu-id="b57b5-112">ISymUnmanagedDocument 接口</span><span class="sxs-lookup"><span data-stu-id="b57b5-112">ISymUnmanagedDocument Interface</span></span>](isymunmanageddocument-interface.md)

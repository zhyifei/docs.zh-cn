---
title: ISymUnmanagedReader::GetSymAttribute 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetSymAttribute
helpviewer_keywords:
- GetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymAttribute method [.NET Framework debugging]
ms.assetid: c675ce7e-76e7-45ff-8273-3b6489a2767c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bfe441831cef3f708792767163b9cf2138cd4335
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473848"
---
# <a name="isymunmanagedreadergetsymattribute-method"></a><span data-ttu-id="c350b-102">ISymUnmanagedReader::GetSymAttribute 方法</span><span class="sxs-lookup"><span data-stu-id="c350b-102">ISymUnmanagedReader::GetSymAttribute Method</span></span>
<span data-ttu-id="c350b-103">获取根据其名称的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="c350b-103">Gets a custom attribute based upon its name.</span></span> <span data-ttu-id="c350b-104">与不同的元数据自定义特性，这些自定义属性保存在符号存储区中。</span><span class="sxs-lookup"><span data-stu-id="c350b-104">Unlike metadata custom attributes, these custom attributes are held in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c350b-105">语法</span><span class="sxs-lookup"><span data-stu-id="c350b-105">Syntax</span></span>  
  
```  
HRESULT GetSymAttribute (  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is (cBuffer),  
        length_is (*pcBuffer)] BYTE buffer[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c350b-106">参数</span><span class="sxs-lookup"><span data-stu-id="c350b-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="c350b-107">[in]为其请求该属性的对象元数据标记。</span><span class="sxs-lookup"><span data-stu-id="c350b-107">[in] The metadata token for the object for which the attribute is requested.</span></span>  
  
 `name`  
 <span data-ttu-id="c350b-108">[in]指示要检索的特性的变量指向的指针。</span><span class="sxs-lookup"><span data-stu-id="c350b-108">[in] A pointer to the variable that indicates the attribute to retrieve.</span></span>  
  
 `cBuffer`  
 <span data-ttu-id="c350b-109">[in] `buffer` 数组的大小。</span><span class="sxs-lookup"><span data-stu-id="c350b-109">[in] The size of the `buffer` array.</span></span>  
  
 `pcBuffer`  
 <span data-ttu-id="c350b-110">[out]指向接收特性数据的长度的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="c350b-110">[out] A pointer to the variable that receives the length of the attribute data.</span></span>  
  
 `buffer`  
 <span data-ttu-id="c350b-111">[out]指向接收属性数据的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="c350b-111">[out] A pointer to the variable that receives the attribute data.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c350b-112">返回值</span><span class="sxs-lookup"><span data-stu-id="c350b-112">Return Value</span></span>  
 <span data-ttu-id="c350b-113">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="c350b-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c350b-114">要求</span><span class="sxs-lookup"><span data-stu-id="c350b-114">Requirements</span></span>  
 <span data-ttu-id="c350b-115">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c350b-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c350b-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="c350b-116">See also</span></span>
- [<span data-ttu-id="c350b-117">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="c350b-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)

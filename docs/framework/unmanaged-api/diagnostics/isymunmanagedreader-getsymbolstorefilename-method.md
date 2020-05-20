---
title: ISymUnmanagedReader::GetSymbolStoreFileName 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetSymbolStoreFileName
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetSymbolStoreFileName
helpviewer_keywords:
- GetSymbolStoreFileName method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymbolStoreFileName method [.NET Framework debugging]
ms.assetid: c84f4846-9bc8-44a4-9a76-e39106d6d8b2
topic_type:
- apiref
ms.openlocfilehash: 6ffab3b2f81680404f870cfd63ae5125173a346c
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615509"
---
# <a name="isymunmanagedreadergetsymbolstorefilename-method"></a><span data-ttu-id="6f3ff-102">ISymUnmanagedReader::GetSymbolStoreFileName 方法</span><span class="sxs-lookup"><span data-stu-id="6f3ff-102">ISymUnmanagedReader::GetSymbolStoreFileName Method</span></span>
<span data-ttu-id="6f3ff-103">提供符号存储区的磁盘上的文件名。</span><span class="sxs-lookup"><span data-stu-id="6f3ff-103">Provides the on-disk file name of the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f3ff-104">语法</span><span class="sxs-lookup"><span data-stu-id="6f3ff-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolStoreFileName (  
    [in]  ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is (cchName),  
        length_is (*pcchName)] WCHAR szName[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f3ff-105">参数</span><span class="sxs-lookup"><span data-stu-id="6f3ff-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="6f3ff-106">中缓冲区的大小 `szName` 。</span><span class="sxs-lookup"><span data-stu-id="6f3ff-106">[in] The size of the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="6f3ff-107">弄指向一个变量的指针，该变量接收返回的名称的长度 `szName` （包括 null 终止）。</span><span class="sxs-lookup"><span data-stu-id="6f3ff-107">[out] A pointer to the variable that receives the length of the name returned in `szName`, including the null termination.</span></span>  
  
 `szName`  
 <span data-ttu-id="6f3ff-108">弄指向接收符号存储区文件名的变量的指针。</span><span class="sxs-lookup"><span data-stu-id="6f3ff-108">[out] A pointer to the variable that receives the file name of the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6f3ff-109">返回值</span><span class="sxs-lookup"><span data-stu-id="6f3ff-109">Return Value</span></span>  
 <span data-ttu-id="6f3ff-110">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="6f3ff-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f3ff-111">要求</span><span class="sxs-lookup"><span data-stu-id="6f3ff-111">Requirements</span></span>  
 <span data-ttu-id="6f3ff-112">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="6f3ff-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f3ff-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6f3ff-113">See also</span></span>

- [<span data-ttu-id="6f3ff-114">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="6f3ff-114">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)

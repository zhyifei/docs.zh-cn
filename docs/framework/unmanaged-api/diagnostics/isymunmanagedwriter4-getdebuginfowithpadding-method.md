---
title: ISymUnmanagedWriter4::GetDebugInfoWithPadding 方法
ms.date: 03/30/2017
ms.assetid: 881e20ca-8131-4bd0-ba41-c2d6391b0fe2
ms.openlocfilehash: 274bf79175bda9e880b1ef3cf8f125a017ad0734
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121659"
---
# <a name="isymunmanagedwriter4getdebuginfowithpadding-method"></a><span data-ttu-id="36719-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding 方法</span><span class="sxs-lookup"><span data-stu-id="36719-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding Method</span></span>
<span data-ttu-id="36719-103">与[GetDebugInfo 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md)相同，不同之处在于，在终止 null 字符后使用零填充路径字符串，使字符串数据成为固定大小的 `MAX_PATH`。</span><span class="sxs-lookup"><span data-stu-id="36719-103">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="36719-104">仅当路径字符串长度本身小于 `MAX_PATH`时才会提供填充。</span><span class="sxs-lookup"><span data-stu-id="36719-104">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span>  
  
 <span data-ttu-id="36719-105">这样可以更轻松地编写不同 PE 文件的工具。</span><span class="sxs-lookup"><span data-stu-id="36719-105">This makes it easier to write tools that difference PE files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36719-106">语法</span><span class="sxs-lookup"><span data-stu-id="36719-106">Syntax</span></span>  
  
```idl  
HRESULT GetDebugInfoWithPadding(    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,    [in] DWORD cData,    [out] DWORD *pcData,    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36719-107">参数</span><span class="sxs-lookup"><span data-stu-id="36719-107">Parameters</span></span>  
  
|<span data-ttu-id="36719-108">参数</span><span class="sxs-lookup"><span data-stu-id="36719-108">Parameter</span></span>|<span data-ttu-id="36719-109">描述</span><span class="sxs-lookup"><span data-stu-id="36719-109">Description</span></span>|  
|---------------|-----------------|  
|`pIDD`||  
|`cData`||  
|`pcData`||  
|`data`||  
  
## <a name="return-value"></a><span data-ttu-id="36719-110">返回值</span><span class="sxs-lookup"><span data-stu-id="36719-110">Return Value</span></span>  
 <span data-ttu-id="36719-111">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="36719-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36719-112">要求</span><span class="sxs-lookup"><span data-stu-id="36719-112">Requirements</span></span>  
 <span data-ttu-id="36719-113">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="36719-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36719-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="36719-114">See also</span></span>

- [<span data-ttu-id="36719-115">ISymUnmanagedWriter4 接口</span><span class="sxs-lookup"><span data-stu-id="36719-115">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)

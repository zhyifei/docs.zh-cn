---
title: ISymUnmanagedWriter4::GetDebugInfoWithPadding 方法
ms.date: 03/30/2017
ms.assetid: 881e20ca-8131-4bd0-ba41-c2d6391b0fe2
ms.openlocfilehash: cfc6c22558cee780823c8cca0c36b883147e9496
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614638"
---
# <a name="isymunmanagedwriter4getdebuginfowithpadding-method"></a><span data-ttu-id="72b8d-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding 方法</span><span class="sxs-lookup"><span data-stu-id="72b8d-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding Method</span></span>
<span data-ttu-id="72b8d-103">与[GetDebugInfo 方法](isymunmanagedwriter-getdebuginfo-method.md)相同，不同之处在于，在终止 null 字符后使用零填充路径字符串，使字符串数据成为固定大小的字符串数据 `MAX_PATH` 。</span><span class="sxs-lookup"><span data-stu-id="72b8d-103">Functions the same as [GetDebugInfo Method](isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="72b8d-104">仅当路径字符串长度本身小于时才会提供填充 `MAX_PATH` 。</span><span class="sxs-lookup"><span data-stu-id="72b8d-104">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span>  
  
 <span data-ttu-id="72b8d-105">这样可以更轻松地编写不同 PE 文件的工具。</span><span class="sxs-lookup"><span data-stu-id="72b8d-105">This makes it easier to write tools that difference PE files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72b8d-106">语法</span><span class="sxs-lookup"><span data-stu-id="72b8d-106">Syntax</span></span>  
  
```idl  
HRESULT GetDebugInfoWithPadding(    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,    [in] DWORD cData,    [out] DWORD *pcData,    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72b8d-107">参数</span><span class="sxs-lookup"><span data-stu-id="72b8d-107">Parameters</span></span>  
  
|<span data-ttu-id="72b8d-108">参数</span><span class="sxs-lookup"><span data-stu-id="72b8d-108">Parameter</span></span>|<span data-ttu-id="72b8d-109">说明</span><span class="sxs-lookup"><span data-stu-id="72b8d-109">Description</span></span>|  
|---------------|-----------------|  
|`pIDD`||  
|`cData`||  
|`pcData`||  
|`data`||  
  
## <a name="return-value"></a><span data-ttu-id="72b8d-110">返回值</span><span class="sxs-lookup"><span data-stu-id="72b8d-110">Return Value</span></span>  
 <span data-ttu-id="72b8d-111">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="72b8d-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72b8d-112">要求</span><span class="sxs-lookup"><span data-stu-id="72b8d-112">Requirements</span></span>  
 <span data-ttu-id="72b8d-113">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="72b8d-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72b8d-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="72b8d-114">See also</span></span>

- [<span data-ttu-id="72b8d-115">ISymUnmanagedWriter4 接口</span><span class="sxs-lookup"><span data-stu-id="72b8d-115">ISymUnmanagedWriter4 Interface</span></span>](isymunmanagedwriter4-interface.md)

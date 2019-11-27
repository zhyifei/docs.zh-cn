---
title: ISymUnmanagedSourceServerModule::GetSourceServerData 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSourceServerModule.GetSourceServerData
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSourceServerModule::GetSourceServerData
helpviewer_keywords:
- ISymUnmanagedSourceServerModule::GetSourceServerData method [.NET Framework debugging]
- GetSourceServerData method [.NET Framework debugging]
ms.assetid: 20bdf8ff-2d15-4c64-8950-6888f642d6c0
topic_type:
- apiref
ms.openlocfilehash: f25150d037a2f6fabb700f2c4bf2191e8e402a8e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446219"
---
# <a name="isymunmanagedsourceservermodulegetsourceserverdata-method"></a><span data-ttu-id="a3b89-102">ISymUnmanagedSourceServerModule::GetSourceServerData 方法</span><span class="sxs-lookup"><span data-stu-id="a3b89-102">ISymUnmanagedSourceServerModule::GetSourceServerData Method</span></span>
<span data-ttu-id="a3b89-103">返回模块的源服务器数据。</span><span class="sxs-lookup"><span data-stu-id="a3b89-103">Returns the source server data for the module.</span></span> <span data-ttu-id="a3b89-104">调用方必须使用 `CoTaskMemFree`释放资源。</span><span class="sxs-lookup"><span data-stu-id="a3b89-104">The caller must free resources by using `CoTaskMemFree`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3b89-105">语法</span><span class="sxs-lookup"><span data-stu-id="a3b89-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceServerData(  
    [out] ULONG* pDataByteCount,   
    [out, size_is (, *pDataByteCount)] BYTE** ppData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3b89-106">参数</span><span class="sxs-lookup"><span data-stu-id="a3b89-106">Parameters</span></span>  
 `pDataByteCount`  
 <span data-ttu-id="a3b89-107">弄指向接收源服务器数据的大小（以字节为单位）的 `ULONG32` 的指针。</span><span class="sxs-lookup"><span data-stu-id="a3b89-107">[out] A pointer to a `ULONG32` that receives the size, in bytes, of the source server data.</span></span>  
  
 `ppData`  
 <span data-ttu-id="a3b89-108">弄指向返回的 `pDataByteCount` 值的指针。</span><span class="sxs-lookup"><span data-stu-id="a3b89-108">[out] A pointer to the returned `pDataByteCount` value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a3b89-109">返回值</span><span class="sxs-lookup"><span data-stu-id="a3b89-109">Return Value</span></span>  
 <span data-ttu-id="a3b89-110">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="a3b89-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3b89-111">要求</span><span class="sxs-lookup"><span data-stu-id="a3b89-111">Requirements</span></span>  
 <span data-ttu-id="a3b89-112">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="a3b89-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3b89-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a3b89-113">See also</span></span>

- [<span data-ttu-id="a3b89-114">ISymUnmanagedSourceServerModule 接口</span><span class="sxs-lookup"><span data-stu-id="a3b89-114">ISymUnmanagedSourceServerModule Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)

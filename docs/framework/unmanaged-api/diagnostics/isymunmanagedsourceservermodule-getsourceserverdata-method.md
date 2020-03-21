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
ms.openlocfilehash: 6904271ed90cf733b9221178927bc680d76b58a6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176573"
---
# <a name="isymunmanagedsourceservermodulegetsourceserverdata-method"></a><span data-ttu-id="fe8c8-102">ISymUnmanagedSourceServerModule::GetSourceServerData 方法</span><span class="sxs-lookup"><span data-stu-id="fe8c8-102">ISymUnmanagedSourceServerModule::GetSourceServerData Method</span></span>
<span data-ttu-id="fe8c8-103">返回模块的源服务器数据。</span><span class="sxs-lookup"><span data-stu-id="fe8c8-103">Returns the source server data for the module.</span></span> <span data-ttu-id="fe8c8-104">调用方必须使用`CoTaskMemFree`释放资源。</span><span class="sxs-lookup"><span data-stu-id="fe8c8-104">The caller must free resources by using `CoTaskMemFree`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe8c8-105">语法</span><span class="sxs-lookup"><span data-stu-id="fe8c8-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceServerData(  
    [out] ULONG* pDataByteCount,
    [out, size_is (, *pDataByteCount)] BYTE** ppData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe8c8-106">parameters</span><span class="sxs-lookup"><span data-stu-id="fe8c8-106">Parameters</span></span>  
 `pDataByteCount`  
 <span data-ttu-id="fe8c8-107">[出]指向`ULONG32`接收源服务器数据的大小（以字节为单位）的指针。</span><span class="sxs-lookup"><span data-stu-id="fe8c8-107">[out] A pointer to a `ULONG32` that receives the size, in bytes, of the source server data.</span></span>  
  
 `ppData`  
 <span data-ttu-id="fe8c8-108">[出]指向返回`pDataByteCount`值的指针。</span><span class="sxs-lookup"><span data-stu-id="fe8c8-108">[out] A pointer to the returned `pDataByteCount` value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe8c8-109">返回值</span><span class="sxs-lookup"><span data-stu-id="fe8c8-109">Return Value</span></span>  
 <span data-ttu-id="fe8c8-110">如果方法成功，S_OK;否则，E_FAIL或其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="fe8c8-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe8c8-111">要求</span><span class="sxs-lookup"><span data-stu-id="fe8c8-111">Requirements</span></span>  
 <span data-ttu-id="fe8c8-112">**标题：** 科西姆.伊德尔，科西姆.h</span><span class="sxs-lookup"><span data-stu-id="fe8c8-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe8c8-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fe8c8-113">See also</span></span>

- [<span data-ttu-id="fe8c8-114">ISymUnmanagedSourceServerModule 接口</span><span class="sxs-lookup"><span data-stu-id="fe8c8-114">ISymUnmanagedSourceServerModule Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)

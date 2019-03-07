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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 69e83a5ff489881938c1e8410f765fd63f3b5d84
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479436"
---
# <a name="isymunmanagedsourceservermodulegetsourceserverdata-method"></a><span data-ttu-id="328a7-102">ISymUnmanagedSourceServerModule::GetSourceServerData 方法</span><span class="sxs-lookup"><span data-stu-id="328a7-102">ISymUnmanagedSourceServerModule::GetSourceServerData Method</span></span>
<span data-ttu-id="328a7-103">返回该模块的源服务器数据。</span><span class="sxs-lookup"><span data-stu-id="328a7-103">Returns the source server data for the module.</span></span> <span data-ttu-id="328a7-104">调用方必须释放资源使用`CoTaskMemFree`。</span><span class="sxs-lookup"><span data-stu-id="328a7-104">The caller must free resources by using `CoTaskMemFree`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="328a7-105">语法</span><span class="sxs-lookup"><span data-stu-id="328a7-105">Syntax</span></span>  
  
```  
HRESULT GetSourceServerData(  
    [out] ULONG* pDataByteCount,   
    [out, size_is (, *pDataByteCount)] BYTE** ppData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="328a7-106">参数</span><span class="sxs-lookup"><span data-stu-id="328a7-106">Parameters</span></span>  
 `pDataByteCount`  
 <span data-ttu-id="328a7-107">[out]一个指向`ULONG32`用于接收大小，以字节为单位的源服务器数据。</span><span class="sxs-lookup"><span data-stu-id="328a7-107">[out] A pointer to a `ULONG32` that receives the size, in bytes, of the source server data.</span></span>  
  
 `ppData`  
 <span data-ttu-id="328a7-108">[out]指向返回的指针`pDataByteCount`值。</span><span class="sxs-lookup"><span data-stu-id="328a7-108">[out] A pointer to the returned `pDataByteCount` value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="328a7-109">返回值</span><span class="sxs-lookup"><span data-stu-id="328a7-109">Return Value</span></span>  
 <span data-ttu-id="328a7-110">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="328a7-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="328a7-111">要求</span><span class="sxs-lookup"><span data-stu-id="328a7-111">Requirements</span></span>  
 <span data-ttu-id="328a7-112">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="328a7-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="328a7-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="328a7-113">See also</span></span>
- [<span data-ttu-id="328a7-114">ISymUnmanagedSourceServerModule 接口</span><span class="sxs-lookup"><span data-stu-id="328a7-114">ISymUnmanagedSourceServerModule Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)

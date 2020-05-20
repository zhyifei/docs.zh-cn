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
ms.openlocfilehash: 9a3a6c07a9cace0ac9834cdb05925a301285204c
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615314"
---
# <a name="isymunmanagedsourceservermodulegetsourceserverdata-method"></a><span data-ttu-id="a1027-102">ISymUnmanagedSourceServerModule::GetSourceServerData 方法</span><span class="sxs-lookup"><span data-stu-id="a1027-102">ISymUnmanagedSourceServerModule::GetSourceServerData Method</span></span>
<span data-ttu-id="a1027-103">返回模块的源服务器数据。</span><span class="sxs-lookup"><span data-stu-id="a1027-103">Returns the source server data for the module.</span></span> <span data-ttu-id="a1027-104">调用方必须使用来释放资源 `CoTaskMemFree` 。</span><span class="sxs-lookup"><span data-stu-id="a1027-104">The caller must free resources by using `CoTaskMemFree`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1027-105">语法</span><span class="sxs-lookup"><span data-stu-id="a1027-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSourceServerData(  
    [out] ULONG* pDataByteCount,
    [out, size_is (, *pDataByteCount)] BYTE** ppData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1027-106">参数</span><span class="sxs-lookup"><span data-stu-id="a1027-106">Parameters</span></span>  
 `pDataByteCount`  
 <span data-ttu-id="a1027-107">弄指向的指针， `ULONG32` 该指针接收源服务器数据的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="a1027-107">[out] A pointer to a `ULONG32` that receives the size, in bytes, of the source server data.</span></span>  
  
 `ppData`  
 <span data-ttu-id="a1027-108">弄指向返回值的指针 `pDataByteCount` 。</span><span class="sxs-lookup"><span data-stu-id="a1027-108">[out] A pointer to the returned `pDataByteCount` value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a1027-109">返回值</span><span class="sxs-lookup"><span data-stu-id="a1027-109">Return Value</span></span>  
 <span data-ttu-id="a1027-110">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="a1027-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1027-111">要求</span><span class="sxs-lookup"><span data-stu-id="a1027-111">Requirements</span></span>  
 <span data-ttu-id="a1027-112">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="a1027-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1027-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a1027-113">See also</span></span>

- [<span data-ttu-id="a1027-114">ISymUnmanagedSourceServerModule 接口</span><span class="sxs-lookup"><span data-stu-id="a1027-114">ISymUnmanagedSourceServerModule Interface</span></span>](isymunmanagedsourceservermodule-interface.md)

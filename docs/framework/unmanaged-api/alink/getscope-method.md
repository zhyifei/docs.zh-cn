---
title: GetScope 方法
ms.date: 03/30/2017
api_name:
- IALink.GetScope
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope
helpviewer_keywords:
- GetScope method
ms.assetid: e1555328-2c71-4ece-b357-9eb6d3a8efc4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c8de6c745b1d32c3d98f1b54e822ab084f0574b2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57486194"
---
# <a name="getscope-method"></a><span data-ttu-id="bdb0b-102">GetScope 方法</span><span class="sxs-lookup"><span data-stu-id="bdb0b-102">GetScope Method</span></span>
<span data-ttu-id="bdb0b-103">获取导入范围。</span><span class="sxs-lookup"><span data-stu-id="bdb0b-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdb0b-104">语法</span><span class="sxs-lookup"><span data-stu-id="bdb0b-104">Syntax</span></span>  
  
```  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="bdb0b-105">参数</span><span class="sxs-lookup"><span data-stu-id="bdb0b-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="bdb0b-106">要导入到程序集的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="bdb0b-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="bdb0b-107">唯一 ID 的文件从导入。</span><span class="sxs-lookup"><span data-stu-id="bdb0b-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="bdb0b-108">要导入的从零开始范围。</span><span class="sxs-lookup"><span data-stu-id="bdb0b-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="bdb0b-109">接收[IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)作用域的接口。</span><span class="sxs-lookup"><span data-stu-id="bdb0b-109">Receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bdb0b-110">返回值</span><span class="sxs-lookup"><span data-stu-id="bdb0b-110">Return Value</span></span>  
 <span data-ttu-id="bdb0b-111">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="bdb0b-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdb0b-112">要求</span><span class="sxs-lookup"><span data-stu-id="bdb0b-112">Requirements</span></span>  
 <span data-ttu-id="bdb0b-113">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="bdb0b-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdb0b-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="bdb0b-114">See also</span></span>
- [<span data-ttu-id="bdb0b-115">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="bdb0b-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="bdb0b-116">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="bdb0b-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="bdb0b-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="bdb0b-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

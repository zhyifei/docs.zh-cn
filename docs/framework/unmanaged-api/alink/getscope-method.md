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
ms.openlocfilehash: 571612796d4e66be9dd8469d748c2380c839ddfa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789813"
---
# <a name="getscope-method"></a><span data-ttu-id="2b97d-102">GetScope 方法</span><span class="sxs-lookup"><span data-stu-id="2b97d-102">GetScope Method</span></span>
<span data-ttu-id="2b97d-103">获取导入范围。</span><span class="sxs-lookup"><span data-stu-id="2b97d-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b97d-104">语法</span><span class="sxs-lookup"><span data-stu-id="2b97d-104">Syntax</span></span>  
  
```  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b97d-105">参数</span><span class="sxs-lookup"><span data-stu-id="2b97d-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="2b97d-106">要导入到程序集的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="2b97d-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="2b97d-107">唯一 ID 的文件从导入。</span><span class="sxs-lookup"><span data-stu-id="2b97d-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="2b97d-108">要导入的从零开始范围。</span><span class="sxs-lookup"><span data-stu-id="2b97d-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="2b97d-109">接收[IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)作用域的接口。</span><span class="sxs-lookup"><span data-stu-id="2b97d-109">Receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2b97d-110">返回值</span><span class="sxs-lookup"><span data-stu-id="2b97d-110">Return Value</span></span>  
 <span data-ttu-id="2b97d-111">如果该方法成功，返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="2b97d-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b97d-112">要求</span><span class="sxs-lookup"><span data-stu-id="2b97d-112">Requirements</span></span>  
 <span data-ttu-id="2b97d-113">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="2b97d-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b97d-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="2b97d-114">See also</span></span>

- [<span data-ttu-id="2b97d-115">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="2b97d-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="2b97d-116">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="2b97d-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="2b97d-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="2b97d-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

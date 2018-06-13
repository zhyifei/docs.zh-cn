---
title: GetScope Method1
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
ms.openlocfilehash: e2746073fbc6adfd7090aa9b3cc38e46c4411744
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33400180"
---
# <a name="getscope-method1"></a><span data-ttu-id="0e16e-102">GetScope Method1</span><span class="sxs-lookup"><span data-stu-id="0e16e-102">GetScope Method1</span></span>
<span data-ttu-id="0e16e-103">获取导入作用域。</span><span class="sxs-lookup"><span data-stu-id="0e16e-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e16e-104">语法</span><span class="sxs-lookup"><span data-stu-id="0e16e-104">Syntax</span></span>  
  
```  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0e16e-105">参数</span><span class="sxs-lookup"><span data-stu-id="0e16e-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="0e16e-106">要导入到程序集的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="0e16e-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="0e16e-107">唯一的文件 ID 从导入。</span><span class="sxs-lookup"><span data-stu-id="0e16e-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="0e16e-108">要导入的从零开始范围。</span><span class="sxs-lookup"><span data-stu-id="0e16e-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="0e16e-109">接收[IMetaDataImport 接口](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)作用域的接口。</span><span class="sxs-lookup"><span data-stu-id="0e16e-109">Receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0e16e-110">返回值</span><span class="sxs-lookup"><span data-stu-id="0e16e-110">Return Value</span></span>  
 <span data-ttu-id="0e16e-111">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="0e16e-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e16e-112">要求</span><span class="sxs-lookup"><span data-stu-id="0e16e-112">Requirements</span></span>  
 <span data-ttu-id="0e16e-113">需要 alink.h</span><span class="sxs-lookup"><span data-stu-id="0e16e-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e16e-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="0e16e-114">See Also</span></span>  
 [<span data-ttu-id="0e16e-115">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="0e16e-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="0e16e-116">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="0e16e-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="0e16e-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="0e16e-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)

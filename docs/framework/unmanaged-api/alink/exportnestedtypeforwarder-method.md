---
title: ExportNestedTypeForwarder 方法
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedTypeForwarder
helpviewer_keywords:
- ExportNestedTypeForwarder method
ms.assetid: 886ea6c5-6b26-4b88-8bf6-448d6d191950
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: eb8112d6d2b5c2cbb257db2f20ff4be5a84e827b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787464"
---
# <a name="exportnestedtypeforwarder-method"></a><span data-ttu-id="f8791-102">ExportNestedTypeForwarder 方法</span><span class="sxs-lookup"><span data-stu-id="f8791-102">ExportNestedTypeForwarder Method</span></span>
<span data-ttu-id="f8791-103">将嵌套类型的类型转发器添加到给定程序集的类型表。</span><span class="sxs-lookup"><span data-stu-id="f8791-103">Adds a type forwarder for a nested type to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8791-104">语法</span><span class="sxs-lookup"><span data-stu-id="f8791-104">Syntax</span></span>  
  
```cpp  
HRESULT ExportNestedTypeForwarder(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8791-105">参数</span><span class="sxs-lookup"><span data-stu-id="f8791-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="f8791-106">要从中导出的程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="f8791-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="f8791-107">定义类型的文件的文件标记或程序集 ID。</span><span class="sxs-lookup"><span data-stu-id="f8791-107">File token or assembly ID of file that defines the type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="f8791-108">类型的标记。</span><span class="sxs-lookup"><span data-stu-id="f8791-108">Token for the type.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="f8791-109">父类型的标记。</span><span class="sxs-lookup"><span data-stu-id="f8791-109">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="f8791-110">要导出的完全限定的类型名称。</span><span class="sxs-lookup"><span data-stu-id="f8791-110">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="f8791-111">`ComType`标志， `tdPublic`如或`tdNested`。</span><span class="sxs-lookup"><span data-stu-id="f8791-111">`ComType` flags such as `tdPublic` or `tdNested`.</span></span>  
  
 `pType`  
 <span data-ttu-id="f8791-112">接收导出类型的令牌。</span><span class="sxs-lookup"><span data-stu-id="f8791-112">Receives token of export type.</span></span> <span data-ttu-id="f8791-113">这仅适用于发出嵌套类型。</span><span class="sxs-lookup"><span data-stu-id="f8791-113">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f8791-114">返回值</span><span class="sxs-lookup"><span data-stu-id="f8791-114">Return Value</span></span>  
 <span data-ttu-id="f8791-115">如果该方法成功，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="f8791-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8791-116">要求</span><span class="sxs-lookup"><span data-stu-id="f8791-116">Requirements</span></span>  
 <span data-ttu-id="f8791-117">需要 alink</span><span class="sxs-lookup"><span data-stu-id="f8791-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8791-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="f8791-118">See also</span></span>

- [<span data-ttu-id="f8791-119">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="f8791-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="f8791-120">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="f8791-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="f8791-121">ALink API</span><span class="sxs-lookup"><span data-stu-id="f8791-121">ALink API</span></span>](index.md)

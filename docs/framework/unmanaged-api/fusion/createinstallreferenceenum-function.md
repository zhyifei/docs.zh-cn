---
title: CreateInstallReferenceEnum 函数
ms.date: 03/30/2017
api_name:
- CreateInstallReferenceEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateInstallReference
helpviewer_keywords:
- CreateInstallReference function [.NET Framework fusion]
ms.assetid: 80dbbbf8-54fc-4894-b74a-0179d3201083
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d696326ff8861ed8496474f76e9eaf89b4ead3e8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795402"
---
# <a name="createinstallreferenceenum-function"></a><span data-ttu-id="2ed04-102">CreateInstallReferenceEnum 函数</span><span class="sxs-lookup"><span data-stu-id="2ed04-102">CreateInstallReferenceEnum Function</span></span>
<span data-ttu-id="2ed04-103">获取一个指针，该指针指向表示应用程序对指定程序集的引用列表的[IInstallReferenceEnum](iinstallreferenceenum-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="2ed04-103">Gets a pointer to an [IInstallReferenceEnum](iinstallreferenceenum-interface.md) instance that represents a list of an application's references to the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ed04-104">语法</span><span class="sxs-lookup"><span data-stu-id="2ed04-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateInstallReferenceEnum (  
    [out] IInstallReferenceEnum **ppRefEnum,  
    [in]  IAssemblyName         *pName,  
    [in]  DWORD                 dwFlags,  
    [in]  LPVOID                pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ed04-105">参数</span><span class="sxs-lookup"><span data-stu-id="2ed04-105">Parameters</span></span>  
 `ppRefEnum`  
 <span data-ttu-id="2ed04-106">弄返回`IInstallReferenceEnum`的指针。</span><span class="sxs-lookup"><span data-stu-id="2ed04-106">[out] The returned `IInstallReferenceEnum` pointer.</span></span>  
  
 `pName`  
 <span data-ttu-id="2ed04-107">中标识要枚举其引用的程序集的[IAssemblyName](iassemblyname-interface.md) 。</span><span class="sxs-lookup"><span data-stu-id="2ed04-107">[in] The [IAssemblyName](iassemblyname-interface.md) that identifies the assembly for which to enumerate references.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="2ed04-108">中影响枚举器行为的标志。</span><span class="sxs-lookup"><span data-stu-id="2ed04-108">[in] Flags that influence the enumerator's behavior.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="2ed04-109">中保留以供将来进行扩展。</span><span class="sxs-lookup"><span data-stu-id="2ed04-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="2ed04-110">`pvReserved`必须为空引用。</span><span class="sxs-lookup"><span data-stu-id="2ed04-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ed04-111">要求</span><span class="sxs-lookup"><span data-stu-id="2ed04-111">Requirements</span></span>  
 <span data-ttu-id="2ed04-112">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2ed04-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ed04-113">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="2ed04-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="2ed04-114">**类库**合成 .dll 和 Mscorwks.dll。</span><span class="sxs-lookup"><span data-stu-id="2ed04-114">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="2ed04-115">使用 Mscorwks.dll 而不是来确保目标为正确的 .NET Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="2ed04-115">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="2ed04-116">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ed04-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ed04-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="2ed04-117">See also</span></span>

- [<span data-ttu-id="2ed04-118">IInstallReferenceEnum 接口</span><span class="sxs-lookup"><span data-stu-id="2ed04-118">IInstallReferenceEnum Interface</span></span>](iinstallreferenceenum-interface.md)
- [<span data-ttu-id="2ed04-119">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="2ed04-119">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="2ed04-120">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="2ed04-120">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)

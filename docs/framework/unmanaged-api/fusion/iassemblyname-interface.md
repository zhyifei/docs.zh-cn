---
title: IAssemblyName 接口
ms.date: 03/30/2017
api_name:
- IAssemblyName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName
helpviewer_keywords:
- IAssemblyName interface [.NET Framework fusion]
ms.assetid: f7f8e605-6b67-4151-936f-f04ecd671d90
topic_type:
- apiref
ms.openlocfilehash: de49d66667033dfc6918b139f90cd5523661597f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134320"
---
# <a name="iassemblyname-interface"></a><span data-ttu-id="696cb-102">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="696cb-102">IAssemblyName Interface</span></span>
<span data-ttu-id="696cb-103">提供用于描述和处理程序集的唯一标识的方法。</span><span class="sxs-lookup"><span data-stu-id="696cb-103">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="696cb-104">方法</span><span class="sxs-lookup"><span data-stu-id="696cb-104">Methods</span></span>  
  
|<span data-ttu-id="696cb-105">方法</span><span class="sxs-lookup"><span data-stu-id="696cb-105">Method</span></span>|<span data-ttu-id="696cb-106">描述</span><span class="sxs-lookup"><span data-stu-id="696cb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="696cb-107">Clone 方法</span><span class="sxs-lookup"><span data-stu-id="696cb-107">Clone Method</span></span>](iassemblyname-clone-method.md)|<span data-ttu-id="696cb-108">创建此 `IAssemblyName` 对象的浅表副本。</span><span class="sxs-lookup"><span data-stu-id="696cb-108">Creates a shallow copy of this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="696cb-109">Finalize 方法</span><span class="sxs-lookup"><span data-stu-id="696cb-109">Finalize Method</span></span>](iassemblyname-finalize-method.md)|<span data-ttu-id="696cb-110">允许此 `IAssemblyName` 对象在调用其析构函数之前释放资源并执行其他清理操作。</span><span class="sxs-lookup"><span data-stu-id="696cb-110">Allows this `IAssemblyName` object to release resources and perform other cleanup operations before its destructor is called.</span></span>|  
|[<span data-ttu-id="696cb-111">GetDisplayName 方法</span><span class="sxs-lookup"><span data-stu-id="696cb-111">GetDisplayName Method</span></span>](iassemblyname-getdisplayname-method.md)|<span data-ttu-id="696cb-112">获取此 `IAssemblyName` 对象所引用的程序集的可读名称。</span><span class="sxs-lookup"><span data-stu-id="696cb-112">Gets the human-readable name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="696cb-113">GetName 方法</span><span class="sxs-lookup"><span data-stu-id="696cb-113">GetName Method</span></span>](iassemblyname-getname-method.md)|<span data-ttu-id="696cb-114">获取此 `IAssemblyName` 对象所引用的程序集的简单、未加密名称。</span><span class="sxs-lookup"><span data-stu-id="696cb-114">Gets the simple, unencrypted name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="696cb-115">GetProperty 方法</span><span class="sxs-lookup"><span data-stu-id="696cb-115">GetProperty Method</span></span>](iassemblyname-getproperty-method.md)|<span data-ttu-id="696cb-116">获取一个指针，该指针指向由指定 `PropertyId`引用的属性。</span><span class="sxs-lookup"><span data-stu-id="696cb-116">Gets a pointer to the property referenced by the specified `PropertyId`.</span></span>|  
|[<span data-ttu-id="696cb-117">GetVersion 方法</span><span class="sxs-lookup"><span data-stu-id="696cb-117">GetVersion Method</span></span>](iassemblyname-getversion-method.md)|<span data-ttu-id="696cb-118">获取此 `IAssemblyName` 对象所引用的程序集的版本信息。</span><span class="sxs-lookup"><span data-stu-id="696cb-118">Gets the version information for the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="696cb-119">IsEqual 方法</span><span class="sxs-lookup"><span data-stu-id="696cb-119">IsEqual Method</span></span>](iassemblyname-isequal-method.md)|<span data-ttu-id="696cb-120">根据指定的比较标志，确定指定的 `IAssemblyName` 对象是否等于此 `IAssemblyName`。</span><span class="sxs-lookup"><span data-stu-id="696cb-120">Determines whether a specified `IAssemblyName` object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>|  
|[<span data-ttu-id="696cb-121">SetProperty 方法</span><span class="sxs-lookup"><span data-stu-id="696cb-121">SetProperty Method</span></span>](iassemblyname-setproperty-method.md)|<span data-ttu-id="696cb-122">设置由指定 `PropertyId`引用的属性的值。</span><span class="sxs-lookup"><span data-stu-id="696cb-122">Sets the value of the property referenced by the specified `PropertyId`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="696cb-123">要求</span><span class="sxs-lookup"><span data-stu-id="696cb-123">Requirements</span></span>  
 <span data-ttu-id="696cb-124">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="696cb-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="696cb-125">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="696cb-125">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="696cb-126">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="696cb-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="696cb-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="696cb-127">See also</span></span>

- [<span data-ttu-id="696cb-128">合成接口</span><span class="sxs-lookup"><span data-stu-id="696cb-128">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="696cb-129">IAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="696cb-129">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)

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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d8d59ef282818dd9852d0ff8d2ec2abd40986d0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697922"
---
# <a name="iassemblyname-interface"></a><span data-ttu-id="9d36a-102">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="9d36a-102">IAssemblyName Interface</span></span>
<span data-ttu-id="9d36a-103">提供用于描述和使用程序集的唯一标识的方法。</span><span class="sxs-lookup"><span data-stu-id="9d36a-103">Provides methods for describing and working with an assembly's unique identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9d36a-104">方法</span><span class="sxs-lookup"><span data-stu-id="9d36a-104">Methods</span></span>  
  
|<span data-ttu-id="9d36a-105">方法</span><span class="sxs-lookup"><span data-stu-id="9d36a-105">Method</span></span>|<span data-ttu-id="9d36a-106">描述</span><span class="sxs-lookup"><span data-stu-id="9d36a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9d36a-107">Clone 方法</span><span class="sxs-lookup"><span data-stu-id="9d36a-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-clone-method.md)|<span data-ttu-id="9d36a-108">创建的浅表副本`IAssemblyName`对象。</span><span class="sxs-lookup"><span data-stu-id="9d36a-108">Creates a shallow copy of this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="9d36a-109">Finalize 方法</span><span class="sxs-lookup"><span data-stu-id="9d36a-109">Finalize Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-finalize-method.md)|<span data-ttu-id="9d36a-110">允许此`IAssemblyName`对象释放资源并调用其析构函数之前执行其他清理操作。</span><span class="sxs-lookup"><span data-stu-id="9d36a-110">Allows this `IAssemblyName` object to release resources and perform other cleanup operations before its destructor is called.</span></span>|  
|[<span data-ttu-id="9d36a-111">GetDisplayName 方法</span><span class="sxs-lookup"><span data-stu-id="9d36a-111">GetDisplayName Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getdisplayname-method.md)|<span data-ttu-id="9d36a-112">获取此引用的程序集的用户可读名称`IAssemblyName`对象。</span><span class="sxs-lookup"><span data-stu-id="9d36a-112">Gets the human-readable name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="9d36a-113">GetName 方法</span><span class="sxs-lookup"><span data-stu-id="9d36a-113">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getname-method.md)|<span data-ttu-id="9d36a-114">获取此引用的程序集的简单、 非加密名称`IAssemblyName`对象。</span><span class="sxs-lookup"><span data-stu-id="9d36a-114">Gets the simple, unencrypted name of the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="9d36a-115">GetProperty 方法</span><span class="sxs-lookup"><span data-stu-id="9d36a-115">GetProperty Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getproperty-method.md)|<span data-ttu-id="9d36a-116">获取一个指针指向由指定引用的属性`PropertyId`。</span><span class="sxs-lookup"><span data-stu-id="9d36a-116">Gets a pointer to the property referenced by the specified `PropertyId`.</span></span>|  
|[<span data-ttu-id="9d36a-117">GetVersion 方法</span><span class="sxs-lookup"><span data-stu-id="9d36a-117">GetVersion Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getversion-method.md)|<span data-ttu-id="9d36a-118">获取此引用的程序集的版本信息`IAssemblyName`对象。</span><span class="sxs-lookup"><span data-stu-id="9d36a-118">Gets the version information for the assembly referenced by this `IAssemblyName` object.</span></span>|  
|[<span data-ttu-id="9d36a-119">IsEqual 方法</span><span class="sxs-lookup"><span data-stu-id="9d36a-119">IsEqual Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-isequal-method.md)|<span data-ttu-id="9d36a-120">确定指定`IAssemblyName`对象是否等于此`IAssemblyName`、 根据指定的比较标志。</span><span class="sxs-lookup"><span data-stu-id="9d36a-120">Determines whether a specified `IAssemblyName` object is equal to this `IAssemblyName`, based on the specified comparison flags.</span></span>|  
|[<span data-ttu-id="9d36a-121">SetProperty 方法</span><span class="sxs-lookup"><span data-stu-id="9d36a-121">SetProperty Method</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-setproperty-method.md)|<span data-ttu-id="9d36a-122">设置由指定引用的属性的值`PropertyId`。</span><span class="sxs-lookup"><span data-stu-id="9d36a-122">Sets the value of the property referenced by the specified `PropertyId`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9d36a-123">要求</span><span class="sxs-lookup"><span data-stu-id="9d36a-123">Requirements</span></span>  
 <span data-ttu-id="9d36a-124">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9d36a-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d36a-125">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="9d36a-125">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="9d36a-126">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d36a-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d36a-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="9d36a-127">See also</span></span>

- [<span data-ttu-id="9d36a-128">合成接口</span><span class="sxs-lookup"><span data-stu-id="9d36a-128">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="9d36a-129">IAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="9d36a-129">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)

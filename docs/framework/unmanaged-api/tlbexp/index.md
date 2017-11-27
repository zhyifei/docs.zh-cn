---
title: "Tlbexp 帮助器函数（非托管 API 参考）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- exporter tool [.NET Framework]
- TlbRef.dll
- Tlbexp.exe
- Type Library Exporter
ms.assetid: 5c0a3d14-5f26-4267-94a9-82c30f8db09a
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d5d0a0b08be725a50442a3db9f9942bceea7cf8a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="tlbexp-helper-functions-unmanaged-api-reference"></a><span data-ttu-id="69e9c-102">Tlbexp 帮助器函数（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="69e9c-102">Tlbexp Helper Functions (Unmanaged API Reference)</span></span>
<span data-ttu-id="69e9c-103">[类型库导出程序工具](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)(Tlbexp.exe) 加载名为 TlbRef.dll 一个动态链接库。</span><span class="sxs-lookup"><span data-stu-id="69e9c-103">The [Type Library Exporter tool](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) loads a dynamic link library named TlbRef.dll.</span></span> <span data-ttu-id="69e9c-104">此 DLL 包含两个 helper 函数和程序集到类型库的转换过程中使用导出程序工具的接口。</span><span class="sxs-lookup"><span data-stu-id="69e9c-104">This DLL contains two helper functions and an interface that the exporter tool uses during the assembly-to-type-library conversion process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="69e9c-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="69e9c-105">In This Section</span></span>  
 [<span data-ttu-id="69e9c-106">GetTypeLibInfo 函数</span><span class="sxs-lookup"><span data-stu-id="69e9c-106">GetTypeLibInfo Function</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/gettypelibinfo-function.md)  
 <span data-ttu-id="69e9c-107">提供类型库的本地化和操作系统的信息。</span><span class="sxs-lookup"><span data-stu-id="69e9c-107">Provides localization and operating system information for a type library.</span></span>  
  
 [<span data-ttu-id="69e9c-108">LoadTypeLibWithResolver 函数</span><span class="sxs-lookup"><span data-stu-id="69e9c-108">LoadTypeLibWithResolver Function</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md)  
 <span data-ttu-id="69e9c-109">通过使用的实现中加载类型库[ITypeLibResolver 接口](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)解析任何引用类型库。</span><span class="sxs-lookup"><span data-stu-id="69e9c-109">Loads a type library by using an implementation of the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) to resolve any referenced type libraries.</span></span>  
  
 [<span data-ttu-id="69e9c-110">ITypeLibResolver 接口</span><span class="sxs-lookup"><span data-stu-id="69e9c-110">ITypeLibResolver Interface</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)  
 <span data-ttu-id="69e9c-111">提供[ResolveTypeLib 方法](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md)，它返回的类型库的完全限定的路径。</span><span class="sxs-lookup"><span data-stu-id="69e9c-111">Provides the [ResolveTypeLib method](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md), which returns the fully qualified path of a type library.</span></span>

---
title: Tlbexp 帮助器函数（非托管 API 参考）
ms.date: 03/30/2017
helpviewer_keywords:
- exporter tool [.NET Framework]
- TlbRef.dll
- Tlbexp.exe
- Type Library Exporter
ms.assetid: 5c0a3d14-5f26-4267-94a9-82c30f8db09a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a95ff535a4d0847fbd4b8af28f873b67a1829a4f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798834"
---
# <a name="tlbexp-helper-functions-unmanaged-api-reference"></a><span data-ttu-id="1f416-102">Tlbexp 帮助器函数（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="1f416-102">Tlbexp Helper Functions (Unmanaged API Reference)</span></span>
<span data-ttu-id="1f416-103">[类型库导出程序工具](../../tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) 加载一个名为“TlbRef.dll”的动态链接库。</span><span class="sxs-lookup"><span data-stu-id="1f416-103">The [Type Library Exporter tool](../../tools/tlbexp-exe-type-library-exporter.md) (Tlbexp.exe) loads a dynamic link library named TlbRef.dll.</span></span> <span data-ttu-id="1f416-104">此 DLL 包含两个 helper 函数和导出程序工具在程序集到类型库转换过程中使用的接口。</span><span class="sxs-lookup"><span data-stu-id="1f416-104">This DLL contains two helper functions and an interface that the exporter tool uses during the assembly-to-type-library conversion process.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1f416-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="1f416-105">In This Section</span></span>  
 [<span data-ttu-id="1f416-106">GetTypeLibInfo 函数</span><span class="sxs-lookup"><span data-stu-id="1f416-106">GetTypeLibInfo Function</span></span>](gettypelibinfo-function.md)  
 <span data-ttu-id="1f416-107">提供类型库的本地化和操作系统信息。</span><span class="sxs-lookup"><span data-stu-id="1f416-107">Provides localization and operating system information for a type library.</span></span>  
  
 [<span data-ttu-id="1f416-108">LoadTypeLibWithResolver 函数</span><span class="sxs-lookup"><span data-stu-id="1f416-108">LoadTypeLibWithResolver Function</span></span>](loadtypelibwithresolver-function.md)  
 <span data-ttu-id="1f416-109">通过使用 [ITypeLibResolver 接口](itypelibresolver-interface.md)的实现来加载类型库，以解析任何引用的类型库。</span><span class="sxs-lookup"><span data-stu-id="1f416-109">Loads a type library by using an implementation of the [ITypeLibResolver interface](itypelibresolver-interface.md) to resolve any referenced type libraries.</span></span>  
  
 [<span data-ttu-id="1f416-110">ITypeLibResolver 接口</span><span class="sxs-lookup"><span data-stu-id="1f416-110">ITypeLibResolver Interface</span></span>](itypelibresolver-interface.md)  
 <span data-ttu-id="1f416-111">提供 [ResolveTypeLib 方法](resolvetypelib-method.md)，这会返回一个类型库的完全限定的路径。</span><span class="sxs-lookup"><span data-stu-id="1f416-111">Provides the [ResolveTypeLib method](resolvetypelib-method.md), which returns the fully qualified path of a type library.</span></span>

---
title: 如何：从类型库生成互操作程序集
ms.date: 03/30/2017
helpviewer_keywords:
- importing type library
- interop assemblies, generating
- Type Library Importer
- type libraries
- COM interop, importing type library
ms.assetid: 4afd40c3-68f2-41c5-8ec1-4951bc148b9c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 95e85578a4879a9af9f262a933150292a4f58ec2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54668855"
---
# <a name="how-to-generate-interop-assemblies-from-type-libraries"></a><span data-ttu-id="7d5d5-102">如何：从类型库生成互操作程序集</span><span class="sxs-lookup"><span data-stu-id="7d5d5-102">How to: Generate Interop Assemblies from Type Libraries</span></span>
<span data-ttu-id="7d5d5-103">[类型库导入程序 (Tlbexp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) 是一个命令行工具，可将 COM 类型库中包含的组件类和接口转换为元数据。</span><span class="sxs-lookup"><span data-stu-id="7d5d5-103">The [Type Library Importer (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) is a command-line tool that converts the coclasses and interfaces contained in a COM type library to metadata.</span></span> <span data-ttu-id="7d5d5-104">此工具会自动为类型信息创建互操作程序集和命名空间。</span><span class="sxs-lookup"><span data-stu-id="7d5d5-104">This tool creates an interop assembly and namespace for the type information automatically.</span></span> <span data-ttu-id="7d5d5-105">类的元数据可用之后，托管客户端可创建 COM 类型的实例并调用其方法，就像它是 .NET 实例一样。</span><span class="sxs-lookup"><span data-stu-id="7d5d5-105">After the metadata of a class is available, managed clients can create instances of the COM type and call its methods, just as if it were a .NET instance.</span></span> <span data-ttu-id="7d5d5-106">Tlbimp.exe 同时将整个类型库转换为元数据，而且无法生成类型库中定义的类型子集的类型信息。</span><span class="sxs-lookup"><span data-stu-id="7d5d5-106">Tlbimp.exe converts an entire type library to metadata at once and cannot generate type information for a subset of the types defined in a type library.</span></span>  
  
### <a name="to-generate-an-interop-assembly-from-a-type-library"></a><span data-ttu-id="7d5d5-107">从类型库生成的互操作程序集</span><span class="sxs-lookup"><span data-stu-id="7d5d5-107">To generate an interop assembly from a type library</span></span>  
  
1.  <span data-ttu-id="7d5d5-108">使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="7d5d5-108">Use the following command:</span></span>  
  
     <span data-ttu-id="7d5d5-109">tlbimp \<type-library-file></span><span class="sxs-lookup"><span data-stu-id="7d5d5-109">**tlbimp** \<*type-library-file*></span></span>  
  
     <span data-ttu-id="7d5d5-110">添加 /out: 开关会生成具有已更改名称的互操作程序集，如 LOANLib.dll。</span><span class="sxs-lookup"><span data-stu-id="7d5d5-110">Adding the **/out:** switch produces an interop assembly with an altered name, such as LOANLib.dll.</span></span> <span data-ttu-id="7d5d5-111">更改互操作程序集名称有助于将它与原始 COM DLL 区分开来，并防止因为具有重复名称而可能发生的问题。</span><span class="sxs-lookup"><span data-stu-id="7d5d5-111">Altering the interop assembly name can help distinguish it from the original COM DLL and prevent problems that can occur from having duplicate names.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d5d5-112">示例</span><span class="sxs-lookup"><span data-stu-id="7d5d5-112">Example</span></span>  
 <span data-ttu-id="7d5d5-113">以下命令在 `Loanlib` 命名空间中生成 Loanlib.dll 程序集。</span><span class="sxs-lookup"><span data-stu-id="7d5d5-113">The following command produces the Loanlib.dll assembly in the `Loanlib` namespace.</span></span>  
  
```  
tlbimp Loanlib.tlb  
```  
  
 <span data-ttu-id="7d5d5-114">以下命令生成具有已更改名称的互操作程序集 (LOANLib.dll)。</span><span class="sxs-lookup"><span data-stu-id="7d5d5-114">The following command produces an interop assembly with an altered name (LOANLib.dll).</span></span>  
  
```  
tlbimp LoanLib.tlb /out: LOANLib.dll  
```  
  
## <a name="see-also"></a><span data-ttu-id="7d5d5-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="7d5d5-115">See also</span></span>
- [<span data-ttu-id="7d5d5-116">将类型库作为程序集导入</span><span class="sxs-lookup"><span data-stu-id="7d5d5-116">Importing a Type Library as an Assembly</span></span>](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md)
- [<span data-ttu-id="7d5d5-117">向 .NET Framework 公开 COM 组件</span><span class="sxs-lookup"><span data-stu-id="7d5d5-117">Exposing COM Components to the .NET Framework</span></span>](../../../docs/framework/interop/exposing-com-components.md)

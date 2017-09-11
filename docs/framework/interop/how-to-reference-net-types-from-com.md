---
title: "如何：从 COM 中引用 .NET 类型"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- importing type library
- COM interop, referencing .NET types
- interoperation with unmanaged code, referencing .NET types
- referencing .NET types
- interoperation with unmanaged code, importing type library
- type libraries
- COM interop, importing type library
ms.assetid: 54917f6f-cb18-4103-b622-856b55da93f3
caps.latest.revision: 7
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 345a698a4d45093dfb873a8303712a7bff5046cd
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="how-to-reference-net-types-from-com"></a><span data-ttu-id="c60c4-102">如何：从 COM 中引用 .NET 类型</span><span class="sxs-lookup"><span data-stu-id="c60c4-102">How to: Reference .NET Types from COM</span></span>
<span data-ttu-id="c60c4-103">从客户端和服务器代码的角度看，COM 和 .NET Framework 之间的区别在很大程度上是不可见的。</span><span class="sxs-lookup"><span data-stu-id="c60c4-103">From the point of view of client and server code, the differences between COM and the .NET Framework are largely invisible.</span></span> <span data-ttu-id="c60c4-104">Microsoft Visual Basic 客户端可在对象浏览器中查看 .NET 对象，这将公开对象方法和语法、属性和字段，正如任何其他 COM 对象那样。</span><span class="sxs-lookup"><span data-stu-id="c60c4-104">Microsoft Visual Basic clients can view a .NET object in the object browser, which exposes the object methods and syntax, properties, and fields exactly as if it were any other COM object.</span></span>  
  
 <span data-ttu-id="c60c4-105">尽管使用相同的工具将元数据导出到 COM 类型库，导入类型库的过程对于 C++ 客户端来说稍微复杂一些。</span><span class="sxs-lookup"><span data-stu-id="c60c4-105">The process for importing a type library is slightly more complicated for C++ clients, although you use the same tools to export metadata to a COM type library.</span></span> <span data-ttu-id="c60c4-106">要从非托管 C++ 客户端引用 .NET 对象成员，通过“#import”指令引用 TLB 文件（使用 Tlbexp.exe 生成）。</span><span class="sxs-lookup"><span data-stu-id="c60c4-106">To reference .NET object members from an unmanaged C++ client, reference the TLB file (produced with Tlbexp.exe) with the **#import** directive.</span></span> <span data-ttu-id="c60c4-107">从 C++ 引用类型库时，必须指定“raw_interfaces_only”选项或在基类库 Mscorlib.tlb 中导入定义。</span><span class="sxs-lookup"><span data-stu-id="c60c4-107">When referencing a type library from C++, you must either specify the **raw_interfaces_only** option or import the definitions in the base class library, Mscorlib.tlb.</span></span>  
  
### <a name="to-import-a-library"></a><span data-ttu-id="c60c4-108">导入库</span><span class="sxs-lookup"><span data-stu-id="c60c4-108">To import a library</span></span>  
  
-   <span data-ttu-id="c60c4-109">在“#import”指令中指定“raw_interfaces_only”选项。</span><span class="sxs-lookup"><span data-stu-id="c60c4-109">Specify the **raw_interfaces_only** option in the **#import** directive.</span></span> <span data-ttu-id="c60c4-110">例如: </span><span class="sxs-lookup"><span data-stu-id="c60c4-110">For example:</span></span>  
  
    ```cpp  
    #import "..\LoanLib\LoanLib.tlb" raw_interfaces_only  
    ```  
  
     <span data-ttu-id="c60c4-111">- 或 -</span><span class="sxs-lookup"><span data-stu-id="c60c4-111">-or-</span></span>  
  
-   <span data-ttu-id="c60c4-112">包括用于 Mscorlib.tlb 的 #import 指令。</span><span class="sxs-lookup"><span data-stu-id="c60c4-112">Include an #import directive for Mscorlib.tlb.</span></span> <span data-ttu-id="c60c4-113">例如: </span><span class="sxs-lookup"><span data-stu-id="c60c4-113">For example:</span></span>  
  
    ```cpp  
    #import "mscorlib.tlb"  
    #import "..\LoanLib\LoanLib.tlb"  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c60c4-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c60c4-114">See Also</span></span>  
 <span data-ttu-id="c60c4-115">[向 COM 公开 .NET Framework 组件](../../../docs/framework/interop/exposing-dotnet-components-to-com.md) </span><span class="sxs-lookup"><span data-stu-id="c60c4-115">[Exposing .NET Framework Components to COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md) </span></span>  
 <span data-ttu-id="c60c4-116">[向 COM 注册程序集](../../../docs/framework/interop/registering-assemblies-with-com.md) </span><span class="sxs-lookup"><span data-stu-id="c60c4-116">[Registering Assemblies with COM](../../../docs/framework/interop/registering-assemblies-with-com.md) </span></span>  
 <span data-ttu-id="c60c4-117">[调用 .NET 对象](http://msdn.microsoft.com/en-us/40c9626c-aea6-4bad-b8f0-c1de462efd33) </span><span class="sxs-lookup"><span data-stu-id="c60c4-117">[Calling a .NET Object](http://msdn.microsoft.com/en-us/40c9626c-aea6-4bad-b8f0-c1de462efd33) </span></span>  
 [<span data-ttu-id="c60c4-118">为 COM 访问部署应用程序</span><span class="sxs-lookup"><span data-stu-id="c60c4-118">Deploying an Application for COM Access</span></span>](http://msdn.microsoft.com/en-us/fb63564c-c1b9-4655-a094-a235625882ce)


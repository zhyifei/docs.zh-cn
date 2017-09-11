---
title: "平台调用示例"
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
- examples [.NET Framework], platform invoke
- unmanaged functions
- COM interop, platform invoke
- platform invoke, examples
- interoperation with unmanaged code, platform invoke
- DLL functions
ms.assetid: 15926806-f0b7-487e-93a6-4e9367ec689f
caps.latest.revision: 10
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ec8f261ab6f6f8b0c57f302859e1212d237b12aa
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="platform-invoke-examples"></a><span data-ttu-id="4dd62-102">平台调用示例</span><span class="sxs-lookup"><span data-stu-id="4dd62-102">Platform Invoke Examples</span></span>
<span data-ttu-id="4dd62-103">以下示例演示如何定义和调用 User32.dll 中的 MessageBox 函数，并将简单字符串作为参数传递。</span><span class="sxs-lookup"><span data-stu-id="4dd62-103">The following examples demonstrate how to define and call the **MessageBox** function in User32.dll, passing a simple string as an argument.</span></span> <span data-ttu-id="4dd62-104">在这些示例中，<xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=fullName> 字段设置为 Auto，以让目标平台确定字符宽度和字符串封送处理。</span><span class="sxs-lookup"><span data-stu-id="4dd62-104">In the examples, the <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=fullName> field is set to **Auto** to let the target platform determine the character width and string marshaling.</span></span>  
  
 <span data-ttu-id="4dd62-105">[!code-cpp[Conceptual.Interop.PInvoke#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.Interop.PInvoke/cpp/Example.cpp#1)] [!code-csharp[Conceptual.Interop.PInvoke#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.Interop.PInvoke/cs/Example1.cs#1)] [!code-vb[Conceptual.Interop.PInvoke#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.Interop.PInvoke/vb/Example1.vb#1)]</span><span class="sxs-lookup"><span data-stu-id="4dd62-105">[!code-cpp[Conceptual.Interop.PInvoke#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.Interop.PInvoke/cpp/Example.cpp#1)] [!code-csharp[Conceptual.Interop.PInvoke#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.Interop.PInvoke/cs/Example1.cs#1)] [!code-vb[Conceptual.Interop.PInvoke#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.Interop.PInvoke/vb/Example1.vb#1)]</span></span>   
  
 <span data-ttu-id="4dd62-106">有关其他示例，请参阅[通过平台调用封送处理数据](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)。</span><span class="sxs-lookup"><span data-stu-id="4dd62-106">For additional examples, see [Marshaling Data with Platform Invoke](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dd62-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4dd62-107">See Also</span></span>  
 <span data-ttu-id="4dd62-108"><xref:System.Runtime.InteropServices.DllImportAttribute></span><span class="sxs-lookup"><span data-stu-id="4dd62-108"><xref:System.Runtime.InteropServices.DllImportAttribute></span></span>   
 <span data-ttu-id="4dd62-109">[在托管代码中创建原型](../../../docs/framework/interop/creating-prototypes-in-managed-code.md) </span><span class="sxs-lookup"><span data-stu-id="4dd62-109">[Creating Prototypes in Managed Code](../../../docs/framework/interop/creating-prototypes-in-managed-code.md) </span></span>  
 [<span data-ttu-id="4dd62-110">指定字符集</span><span class="sxs-lookup"><span data-stu-id="4dd62-110">Specifying a Character Set</span></span>](../../../docs/framework/interop/specifying-a-character-set.md)


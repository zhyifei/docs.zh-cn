---
title: 封送 MDA
ms.date: 03/30/2017
helpviewer_keywords:
- marshaling, run-time errors
- marshaling MDA
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
ms.assetid: 5433b1f8-b0e5-40c9-a49a-0e5bd213363d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 463c8e42e76a61eb0820c1af72c20d004161ad25
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61753967"
---
# <a name="marshaling-mda"></a><span data-ttu-id="94400-102">封送 MDA</span><span class="sxs-lookup"><span data-stu-id="94400-102">marshaling MDA</span></span>
<span data-ttu-id="94400-103">当 CLR 为方法参数或结构的字段设置封送处理信息时，将激活 `marshaling` 托管调试助手 (MDA)。</span><span class="sxs-lookup"><span data-stu-id="94400-103">The `marshaling` managed debugging assistant (MDA) is activated when the CLR sets up marshaling information for a method parameter or a field of a structure.</span></span> <span data-ttu-id="94400-104">此 MDA 不适合 JIT 编译的程序集。</span><span class="sxs-lookup"><span data-stu-id="94400-104">This MDA does not work for JIT-compiled assemblies.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="94400-105">对运行时的影响</span><span class="sxs-lookup"><span data-stu-id="94400-105">Effect on the Runtime</span></span>  
 <span data-ttu-id="94400-106">此 MDA 对 CLR 无任何影响。</span><span class="sxs-lookup"><span data-stu-id="94400-106">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="94400-107">Output</span><span class="sxs-lookup"><span data-stu-id="94400-107">Output</span></span>  
 <span data-ttu-id="94400-108">此 MDA 显示托管和非托管上下文中参数或字段的类型，以及包含此类型的结构或方法。</span><span class="sxs-lookup"><span data-stu-id="94400-108">The MDA displays the type of the parameter or field in the managed and unmanaged contexts, and the structure or method containing the type.</span></span>  <span data-ttu-id="94400-109">以下是字段输出的示例：</span><span class="sxs-lookup"><span data-stu-id="94400-109">The following is an example of the output for a field:</span></span>  
  
```  
Marshaling from 'Char' to 'ANSI char'  
name="assembly!Namespace.Class::myChar  
```  
  
## <a name="configuration"></a><span data-ttu-id="94400-110">配置</span><span class="sxs-lookup"><span data-stu-id="94400-110">Configuration</span></span>  
 <span data-ttu-id="94400-111">MDA 配置允许你基于所涉及的字段或方法名称，筛选报告的封送处理信息。</span><span class="sxs-lookup"><span data-stu-id="94400-111">The MDA configuration allows you to filter the reported marshaling information based on the involved field or method names.</span></span>  <span data-ttu-id="94400-112">以下示例演示如何使用 `methodFilter``fieldFilter` 和 `match` 元素指定筛选器。</span><span class="sxs-lookup"><span data-stu-id="94400-112">The following example shows the use of the `methodFilter`, `fieldFilter`, and `match` elements to specify filters.</span></span>  <span data-ttu-id="94400-113">将 `name` 的属性设置为星号 (\*) 可匹配所有内容。</span><span class="sxs-lookup"><span data-stu-id="94400-113">Setting the `name` attribute to an asterisk (\*) will match everything.</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <marshaling>  
      <methodFilter>  
        <match name="Method1"/>  
        <match name="Method2"/>  
      </methodFilter>  
      <fieldFilter>  
        <match name="Field1"/>  
        <match name="Field2"/>  
       </fieldFilter>  
    </marshaling>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="94400-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="94400-114">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="94400-115">使用托管调试助手诊断错误</span><span class="sxs-lookup"><span data-stu-id="94400-115">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="94400-116">互操作封送处理</span><span class="sxs-lookup"><span data-stu-id="94400-116">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)

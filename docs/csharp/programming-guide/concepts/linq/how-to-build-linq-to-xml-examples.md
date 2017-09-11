---
title: "如何：生成 LINQ to XML 示例 (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: e5d18fa1-2704-48fe-a44b-1564f97c9e9c
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d95748a69ac42f1c767dcf19c9f6d2edc8c872ee
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-build-linq-to-xml-examples-c"></a><span data-ttu-id="33625-102">如何：生成 LINQ to XML 示例 (C#)</span><span class="sxs-lookup"><span data-stu-id="33625-102">How to: Build LINQ to XML Examples (C#)</span></span>
<span data-ttu-id="33625-103">本文档中的各代码段和示例使用多个命名空间中的类和类型。</span><span class="sxs-lookup"><span data-stu-id="33625-103">The various snippets and examples in this documentation use classes and types from a variety of namespaces.</span></span> <span data-ttu-id="33625-104">在编译 C# 代码时，您需要提供相应的 `using` 指令。</span><span class="sxs-lookup"><span data-stu-id="33625-104">When compiling C# code, you need to supply appropriate `using` directives.</span></span>  
  
## <a name="example"></a><span data-ttu-id="33625-105">示例</span><span class="sxs-lookup"><span data-stu-id="33625-105">Example</span></span>  
 <span data-ttu-id="33625-106">下面的代码包含 C# 示例需要生成和运行的 `using` 指令。</span><span class="sxs-lookup"><span data-stu-id="33625-106">The following code contains the `using` directives that the C# examples require to build and run.</span></span> <span data-ttu-id="33625-107">并非每个示例都需要所有 `using` 指令。</span><span class="sxs-lookup"><span data-stu-id="33625-107">Not all `using` directives are required for every example.</span></span>  
  
```csharp  
using System;  
using System.Diagnostics;  
using System.Collections;  
using System.Collections.Generic;  
using System.Collections.Specialized;  
using System.Text;  
using System.Linq;  
using System.Xml;  
using System.Xml.Linq;  
using System.Xml.Schema;  
using System.Xml.XPath;  
using System.Xml.Xsl;  
using System.IO;  
using System.Threading;  
using System.Reflection;  
using System.IO.Packaging;  
```  
  
## <a name="see-also"></a><span data-ttu-id="33625-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33625-108">See Also</span></span>  
 [<span data-ttu-id="33625-109">LINQ to XML 编程概述 (C#)</span><span class="sxs-lookup"><span data-stu-id="33625-109">LINQ to XML Programming Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)


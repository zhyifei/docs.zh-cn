---
title: 如何生成 LINQ to XML 示例 (C#)
ms.date: 07/20/2015
ms.assetid: e5d18fa1-2704-48fe-a44b-1564f97c9e9c
ms.openlocfilehash: 289a13daed7e3c871156bf50c6fa04c113c0cd13
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141465"
---
# <a name="how-to-build-linq-to-xml-examples-c"></a><span data-ttu-id="6d2df-102">如何生成 LINQ to XML 示例 (C#)</span><span class="sxs-lookup"><span data-stu-id="6d2df-102">How to build LINQ to XML examples (C#)</span></span>
<span data-ttu-id="6d2df-103">本文档中的各代码段和示例使用多个命名空间中的类和类型。</span><span class="sxs-lookup"><span data-stu-id="6d2df-103">The various snippets and examples in this documentation use classes and types from a variety of namespaces.</span></span> <span data-ttu-id="6d2df-104">在编译 C# 代码时，您需要提供相应的 `using` 指令。</span><span class="sxs-lookup"><span data-stu-id="6d2df-104">When compiling C# code, you need to supply appropriate `using` directives.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d2df-105">示例</span><span class="sxs-lookup"><span data-stu-id="6d2df-105">Example</span></span>  
 <span data-ttu-id="6d2df-106">下面的代码包含 C# 示例需要生成和运行的 `using` 指令。</span><span class="sxs-lookup"><span data-stu-id="6d2df-106">The following code contains the `using` directives that the C# examples require to build and run.</span></span> <span data-ttu-id="6d2df-107">并非每个示例都需要所有 `using` 指令。</span><span class="sxs-lookup"><span data-stu-id="6d2df-107">Not all `using` directives are required for every example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6d2df-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="6d2df-108">See also</span></span>

- [<span data-ttu-id="6d2df-109">LINQ to XML 编程概述 (C#)</span><span class="sxs-lookup"><span data-stu-id="6d2df-109">LINQ to XML Programming Overview (C#)</span></span>](./linq-to-xml-overview.md)

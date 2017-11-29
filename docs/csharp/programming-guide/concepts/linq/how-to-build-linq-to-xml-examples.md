---
title: "如何：生成 LINQ to XML 示例 (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: e5d18fa1-2704-48fe-a44b-1564f97c9e9c
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8df8555f587714834b2c444f3455d505a39dac02
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-build-linq-to-xml-examples-c"></a><span data-ttu-id="92be0-102">如何：生成 LINQ to XML 示例 (C#)</span><span class="sxs-lookup"><span data-stu-id="92be0-102">How to: Build LINQ to XML Examples (C#)</span></span>
<span data-ttu-id="92be0-103">本文档中的各代码段和示例使用多个命名空间中的类和类型。</span><span class="sxs-lookup"><span data-stu-id="92be0-103">The various snippets and examples in this documentation use classes and types from a variety of namespaces.</span></span> <span data-ttu-id="92be0-104">在编译 C# 代码时，您需要提供相应的 `using` 指令。</span><span class="sxs-lookup"><span data-stu-id="92be0-104">When compiling C# code, you need to supply appropriate `using` directives.</span></span>  
  
## <a name="example"></a><span data-ttu-id="92be0-105">示例</span><span class="sxs-lookup"><span data-stu-id="92be0-105">Example</span></span>  
 <span data-ttu-id="92be0-106">下面的代码包含 C# 示例需要生成和运行的 `using` 指令。</span><span class="sxs-lookup"><span data-stu-id="92be0-106">The following code contains the `using` directives that the C# examples require to build and run.</span></span> <span data-ttu-id="92be0-107">并非每个示例都需要所有 `using` 指令。</span><span class="sxs-lookup"><span data-stu-id="92be0-107">Not all `using` directives are required for every example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="92be0-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="92be0-108">See Also</span></span>  
 [<span data-ttu-id="92be0-109">LINQ to XML 编程概述 (C#)</span><span class="sxs-lookup"><span data-stu-id="92be0-109">LINQ to XML Programming Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)

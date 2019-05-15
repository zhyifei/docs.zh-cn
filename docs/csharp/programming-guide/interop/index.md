---
title: 互操作性 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- COM interop
- interoperability
- platform invoke, accessing APIs with C#
- C# language, interoperability
ms.assetid: 238bb95a-e962-4026-bbd5-197055bdb8ee
ms.openlocfilehash: b568bdc149123b490f3b058afc668aabcf558d55
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2019
ms.locfileid: "65585465"
---
# <a name="interoperability-c-programming-guide"></a><span data-ttu-id="7601e-102">互操作性（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="7601e-102">Interoperability (C# Programming Guide)</span></span>
<span data-ttu-id="7601e-103">借助互操作性，可以保留和利用对非托管代码的现有投资工作。</span><span class="sxs-lookup"><span data-stu-id="7601e-103">Interoperability enables you to preserve and take advantage of existing investments in unmanaged code.</span></span> <span data-ttu-id="7601e-104">在公共语言运行时 (CLR) 控制下运行的代码称为*托管代码*，不在 CLR 控制下运行的代码称为*非托管代码*。</span><span class="sxs-lookup"><span data-stu-id="7601e-104">Code that runs under the control of the common language runtime (CLR) is called *managed code*, and code that runs outside the CLR is called *unmanaged code*.</span></span> <span data-ttu-id="7601e-105">例如，COM、COM+、C++ 组件、ActiveX 组件和 Microsoft Windows API 都是非托管代码。</span><span class="sxs-lookup"><span data-stu-id="7601e-105">COM, COM+, C++ components, ActiveX components, and Microsoft Windows API are examples of unmanaged code.</span></span>  
  
 <span data-ttu-id="7601e-106">使用 .NET Framework，可以通过平台调用服务、<xref:System.Runtime.InteropServices> 命名空间、C++ 互操作性和 COM 互操作性（COM 互操作），实现与非托管代码的互操作性。</span><span class="sxs-lookup"><span data-stu-id="7601e-106">The .NET Framework enables interoperability with unmanaged code through platform invoke services, the <xref:System.Runtime.InteropServices> namespace, C++ interoperability, and COM interoperability (COM interop).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7601e-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="7601e-107">In This Section</span></span>  
 [<span data-ttu-id="7601e-108">互操作性概述</span><span class="sxs-lookup"><span data-stu-id="7601e-108">Interoperability Overview</span></span>](../../../csharp/programming-guide/interop/interoperability-overview.md)  
 <span data-ttu-id="7601e-109">介绍了实现 C# 托管代码和非托管代码的互操作性的方法。</span><span class="sxs-lookup"><span data-stu-id="7601e-109">Describes methods to interoperate between C# managed code and unmanaged code.</span></span>  
  
 [<span data-ttu-id="7601e-110">如何：通过使用 Visual C# 功能访问 Office 互操作对象</span><span class="sxs-lookup"><span data-stu-id="7601e-110">How to: Access Office Interop Objects by Using Visual C# Features</span></span>](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)  
 <span data-ttu-id="7601e-111">介绍了 Visual C# 为了推动 Office 编程而引入的功能 。</span><span class="sxs-lookup"><span data-stu-id="7601e-111">Describes features that are introduced in Visual C# to facilitate Office programming.</span></span>  
  
 [<span data-ttu-id="7601e-112">如何：在 COM 互操作编程中使用已编制索引的属性</span><span class="sxs-lookup"><span data-stu-id="7601e-112">How to: Use Indexed Properties in COM Interop Programming</span></span>](../../../csharp/programming-guide/interop/how-to-use-indexed-properties-in-com-interop-rogramming.md)  
 <span data-ttu-id="7601e-113">介绍了如何使用已编入索引的属性来访问包含参数的 COM 属性。</span><span class="sxs-lookup"><span data-stu-id="7601e-113">Describes how to use indexed properties to access COM properties that have parameters.</span></span>  
  
 [<span data-ttu-id="7601e-114">如何：使用平台调用播放波形文件</span><span class="sxs-lookup"><span data-stu-id="7601e-114">How to: Use Platform Invoke to Play a Wave File</span></span>](../../../csharp/programming-guide/interop/how-to-use-platform-invoke-to-play-a-wave-file.md)  
 <span data-ttu-id="7601e-115">介绍了如何使用平台调用服务在 Windows 操作系统中播放 .wav 声音文件。</span><span class="sxs-lookup"><span data-stu-id="7601e-115">Describes how to use platform invoke services to play a .wav sound file on the Windows operating system.</span></span>  
  
 [<span data-ttu-id="7601e-116">演练：Office 编程</span><span class="sxs-lookup"><span data-stu-id="7601e-116">Walkthrough: Office Programming</span></span>](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)  
 <span data-ttu-id="7601e-117">展示了如何创建 Excel 工作簿和包含指向此工作簿的链接的 Word 文档。</span><span class="sxs-lookup"><span data-stu-id="7601e-117">Shows how to create an Excel workbook and a Word document that contains a link to the workbook.</span></span>  
  
 [<span data-ttu-id="7601e-118">COM 类示例</span><span class="sxs-lookup"><span data-stu-id="7601e-118">Example COM Class</span></span>](../../../csharp/programming-guide/interop/example-com-class.md)  
 <span data-ttu-id="7601e-119">展示了如何将 C# 类公开为 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="7601e-119">Demonstrates how to expose a C# class as a COM object.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="7601e-120">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="7601e-120">C# Language Specification</span></span>  

<span data-ttu-id="7601e-121">有关详细信息，请参阅 [C# 语言规范](../../language-reference/language-specification/index.md)中的[基本概念](~/_csharplang/spec/unsafe-code.md)。</span><span class="sxs-lookup"><span data-stu-id="7601e-121">For more information, see [Basic concepts](~/_csharplang/spec/unsafe-code.md) in the [C# Language Specification](../../language-reference/language-specification/index.md).</span></span> <span data-ttu-id="7601e-122">该语言规范是 C# 语法和用法的权威资料。</span><span class="sxs-lookup"><span data-stu-id="7601e-122">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7601e-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="7601e-123">See also</span></span>

- <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType>
- [<span data-ttu-id="7601e-124">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="7601e-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="7601e-125">与非托管代码交互操作</span><span class="sxs-lookup"><span data-stu-id="7601e-125">Interoperating with Unmanaged Code</span></span>](../../../../docs/framework/interop/index.md)
- [<span data-ttu-id="7601e-126">演练：Office 编程</span><span class="sxs-lookup"><span data-stu-id="7601e-126">Walkthrough: Office Programming</span></span>](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)

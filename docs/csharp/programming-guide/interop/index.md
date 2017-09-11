---
title: "互操作性（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- COM interop
- interoperability
- platform invoke, accessing APIs with C#
- C# language, interoperability
ms.assetid: 238bb95a-e962-4026-bbd5-197055bdb8ee
caps.latest.revision: 31
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: df2f33c4599baef6d606738cbe5766fdd88e4ef3
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="interoperability-c-programming-guide"></a><span data-ttu-id="ab693-102">互操作性（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="ab693-102">Interoperability (C# Programming Guide)</span></span>
<span data-ttu-id="ab693-103">借助互操作性，可以保留和利用对非托管代码的现有投资工作。</span><span class="sxs-lookup"><span data-stu-id="ab693-103">Interoperability enables you to preserve and take advantage of existing investments in unmanaged code.</span></span> <span data-ttu-id="ab693-104">在公共语言运行时 (CLR) 控制下运行的代码称为*托管代码*，不在 CLR 控制下运行的代码称为*非托管代码*。</span><span class="sxs-lookup"><span data-stu-id="ab693-104">Code that runs under the control of the common language runtime (CLR) is called *managed code*, and code that runs outside the CLR is called *unmanaged code*.</span></span> <span data-ttu-id="ab693-105">例如，COM、COM+、C++ 组件、ActiveX 组件和 Microsoft Win32 API 都是非托管代码。</span><span class="sxs-lookup"><span data-stu-id="ab693-105">COM, COM+, C++ components, ActiveX components, and Microsoft Win32 API are examples of unmanaged code.</span></span>  
  
 <span data-ttu-id="ab693-106">使用 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]，可以通过平台调用服务、<xref:System.Runtime.InteropServices> 命名空间、C++ 互操作性和 COM 互操作性（COM 互操作），实现与非托管代码的互操作性。</span><span class="sxs-lookup"><span data-stu-id="ab693-106">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] enables interoperability with unmanaged code through platform invoke services, the <xref:System.Runtime.InteropServices> namespace, C++ interoperability, and COM interoperability (COM interop).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ab693-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="ab693-107">In This Section</span></span>  
 [<span data-ttu-id="ab693-108">互操作性概述</span><span class="sxs-lookup"><span data-stu-id="ab693-108">Interoperability Overview</span></span>](../../../csharp/programming-guide/interop/interoperability-overview.md)  
 <span data-ttu-id="ab693-109">介绍了实现 C# 托管代码和非托管代码的互操作性的方法。</span><span class="sxs-lookup"><span data-stu-id="ab693-109">Describes methods to interoperate between C# managed code and unmanaged code.</span></span>  
  
 [<span data-ttu-id="ab693-110">如何：通过使用 Visual C# 功能访问 Office 互操作对象</span><span class="sxs-lookup"><span data-stu-id="ab693-110">How to: Access Office Interop Objects by Using Visual C# Features</span></span>](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)  
 <span data-ttu-id="ab693-111">介绍了 Visual C# 为了推动 Office 编程而引入的功能 。</span><span class="sxs-lookup"><span data-stu-id="ab693-111">Describes features that are introduced in Visual C# to facilitate Office programming.</span></span>  
  
 [<span data-ttu-id="ab693-112">如何：在 COM 互操作编程中使用索引属性</span><span class="sxs-lookup"><span data-stu-id="ab693-112">How to: Use Indexed Properties in COM Interop Programming</span></span>](../../../csharp/programming-guide/interop/how-to-use-indexed-properties-in-com-interop-rogramming.md)  
 <span data-ttu-id="ab693-113">介绍了如何使用已编入索引的属性来访问包含参数的 COM 属性。</span><span class="sxs-lookup"><span data-stu-id="ab693-113">Describes how to use indexed properties to access COM properties that have parameters.</span></span>  
  
 [<span data-ttu-id="ab693-114">如何：使用平台调用播放波形文件</span><span class="sxs-lookup"><span data-stu-id="ab693-114">How to: Use Platform Invoke to Play a Wave File</span></span>](../../../csharp/programming-guide/interop/how-to-use-platform-invoke-to-play-a-wave-file.md)  
 <span data-ttu-id="ab693-115">介绍了如何使用平台调用服务在 Windows 操作系统中播放 .wav 声音文件。</span><span class="sxs-lookup"><span data-stu-id="ab693-115">Describes how to use platform invoke services to play a .wav sound file on the Windows operating system.</span></span>  
  
 [<span data-ttu-id="ab693-116">演练：Office 编程</span><span class="sxs-lookup"><span data-stu-id="ab693-116">Walkthrough: Office Programming</span></span>](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)  
 <span data-ttu-id="ab693-117">展示了如何创建 Excel 工作簿和包含指向此工作簿的链接的 Word 文档。</span><span class="sxs-lookup"><span data-stu-id="ab693-117">Shows how to create an Excel workbook and a Word document that contains a link to the workbook.</span></span>  
  
 [<span data-ttu-id="ab693-118">COM 类示例</span><span class="sxs-lookup"><span data-stu-id="ab693-118">Example COM Class</span></span>](../../../csharp/programming-guide/interop/example-com-class.md)  
 <span data-ttu-id="ab693-119">展示了如何将 C# 类公开为 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="ab693-119">Demonstrates how to expose a C# class as a COM object.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="ab693-120">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="ab693-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ab693-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ab693-121">See Also</span></span>  
 <span data-ttu-id="ab693-122"><xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="ab693-122"><xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=fullName></span></span>   
 <span data-ttu-id="ab693-123">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ab693-123">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="ab693-124">[与非托管代码的互操作性](https://msdn.microsoft.com/library/sd10k43k) </span><span class="sxs-lookup"><span data-stu-id="ab693-124">[Interoperating with Unmanaged Code](https://msdn.microsoft.com/library/sd10k43k) </span></span>  
 [<span data-ttu-id="ab693-125">演练：Office 编程</span><span class="sxs-lookup"><span data-stu-id="ab693-125">Walkthrough: Office Programming</span></span>](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)


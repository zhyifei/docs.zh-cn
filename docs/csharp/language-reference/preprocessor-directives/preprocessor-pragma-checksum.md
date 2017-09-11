---
title: "#<a name=\"pragma-checksum-c-reference\"></a>杂注校验和（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#pragma checksum'
dev_langs:
- CSharp
helpviewer_keywords:
- '#pragma checksum [C#]'
ms.assetid: 3673e4ca-6098-4ec1-890f-8fceb2a794a2
caps.latest.revision: 11
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
ms.openlocfilehash: c48d99843b9ba398dfe8dc3cf0d2264aaf72be9f
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="pragma-checksum-c-reference"></a><span data-ttu-id="751dc-102">#pragma checksum（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="751dc-102">#pragma checksum (C# Reference)</span></span>
<span data-ttu-id="751dc-103">为源文件生成校验和，以帮助调试校验 [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] 页。</span><span class="sxs-lookup"><span data-stu-id="751dc-103">Generates checksums for source files to aid with debugging [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] pages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="751dc-104">语法</span><span class="sxs-lookup"><span data-stu-id="751dc-104">Syntax</span></span>  
  
```csharp
#pragma checksum "filename" "{guid}" "checksum bytes"  
```  
  
#### <a name="parameters"></a><span data-ttu-id="751dc-105">参数</span><span class="sxs-lookup"><span data-stu-id="751dc-105">Parameters</span></span>  
 `"filename"`  
 <span data-ttu-id="751dc-106">需要监视更改或更新的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="751dc-106">The name of the file that requires monitoring for changes or updates.</span></span>  
  
 `"{guid}"`  
 <span data-ttu-id="751dc-107">文件的全局唯一标识符 (GUID)。</span><span class="sxs-lookup"><span data-stu-id="751dc-107">The Globally Unique Identifier (GUID) for the file.</span></span>  
  
 `"checksum_bytes"`  
 <span data-ttu-id="751dc-108">表示校验和字节的十六进制数字的字符串。</span><span class="sxs-lookup"><span data-stu-id="751dc-108">The string of hexadecimal digits representing the bytes of the checksum.</span></span> <span data-ttu-id="751dc-109">必须是偶数个十六进制数字。</span><span class="sxs-lookup"><span data-stu-id="751dc-109">Must be an even number of hexadecimal digits.</span></span> <span data-ttu-id="751dc-110">奇数个十六进制数字会导致编译时警告，指令会被忽略。</span><span class="sxs-lookup"><span data-stu-id="751dc-110">An odd number of digits results in a compile-time warning, and the directive are  ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="751dc-111">备注</span><span class="sxs-lookup"><span data-stu-id="751dc-111">Remarks</span></span>  
 <span data-ttu-id="751dc-112">Visual Studio 调试器使用校验和确保它可始终找到正确的源。</span><span class="sxs-lookup"><span data-stu-id="751dc-112">The Visual Studio debugger uses a checksum to make sure  that it always finds the right source.</span></span> <span data-ttu-id="751dc-113">编译器为源文件计算校验和，然后将输出发出到程序数据库 (PDB) 文件。</span><span class="sxs-lookup"><span data-stu-id="751dc-113">The compiler computes the checksum for a source file, and then emits the output to the program database (PDB) file.</span></span> <span data-ttu-id="751dc-114">调试器随后使用 PDB 针对它为源文件计算的校验和进行比较。</span><span class="sxs-lookup"><span data-stu-id="751dc-114">The debugger then uses the PDB to compare against the checksum that it computes for the source file.</span></span>  
  
 <span data-ttu-id="751dc-115">此解决方案不适合 [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] 项目，因为计算的校验和用于生成的源文件，而不是 .aspx 文件。</span><span class="sxs-lookup"><span data-stu-id="751dc-115">This solution does not work for [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] projects, because the computed checksum is for the generated source file, rather than the .aspx file.</span></span> <span data-ttu-id="751dc-116">为了解决此问题，`#pragma checksum` 为 [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] 页提供了校验和支持。</span><span class="sxs-lookup"><span data-stu-id="751dc-116">To address this problem, `#pragma checksum` provides checksum support for [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] pages.</span></span>  
  
 <span data-ttu-id="751dc-117">在 [!INCLUDE[csprcs](~/includes/csprcs-md.md)] 中创建 [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] 项目时，生成的源文件包含从其生成源的 .aspx 文件的校验和。</span><span class="sxs-lookup"><span data-stu-id="751dc-117">When you create an [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] project in [!INCLUDE[csprcs](~/includes/csprcs-md.md)], the generated source file contains a checksum for the .aspx file, from which the source is generated.</span></span> <span data-ttu-id="751dc-118">编译器随后将此信息写入 PDB 文件中。</span><span class="sxs-lookup"><span data-stu-id="751dc-118">The compiler then writes this information into the PDB file.</span></span>  
  
 <span data-ttu-id="751dc-119">如果编译器在文件中未遇到 `#pragma checksum` 指令，则它会计算校验和并将值写入 PDB 文件中。</span><span class="sxs-lookup"><span data-stu-id="751dc-119">If the compiler encounters no `#pragma checksum` directive in the file, it computes the checksum and writes the value to the PDB file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="751dc-120">示例</span><span class="sxs-lookup"><span data-stu-id="751dc-120">Example</span></span>  
  
```csharp
class TestClass  
{  
    static int Main()  
    {  
        #pragma checksum "file.cs" "{3673e4ca-6098-4ec1-890f-8fceb2a794a2}" "{012345678AB}" // New checksum  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="751dc-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="751dc-121">See Also</span></span>  
 <span data-ttu-id="751dc-122">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="751dc-122">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="751dc-123">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="751dc-123">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="751dc-124">C# 预处理器指令</span><span class="sxs-lookup"><span data-stu-id="751dc-124">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)


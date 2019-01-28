---
title: '#pragma checksum - C# 参考'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#pragma checksum'
helpviewer_keywords:
- '#pragma checksum [C#]'
ms.assetid: 3673e4ca-6098-4ec1-890f-8fceb2a794a2
ms.openlocfilehash: c52e93bcf5771fe556730a1d7cf45b8f1c9432b6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54513017"
---
# <a name="pragma-checksum-c-reference"></a><span data-ttu-id="e14cf-102">#pragma checksum（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="e14cf-102">#pragma checksum (C# Reference)</span></span>
<span data-ttu-id="e14cf-103">为源文件生成校验和，以帮助调试校验 [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] 页。</span><span class="sxs-lookup"><span data-stu-id="e14cf-103">Generates checksums for source files to aid with debugging [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] pages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e14cf-104">语法</span><span class="sxs-lookup"><span data-stu-id="e14cf-104">Syntax</span></span>  
  
```csharp
#pragma checksum "filename" "{guid}" "checksum bytes"  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e14cf-105">参数</span><span class="sxs-lookup"><span data-stu-id="e14cf-105">Parameters</span></span>  
 `"filename"`  
 <span data-ttu-id="e14cf-106">需要监视更改或更新的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="e14cf-106">The name of the file that requires monitoring for changes or updates.</span></span>  
  
 `"{guid}"`  
 <span data-ttu-id="e14cf-107">哈希算法的全局唯一标识符 (GUID)。</span><span class="sxs-lookup"><span data-stu-id="e14cf-107">The Globally Unique Identifier (GUID) for the hash algorithm.</span></span>  
  
 `"checksum_bytes"`  
 <span data-ttu-id="e14cf-108">表示校验和字节的十六进制数字的字符串。</span><span class="sxs-lookup"><span data-stu-id="e14cf-108">The string of hexadecimal digits representing the bytes of the checksum.</span></span> <span data-ttu-id="e14cf-109">必须是偶数个十六进制数字。</span><span class="sxs-lookup"><span data-stu-id="e14cf-109">Must be an even number of hexadecimal digits.</span></span> <span data-ttu-id="e14cf-110">奇数个十六进制数字会导致编译时警告出现，且指令遭忽略。</span><span class="sxs-lookup"><span data-stu-id="e14cf-110">An odd number of digits results in a compile-time warning, and the directive are ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e14cf-111">备注</span><span class="sxs-lookup"><span data-stu-id="e14cf-111">Remarks</span></span>  
 <span data-ttu-id="e14cf-112">Visual Studio 调试器使用校验和确保它可始终找到正确的源。</span><span class="sxs-lookup"><span data-stu-id="e14cf-112">The Visual Studio debugger uses a checksum to make sure  that it always finds the right source.</span></span> <span data-ttu-id="e14cf-113">编译器为源文件计算校验和，然后将输出发出到程序数据库 (PDB) 文件。</span><span class="sxs-lookup"><span data-stu-id="e14cf-113">The compiler computes the checksum for a source file, and then emits the output to the program database (PDB) file.</span></span> <span data-ttu-id="e14cf-114">调试器随后使用 PDB 针对它为源文件计算的校验和进行比较。</span><span class="sxs-lookup"><span data-stu-id="e14cf-114">The debugger then uses the PDB to compare against the checksum that it computes for the source file.</span></span>  
  
 <span data-ttu-id="e14cf-115">此解决方案不适合 [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] 项目，因为计算的校验和用于生成的源文件，而不是 .aspx 文件。</span><span class="sxs-lookup"><span data-stu-id="e14cf-115">This solution does not work for [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] projects, because the computed checksum is for the generated source file, rather than the .aspx file.</span></span> <span data-ttu-id="e14cf-116">为了解决此问题，`#pragma checksum` 为 [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] 页提供了校验和支持。</span><span class="sxs-lookup"><span data-stu-id="e14cf-116">To address this problem, `#pragma checksum` provides checksum support for [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] pages.</span></span>  
  
 <span data-ttu-id="e14cf-117">在 Visual C# 中创建 [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] 项目时，生成的源文件包含从其生成源的 .aspx 文件的校验和。</span><span class="sxs-lookup"><span data-stu-id="e14cf-117">When you create an [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] project in Visual C#, the generated source file contains a checksum for the .aspx file, from which the source is generated.</span></span> <span data-ttu-id="e14cf-118">编译器随后将此信息写入 PDB 文件中。</span><span class="sxs-lookup"><span data-stu-id="e14cf-118">The compiler then writes this information into the PDB file.</span></span>  
  
 <span data-ttu-id="e14cf-119">如果编译器在文件中未遇到 `#pragma checksum` 指令，则它会计算校验和并将值写入 PDB 文件中。</span><span class="sxs-lookup"><span data-stu-id="e14cf-119">If the compiler encounters no `#pragma checksum` directive in the file, it computes the checksum and writes the value to the PDB file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e14cf-120">示例</span><span class="sxs-lookup"><span data-stu-id="e14cf-120">Example</span></span>  
  
```csharp
class TestClass  
{  
    static int Main()  
    {  
        #pragma checksum "file.cs" "{406EA660-64CF-4C82-B6F0-42D48172A799}" "ab007f1d23d9" // New checksum  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="e14cf-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="e14cf-121">See also</span></span>

- [<span data-ttu-id="e14cf-122">C# 参考</span><span class="sxs-lookup"><span data-stu-id="e14cf-122">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="e14cf-123">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="e14cf-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="e14cf-124">C# 预处理器指令</span><span class="sxs-lookup"><span data-stu-id="e14cf-124">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)

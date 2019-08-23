---
title: -filealign
ms.date: 03/10/2018
helpviewer_keywords:
- sections compiler option [Visual Basic]
- alignment compiler option [Visual Basic]
- -filealign compiler option [Visual Basic]
- section alignment
- /filealign compiler option [Visual Basic]
- filealign compiler option [Visual Basic]
ms.assetid: cc61ec3d-ad38-4b28-9659-099d73cad099
ms.openlocfilehash: 2893c1760a856a7d736e9c03ba33d9771722b5b2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929474"
---
# <a name="-filealign"></a><span data-ttu-id="8e44a-102">-filealign</span><span class="sxs-lookup"><span data-stu-id="8e44a-102">-filealign</span></span>
<span data-ttu-id="8e44a-103">指定输出文件各节的对齐位置。</span><span class="sxs-lookup"><span data-stu-id="8e44a-103">Specifies where to align the sections of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e44a-104">语法</span><span class="sxs-lookup"><span data-stu-id="8e44a-104">Syntax</span></span>  
  
```  
-filealign:number  
```  
  
## <a name="arguments"></a><span data-ttu-id="8e44a-105">自变量</span><span class="sxs-lookup"><span data-stu-id="8e44a-105">Arguments</span></span>  
 `number`  
 <span data-ttu-id="8e44a-106">必需。</span><span class="sxs-lookup"><span data-stu-id="8e44a-106">Required.</span></span> <span data-ttu-id="8e44a-107">一个值, 该值指定输出文件中各节的对齐方式。</span><span class="sxs-lookup"><span data-stu-id="8e44a-107">A value that specifies the alignment of sections in the output file.</span></span> <span data-ttu-id="8e44a-108">有效值为 512、1024、2048、4096 和 8192。</span><span class="sxs-lookup"><span data-stu-id="8e44a-108">Valid values are 512, 1024, 2048, 4096, and 8192.</span></span> <span data-ttu-id="8e44a-109">这些值以字节为单位。</span><span class="sxs-lookup"><span data-stu-id="8e44a-109">These values are in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e44a-110">备注</span><span class="sxs-lookup"><span data-stu-id="8e44a-110">Remarks</span></span>  
 <span data-ttu-id="8e44a-111">您可以使用`-filealign`选项指定输出文件中各节的对齐方式。</span><span class="sxs-lookup"><span data-stu-id="8e44a-111">You can use the `-filealign` option to specify the alignment of sections in your output file.</span></span> <span data-ttu-id="8e44a-112">节是可移植可执行 (PE) 文件中包含代码或数据的连续内存块。</span><span class="sxs-lookup"><span data-stu-id="8e44a-112">Sections are blocks of contiguous memory in a Portable Executable (PE) file that contains either code or data.</span></span> <span data-ttu-id="8e44a-113">`-filealign`选项允许你使用非标准对齐方式编译应用程序; 大多数开发人员不需要使用此选项。</span><span class="sxs-lookup"><span data-stu-id="8e44a-113">The `-filealign` option lets you compile your application with a nonstandard alignment; most developers do not need to use this option.</span></span>  
  
 <span data-ttu-id="8e44a-114">每个部分在作为`-filealign`值的倍数的边界上对齐。</span><span class="sxs-lookup"><span data-stu-id="8e44a-114">Each section is aligned on a boundary that is a multiple of the `-filealign` value.</span></span> <span data-ttu-id="8e44a-115">没有固定的默认值。</span><span class="sxs-lookup"><span data-stu-id="8e44a-115">There is no fixed default.</span></span> <span data-ttu-id="8e44a-116">如果`-filealign`未指定, 编译器将在编译时选取默认值。</span><span class="sxs-lookup"><span data-stu-id="8e44a-116">If `-filealign` is not specified, the compiler picks a default at compile time.</span></span>  
  
 <span data-ttu-id="8e44a-117">通过指定节大小, 可以更改输出文件的大小。</span><span class="sxs-lookup"><span data-stu-id="8e44a-117">By specifying the section size, you can change the size of the output file.</span></span> <span data-ttu-id="8e44a-118">修改节的大小可能对将在较小设备上运行的程序有用。</span><span class="sxs-lookup"><span data-stu-id="8e44a-118">Modifying section size may be useful for programs that will run on smaller devices.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8e44a-119">此`-filealign`选项在 Visual Studio 开发环境中不可用; 它仅在从命令行编译时可用。</span><span class="sxs-lookup"><span data-stu-id="8e44a-119">The `-filealign` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e44a-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="8e44a-120">See also</span></span>

- [<span data-ttu-id="8e44a-121">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="8e44a-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)

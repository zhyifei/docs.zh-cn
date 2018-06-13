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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf9c854060e5254cedc6c1004ac3e4f25fbdbbd8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650662"
---
# <a name="-filealign"></a><span data-ttu-id="f8ce1-102">-filealign</span><span class="sxs-lookup"><span data-stu-id="f8ce1-102">-filealign</span></span>
<span data-ttu-id="f8ce1-103">指定输出文件各节的对齐位置。</span><span class="sxs-lookup"><span data-stu-id="f8ce1-103">Specifies where to align the sections of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8ce1-104">语法</span><span class="sxs-lookup"><span data-stu-id="f8ce1-104">Syntax</span></span>  
  
```  
-filealign:number  
```  
  
## <a name="arguments"></a><span data-ttu-id="f8ce1-105">自变量</span><span class="sxs-lookup"><span data-stu-id="f8ce1-105">Arguments</span></span>  
 `number`  
 <span data-ttu-id="f8ce1-106">必须的。</span><span class="sxs-lookup"><span data-stu-id="f8ce1-106">Required.</span></span> <span data-ttu-id="f8ce1-107">一个值，指定输出文件中的各节的对齐方式。</span><span class="sxs-lookup"><span data-stu-id="f8ce1-107">A value that specifies the alignment of sections in the output file.</span></span> <span data-ttu-id="f8ce1-108">有效值为 512、1024、2048、4096 和 8192。</span><span class="sxs-lookup"><span data-stu-id="f8ce1-108">Valid values are 512, 1024, 2048, 4096, and 8192.</span></span> <span data-ttu-id="f8ce1-109">这些值以字节为单位。</span><span class="sxs-lookup"><span data-stu-id="f8ce1-109">These values are in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8ce1-110">备注</span><span class="sxs-lookup"><span data-stu-id="f8ce1-110">Remarks</span></span>  
 <span data-ttu-id="f8ce1-111">你可以使用`-filealign`选项以指定输出文件中的各节的对齐方式。</span><span class="sxs-lookup"><span data-stu-id="f8ce1-111">You can use the `-filealign` option to specify the alignment of sections in your output file.</span></span> <span data-ttu-id="f8ce1-112">节是包含代码或数据的可移植可执行文件 (PE) 文件中的连续内存块。</span><span class="sxs-lookup"><span data-stu-id="f8ce1-112">Sections are blocks of contiguous memory in a Portable Executable (PE) file that contains either code or data.</span></span> <span data-ttu-id="f8ce1-113">`-filealign`选项，可以编译为非标准的对齐方式与应用程序; 大多数开发人员不需要使用此选项。</span><span class="sxs-lookup"><span data-stu-id="f8ce1-113">The `-filealign` option lets you compile your application with a nonstandard alignment; most developers do not need to use this option.</span></span>  
  
 <span data-ttu-id="f8ce1-114">每个部分在的倍数的边界上对齐`-filealign`值。</span><span class="sxs-lookup"><span data-stu-id="f8ce1-114">Each section is aligned on a boundary that is a multiple of the `-filealign` value.</span></span> <span data-ttu-id="f8ce1-115">没有固定的默认值。</span><span class="sxs-lookup"><span data-stu-id="f8ce1-115">There is no fixed default.</span></span> <span data-ttu-id="f8ce1-116">如果`-filealign`未指定，则编译器在编译时将选取默认值。</span><span class="sxs-lookup"><span data-stu-id="f8ce1-116">If `-filealign` is not specified, the compiler picks a default at compile time.</span></span>  
  
 <span data-ttu-id="f8ce1-117">通过指定节的大小，你可以更改输出文件的大小。</span><span class="sxs-lookup"><span data-stu-id="f8ce1-117">By specifying the section size, you can change the size of the output file.</span></span> <span data-ttu-id="f8ce1-118">修改节的大小可能对将在较小设备上运行的程序有用。</span><span class="sxs-lookup"><span data-stu-id="f8ce1-118">Modifying section size may be useful for programs that will run on smaller devices.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f8ce1-119">`-filealign`选项不是可从 Visual Studio 开发环境中; 仅当从命令行进行编译时，它才可用。</span><span class="sxs-lookup"><span data-stu-id="f8ce1-119">The `-filealign` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8ce1-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="f8ce1-120">See Also</span></span>  
 [<span data-ttu-id="f8ce1-121">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="f8ce1-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)

---
title: /filealign
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- sections compiler option [Visual Basic]
- alignment compiler option [Visual Basic]
- -filealign compiler option [Visual Basic]
- section alignment
- /filealign compiler option [Visual Basic]
- filealign compiler option [Visual Basic]
ms.assetid: cc61ec3d-ad38-4b28-9659-099d73cad099
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: dbabc19c85501b97ef5443a6f6e12524f8de7d91
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="filealign"></a><span data-ttu-id="5f0c9-102">/filealign</span><span class="sxs-lookup"><span data-stu-id="5f0c9-102">/filealign</span></span>
<span data-ttu-id="5f0c9-103">指定输出文件各节的对齐位置。</span><span class="sxs-lookup"><span data-stu-id="5f0c9-103">Specifies where to align the sections of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f0c9-104">语法</span><span class="sxs-lookup"><span data-stu-id="5f0c9-104">Syntax</span></span>  
  
```  
/filealign:number  
```  
  
## <a name="arguments"></a><span data-ttu-id="5f0c9-105">参数</span><span class="sxs-lookup"><span data-stu-id="5f0c9-105">Arguments</span></span>  
 `number`  
 <span data-ttu-id="5f0c9-106">必需。</span><span class="sxs-lookup"><span data-stu-id="5f0c9-106">Required.</span></span> <span data-ttu-id="5f0c9-107">一个值，指定输出文件中的各节的对齐方式。</span><span class="sxs-lookup"><span data-stu-id="5f0c9-107">A value that specifies the alignment of sections in the output file.</span></span> <span data-ttu-id="5f0c9-108">有效值为 512、1024、2048、4096 和 8192。</span><span class="sxs-lookup"><span data-stu-id="5f0c9-108">Valid values are 512, 1024, 2048, 4096, and 8192.</span></span> <span data-ttu-id="5f0c9-109">这些值以字节为单位。</span><span class="sxs-lookup"><span data-stu-id="5f0c9-109">These values are in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5f0c9-110">备注</span><span class="sxs-lookup"><span data-stu-id="5f0c9-110">Remarks</span></span>  
 <span data-ttu-id="5f0c9-111">你可以使用`/filealign`选项以指定输出文件中的各节的对齐方式。</span><span class="sxs-lookup"><span data-stu-id="5f0c9-111">You can use the `/filealign` option to specify the alignment of sections in your output file.</span></span> <span data-ttu-id="5f0c9-112">节是包含代码或数据的可移植可执行文件 (PE) 文件中的连续内存块。</span><span class="sxs-lookup"><span data-stu-id="5f0c9-112">Sections are blocks of contiguous memory in a Portable Executable (PE) file that contains either code or data.</span></span> <span data-ttu-id="5f0c9-113">`/filealign`选项，可以编译为非标准的对齐方式与应用程序; 大多数开发人员不需要使用此选项。</span><span class="sxs-lookup"><span data-stu-id="5f0c9-113">The `/filealign` option lets you compile your application with a nonstandard alignment; most developers do not need to use this option.</span></span>  
  
 <span data-ttu-id="5f0c9-114">每个部分在的倍数的边界上对齐`/filealign`值。</span><span class="sxs-lookup"><span data-stu-id="5f0c9-114">Each section is aligned on a boundary that is a multiple of the `/filealign` value.</span></span> <span data-ttu-id="5f0c9-115">没有固定的默认值。</span><span class="sxs-lookup"><span data-stu-id="5f0c9-115">There is no fixed default.</span></span> <span data-ttu-id="5f0c9-116">如果`/filealign`未指定，则编译器在编译时将选取默认值。</span><span class="sxs-lookup"><span data-stu-id="5f0c9-116">If `/filealign` is not specified, the compiler picks a default at compile time.</span></span>  
  
 <span data-ttu-id="5f0c9-117">通过指定节的大小，你可以更改输出文件的大小。</span><span class="sxs-lookup"><span data-stu-id="5f0c9-117">By specifying the section size, you can change the size of the output file.</span></span> <span data-ttu-id="5f0c9-118">修改节的大小可能对将在较小设备上运行的程序有用。</span><span class="sxs-lookup"><span data-stu-id="5f0c9-118">Modifying section size may be useful for programs that will run on smaller devices.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5f0c9-119">`/filealign`选项不是可从 Visual Studio 开发环境中; 仅当从命令行进行编译时，它才可用。</span><span class="sxs-lookup"><span data-stu-id="5f0c9-119">The `/filealign` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f0c9-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f0c9-120">See Also</span></span>  
 [<span data-ttu-id="5f0c9-121">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="5f0c9-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)

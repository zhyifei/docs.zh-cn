---
title: -noconfig（C# 编译器选项）
ms.date: 07/20/2015
f1_keywords:
- /noconfig
helpviewer_keywords:
- /noconfig compiler option [C#]
- csc.rsp
- -noconfig compiler option [C#]
- noconfig compiler option [C#]
ms.assetid: cd26967e-e494-4c8c-b5c9-af13b2f78b2e
ms.openlocfilehash: 8d28ef1334df847865721783fa98aaa9d8c576be
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54528571"
---
# <a name="-noconfig-c-compiler-options"></a><span data-ttu-id="ee166-102">-noconfig（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="ee166-102">-noconfig (C# Compiler Options)</span></span>
<span data-ttu-id="ee166-103">-noconfig 选项告知编译器不要在 csc.rsp 文件中编译，该文件的位置和加载位置是与 csc.exe 文件相同的目录。</span><span class="sxs-lookup"><span data-stu-id="ee166-103">The **-noconfig** option tells the compiler not to compile with the csc.rsp file, which is located in and loaded from the same directory as the csc.exe file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee166-104">语法</span><span class="sxs-lookup"><span data-stu-id="ee166-104">Syntax</span></span>  
  
```console  
-noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="ee166-105">备注</span><span class="sxs-lookup"><span data-stu-id="ee166-105">Remarks</span></span>  
 <span data-ttu-id="ee166-106">csc.rsp 文件引用 .NET Framework 随附的所有程序集。</span><span class="sxs-lookup"><span data-stu-id="ee166-106">The csc.rsp file references all the assemblies shipped with the .NET Framework.</span></span> <span data-ttu-id="ee166-107">Visual Studio .NET 开发环境包括的实际引用取决于项目类型。</span><span class="sxs-lookup"><span data-stu-id="ee166-107">The actual references that the Visual Studio .NET development environment includes depend on the project type.</span></span>  
  
 <span data-ttu-id="ee166-108">可以修改 csc.rsp 文件并使用 csc.exe 的命令行指定每个编译中应包含的其他编译器选项（-noconfig 选项外）。</span><span class="sxs-lookup"><span data-stu-id="ee166-108">You can modify the csc.rsp file and specify additional compiler options that should be included in every compilation from the command line with csc.exe (except the **-noconfig** option).</span></span>  
  
 <span data-ttu-id="ee166-109">编译器将处理最后传递给 csc 命令的选项。</span><span class="sxs-lookup"><span data-stu-id="ee166-109">The compiler processes the options passed to the **csc** command last.</span></span> <span data-ttu-id="ee166-110">因此，命令行中的任何选项都将替代 csc.rsp 文件中相同选项的设置。</span><span class="sxs-lookup"><span data-stu-id="ee166-110">Therefore, any option on the command line overrides the setting of the same option in the csc.rsp file.</span></span>  
  
 <span data-ttu-id="ee166-111">如果不希望编译器查询和使用 csc.rsp 文件中的设置，请指定 -noconfig。</span><span class="sxs-lookup"><span data-stu-id="ee166-111">If you do not want the compiler to look for and use the settings in the csc.rsp file, specify **-noconfig**.</span></span>  
  
 <span data-ttu-id="ee166-112">此编译器选项在 Visual Studio 中不可用，并且无法以编程方式更改。</span><span class="sxs-lookup"><span data-stu-id="ee166-112">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee166-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="ee166-113">See also</span></span>

- [<span data-ttu-id="ee166-114">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="ee166-114">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="ee166-115">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="ee166-115">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

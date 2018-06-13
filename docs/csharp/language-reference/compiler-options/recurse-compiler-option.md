---
title: -recurse（C# 编译器选项）
ms.date: 07/20/2015
f1_keywords:
- /recurse
helpviewer_keywords:
- /recurse compiler option [C#]
- recurse compiler option [C#]
- -recurse compiler option [C#]
ms.assetid: 4e8212e5-04e3-45b1-8a42-41bc50e683b0
ms.openlocfilehash: 7d18fb2b1710e074653e054d003be762d947d1be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33214584"
---
# <a name="-recurse-c-compiler-options"></a><span data-ttu-id="86e0e-102">-recurse（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="86e0e-102">-recurse (C# Compiler Options)</span></span>
<span data-ttu-id="86e0e-103">通过 -recurse 选项，可在指定目录 (dir) 的所有子目录中，或项目目录的所有子目录中编译源代码文件。</span><span class="sxs-lookup"><span data-stu-id="86e0e-103">The -recurse option enables you to compile source code files in all child directories of either the specified directory (dir) or of the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86e0e-104">语法</span><span class="sxs-lookup"><span data-stu-id="86e0e-104">Syntax</span></span>  
  
```console  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="86e0e-105">自变量</span><span class="sxs-lookup"><span data-stu-id="86e0e-105">Arguments</span></span>  
 <span data-ttu-id="86e0e-106">`dir`（可选）</span><span class="sxs-lookup"><span data-stu-id="86e0e-106">`dir` (optional)</span></span>  
 <span data-ttu-id="86e0e-107">希望从中开始搜索的目录。</span><span class="sxs-lookup"><span data-stu-id="86e0e-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="86e0e-108">如未指定目录，搜索将从项目目录开始。</span><span class="sxs-lookup"><span data-stu-id="86e0e-108">If this is not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="86e0e-109">要搜索的文件。</span><span class="sxs-lookup"><span data-stu-id="86e0e-109">The file(s) to search for.</span></span> <span data-ttu-id="86e0e-110">允许通配符。</span><span class="sxs-lookup"><span data-stu-id="86e0e-110">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86e0e-111">备注</span><span class="sxs-lookup"><span data-stu-id="86e0e-111">Remarks</span></span>  
 <span data-ttu-id="86e0e-112">通过 -recurse 选项，可在指定目录 (`dir`) 的所有子目录中，或项目目录的所有子目录中编译源代码文件。</span><span class="sxs-lookup"><span data-stu-id="86e0e-112">The **-recurse** option lets you compile source code files in all child directories of either the specified directory (`dir`) or of the project directory.</span></span>  
  
 <span data-ttu-id="86e0e-113">可在文件名中使用通配符，对项目目录中的所有匹配文件进行编译，而无需使用 -recurse。</span><span class="sxs-lookup"><span data-stu-id="86e0e-113">You can use wildcards in a file name to compile all matching files in the project directory without using **-recurse**.</span></span>  
  
 <span data-ttu-id="86e0e-114">此编译器选项在 Visual Studio 中不可用，并且无法以编程方式更改。</span><span class="sxs-lookup"><span data-stu-id="86e0e-114">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86e0e-115">示例</span><span class="sxs-lookup"><span data-stu-id="86e0e-115">Example</span></span>  
 <span data-ttu-id="86e0e-116">在当前目录中编译所有 C# 文件：</span><span class="sxs-lookup"><span data-stu-id="86e0e-116">Compiles all C# files in the current directory:</span></span>  
  
```console  
csc *.cs  
```  
  
 <span data-ttu-id="86e0e-117">编译 dir1\dir2 目录及其下的任何目录中的所有 C# 文件，并生成 dir2.dll：</span><span class="sxs-lookup"><span data-stu-id="86e0e-117">Compiles all of the C# files in the dir1\dir2 directory and any directories below it and generates dir2.dll:</span></span>  
  
```console  
csc -target:library -out:dir2.dll -recurse:dir1\dir2\*.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="86e0e-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="86e0e-118">See Also</span></span>  
 [<span data-ttu-id="86e0e-119">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="86e0e-119">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="86e0e-120">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="86e0e-120">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

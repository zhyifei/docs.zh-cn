---
title: "-recurse（C# 编译器选项）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /recurse
helpviewer_keywords:
- /recurse compiler option [C#]
- recurse compiler option [C#]
- -recurse compiler option [C#]
ms.assetid: 4e8212e5-04e3-45b1-8a42-41bc50e683b0
caps.latest.revision: "12"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a053e5676b10de3bd2eecf6de8be7a30329962af
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="recurse-c-compiler-options"></a><span data-ttu-id="e7480-102">/recurse (C# 编译器选项)</span><span class="sxs-lookup"><span data-stu-id="e7480-102">/recurse (C# Compiler Options)</span></span>
<span data-ttu-id="e7480-103">通过 /recurse 选项，可在指定目录 (dir) 的所有子目录中，或项目目录的所有子目录中编译源代码文件。</span><span class="sxs-lookup"><span data-stu-id="e7480-103">The /recurse option enables you to compile source code files in all child directories of either the specified directory (dir) or of the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7480-104">语法</span><span class="sxs-lookup"><span data-stu-id="e7480-104">Syntax</span></span>  
  
```console  
/recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="e7480-105">参数</span><span class="sxs-lookup"><span data-stu-id="e7480-105">Arguments</span></span>  
 <span data-ttu-id="e7480-106">`dir`（可选）</span><span class="sxs-lookup"><span data-stu-id="e7480-106">`dir` (optional)</span></span>  
 <span data-ttu-id="e7480-107">希望从中开始搜索的目录。</span><span class="sxs-lookup"><span data-stu-id="e7480-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="e7480-108">如未指定目录，搜索将从项目目录开始。</span><span class="sxs-lookup"><span data-stu-id="e7480-108">If this is not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="e7480-109">要搜索的文件。</span><span class="sxs-lookup"><span data-stu-id="e7480-109">The file(s) to search for.</span></span> <span data-ttu-id="e7480-110">允许通配符。</span><span class="sxs-lookup"><span data-stu-id="e7480-110">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7480-111">备注</span><span class="sxs-lookup"><span data-stu-id="e7480-111">Remarks</span></span>  
 <span data-ttu-id="e7480-112">通过 /recurse 选项，可在指定目录 (`dir`) 的所有子目录中，或项目目录的所有子目录中编译源代码文件。</span><span class="sxs-lookup"><span data-stu-id="e7480-112">The **/recurse** option lets you compile source code files in all child directories of either the specified directory (`dir`) or of the project directory.</span></span>  
  
 <span data-ttu-id="e7480-113">可在文件名中使用通配符，对项目目录中的所有匹配文件进行编译，而无需使用 /recurse。</span><span class="sxs-lookup"><span data-stu-id="e7480-113">You can use wildcards in a file name to compile all matching files in the project directory without using **/recurse**.</span></span>  
  
 <span data-ttu-id="e7480-114">此编译器选项在 Visual Studio 中不可用，并且无法以编程方式更改。</span><span class="sxs-lookup"><span data-stu-id="e7480-114">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e7480-115">示例</span><span class="sxs-lookup"><span data-stu-id="e7480-115">Example</span></span>  
 <span data-ttu-id="e7480-116">在当前目录中编译所有 C# 文件：</span><span class="sxs-lookup"><span data-stu-id="e7480-116">Compiles all C# files in the current directory:</span></span>  
  
```console  
csc *.cs  
```  
  
 <span data-ttu-id="e7480-117">编译 dir1\dir2 目录及其下的任何目录中的所有 C# 文件，并生成 dir2.dll：</span><span class="sxs-lookup"><span data-stu-id="e7480-117">Compiles all of the C# files in the dir1\dir2 directory and any directories below it and generates dir2.dll:</span></span>  
  
```console  
csc /target:library /out:dir2.dll /recurse:dir1\dir2\*.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="e7480-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e7480-118">See Also</span></span>  
 [<span data-ttu-id="e7480-119">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="e7480-119">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="e7480-120">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="e7480-120">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

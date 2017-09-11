---
title: "-recurse（C# 编译器选项）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /recurse
dev_langs:
- CSharp
helpviewer_keywords:
- /recurse compiler option [C#]
- recurse compiler option [C#]
- -recurse compiler option [C#]
ms.assetid: 4e8212e5-04e3-45b1-8a42-41bc50e683b0
caps.latest.revision: 12
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
ms.openlocfilehash: 99664f8b32f5f9e5bf491c5bfde2c1649de42dd9
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="recurse-c-compiler-options"></a><span data-ttu-id="00f8f-102">/recurse (C# 编译器选项)</span><span class="sxs-lookup"><span data-stu-id="00f8f-102">/recurse (C# Compiler Options)</span></span>
<span data-ttu-id="00f8f-103">通过 /recurse 选项，可在指定目录 (dir) 的所有子目录中，或项目目录的所有子目录中编译源代码文件。</span><span class="sxs-lookup"><span data-stu-id="00f8f-103">The /recurse option enables you to compile source code files in all child directories of either the specified directory (dir) or of the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00f8f-104">语法</span><span class="sxs-lookup"><span data-stu-id="00f8f-104">Syntax</span></span>  
  
```console  
/recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="00f8f-105">参数</span><span class="sxs-lookup"><span data-stu-id="00f8f-105">Arguments</span></span>  
 <span data-ttu-id="00f8f-106">`dir`（可选）</span><span class="sxs-lookup"><span data-stu-id="00f8f-106">`dir` (optional)</span></span>  
 <span data-ttu-id="00f8f-107">希望从中开始搜索的目录。</span><span class="sxs-lookup"><span data-stu-id="00f8f-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="00f8f-108">如未指定目录，搜索将从项目目录开始。</span><span class="sxs-lookup"><span data-stu-id="00f8f-108">If this is not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="00f8f-109">要搜索的文件。</span><span class="sxs-lookup"><span data-stu-id="00f8f-109">The file(s) to search for.</span></span> <span data-ttu-id="00f8f-110">允许通配符。</span><span class="sxs-lookup"><span data-stu-id="00f8f-110">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00f8f-111">备注</span><span class="sxs-lookup"><span data-stu-id="00f8f-111">Remarks</span></span>  
 <span data-ttu-id="00f8f-112">通过 /recurse 选项，可在指定目录 (`dir`) 的所有子目录中，或项目目录的所有子目录中编译源代码文件。</span><span class="sxs-lookup"><span data-stu-id="00f8f-112">The **/recurse** option lets you compile source code files in all child directories of either the specified directory (`dir`) or of the project directory.</span></span>  
  
 <span data-ttu-id="00f8f-113">可在文件名中使用通配符，对项目目录中的所有匹配文件进行编译，而无需使用 /recurse。</span><span class="sxs-lookup"><span data-stu-id="00f8f-113">You can use wildcards in a file name to compile all matching files in the project directory without using **/recurse**.</span></span>  
  
 <span data-ttu-id="00f8f-114">此编译器选项在 Visual Studio 中不可用，并且无法以编程方式更改。</span><span class="sxs-lookup"><span data-stu-id="00f8f-114">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00f8f-115">示例</span><span class="sxs-lookup"><span data-stu-id="00f8f-115">Example</span></span>  
 <span data-ttu-id="00f8f-116">在当前目录中编译所有 C# 文件：</span><span class="sxs-lookup"><span data-stu-id="00f8f-116">Compiles all C# files in the current directory:</span></span>  
  
```console  
csc *.cs  
```  
  
 <span data-ttu-id="00f8f-117">编译 dir1\dir2 目录及其下的任何目录中的所有 C# 文件，并生成 dir2.dll：</span><span class="sxs-lookup"><span data-stu-id="00f8f-117">Compiles all of the C# files in the dir1\dir2 directory and any directories below it and generates dir2.dll:</span></span>  
  
```console  
csc /target:library /out:dir2.dll /recurse:dir1\dir2\*.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="00f8f-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00f8f-118">See Also</span></span>  
 <span data-ttu-id="00f8f-119">[（C# 编译器选项）](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="00f8f-119">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="00f8f-120">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="00f8f-120">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)


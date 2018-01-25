---
title: "-pdb（C# 编译器选项）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /pdb
helpviewer_keywords:
- -pdb compiler option [C#]
- pdb compiler option [C#]
- /pdb compiler option [C#]
ms.assetid: e9d0f96a-5b75-45d6-9765-92538dd5f823
caps.latest.revision: "8"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7528283765c2b6f4a9d5e84015526a95938a6281
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="-pdb-c-compiler-options"></a><span data-ttu-id="ef373-102">-pdb（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="ef373-102">-pdb (C# Compiler Options)</span></span>
<span data-ttu-id="ef373-103">-pdb 编译器选项指定调试符号文件的名称和位置。</span><span class="sxs-lookup"><span data-stu-id="ef373-103">The **-pdb** compiler option specifies the name and location of the debug symbols file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef373-104">语法</span><span class="sxs-lookup"><span data-stu-id="ef373-104">Syntax</span></span>  
  
```console  
-pdb:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="ef373-105">自变量</span><span class="sxs-lookup"><span data-stu-id="ef373-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="ef373-106">调试符号文件的名称和位置。</span><span class="sxs-lookup"><span data-stu-id="ef373-106">The name and location of the debug symbols file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef373-107">备注</span><span class="sxs-lookup"><span data-stu-id="ef373-107">Remarks</span></span>  
 <span data-ttu-id="ef373-108">指定 [-debug（C# 编译器选项）](../../../csharp/language-reference/compiler-options/debug-compiler-option.md)后，编译器将在创建输出文件（.exe 或 .dll）的目录中创建 .pdb 文件，且名称与输出文件的名称相同。</span><span class="sxs-lookup"><span data-stu-id="ef373-108">When you specify [-debug (C# Compiler Options)](../../../csharp/language-reference/compiler-options/debug-compiler-option.md), the compiler will create a .pdb file in the same directory where the compiler will create the output file (.exe or .dll) with a file name that is the same as the name of the output file.</span></span>  
  
 <span data-ttu-id="ef373-109">-pdb 允许为 .pdb 文件指定非默认的文件名和位置。</span><span class="sxs-lookup"><span data-stu-id="ef373-109">**-pdb** allows you to specify a non-default file name and location for the .pdb file.</span></span>  
  
 <span data-ttu-id="ef373-110">不能在 Visual Studio 开发环境中设置此编译器选项，也不能以编程方式对其进行更改。</span><span class="sxs-lookup"><span data-stu-id="ef373-110">This compiler option cannot be set in the Visual Studio development environment, nor can it be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef373-111">示例</span><span class="sxs-lookup"><span data-stu-id="ef373-111">Example</span></span>  
 <span data-ttu-id="ef373-112">编译 `t.cs` 并创建名为 tt.pdb 的 .pdb 文件：</span><span class="sxs-lookup"><span data-stu-id="ef373-112">Compile `t.cs` and create a .pdb file called tt.pdb:</span></span>  
  
```console  
csc -debug -pdb:tt t.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="ef373-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="ef373-113">See Also</span></span>  
 [<span data-ttu-id="ef373-114">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="ef373-114">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="ef373-115">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="ef373-115">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
